
概述
用于在Openshift上部署V2Ray Websocket。

Openshift为我们提供了免费的容器服务，我们不应该滥用它。正因如此，本项目不宜做为长期翻墙使用。

Openshift的网络并不稳定，部署前请三思。

镜像
DockerHub的镜像：设定
单纯地使用Websocket
CONFIG_JSON > 服务端配置文件

Websocket + TLS
CONFIG_JSON > 服务端配置文件

CERT_PEM > 证书文件内容

KEY_PEM > 私钥文件内容

事实上，Openshift配置Websocket + TLS用不着第二种方法这么麻烦，只需要配置好CONFIG_JSON，然后在Route中勾选Secure Route即可实现TLS。第二种方法是面向其它容器平台的。

亦可使用该方法部署到日本的Arukas上。请自行变通。

注意
设定ENV时，务必将配置文件的换行符\r\n变更为\n，然后填入ENV。使用Linux的朋友可以不用管这一步。


环境变量： CONFIG_JSON（配置）、

用notepad++将上述变量中 \r\n 替换为\n，变成一行，导入容器。

客户端： android Actinium、windows v2ray 可用同一个服务端
