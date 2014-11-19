U-Boot bootloader for HLK-RM04 board
====================================

When HLK-RM04 board is used in projects without ethernet socket it is impossible to update it's firmware through TFTP.
This modified bootloader includes new boot option - "Load system code then write to Flash via Serial.".
Just press "0" when prompted and upload new firmware using kermit protocol.


Build instructions
------------------

MIPS gcc toolchain version 3.42 is required to build this bootloader. Newer versions of toolchain will produce errors and are not recommended.

If you installed the toolchain in /opt/buildroot-gcc342/ just run "make".
The resulting image is placed in the root directory and is called uboot.img

To adjust build settings including toolchain location run "make menuconfig".


WARNING
-------

Build and update the bootloader at your own risk!
If the bootloader gets broken your board will not boot at all.
In this case the only option is to desolder the flash chip and use external programmer to restore the original bootloader from backup.



