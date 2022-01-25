20180919

Just a quickie that uses the GPL powerup code to search an attached multi-bank ROM (up to 512k) for a cartridge named 'PROGRAM'. If it finds it, it starts immediately without displaying the master title page.

Although 'PROGRAM' can be on any bank of the ROM, it must be able to run successfully from the ROM cartridge before you add the GROM - the GROM just auto-selects it for you. If no 'PROGRAM' can be found, the title page is displayed as per normal.

In theory you can hold space to abort the startup, but that's been tough to test in emulation for timing reasons.

There is a remote chance that this may be incompatible with some devices, if they require a GPL powerup. I'm not aware of any at this time.

To use this with the UberGROM, just drop the GROMStartG.BIN into the >6000 slot on any base. If you are not using the GROM for anything else, put it on BOTH bases >9800 and >9804 (the first two). This works around a bug in the TI ROM related to "REVIEW MODULE LIBRARY" that will otherwise lock up the console.

Advanced: If you want to run the GROM at another address, just change the powerup link address in the header and at offset >0092 in the binary file. The rest of the code will run on any GROM.

I hand-assembled the GPL code, so I don't know if it will build in any GPL Assemblers. The syntax I use is that the destination comes first.

The patched 4ADOS is included here in both 8k version (for basic carts) and 512k version (for UberGROM cart) - they are the exact same data, the big one is just duplicated.
