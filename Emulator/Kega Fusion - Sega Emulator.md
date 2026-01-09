Kega Fusion Readme Document
What is Fusion ?
----------------

Fusion:

* Emulates the Sega SG-1000, SC-3000, SF-7000, Master System, and GameGear
  with a high degree of accuracy.

* Emulates the Sega MegaDrive/Genesis more accurately than any other
  emulator.

* Emulates the Sega MegaCD/SegaCD more accurately than any other emulator.

* Emulates the Sega 32X more accurately than any other emulator. 

* Emulates the Sega CD+32X together, no other emulator can do this.

* Emulates the Sega Pico and Sega Virtua Processor.

* Has many other interesting features.


The following applies to the Windows Build (other builds are basically
ports of the Windows Build) - most of the rest of the file will apply to
all builds. There is some build-specific information at the bottom of the
file.
 
Fusion is written mainly in hand optimised x86 ASM, with small parts
(Windows interface, DirectX interface, File Handling) written in C.
All code is written by me - Steve Snake.

Fusion requires DirectX 7.0 or above to operate, and your desktop must be
set to either 16-Bit (HI-COLOR) or 32-Bit (TRUE-COLOR). A modern graphics
card is recommended, however a fallback compatibility mode is included if
you have an older card, or experience speed issues or other problems. This
will kick in automatically if needed, but can be forced by editing the INI
file value for "ForceCompatibleGFX" to 1 should your performance suffer.
You could also try settings of either 0 or 1 for "CompatibleGFXOpt" to see
which works fastest on your hardware. Note however that this mode is no
longer supported, is somewhat slower, has less features, and requires the
desktop to be in 16-Bit (HI-COLOR) Mode.

Under Win9x/WinME, it requires an ASPI manager in order to access CD-ROM
drives. Under Win2k/WinXP it will attempt to use IOCTL instead, but should
you encounter problems with this you can edit the INI file value for
"ForceASPI" to 1, and install ASPI anyway.





---------------------------------------------------------------------------
Using Fusion - the basics
---------------------------------------------------------------------------

The basic operation of Fusion should be fairly self-explanatory, so until a
proper manual exists, here is some basic information on using it.

Some more detail, and some "special features" are explained at the end of
this file.




FILE menu
---------

Load MasterSystem ROM - Load a MasterSystem/SG-1000/SC-3000 ROM

Load GameGear ROM     - Load a GameGear ROM

Load Genesis/32X ROM  - Load a Genesis or 32X ROM

Load SegaCD Image     - Load a SegaCD CUE, ISO or BIN Image File

Boot SegaCD           - Boot SegaCD from a real CD in your drive (Win only)

Power On/Hard Reset   - Power On or Hard Reset current console

Power Off             - Power off the current console

Soft Reset            - Soft Reset the current console

Game Genie/PAR        - Enter/Edit/Toggle/Find Game Genie or PAR codes

Netplay               - Join/Start/Exit a Netplay game

Load State As         - Load a specified State File

Save State As         - Save to a specified State File

Load State/Save State - Load or Save to one of 10 State Slots

Change State Slot     - Select State Slot for Load/Save

Save Screenshot       - Save Screenshot in TGA or BMP format

Load RAM Cart         - Load a SegaCD RAM Cartridge

Create New RAM Cart   - Create and Load a new SegaCD RAM Cartridge

File History          - List or load up to 16 recently used files

Clear File History    - Clears the above list

Exit                  - Exits Fusion



VIDEO menu
----------

From here you can select (seperately) the Window size (for Windowed Mode)
and the Resolution (for FullScreen Mode). The options available will depend
on your system.

"Fixed Aspect (Fit)" will attempt to fit the picture to the selected
resolution without altering the aspect ratio, assuming square pixels. This
means if you have, for example, a TFT display of 1280x1024, the image will
be displayed centered at 1280x960. But if you have a widescreen TFT display
of 1280x768, the image will be displayed centered at 960x720 (the closest
to the original 4:3 aspect ratio.)

