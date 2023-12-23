
## Summary
Challenge Name: Special

Points: 300

Tags: picoCTF 2023, General Skills, bash, ssh

Author: LT 'SYREAL' JONES

## Description
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)
Start your instance to see connection details.
Additional details will be available after launching your challenge instance.

## Hints
Experiment with different shell syntax

## Initialize

Click the start instance and get the meachine info. Login to the machine using ssh, In my case i received a machine with this address "ssh -p 64471 ctf-player@saturn.picoctf.net" the port number will be autogenerated while staring your challenge instance. Then type "yes" for session fingerprint registration. Press enter and type your password "fd7746b4" the password will be almost same for all challenge instances. 

we receive a terminal prompting,

    Special$

I stared typing various commands but all failed with an error. I saw that the output seems suspecious,

    Special$ ls
    Is
    sh: 1: Is: not found

Then, I tried cat,pwd,ls,cd,echo etc.. but all in vain. While providing random inputs I came across an error from the CTF machine,

    Special$
    Traceback (most recent call last):
    File "/usr/local/Special.py", line 34, in <module>
    first_word = words[0]
    IndexError: list index out of range
    Connection to saturn.picoctf.net closed.

I figured out that the input is validated by a python file then I decide to trick the python program, 😉

After a big warfare of executing random syntax manually, I find a way,

     """"
Four double quotes at the begining of the command can bypass the program 😇 . I tried executing ls and cat commands and it work's.
while executing ls command:

    Special$ """"ls
    """"ls
    blargh
There is a directory named "blargh". Let's, check inside the blargh directory for flag.

    Special$ """"ls "blargh"
    """"ls "blargh"
    flag.txt

Here I find the file "flag.txt". I printed it in console by using cat command,

    Special$ """"cat "blargh/flag.txt"
    """"cat "blargh/flag.txt"
    picoCTF{......<find it yourself>......}

Finally, we received the flag. This is not the correct flag you can get the correct flag by following the above steps. I changed the flag to heat up your challenge 🔥. Relish the Adventure.
