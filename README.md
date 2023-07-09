# openwrt_tplink_c20
# to enter failsafe mode you just set your lan ip 192.168.1.2
# then connect wan port lan wire
# power on the router and after 2-3sec just press Wifi/Wps button the power light continuesly blinking
# wow you are in failsafe mode
# then go to windows powershell command - $ ssh root@192.168.1.1
# the followed this command for reset root password
# -> $ mount_root
# $ passwd
# then enter your desired password
# after that reboot requred by command $ reboot -f
# all done
reset failsafemode
Resetting the root password
If you have forgotten the root password or if the root password no longer works, you have to use the Failsafe Mode and Factory Reset.

From there, you don't have to reset the whole configuration. Note that fail safe mode does not require a password for authentication of root (!)

You only have to mount the root file system and set a new password with passwd and then trigger a restart. In fail safe mode, passwd will not ask for the old password (that you may have forgotten):

root@(none):~# mount_root
switching to jffs2 overlay
root@(none):/rom/root# passwd
Changing password for root
New password:
Retype password:
passwd: password for root changed by root
root@(none):/rom/root# reboot -f