"Fixed Aspect (Zoom)" does kinda the opposite of above. Rather than trying
to fit all the picture, it instead tries to fill as much of the screen as
possible, again without altering the aspect ratio, assuming square pixels.
This means if you have, for example, a widescreen TFT display of 1280x768,
the image will be displayed centered at 1280x960 - with 96 pixels at the
top and bottom being cut off. It's similar to the 'Zoom' mode found on
widescreen TVs.

Both of these modes will scale to exact pixel multiples only if the
"Nearest Multiple" option is enabled. Turning this off may allow more of
your monitor to be used, but the image may not look as sharp. It's all down
to personal preference.

If both Fixed Aspect options are turned off, the image will just be scaled
to fill the whole screen.

The Brighten option simply brightens the display, to take care of the
differences in brightness between a CRT TV and a PC monitor.

The Log AVI option will allow you to log gameplay to a video file. Fusion
uses a custom video codec, which is included in the zip file you downloaded.
This codec is intended to allow you to log video without affecting emulator
performance too much, because other codecs take a large amount of CPU time.
It is not intended as the final codec for your files, however - you should
use a tool, such as the excellent VirtualDub (google it) to convert the AVI
files to some more popular codec.

The rest of the options are fairly self explanatory. You can toggle
FullScreen or Windowed mode, enable or disable VSync, and select the render
mode. Render Plugins are available seperately and should be placed either
in the same folder as the Fusion.exe, or in their own folder named Plugins.

Please note that VSync in Windowed mode may be quite slow. This is because
the only way to do VSync in windowed mode is to physically sit there and
wait until the VSync happens. Obviously that can be a huge waste of CPU
time, especially if, at the point you start waiting, you've only just
missed the last VSync...




SOUND menu
----------

From here you can enable/disable sound emulation, and choose your desired
samplerate.

It is recommended that, if your PC is fast enough, you select "SuperHQ"
mode. The soundchips in each console are emulated much more accurately in
this mode, and sound very close to the real thing. The samplerate will also
be fixed to 44100Hz when you select this mode. The Mac Build does not have
these options, since all Intel Macs are easily fast enough, and always run
in SuperHQ mode.

The OVERDRIVE option doubles the volume of sound output, making it sound
closer in volume to most other emulators using the MAME sound core. However
doing this means that the YM2612, and possibly other chips, are slightly
distorted by clipping. If you turn this option off, and your speakers up,
you will get a slightly cleaner sound. But no doubt most users will prefer
OVERDRIVE mode, since the difference in quality may be very subtle.

You can log sound output to either a WAV file, or a VGM file. Select either
of these options, choose a filename to log to, and the logging will begin.
To stop logging at any time, simply select the option again.

A Filter is available which will filter the sound very close to a real
Model 1 Genesis. For nostalgia freaks only, it sounds much nicer without it.




OPTIONS menu
------------

SET CONFIG - See CONFIG


COUNTRY submenu:

Select USA/JAP/EUR modes, or Auto Detect. Auto Detect may not work for all
games because of incorrect data in the ROM header. You can also select the
preferred order of country detection, for games that work in more than one
region.


CD DRIVE submenu: (Windows only)

Your CD-ROM drive(s) should appear here, if available. Select the one you
wish to boot from.


PERFECT SYNC - Some SegaCD/MegaCD games will only run correctly if the two
MC68000 processors inside the console are perfectly syncronised. This
option enables this feature. Traditionally this type of feature requires
a lot more processor power, but Fusion is very highly optimised, and this
feature isn't usually noticably slower, so it should be ok to leave it
enabled all the time. If you do notice poor performance, or notice any
strange problems with certain MegaCD/SegaCD games, you may wish to try it
both ways.

You can choose to enable or disable display of a frames per second counter,
and the SegaCD LEDs.

USE ALTERNATE TIMING - Normally the sound card will be used for timing
purposes - this ensures a clean, pop/gap free sound stream. However, some
sound cards/drivers do not provide accurate timing information. If you
notice any speedup / slowdown or inconsistent speed problems, you can try
enabling alternate timing instead. Note though that you may get some
problems with sound if you do so. This option will be forced ON if you
have no sound card in your machine, or you disable sound.

