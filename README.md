# xpt2046 LCD driver for the Raspberry PI Installation

## Updates:
- v1.2-20170302
  - Add xserver-xorg-input-evdev_1%3a2.10.3-1_armhf.deb to support Raspbian-2017-03-02
- v1.1-20160815

## How to Install
1. Install Raspbian OS (If you have installed, you may skip this step)
    - Download official Raspbian-Jessie image from [Raspberry Pi official website](https://www.raspberrypi.org/downloads/)
    - Download [Etcher](https://etcher.io/) or other tools to burn image to your SD card
     
2. Clone this repo into your pi, open LX Terminal and enter following commands:

```
  $ git clone https://github.com/goodtft/LCD-show.git
  $ sudo chmod -R 755 LCD-show
  $ cd LCD-show/
```
  
3. According to your LCD's type, execute:
    - 2.8" LCD - `$ sudo ./LCD28-show`
    - 3.2" LCD - `$ sudo ./LCD32-show`
    - 3.5" LCD - `$ sudo ./LCD35-show`
    - 3.97" LCD - `$ sudo ./LCD397-show`
    - 4.3" LCD - `$ sudo ./LCD43-show`
    - 5" LCD - `$ sudo ./LCD5-show`
    - 7inch(B)-800X480 RPI LCD - `$ sudo ./LCD7B-show`
    - 7inch(C)-1024X600 RPI LCD - `$ sudo ./LCD7C-show`
    - Original HDMI display - `$ sudo ./LCD-hdmi`

4. Wait a few minutes, the system will restart automatically.

5. If you are using Raspbian image version 2017-03-02 or later, you need to execute these additional 2 commands below after step 4 to allow calibration of resistive touch screen. Then reboot the system.
  ```
    $ cd LCD-show
    $ sudo dpkg -i -B xserver-xorg-input-evdev_1%3a2.10.3-1_armhf.deb
    $ sudo cp -rf /usr/share/X11/xorg.conf.d/10-evdev.conf /usr/share/X11/xorg.conf.d/45-evdev.conf
    $ sudo reboot
  ```
6. Enjoy the LCD!
