# Fish Shell — Beginner-Friendly Guide

A simple guide to what Fish is, how to install it, how to use it, and how to switch back to another shell.

## 1. Introduction to Fish Shell

**Fish** means **Friendly Interactive SHell**. It is a command-line shell designed to make everyday terminal use easier.

Useful built-in features include:
- **Autosuggestions** as you type.
- **Syntax highlighting** to help spot invalid commands.
- **Tab completion** for commands, options, and file names.
- **`fish_config`** to customize the prompt and colors.

Fish is great for interactive terminal use, but its scripting syntax is different from Bash.

## 2. How to Install Fish

On Ubuntu or Debian, install Fish from your configured package repositories:

```bash
sudo apt update
sudo apt install fish
```

Check the installation:

```bash
fish --version
```

Try Fish without changing your default shell:

```bash
fish
```

To leave Fish and return to the shell you started from:

```fish
exit
```

## 3. How to Use Fish

Here are a few useful basics:

```fish
# Run everyday commands
ls -la
cd ~/projects

# Set and print a variable
set NAME "value"
echo $NAME

# Open Fish's configuration interface
fish_config

# Get help
help
```

- Press **Tab** to see available completions.
- Fish shows suggestions as you type; press **Right Arrow** to accept a suggestion.
- Fish uses different syntax from Bash, so Bash commands and scripts may need changes when typed or sourced directly in Fish.

## 4. How to Change Back to Another Shell

To make Bash your login shell:

```bash
chsh -s /bin/bash
```

To use Zsh instead, if it is installed:

```bash
chsh -s "$(which zsh)"
```

Log out and log back in for the login-shell change to take effect.

Check your configured login shell and available shells:

```bash
echo "$SHELL"
cat /etc/shells
```

To leave a temporary Fish session, simply type `exit`.

## 5. Is Fish Safe?

Fish is generally suitable for everyday interactive use when installed from trusted repositories and kept updated.

Remember:
- Install software from trusted sources.
- Keep Fish and your system updated.
- Read commands before running them, especially commands using `sudo`.
- Fish's extra convenience features do not replace normal security precautions.

## 6. How Fish Works

- **Autosuggestions** use your command history and available completions to suggest what you may type next.
- **Syntax highlighting** checks and colors commands while you type.
- **Tab completion** helps complete commands, options, and paths.
- **Universal variables** can persist between Fish sessions. For example:

```fish
set -Ux EDITOR vim
```

Fish's scripting language is different from Bash, so scripts written specifically for Bash should normally be run with Bash rather than pasted or sourced into Fish.

## 7. Important Caveats

- **Do not set Fish as `/bin/sh`.** System scripts often expect a POSIX-compatible shell, and replacing `/bin/sh` can break system tools or maintenance tasks.
- **Be careful when choosing Fish as your login shell** on servers or critical systems. Some startup configuration is written for POSIX shells and may not work directly in Fish.
- **Do not use Fish as root's shell** on systems where administrative or recovery scripts expect a POSIX shell.
- **Bash syntax is not always valid in Fish.** For example, variable assignment and command substitution use different syntax.
- **Check tool setup instructions.** Some developer tools need Fish-specific configuration.

A cautious approach is to keep Bash as the login shell on important systems and start Fish when you want to use it interactively.

## 8. Summary

- Fish is a user-friendly shell with suggestions, highlighting, and helpful completions.
- Install it with `sudo apt install fish` on Ubuntu/Debian systems where the package is available.
- Start it by running `fish`; leave it with `exit`.
- Use `chsh` to change your login shell, and log out and back in afterward.
- Fish is useful for interactive work, but it is **not a drop-in replacement for Bash scripts or `/bin/sh`**.

**In short:** Fish can make everyday terminal use more comfortable. Use it as an interactive shell, and keep system-shell and scripting compatibility in mind.