SLEEP WHILE WAITING - Normally, when Fusion has finished rendering a frame
it will begin waiting until it's time to start rendering the next one. The
timing required here is very precise. Because during this time Fusion is
not completely inactive (it's constantly saying 'Are we there yet?') this
results in a high CPU usage measured in the Windows Task Manager. This is
not a problem, Fusion will give time up to other applications that need
it - still, some people don't seem to like, or understand, this.
SLEEP WHILE WAITING means that Fusion will instead go to sleep at the end
of rendering a frame, giving much lower CPU usage measurements. But do
understand that if you enable this feature, it is not possible to get the
precise timing needed, and Fusion *can not* wake up in time to render the
next frame. The frame rate will be 'choppy' at best. I leave it up to you
to decide which you prefer.

HIGH PRIORITY - Because Fusion does, in fact, give up time to other
applications (see above), sometimes background tasks such as virus scan,
or other programs that you have running, can cause the framerate to drop
or become 'choppy'. This option should improve the situation considerably.
Please note that there is very little point enabling HIGH PRIORITY and
SLEEP WHILE WAITING at the same time, because of the problems mentioned
above.

PAUSE/FRAME ADVANCE/FAST FORWARD do exactly what you'd expect.

DISABLE KEY SHORTCUTS - turns off all keyboard shortcuts (except ESC) to
prevent the accidental selection of some option while playing a game with
the keyboard.




CONFIG
------

The config dialog is split into several tabs:


SMS/GG:
-------

You can specify where to find the USA/JAP/EUR BIOS files for the Sega
Master System, and the GG BIOS file for the GameGear. None of these files
are required for operation, but you can use them if you wish.

SxM Files - these are the emulated battery-backed RAM files used in some
cartridges. Select the folder where you want these files to be saved.

State Files - See LOAD/SAVE STATE. Select the folder where you want these
files to be saved.

SMS Patch/GG Patch - these are files that store GameGenie or PAR codes for
each game. Select the folders where you want these files to be saved.

Sprite Limiter - a real SMS/GG can only display a small number of
sprites on any one line of the display, and after that, the rest will not
be shown. Some games use this fact to make sprites disappear under other
objects. However you can disable this effect and let all sprites be
drawn - for some games this will remove a lot of flickering.

BIOS Use - allows you to ignore the BIOS files without having to manually
edit them all out. SG-1000/SC-3000 games, for example, probably won't run
if the BIOS files are enabled, because they lack data that the BIOS files
look for.

SMS Border - some people didn't like the fact that the area outside the
SMS display is filled with a "border colour". This is how a real SMS
does things, but by request, this option removes the "border colour" and
instead fills the area with black.

YM2413FM - an extra soundchip present only in some Japanese systems. This
should not be accessed by any software that doesn't make use of it, but
you can disable it here should any weird sounds be heard, or if you
prefer the sound from a system without this chip.

GG Zoom - Zooms the GameGear screen up to full screen.


Genesis:
--------

SRM Files - these are the emulated battery-backed RAM files used in some
cartridges. Select the folder where you want these files to be saved.

State Files - See LOAD/SAVE STATE. Select the folder where you want these
files to be saved.

Patch Files - these are Game Genie or PAR code files. Select the folder
where you want these files to be saved.

BIOS File - you can specify where to find the Genesis BIOS file. This file
is not required for operation, but you can use it if you wish.

AutoFix Checksums - Fixes Checksums on ROMs with bad checksums. Some ROMs
are *supposed* to have a bad chacksum, and fixing it will stop the game
from running. In either case, if your game locks up (often with a red
screen) try altering this option and reloading the ROM.

Disable SRAM - Some games have a kind of protection whereby they will try
to write to SRAM. The cartridge itself didn't actually *have* any SRAM -
so if the write is successful, the game will not work correctly. Pugsy is
one such game, there may be others.

Disable Border - the border area is filled with black instead of the
correct border colour. Again, by request.



Sega CD:
--------

USA/JAP/EUR BIOS - locate the BIOS files required for SegaCD emulation.
Repeat - These files are *required* for SegaCD emulation.

BRM Files - Select the folder where you wish SegaCD Save Games to be saved.

State Files - See LOAD/SAVE STATE. Select the folder where you want these
files to be saved.

ReadAhead - Select amount of ReadAhead the CD drive does while running
SegaCD games. Which works best really depends on the speed of your PC and
CD-ROM drive. Experiment !

Built-In RAM - Per Game will create and save a new RAM file for each game
loaded. Per BIOS will use just one built-in RAM file for each territory.
This is much closer to how the original console operated and is much
preferred.

CD+G - Specify how CD+G codes are treated. This is dependant on your CD
drive, and is only useful if you are playing an audio CD containing CD+G
codes from within the SegaCD BIOS. Most of the time you should leave this
OFF (it has no use at all while playing games or normal audio CDs, and may
affect performance) but if you have a CD+G disc, you can try either RAW or
COOKED mode. Which works best is dependant on your CD drive - a lot of CD
drives don't work at all, but most CD-RW drives should support at least one
or the other format.

Please note that CD+G itself is fairly unreliable - the CD+G data is not
protected by checksums/correction data like the rest of the data on a CD.
So if you see some corruption while watching a CD+G disk, don't be too
surprised by it ;-) There is not much that can be done about this, its a
problem with the CD+G format, and is quite common.


