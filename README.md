Zabbix Server
=============
To be reviewed

This playbook will install the Zabbix Server

1. Edit the zabbix-server.yml file and add replace host
2. Edit files in directory defaults and change variables to your needs
3. Install with tags if u want to exclude apache, postgres or zabbix
4. ansible-playbook zabbix-server.yml --tags "postgres,http,zabbix"
5. Else just run ansible-playbook zabbix-server.yml

Version
-------
11/08/2015


Requirements
------------
To be reviewed

At this moment the script only works on Redhat/Centos 6.x or Redhat/Centos 7.x
This script works with PostgreSQL and MySQL
You still need ansible playbooks to install PostgreSQL or MySQL and Apache
Mysql will create a Database Postgresql expects the Db to be there (todo)

Role Variables
--------------

To be reviewed

All variables can be altered in the defaults directory.

* httpd.yml
* main.yml
* postgresql.yml
* zabbix.yml

Example Playbook
-------------------------
```yaml
# file: localrepo.yml
- hosts: ZabbixServer
  user: someuser
  sudo: yes
  sudo_user: root
  roles:
    - Zabbix-Server
```

Dependencies
------------
To be reviewed

* Database like mysql or postgresql needs to be installed seperate
* Apache or another webserver needs to be installed seperate
* For Postgresql you can make use of my Postgresql playbook
* ansible-galaxy install patrik.uytterhoeven.PostgreSQL-For-RHEL6x

Todo
----
1. add config for debian

License
-------

GPL V2

Author Information
------------------

* Patrik Uytterhoeven
* patrik( at )open-future.be
* [www.open-future.be](http://www.open-future.be)
