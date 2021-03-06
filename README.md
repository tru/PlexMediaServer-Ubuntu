# Plex Media Server ubuntu package #

## What is this?
These are scripts that repackage binaries released by plexapp.com to a
Ubuntu package.

## What's good about them?
* Automatically depends on avahi packages and ia32 libs.
* Installs upstart scripts
* Automatically creates a plex user that will run the server
* It's much cleaner!

## Who did this?
These are *NOT OFFICIAL* packages, rather made by Tobias Hieta, because
I like to have things clean on my Ubuntu server.

## How to use?
* Get the Ubuntu Linux build of Plex Media Server from http://plexapp.com/labs.
* Untar it alongside the debian directory.
* Then rename PlexMediaServer-<version> to `src`.
* Run `fakeroot dpkg-buildpackage -us -uc -b` - This will get you a plexmediaserver-xx.deb in the parent directory
* Install it with `dpkg -i *deb`

That's it!

## Why can't I just get a .deb or a apt source?
I would love to, but
1. I don't have the official OK to redistribute the binaries, so I don't
   want that until that is sorted.
2. I am not sure how many downloads a .deb would get and since the files
   are pretty big, I am not sure that I have the available bandwidth for
   that.

Hopefully the Plex team will agree and we can work something out :-)

## Have you tested this?
Yes, but only on ubuntu 10.04 LTS amd64. So I am not sure that it will
work on other systems.

## Where can I file bugs and see the scripts?
On github. https://github.com/tru/PlexMediaServer-Ubuntu

## Details please!
OK! The debian package creates a new user called `plex` that runs the
Plex Media Server. The Library folder can be found in `/var/lib/plexmediaserver`

The package also installs a upstart configuration file that will start PMS
upon boot. It will also respawn if something goes wrong.


