
# Readme

This is yet an other OSX firewall script, but a rather simple one. It switches between two settings

  - **private**: assuming you are on a private LAN of some sort behind an other firewall and with more need for AirPlay, BonJour, SMB ant the like, and little need for paranoid security. This is more or less the setting(s) you will see, when you open System Preferences->Security & Privacy->Firewall (assuming it is enabled) and honors your list of allowed and disallowed applications
  - **public**: assumes you have no need for AirPlay, BonJour, SMB ant the like and don't trust the network connection. All incoming connections are blocked.

Place the script some where nicely i.e. ~/bin, make it executable and run it. It will ask for a password as it uses `sudo`.

Install with

`````bash
test -d ~/bin || mkdir ~/bin
mv set-fw ~/bin
chmod 555 ~/bin/set-fw
`````

Run with

`````bash
# on a public network
~/bin/set-fw public
# on a private network
~/bin/set-fw private
# see current status
~/bin/set-fw fwstat
`````

## Why do it?

Apple consider [pf](https://en.wikipedia.org/wiki/PF_(firewall)) part of the base operating system, so if you make any changes they may be replaced during a system update. If you like me are most comfortable with the command line, then it makes sense to change settings depending on your current connection with a script.

## Tested on

The script has only been tested on High Sierra. It will fail if Apple make changes to socketfilterfw.

