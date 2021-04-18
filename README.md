# installNET
install Linux OS or Windows on linux server

Credit: Vicer - moeclub

<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#1-install-required-tools-on">Install required tools</a>
    </li>
    <li>
      <a href="#2-express-install-example-debian10-x64-default-root-password-is-mypass">Express Install Example</a>
    </li>
    <li>
      <a href="#3-install-syntax">Install Syntax</a>
    </li>
    <li>
      <a href="#4-advance-example">Advance Example</a>
    </li>
    <li><a href="#license">License</a></li>
  </ol>
</details>




# Instructions:

## 1. Install required tools on:

### a. Debian / Ubuntu 16.04:
```
apt update
apt install -y xz-utils openssl gawk file
```
### b. RedHat / CentOS:
```
yum update
yum install -y xz openssl gawk file
```
## 2. Express Install Example (Debian10 x64, default root password is 'mypass'):
```
bash <(wget -qO- 'https://raw.githubusercontent.com/tonywww/installNET/master/InstallNET.sh') -d 10 -v 64 -a -p 'mypass' -firmware
```
## 3. Install Syntax:

### Please change the following default user and password after finishing installation.
```
Linux default user & password:
root / MoeClub.org

Windows default user & password:
Administrator / Vicer
```


```
Usage:
        bash InstallNET.sh      -d/--debian [dist-name]
                                -u/--ubuntu [dist-name]
                                -c/--centos [dist-version]
                                -v/--ver [32/i386|64/amd64]
                                --ip-addr/--ip-gate/--ip-mask
                                -apt/-yum/--mirror
                                -dd/--image
                                -a/-m
                                -p [default password]
 
# dist-name: 发行版本代号
# dist-version: 发行版本号
# -apt/-yum/--mirror : 使用定义镜像
# -a/-m : 询问是否能进入VNC自行操作. -a 为不提示(一般用于全自动安装), -m 为提示.
# -p : set default password
# -firmware 额外驱动支持
# --ip-addr :IP Address/IP地址
# --ip-gate :Gateway   /网关
# --ip-mask :Netmask   /子网掩码
# 以下示例中,将X.X.X.X替换为自己的网络参数.
```


## 4. Advance Example
```
# Automatically install using the default mirror
bash InstallNET.sh -d 8 -v 64 -a
 
# Automatically install using custom mirror
bash InstallNET.sh -c 6.9 -v 64 -a --mirror 'http://mirror.centos.org/centos'
 
 
# In the following example, replace X.X.X.X with its own network parameters.
# --ip-addr :IP Address
# --ip-gate :Gateway
# --ip-mask :Netmask
 
#Use custom mirror and custom Network Parameters
#bash InstallNET.sh -u 16.04 -v 64 -a --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x --mirror 'http://archive.ubuntu.com/ubuntu'
 
#Use the custom network parameters to install windows
#bash InstallNET.sh --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x -dd 'link-to-image-vhd'
 ```

## License
[BSD 2-Clause](LICENSE) © tonywww
