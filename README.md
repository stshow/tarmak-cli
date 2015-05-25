# Tarmak for CLI
A shell script for creating the intermediate key layouts used for learning Colemak on CLI terminals.

Only the letter keys and (semi-)colon are moved, so all your other keys will stay the same as they are on your current/preferred keymap.

## Prerequisites
 - a UNIX (Linux, BSD, Mac...) box...
 - running from a CLI terminal...
 - that you have root access to

## Quick Start
Download the files with **`$ git clone https://github.com/azmr/tarmak.git`**, or as a .zip file from the side of the GitHub page. Alternatively, make a new file using the script at https://github.com/azmr/tarmak/blob/master/tmk.sh.

Run the script using **`$ sudo bash tmk.sh`** and follow the prompts.
The defaults worked out from your system should be appropriate, but if they aren't, you can enter your preferred map file and destination.

To use one of the layouts until you turn off the computer, enter **`$ sudo loadkeys tarmakX`** (for any of tarmak1-4). This is **recommended for your first use**, just to make sure everything works as expected.

To set the layout in a persistent way, enter **`$ sudo localectl set-keymap tarmakX`**. *Caution: the new keymap will be active when you input your password, so make sure you can type with it!

## Brief introduction to Tarmak
*For a more complete explanation, please see this [post](http://forum.colemak.com/viewtopic.php?id=1858 "Learn Colemak in steps with the Tarmak layouts!") in the Colemak forums.*

As you've found your way here, you probably already know a little about Tarmak, but just in case...

Colemak is a keyboard layout, created primarily as an alternative to QWERTY, "designed for efficient and ergonomic touch typing" [[colemak.com](http://colemak.com)].

Switching layout all at once - 'cold turkey' - can be crippling for typing speed while learning the new muscle memory.
The frustration from this causes some people to quit prematurely.
To make the jump less drastic, Colemak forum member DreymaR created multiple intermediate layouts that each change only a few keys, allows for people to retain a functional typing speed while progressing toward full-blown Colemak.

These intermediate steps are collectively called Tarmak.

## Manual Setup
1. Determine your current keymap using **`$ localectl status`** or from `/etc/vconsole.conf`
2. Find the file for that/your preferred keymap (in `/usr/share/kbd/keymaps/` for Linux and `/usr/share/syscons/keymaps/` for BSD)
3. Make 4 copies of the keymap to somewhere suitable with the names you want, e.g. in the `colemak` subdirectory under the same base directory with the names tarmak1-4.
4. *Optional but preferable:* unzip all the tarmak maps using **`$ sudo gunzip tarmak*`**
5. Append the appropriate key changes to each file. These can be copied and pasted from https://github.com/azmr/tarmak/blob/master/keychanges.txt.
6. Rezip all the maps using **`$ sudo gzip tarmak*`**
7. Set the new layout with **`$ sudo loadkeys tarmakX`** or **`$ sudo localectl set-keymap tarmakX`**.


## Disclaimer
This script should work on most hardware running UNIX, and certainly shouldn't do any damage, but has only been tested at a very small scale.
Use at your own risk.

If you have any issues, please let me know.
