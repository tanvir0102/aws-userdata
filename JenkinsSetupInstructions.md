##Jenkins Setup on Centos/Amazon Linux on EC2

#Native installation:

#Step01: Check Java Version/installation

[ansadm@localhost ~]$ java -version
openjdk version "1.8.0_131"
OpenJDK Runtime Environment (build 1.8.0_131-b11)
OpenJDK 64-Bit Server VM (build 25.131-b11, mixed mode)
if older version is installed then remove it and install java version 8

```
sudo yum remove java
sudo yum install java-1.8.0-openjdk-devel
```
#Step02: add jenkin to centos repo

```
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
```
#Step03: install jenkins

```
sudo yum install jenkins
```
#Step04: start/status/stop jenkins service

```
/etc/init.d/jenkins start | stop | restart
chkconfig jenkins on
```
#Step05: Varify Jenkins
```
netstat -ntulp | grep 8080
```

Step07: Access Jenkins
Go to your browser and type http://<ipaddress>:<8080>/