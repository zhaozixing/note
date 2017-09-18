#  Linux SSH

###  1:SSH 介绍

SSH（安全外壳协议）

SSH 为 Secure Shell 的缩写，由 IETF 的网络小组（Network Working Group）所制定；SSH 为建立在应用层基础上的安全协议。SSH 是目前较可靠，专为远程登录会话和其他网络服务提供安全性的协议。利用 SSH 协议可以有效防止远程管理过程中的信息泄露问题。SSH最初是UNIX系统上的一个程序，后来又迅速扩展到其他操作平台。SSH在正确使用时可弥补网络中的漏洞。SSH客户端适用于多种平台。几乎所有UNIX平台—包括HP-UX、Linux、AIX、Solaris、Digital UNIX、Irix，以及其他平台，都可运行SSH。

###  2:SSH 安装

* ubuntu:```sudo apt-get install openssh-server openssh-client -y```

* centos:```sudo yum install openssh-server openssh-client -y```

###  3:SSH 配置

更改```/etc/ssh/sshd_config```文件

允许root用户通过SSH远程登陆,禁用root用户远程则设置为```false```:
```
    #PermitRootLogin prohibit-password
    PermitRootLogin yes
```

更改SSH端口,默认22:
```
    #Port 22
    Port 123
```

###  4:SSH 使用

通过ssh命令可以远程登陆

#####  不指定用户:
```
    ssh 192.168.56.101
```

#####  指定用户:
```
    ssh -l root 192.168.56.101
```
或者
```
    ssh root@192.168.56.101
```


#####  如果修改过ssh登录端口的可以:

```
    ssh -p 123 192.168.56.101
```
或者
```
    ssh -l root -p 123 192.168.56.101
```
或者
```
    ssh -p 123 root@192.168.56.101
```
