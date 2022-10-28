# [LG Gram 17Z90N Hackintosh](https://www.lg.com/us/laptops/lg-17z90n-r.aac8u1-ultra-slim-laptop)
### Opencore Version: 0.8.5
| Specification       | Details                                 |
| ------------------- | --------------------------------------- |
| Model               | LG gram 14 (2 in 1) - 2020 (14T90N)              |
| Processor           | Intel Core i7-10510U Comet Lake                    |
| Integrated Graphics | Intel UHD 620                       |
| Memory              | 16GB RAM & 512GB SSD                    |
| Sound Card          | Conexant CX8200                         |
| Wireless Card       | Intel® Wi-Fi 6 AX201                    |

# Work In Progress
- Thanks to AskDavis (and others in credits) for providing the original EFI for my LG Gram 17 - it is the perfect 17" laptop!
- That prompted me to get this 14" convertible option and give it a go.

## Instructions
### 1. BIOS Settings
- Hold F2 to enter BIOS on boot up
- Security - Secure Boot - Disabled
- Security - TPM Support - OFF
- Exit - Exit Saving Changes

### 2. Generate SMBIOS
- https://github.com/corpnewt/GenSMBIOS
- MacbookPro16,3
- Follow Guide to Add to config.plist - https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake-plus.html#starting-point

### 3. Boot Installer
- Boot Opencore, select installer, and Install Big Sur. (Youll have to Create a MacOS Big Sur installer)

## Notes
- The NVME Drive that comes with this Laptop is a SKHynix 512GB which is not supported by Mac OS, Please replace it as it will not boot with it installed. (It might also come with Samsung SSD which can panic, so change that too).

### Working
- WIFI
- Bluetooth
- Sound / Microphone
- Graphics Acceleration
- Keyboard
- Battery Settings
- Webcam
- USB-C
- USB - all ports mapped
- Sleep / Wake
- TOUCHSCREEN works! Including multi-gestures
- Gyroscope works! This is the first I've seen work on a Hackintosh, screen rotates in all four orientations.

### Partial Working
- Function keys - Brightness can be mapped via Keyboard Shortcut preferences. Volume keys don't seem to work properly


### Not Working

- TRACKPAD - Despite attempting GPIO pinning (and touchscreen working), I can't seem to get it to work. Windows Device Manager show it's a Synaptic trackpad (SYNA1D34). BIOS device names for the two I2C HID devices (one is the touchscreen, other is trackpad I suspect) - SB.PCI0.I2C2.SHUB and SB.PCI0.I2C1.TPD0

- Thunderbolt
- HDMI
- FingerPrint Reader

## Credits
- Thanks [Opencore community](https://github.com/acidanthera/OpenCorePkg)
- Thanks 1OldSWguy
- Thanks daniyo27
