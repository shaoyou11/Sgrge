# Sgrge

Linux Installation CN
栽培者 edited this page on 13 Oct 2018 · 10 revisions
在 Linux 下安装与更新

Transmission 在 Linux 下使用比较多，在安装 Transmission Web Control 之前，你可能需要一些 Linux 基本操作。

如何安装（SSH方式）

安装之前
请确认系统已安装 Transmission；
请确认你是否有 root 用户权限；
获取最新的安装脚本

使用终端以 root 用户登录到你的系统，以下脚本假设你已经使用 root 用户；（方法自行搜索）
记住当前路径（如 /volume1/ ），以后用到，因为 wget 下载的文件会保存到当前目录；
获取最新的安装脚本：
wget https://github.com/ronggang/transmission-web-control/raw/master/release/install-tr-control-cn.sh
请留意执行结果，如果出现 install-tr-control-cn.sh.1 之类的提示，表示文件已存在，请使用 rm install-tr-control-cn.sh* 删除之前的脚本再重新执行上面的命令；
如果提示 https 获取失败，请使用以下命令获取安装脚本：
wget https://github.com/ronggang/transmission-web-control/raw/master/release/install-tr-control-cn.sh --no-check-certificate
如果提示文件已存在，可以通过 rm install-tr-control-cn.sh 进行删除后再执行下载；或者在 wget 后面添加 -N 参数，如：
wget -N https://github.com/ronggang/transmission-web-control/raw/master/release/install-tr-control-cn.sh --no-check-certificate
执行安装脚本

执行安装脚本（如果系统不支持 bash 命令，请尝试将 bash 改为 sh ）：
bash install-tr-control-cn.sh
如果出现 Permission denied 之类的提示，表示没有权限，可尝试添加执行权限：
chmod +x install-tr-control-cn.sh
如果命令成功执行，将出现以下界面：

install-tr-control-cn

按照提示，输入相应的数字，按回车即可；

如果无法正常显示中文，请尝试设置SSH客户端编码为 UTF-8 ，如依然不能显示中文，请下载并使用英文安装脚本 install-tr-control.sh

wget https://github.com/ronggang/transmission-web-control/raw/master/release/install-tr-control.sh --no-check-certificate
安装完成后，用浏览器访问 Transmission Web Interface（如：http://192.168.1.1:9091/ ）即可看到新的界面；如果无法看到新界面，可能是浏览器缓存了，请按 Ctrl + F5 强制刷新页面或 清空缓存 后再重新打开；
如果在知道自己的 Transmission Web 所在目录，也可以在安装脚本后面直接加路径，以避免搜索，如：
bash install-tr-control-cn.sh /usr/local/transmission/share/transmission
注意，路径最后 不要 加 web ；
如何更新

以下几种情况，需要更新 Transmission Web Control：

Transmission 重新安装或升级之后；
Transmission Web Control 版本更新时；
如何更新：

如果之前已经下载过安装脚本，只需要在安装脚本所在目录执行一次脚本即可：
 sudo bash install-tr-control-cn.sh	
如果没有下载过安装脚本，或脚本有更新时，请参考安装方式重新下载安装脚本执行安装即可。
