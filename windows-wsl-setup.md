
## Install software
  - Alacrity
```sh 
# Copy Alacritty config into Windows
cp $HOME/.config/alacritty/alacritty.toml  /mnt/c/Users/sterx/AppData/Roaming/alacritty

# We use Alacritty's default Linux config directory as our storage location here.
mkdir -p ~/.config/alacritty/themes
git clone https://github.com/alacritty/alacritty-theme ~/.config/alacritty/themes
```

```sh
# Alacritty Configuration

[general]
import = [
  "~/.config/alacritty/themes/themes/tokyo_night.toml"
]

[env]
TERM = "xterm-256color"
COLORTERM = "truecolor"
LANG = "en_US.UTF-8"

[selection]
save_to_clipboard = true

[font]
size = 22

[window]
startup_mode = "Fullscreen" 
```
  - WSL


## Configure Windows:
- Setup Windows panel for quick app launch
  - Alacrity =  Win+1
  - Notepad++ = Win+2 etc
  - Zoom
  - Chrome 

## TODO - setup file search or app launch using win key 

## WSL
Setup  WSL (From Windows CLI)
```
wsl --install -d Debian
wsl --set-default-version 2
```

## Setup  Git in  WSL
```sh
sudo apt update
sudo apt install -y git

# Set up git in WSL
git config --global alias.st status
git config --global user.name "Valentins Fedotovs"
git config --global user.email "vtrader@inbox.lv"
```

## dot-files
```sh
git clone https://github.com/alexey-goloburdin/dotfiles

# Copy Alacritty config into Windows
cp $HOME/.config/alacritty/alacritty.toml \
    /mnt/c/Users/sterx/AppData/Roaming/alacritty

# We use Alacritty's default Linux config directory as our storage location here.
mkdir -p ~/.config/alacritty/themes
git clone https://github.com/alacritty/alacritty-theme ~/.config/alacritty/themes
```

## Linux core utils in WSL
```sh
sudo apt install -y \
    zsh git gpg pass zip unzip \
    curl wget tmux gcc bsdmainutils htop fzf ripgrep build-essential

```

## Coonfigure WSL Linux nvim, tmux 
```sh
# Install oh-my-zsh
# https://ohmyz.sh/

echo "source \$HOME/.config/zsh/env.zsh" >> ~/.zshrc
echo "source \$HOME/.config/zsh/aliases.zsh" >> ~/.zshrc

# Download nvim into ~/.soft
# https://github.com/neovim/neovim/releases
wget https://github.com/neovim/neovim/releases/download/v0.10.2/nvim-linux64.tar.gz
tar -xzvf nvim-linux64.tar.gz
mv nvim-linux64 .soft/nvim
sudo ln -s $HOME/.soft/nvim/bin/nvim /usr/local/bin/nvim
nvim

echo "alias n=nvim" >> ~/.zshrc && . ~/.zshrc
echo "export EDITOR=vim" >> ~/.zshrc && . ~/.zshrc
```















