test
Paragraph one

Technical Test

1.	Setup use of 10.0.0.2/16 static IP address, Netmask 255.255.0.0, gateway 10.0.0.1/16
2.	Install Nginx, configure it to serve as a frontend for Django APP.
3.	Install PostgreSQL DBMS and create DB, user for DB, set users password.
4.	Install Django, version 2.2.2, wich would serve "Hello World" appliction. Use PostgreSQL DB you created as a backend for Django.
5.	Add Firewall which would allow only port 22 and 80.
6.	Make sure all your changes are persistent after reboot.


First point
Setup two virtual servers based on VirtualBox machines with two eth's enp0s3 and enp0s8
1 server - depl (when code is based)
2 server - prod (when it will be deploy)

Both server have Ubuntu 18.04 and configurated to access without log/pass (with .ssh/ configs)

Second point

All of 1/2/3/5/6 of the test are working. Python vers both 3.6.9

Three point
Django can be installed correct

Four point
The tree

root@depl:/etc/ansible# tree .

├── ansible.cfg
├── ansible.cfg.bak
├── hosts
│   └── hosts
├── hosts.bak
├── roles
│   ├── django
│   │   ├── files
│   │   ├── handlers
│   │   ├── meta
│   │   ├── tasks
│   │   │   └── main.yml
│   │   ├── templates
│   │   │   └── settings.py.j2
│   │   └── vars
│   │       └── main.yml
│   ├── fw
│   │   ├── defaults
│   │   │   └── main.yml
│   │   └── tasks
│   │       └── main.yml
│   ├── general
│   │   └── tasks
│   │       └── main.yml
│   ├── nginx
│   │   ├── handlers
│   │   │   └── main.yml
│   │   ├── tasks
│   │   │   └── main.yml
│   │   ├── templates
│   │   │   └── default.j2
│   │   └── vars
│   │       └── main.yml
│   └── postgres
│       ├── handlers
│       │   └── main.yml
│       ├── tasks
│       │   └── main.yml
│       └── vars
│           └── main.yml
└── start.yml

Five point

After reboot Nginx and DB is working fine
