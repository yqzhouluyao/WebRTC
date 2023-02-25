# WebRTC
WebRTC在iOS设备上的一些基本应用。

## 启动步骤
1、开启Swift信令服务器，指令在下面
2、找到WebRTC_Demo文件夹
3、打开WebRTC_Demo.xcodeproj
4、在项目中打开`Config.swift`设置 `defaultSignalingServerUrl`变量为你的Swift信令服务器和端口，在哪个电脑上启动Swift信令服务器就是哪个ip，端口在服务器启动成功后会有打印，不要使用`localhost` 或者 `127.0.0.1` 如果你想连接其他设备到你在Mac上启动的服务器.
5、在模拟器上不支持视频捕获，并且该项目的WebRTC库不支持模拟器架构。

## 开启Swift信令服务器
Note: This step requires MacOS 10.15

    1. Navigate to the `signaling/Swift` folder.
    2. Run `make`
    3. Run `./server` to start the server

本项目用的Swift信令服务器是一个广播服务器，不是一个真正的信令服务器，目的在演示一些WebRTC的基本操作，如果做一个生产环境的VoIP应用需要搭建一个真正的信令服务器，配置你自己的Turn 服务器。


 ## 运行步骤
1、运行两个设备连接到信令服务器，确保两个设备都链接到信令服务器上了
2、在第一个设备上点击'Send offer', 将会生成一个本地的offer SDP(Session Descrription Protocol),发送给其他已经连接到这个信令服务器的客户端
3、等待第二个设备接收到offer 从第一个设备上，（在第二个设备上会显示，remote SDP has arrived）
4、在第二个设备点击'Send answer'
5、当answer到达了第一个设备，这样两个设备就已经相互连接了通过WebRTC,可以点击video 按钮采集视频给对方
6、重启两个设备的进程，重复上面的步骤
 
 
 ## References:
* WebRTC website: https://webrtc.org/
* WebRTC source code: https://webrtc.googlesource.com/src
* WebRTC iOS compile guide: https://webrtc.github.io/webrtc-org/native-code/ios/
* appear.in dev blog post: https://github.com/appearin/tech.appear.in/blob/master/source/_posts/Getting-started-with-WebRTC-on-iOS.md (it uses old WebRTC api but still very informative)
* AppRTC: More detailed app to demonstrate WebRTC: https://webrtc.googlesource.com/src/+/refs/heads/master/examples/objc/AppRTCMobile/
* Useful information from pexip: https://pexip.github.io/pexkit-sdk/ios_media
* [Video Chat using WebRTC and Firestore](https://medium.com/@quangtqag/video-chat-using-webrtc-and-firestore-a925de6f89f4) by [Quang](https://github.com/quangtqag)
