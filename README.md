# Schroenser's "Oh My Posh" setup

## Zsh

### Install Zsh

```Shell
sudo apt update
sudo apt install zsh -y
```

### Initially configure Zsh

```Shell
zsh
```

### Set Zsh as default shell

```Shell
chsh -s $(which zsh)
```

### Make sure .profile is loaded

```Shell
nano ~/.zprofile
```

and add

```Shell
emulate sh -c '. ~/.profile'
```

### Make sure nvm and npm work

```Shell
nano ~/.zshrc
```

and add

```Shell
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
```

## Oh My Posh

### Installation

#### Powershell

```PowerShell
Set-ExecutionPolicy RemoteSigned
winget install JanDeDobbeleer.OhMyPosh -s winget
notepad $PROFILE
```

and add

```PowerShell
oh-my-posh init pwsh --config 'https://raw.githubusercontent.com/schroenser/oh-my-posh-config/main/config.json' | Invoke-Expression
```

If `$PROFILE` is not found run

```PowerShell
New-Item -Path $PROFILE -Type File -Force
```

### Linux

```Shell
curl -s https://ohmyposh.dev/install.sh | bash -s
```

#### Bash

```Shell
nano ~/.bashrc
```

and add

```Shell
eval "$(oh-my-posh init bash --config 'https://raw.githubusercontent.com/schroenser/oh-my-posh-config/main/config.json')"
```

#### Zsh

```Shell
nano ~/.zshrc
```

and add

```Shell
eval "$(oh-my-posh init zsh --config 'https://raw.githubusercontent.com/schroenser/oh-my-posh-config/main/config.json')"
```

### Fonts

In an elevated PowerShell, run

```
oh-my-posh font install
```

then set the new font for the Terminal application, Visual Studio Code and IntelliJ.

### Update

#### Powershell

```PowerShell
winget upgrade JanDeDobbeleer.OhMyPosh -s winget
```
