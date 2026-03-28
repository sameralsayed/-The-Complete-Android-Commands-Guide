# 📱 The Complete Android Commands Guide

[![Android](https://img.shields.io/badge/Android-ADB-green?logo=android)](https://developer.android.com/studio/command-line/adb)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

[![by SAMER SAEID ♥️](https://img.shields.io/badge/by-SAMER%20SAEID%20%E2%99%A5%EF%B8%8F-red)](https://bio.link/samer)

## 📖 Description
A **comprehensive reference** for essential Android commands — from ADB (Android Debug Bridge) to fastboot and shell utilities. Whether you're a developer, power user, or tester, this guide helps you control devices, install apps, debug, and automate tasks with practical examples and tutorials.

## 🏷️ Tags
`android` `adb` `fastboot` `commands` `tutorial` `debugging` `development` `terminal` `shell`

## ✨ Features
- 🔍 **Over 70+ ADB & fastboot commands** explained
- 📘 **Tutorial‑style usage** with real examples
- 🚀 Covers device management, app operations, logs, files, and more
- 📂 Organized by categories for quick lookup
- 🎨 Emojis for easy scanning
- 💡 Tips and common use cases

---

## 📚 How to Use This Guide
1. **Install ADB**  
   - Download [Android SDK Platform Tools](https://developer.android.com/studio/releases/platform-tools)  
   - Add `platform-tools` folder to your PATH  
   - Verify: `adb version`

2. **Enable USB Debugging** on your Android device:  
   - Go to **Settings → About phone** → tap **Build number** 7 times  
   - Go to **Settings → Developer options** → enable **USB debugging**

3. **Connect your device** via USB and authorize the connection.

4. Try the commands below in your terminal.

---

## 📱 Device Management

| Command | Description |
|---------|-------------|
| 🔌 `adb devices` | List connected devices. <br> 💻 `adb devices` → shows device serial and status. |
| 🔌 `adb usb` | Restart ADB in USB mode. <br> 💻 `adb usb` → switches device to USB mode. |
| 🌐 `adb connect <ip>:<port>` | Connect to a device over TCP/IP. <br> 💻 `adb connect 192.168.1.10:5555` |
| 🔌 `adb disconnect <ip>` | Disconnect from a TCP/IP device. <br> 💻 `adb disconnect 192.168.1.10` |
| 🔄 `adb reboot` | Reboot the device. <br> 💻 `adb reboot` → normal reboot. |
| 🔄 `adb reboot bootloader` | Reboot into bootloader (fastboot mode). <br> 💻 `adb reboot bootloader` |
| 🔄 `adb reboot recovery` | Reboot into recovery mode. <br> 💻 `adb reboot recovery` |
| 🔄 `adb sideload <ota.zip>` | Sideload an OTA update from recovery. <br> 💻 `adb sideload update.zip` |
| ⚡ `adb root` | Restart ADB with root permissions (if device rooted). <br> 💻 `adb root` |
| ⚡ `adb unroot` | Restart ADB without root. <br> 💻 `adb unroot` |

---

## 📦 App Management

| Command | Description |
|---------|-------------|
| 📲 `adb install <package.apk>` | Install an APK. <br> 💻 `adb install app-debug.apk` |
| 🔁 `adb install -r <package.apk>` | Reinstall/keep data. <br> 💻 `adb install -r app.apk` |
| 💾 `adb install -s <package.apk>` | Install to SD card. <br> 💻 `adb install -s app.apk` |
| 🗑️ `adb uninstall <package.name>` | Uninstall an app. <br> 💻 `adb uninstall com.example.app` |
| 🗑️ `adb uninstall -k <package.name>` | Uninstall but keep data/cache. <br> 💻 `adb uninstall -k com.example.app` |
| 📋 `adb shell pm list packages` | List all installed packages. <br> 💻 `adb shell pm list packages` → shows all. |
| 🔍 `adb shell pm list packages -f` | Show APK file location. <br> 💻 `adb shell pm list packages -f` |
| 📦 `adb shell pm path <package>` | Show path of APK. <br> 💻 `adb shell pm path com.android.chrome` |
| 🧹 `adb shell pm clear <package>` | Clear app data and cache. <br> 💻 `adb shell pm clear com.example.app` |
| 🔄 `adb shell am force-stop <package>` | Force stop an app. <br> 💻 `adb shell am force-stop com.example.app` |
| 🚀 `adb shell am start -n <package>/<activity>` | Launch an activity. <br> 💻 `adb shell am start -n com.android.chrome/com.google.android.apps.chrome.Main` |
| 📝 `adb shell am start -a android.intent.action.VIEW -d <url>` | Open a URL. <br> 💻 `adb shell am start -a android.intent.action.VIEW -d https://google.com` |
| 🔙 `adb shell input keyevent <keycode>` | Simulate key press. <br> 💻 `adb shell input keyevent KEYCODE_BACK` (or `4`) |
| 🖱️ `adb shell input tap <x> <y>` | Simulate tap. <br> 💻 `adb shell input tap 500 1000` |
| ⌨️ `adb shell input text "hello"` | Type text. <br> 💻 `adb shell input text "HelloWorld"` |

---

## 📁 File Operations

| Command | Description |
|---------|-------------|
| 📤 `adb push <local> <remote>` | Copy file/dir to device. <br> 💻 `adb push file.txt /sdcard/` |
| 📥 `adb pull <remote> [local]` | Copy file/dir from device. <br> 💻 `adb pull /sdcard/file.txt .` |
| 📂 `adb shell ls` | List directory contents. <br> 💻 `adb shell ls /sdcard` |
| 🗑️ `adb shell rm` | Remove file. <br> 💻 `adb shell rm /sdcard/temp.txt` |
| 📁 `adb shell mkdir` | Create directory. <br> 💻 `adb shell mkdir /sdcard/backup` |
| 📄 `adb shell cat` | Display file content. <br> 💻 `adb shell cat /proc/cpuinfo` |

---

## 📊 Logging & Debugging

| Command | Description |
|---------|-------------|
| 📜 `adb logcat` | View device logs. <br> 💻 `adb logcat` → live log stream. |
| 🧹 `adb logcat -c` | Clear log buffer. <br> 💻 `adb logcat -c` |
| 📄 `adb logcat -d` | Dump logs and exit. <br> 💻 `adb logcat -d > logs.txt` |
| 🎯 `adb logcat -s <tag>` | Filter by tag. <br> 💻 `adb logcat -s ActivityManager` |
| 🚨 `adb logcat *:V` | Verbose level (lowest). <br> 💻 `adb logcat *:V` |
| 🔴 `adb logcat *:E` | Errors only. <br> 💻 `adb logcat *:E` |
| 📊 `adb bugreport` | Generate full bug report. <br> 💻 `adb bugreport` → creates zip file. |
| 🖥️ `adb shell dumpsys` | Dump system service info. <br> 💻 `adb shell dumpsys battery` → battery info. |
| 🔋 `adb shell dumpsys battery` | Show battery status. <br> 💻 `adb shell dumpsys battery` |
| 📶 `adb shell dumpsys wifi` | WiFi info. <br> 💻 `adb shell dumpsys wifi` |
| 📱 `adb shell dumpsys window` | Window manager info. <br> 💻 `adb shell dumpsys window | grep mCurrentFocus` → current app. |
| 📸 `adb shell screencap` | Take screenshot. <br> 💻 `adb shell screencap /sdcard/screen.png` then `adb pull /sdcard/screen.png` |
| 🎥 `adb shell screenrecord` | Record screen. <br> 💻 `adb shell screenrecord /sdcard/video.mp4` (stop with Ctrl+C) |

---

## 🔧 Fastboot Commands (Bootloader Mode)

*To enter fastboot mode: `adb reboot bootloader` or use hardware keys*

| Command | Description |
|---------|-------------|
| 🔍 `fastboot devices` | List devices in fastboot mode. |
| 📦 `fastboot flash <partition> <file>` | Flash image to partition. <br> 💻 `fastboot flash boot boot.img` |
| 🗑️ `fastboot erase <partition>` | Erase a partition. <br> 💻 `fastboot erase userdata` |
| 🔓 `fastboot oem unlock` | Unlock bootloader (varies by device). <br> 💻 `fastboot oem unlock` |
| 🔒 `fastboot oem lock` | Lock bootloader. |
| 🔄 `fastboot reboot` | Reboot device from fastboot. |
| 💻 `fastboot getvar <variable>` | Get bootloader variable. <br> 💻 `fastboot getvar all` → show all info. |
| 🖥️ `fastboot boot <image>` | Boot a kernel/ramdisk without flashing. <br> 💻 `fastboot boot twrp.img` |

---

## 🐚 Advanced Shell Commands

When you start an interactive shell with `adb shell`, you can use standard Linux commands:

| Command | Description |
|---------|-------------|
| 🏃 `adb shell` | Start interactive shell. |
| 📄 `adb shell echo` | Print text. <br> 💻 `adb shell echo "Hello"` |
| 📋 `adb shell grep` | Search text. <br> 💻 `adb shell logcat | grep "MyApp"` |
| 🔑 `adb shell wm size` | Get display resolution. <br> 💻 `adb shell wm size` |
| 🔑 `adb shell wm density` | Get screen density. <br> 💻 `adb shell wm density` |
| 📴 `adb shell svc wifi enable/disable` | Turn WiFi on/off. <br> 💻 `adb shell svc wifi disable` |
| 📶 `adb shell svc data enable/disable` | Turn mobile data on/off. <br> 💻 `adb shell svc data enable` |
| 🔄 `adb shell settings put global <key> <value>` | Modify system settings. <br> 💻 `adb shell settings put global airplane_mode_on 1` then `adb shell am broadcast -a android.intent.action.AIRPLANE_MODE` |
| 🎨 `adb shell settings put system user_rotation <0-3>` | Force rotation. <br> 💻 `adb shell settings put system user_rotation 0` → portrait |

---

## 📘 Tutorials

### Tutorial 1: Install a Debug APK and View Logs
```bash
# 1. Connect device
adb devices

# 2. Install APK
adb install myapp-debug.apk

# 3. Launch app (optional)
adb shell am start -n com.example.myapp/.MainActivity

# 4. Filter logs for your app
adb logcat -s MyAppTag
