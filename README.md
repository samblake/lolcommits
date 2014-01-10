# lolcommits (git + webcam = lol)

lolcommits takes a snapshot with your webcam every time you git commit code, and archives a lolcat style image with it.
Git blame has never been so much fun.

For full details see the [official github](https://github.com/mroth/lolcommits/)

## Installation

**Note**: This guide is not for cygwin, and assumes you have installed Ruby via the [one-click installer](http://rubyinstaller.org/).

### Ruby Development Kit

You can skip this step if you already have this installed.

1. Download the **Ruby Development Kit** from here: http://rubyinstaller.org/downloads/
2. Unpack it somewhere (e.g. `C:\RubyDevKit`)
3. `cd` to where you unpacked it too
4. Run `dk.rb init`. This will generate a `config.yml` file that details the list of Rubies found on your system. You can configure this before installing if need be. Run `dk.rb review` to review the install
5. Finally run `dk.rb install`.

For more information see https://github.com/oneclick/rubyinstaller/wiki/Development-Kit.

### Installing RMagick and ImageMagick

The following guide is for Ruby 1.9

1. Download **ImageMagick**. I have this working with `ImageMagick-6.7.6-6-Q16-windows-dll.exe`. It can be found on google. Other versions may cause issues.
2. Install to a path **without spaces**. E.g. `C:\ImageMagick`
3. Make sure **Add application directory to your system path** and **Install development headers and libraries for C and C++** are checked:
![ImageMagick installation](http://i.imgur.com/QlL7a.png)
4. Close and reopen Command Prompt to reload your PATH variables (you can run `PATH` or `convert -v` to ensure ImageMagick is there)
5. Run the following command (replacing the location of ImageMagick on your system if you opted for something different):
```
gem install rmagick --platform=ruby -- --with-opt-lib=C:/ImageMagick/lib --with-opt-include=C:/ImageMagick/include
```
It will take a while to build the native extensions, but it should install it cleanly now.

If you run into any issues, there's probably a solution on Google.

## Lolcommits

Woo, all the prerequisites have been taken care of, now all you need to do is install lolcommits:

```
gem install lolcommits
```