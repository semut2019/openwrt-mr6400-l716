# OpenWrt for MT7628 Generic + Fibocom L716

Custom OpenWrt firmware tailored for routers with:
- MediaTek MT7628 SoC (Generic board)
- Internal Fibocom L716 4G LTE modem
- 8MB SPI flash

## ✨ Features
- LuCI Web GUI
- Auto-connect to LTE using QMI
- GPIO-based USB modem power-on script
- Lightweight config for small flash
- TFTP-safe image (< 8MB) and sysupgrade support
- Logs modem attach/remove via hotplug

## 📡 Default Configuration
- LAN IP: `192.168.2.1`
- Modem interface: `/dev/cdc-wdm0` using `uqmi`
- APN: `internet`
- WiFi SSID: `OpenWrt-MT7628`
- No password set (first boot)

## 🔧 GPIO Power for Modem
Ensure the correct GPIO number in `rc.local`:
```sh
echo 513 > /sys/class/gpio/export
echo out > /sys/class/gpio/gpio513/direction
echo 1 > /sys/class/gpio/gpio513/value
