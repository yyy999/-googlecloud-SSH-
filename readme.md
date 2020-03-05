# 用SSH工具XShell连接谷歌云 root用户或普通用户,实现SSH代理上网

## 方法
1.以root用户登入
或者普通用户，秘钥登入
## 步骤
1.用root用户登入

1.1.进入谷歌云实例面板

1.2.切换到root角色

```
sudo -i 
```
1.3.修改SSH配置文件/etc/ssh/sshd_config

```
vi /etc/ssh/sshd_config
```
修改PermitRootLogin和PasswordAuthentication为yes

```
PermitRootLogin yes //默认为no，需要开启root用户访问改为yes
PasswordAuthentication yes //默认为no，改为yes开启密码登陆
```
1.4.给root用户设置密码

```
passwd root
```

1.5.重启SSH服务使修改生效

```
/etc/init.d/ssh restart
```

1.6.登录XShell

在xshell中，直接使用root账号密码登录。然后在连接>SSH>隧道tcp/ip转移内选择dynamic设置成1080代理,成功连接后会提示用户登录$标志符

1.7在chrome内安装SwitchyOmega扩展插件

创建SSH代理,协议默认选socks5,服务器:127.0.0.1,端口:1080
这时你就可以通过ssh代理上网了，超强的视频流畅体验，让你畅游互联网的世界

提供VPS服务
极客技术群
加微信yyy99966


