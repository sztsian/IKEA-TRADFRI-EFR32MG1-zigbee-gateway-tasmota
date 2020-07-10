# Firmware files:

### Gecko Bootloaders:
The ICC-A-1 module have an Gecko Application Bootloader installed that only works with OTA files downloaded thrue Zigbee and stored on the external flash.  
  
So first we need to flash one new bootloader for loading the NCP app in the flash.  
  
Flashing new bootloader to the gecko must being done with J-tag or SWD and using s37 files.    
  
Its normaly OK flashing without erasing the internal flash then its use the icc-a-1-bootloader.s37 that contain only the secund stage (Main bootloader).  
If erasing the internal flash you must flashing the icc-a-1-bootloader-combined.s37 that contains both the first stage and secund stage (Main bootloader) or your gecko dont boot at all or making cracy GECKO things !  
I have booting to bootloader after erasing internal and flashing botloader and reading it back and the first 0x0800 wos only ff = empty,  and from the bootloader flashing one app and it wos written it ofset and coruppted the perfials and lockbits aria = Hard brick !!!  

### Gecko NCP:
NCP app can being flashed from main bootloader with gbl files or with  J-tag / SWD with s37 files.  
My current NCP gbl file its not accsepted bye the bootloader but the s37 version flashed over SWD works OK.  


### Big  thanks to : mx512, grobasoz and jnicolson for helping putting working firmware together.  
