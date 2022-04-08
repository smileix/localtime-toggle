# 多系统情况下，修改各个系统时间设定：

## 设定一：将BIOS时间当做本地时间而非UTC时间
### MacOS：
#### 方法一：直接运行
```
sudo sh -c "$(curl -fsSL https://raw.githubusercontent.com/maxlike/localtime-toggle/main/fix_time_osx.sh)"
```
#### 方法二：先下载到本地再运行
```
wget https://raw.githubusercontent.com/smileix/localtime-toggle/main/fix_time_osx.sh
sudo sh fix_time_osx.sh
```
### Linux：
```
sudo hwclock --localtime --systohc
```
### Windows:
不需要做更改

## 设定二：将BIOS时间当做UTC而非本地时间。
只需要更改Windows的时间设定，更改注册表即可。
```
Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1
```
