# tvOS-26.1-Jailbreak
A working jalbreak for tvOS 26.1! Thanks to sawyerthemiller for providing the guide on how you do this.


This is tested on an Apple TV HD 4th Generation
# How was this made?
This is basically palera1n for 26.0.1 but with a special branch of PongoOS that has support for 26.1. I was not the one who made this special branch but I have compiled it which makes it easy to run on old hardware without full compiling support and simplifies it.
# Usage
Download the correct version for your OS. If you need to rejailbreak, go to the bottom.
> [!NOTE]
>You need to factory reset your apple TV before starting

>  [!WARNING]
> This will not work on 26.2, apple changed the kernal so it will panic every time.

Once you have reset the apple TV, run 

```
./palera1n -f --force-revert
```
This will put the apple TV in recovery, then follow the instructions to put into DFU mode.
>[!NOTE]
>If you are on Mac, macOS prevents the file from opening. It will report it as damaged so to fix this run:
>```
>xattr -d com.apple.quarantine palera1n
>```
>This will disable the protection for the file.

>[!NOTE]
> If it gets stuck on 'booting PongoOS' use Ctrl+C and run the command again. You will have to do this often.

Now it will boot back into the OS and you can setup your apple TV.

Once you have set it up we can begin the jailbreak.
Run:
```
./palera1n --override-pongo build/Pongo.bin --override-kpf build/checkra1n-kpf-pongo --fakefs --setup-fakefs
```
Now be patient. It will reboot to recovery in about 8 minutes once it gets past 'booting PongoOS'

If it does get stuck, like for more than 20 minutes, unplug your apple tv and plug it back in, fake fs failed to setup. Hopefully you will still be able to get back to the homescreen.

You now will be back at the recovery screen. Now you can run this command:
```
./palera1n --override-pongo build/Pongo.bin --override-kpf build/checkra1n-kpf-pongo --fakefs
```
>[!NOTE]
> To rejailbreak simpliy run this command everytime after a reboot.

You should now have the palera1n launcher on the home screen.

# Building it yourself
If any of my compiled files don't work or don't work on your OS, like different versions of linux, you can build it yourself.
>[!Note]
>You will need to have a newish OS to compile with the latest tools.

You will need standard build tools installed on your mac, or linux computer. Run:
```
git clone https://github.com/palera1n/PongoOS.git
```
Run:
```
git checkout ee8ad2d
```
This is a special commit to the apple tv branch to fix 26.1.

Run:
```
make all
```
Now download the latest palera1n from the releases tab for your computer, Rename it to 'palera1n' move it to your PongoOS folder after it's built and run:
```
sudo chmod +x palera1n
```
Now you can continue with the jailbreak.



