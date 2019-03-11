# RTL8821CE无线网络驱动（Linux）

> 联想Thinkpad E470(c)系列笔记本内置无线网络芯片为RTL8821CE的驱动解决方案。

**仅在`Ubuntu16.04LTS`和`Ubuntu18.04LTS`** 版本下测试可用。

## 要求

- Ubuntu内核切换成4.14版本，下载：[百度网盘](https://pan.baidu.com/s/1RFVrimL2BMW23hpchlZ3jQ)

**Ubuntu 16.04升级内核:**

```bash
# 查看当前内核版本是否为4.14，不是继续
uname -sr

# 解压内核压缩包，包含三个文件
tar zxvf linux-kernel-4.14.tar.gz

# 安装（三个文件一次安装）
sudo dpkg -i *.deb

# 重启
sudo reboot

# 确认内核版本为4.14
uname -sr
```

**Ubuntu 18.04降级内核:**

```bash
# 查看当前内核版本是否为4.14，不是继续
uname -sr

# 解压内核压缩包，包含三个文件
tar zxvf linux-kernel-4.14.tar.gz

# 安装（三个文件一次安装）
sudo dpkg -i *.deb

# 删除默认内核文件
cd /boot
rm -rf `比4.14高版本的内核文件`

# 重启
sudo reboot

# 确认内核版本为4.14
uname -sr
```

## 驱动安装

```bash
cd rtl8821ce
make
sudo make install
sudo modprobe -a 8821ce
```
