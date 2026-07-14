# Linux LARP

<p align="center">
  <img src="LINUX-LARP-LOGO.png" alt="Linux LARP Logo" width="820">
</p>

<p align="center">
  <img src="larper-desktop.png" alt="Linux LARP Desktop Screenshot" width="900">
</p>

<p align="center">
  <a href="https://youtu.be/FRgE8DjzMAs">
    <img src="https://img.youtube.com/vi/FRgE8DjzMAs/maxresdefault.jpg" alt="Linux LARP showcase video" width="720">
  </a>
</p>

## [CLICK HERE TO WATCH THE VIDEO SHOWCASE OF LINUX LARP](https://youtu.be/FRgE8DjzMAs)

---

<p align="center">
  <b>Linux LARP</b> is a Debian-based live joke distro for larping. Below are the features.
</p>

---
# Hackermode Terminal is now it's own <b>[STANDALONE SCRIPT](https://github.com/dzumq/Hackermode)</b> for those that want the terminal without installing the entire OS

---

## Features of Linux Larp

Linux LARP features a useless terminal which cannot execute commands, instead it just outputs a fake "hackertyper" like output. Additionally the default Browser is Google Chrome for "Privacy" lol

This is currently a **live ISO**, not a traditional installable distro. Booting it runs the system from the ISO, USB, or VM. Changes do not persist after reboot.

---

## Download

Download the latest ISO from the **Releases** page:

```text
linux-larp-1.0-amd64.iso
linux-larp-1.0-amd64.iso.sha256
```

Then simply put the .iso in a vm and set OS as debian 13 if your vm software asks for that.

To verify the ISO:

```text
sha256sum -c linux-larp-1.0-amd64.iso.sha256
```

---

## Building from source

Build on a Debian-based system.

### 1. Install build dependencies

~~~bash
sudo apt update
sudo apt install live-build dpkg-dev xorriso isolinux syslinux-common qemu-system-x86
~~~

### 2. Clone the repository

~~~bash
git clone https://github.com/dzumq/linux-larp.git
cd linux-larp
~~~

### 3. Build the custom packages

~~~bash
mkdir -p repo

dpkg-deb --root-owner-group --build packages/hackermode repo/hackermode_1.0_all.deb
dpkg-deb --root-owner-group --build packages/wallpapers repo/wallpapers_1.0_all.deb
dpkg-deb --root-owner-group --build packages/fetch repo/fetch_1.0_all.deb
dpkg-deb --root-owner-group --build packages/defaults repo/defaults_1.0_all.deb
~~~

### 4. Copy packages into the live-build config

~~~bash
mkdir -p iso/config/includes.chroot/opt/larp-packages
rm -f iso/config/includes.chroot/opt/larp-packages/*.deb
cp repo/*.deb iso/config/includes.chroot/opt/larp-packages/
~~~

### 5. Build the ISO

~~~bash
cd iso
sudo lb clean --purge
lb config
sudo lb build
~~~

The finished ISO should appear as:

~~~text
iso/live-image-amd64.hybrid.iso
~~~

---
### LICENSE

~~~bash
MIT License

Copyright (c) 2026 dzuma

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
~~~


## HAPPY LARPING
