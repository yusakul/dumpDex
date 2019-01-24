# dumpDex-Android脱壳

> 插件需要在xposed环境中使用,支持市面上大多数加密壳,软件仅供学习用，请勿用于其他用途,项目不是成品，可能会引起软件崩溃

### 编译环境

Android Studio 3.2

### 使用方式

下载源码编译或者下载apk包并安装，应用xposed模块后重启，运行加固的应用后，插件会自动将dex文件dump到 **/data/data/包名/dump** 目录

### 源码编译

将源码下载或者clone到本地，使用android studio打开，编译成功后，安装apk，将 **lib/armeabi/libnativeDump.so** 复制到 */data/local/tmp/libnativeDump.so* ，权限 设置为777，arm64机型还需要将将 **lib/arm64-v8a/libnativeDump.so** 复制到 */data/local/tmp/libnativeDump64.so*可以通过文件管理器操作，也可以使用如下adb shell命令

```bash
#仅适用于32位手机
adb shell
su
cp /data/data/com.wrbug.dumpdex/lib/libnativeDump.so /data/local/tmp
chmod 777 /data/local/tmp/libnativeDump.so

```

配置完成后激活xposed重启即可