32X:
----

M68K/Master/Slave BIOS - you can specify where to find the three 32X BIOS
files for M68K, Master and Slave. These files are not required for use,
but you can use them if you wish.

Disable 32X - Unlike most other emulators that treat the 32X as an entirely
seperate console, in this emulator the 32X is connected to the Genesis at
all times - much like a real system, Genesis and SegaCD games work as
normal, and only when a game attempts to initialise the 32X, it springs to
life. This makes for a nicer user experience - the user does not need to
know beforehand if the 32X is required or not. However, although it should
not happen, it is possible that some programs MAY accidentally trigger the
32X, which will do nothing much except affect performance. If this is the
case it can be disabled (effectively, unplugged) here. Another reason why
you may wish to disable the 32X is that some SegaCD/32X games will work
with or without the 32X - this will allow you to see both versions.

Fast 32X Timing - this option should be left disabled. It's only there to
allow some prototype carts to work correctly. All retail games work fine
without it.


Controllers:
------------

Here you can select which type of controller is connected to each of the
control ports. You can also select whether each of these controllers uses
Keyboard, Joystick, or in some cases, Mouse control. Clicking the DEFINE
button allows you to set keys or Joystick buttons.

Genesis controllers supported are: 3 Button Pad, 6 Button Pad, Sega Mouse,
Sega Menacer, and Konami Justifier.

SMS controllers supported are: 2 Button 'Control Pad', Paddle, and Light Phaser.

The PC Mouse can be used to control the Sega Mouse, Menacer, Justifier, Paddle, and Light Phaser only. It is also used for the Pico Pen/Touchpad.

Also supported is the Sega TeamPlayer (in port 1, port 2, or both), the EA
4-Way-Play (which takes up both ports), and the J-Cart (used for some
Codemasters games) - these devices all allow more than 2 controllers to be
connected. Note that none of these devices should be enabled unless the
game you are playing supports them, otherwise controller input may not
work correctly.

Finally, you can invert the Sega Mouse (some games require this) and enable
a cursor for the LightGuns, if you wish.


Extras:
-------

Specify the folder and format for Screenshot files.




---------------------------------------------------------------------------
Special Features
---------------------------------------------------------------------------

* You can play multiple CD games. When it comes time to change discs, you
  should see a flashing CD tray icon in the bottom left of the display.
  This means the emulated CD tray is OPEN. You can safely change discs at
  this point - alternatively you can load a new SegaCD Image file.

* You can play with the SMS BIOS by hitting "Power On" while the emulator
  is in a "Power Off" state. The SMS will boot without a cartridge, thus
  letting you play with games etc. stored in the BIOS.

* You can play with the MegaCD Cartridge "Flux" by first loading it as a
  Genesis cartridge. When it reports that you need a MegaCD to use it, you
  can then put an audio CD in your CD-ROM drive and hit "Boot CD". Flux
  will now run, and will stay active until you hit "Power Off".
