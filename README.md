# 概要

rbenv(ruby), pyenv(python), plenv(perl), phpenv(php)で各LL言語をインストールするplaybookです。

# playbook実行環境

Vagrant + CentOS7.1 + ansible v1.9.1 で正常動作している事を確認しています。

# インベントリ

ansible-playbook-lllang-envs/development

```ini
[envs]
192.168.33.31

[envs:vars]
ansible_ssh_port=22
ansible_ssh_user=vagrant
ansible_ssh_pass=vagrant
```

[envs]の部分を任意のIPに変更して下さい。

# 実行方法

```
ansible-playbook -i development site.yml
```

# インストールする言語のバージョン設定

ansible-playbook-lllang-envs/group_vars/common.yml より設定可能です。
```
user: vagrant
group: vagrant

ruby_version: 2.2.2
python_version: 3.4.3
perl_version: 5.21.11
php_version: 5.6.9
```

# 注意事項

phpenvはrbenvに依存しているため、phpenvをインストールするには事前にrbenvをインストールする必要があります。