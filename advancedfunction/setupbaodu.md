## 安装包报毒解决方法

通过执行setup.exe（不要签名），先生成卸载程序，然后对卸载程序进行签名，再将卸载程序打包进setup.exe。
1）首先，由NSIS生成setup.exe，注意：不要对setup.exe进行签名。
2）执行setup.exe，待安装完成后，到安装目录找到uninst.exe，然后对uninst.exe进行签名。
3）将uninst.exe文件与需要被释放到安装目录下的文件一起打包 (放到FilesToInstall目录下)。
4）注释掉commonfunc.nsh文件中的这句：WriteUninstaller "$INSTDIR\uninst.exe"。
5）重新编译setup.nsi生成setup.exe，并对其进行签名。

参考地址：
http://blog.csdn.net/hellokandy/article/details/52212495