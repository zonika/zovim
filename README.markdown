# everything is fine

zovim is a distribution of vim plugins and resources for Vim, Gvim and [MacVim]. 

fork of [spf13-vim](https://github.com/spf13/spf13-vim).

# Installation

## Linux, \*nix, Mac OSX Installation

The easiest way to install zovim is by simply copying and pasting the following line into a terminal. This will install vim404 and backup your existing vim configuration. 

*Requires Git 1.7+ and Vim 7.3+*

```bash
    curl https://raw.githubusercontent.com/zonika/zovim/master/bootstrap.sh -L > zovim.sh && sh zovim.sh
```

### Installing dependencies

#### Install [Vim]

After the installation of Vim you must add a new directory to your environment variables path to make it work with the script installation of zovim.

Open Vim and write the following command, it will show the installed directory:

    :echo $VIMRUNTIME
    C:\Program Files (X86)\Vim\vim74

Then you need to add it to your environment variable path. After that try execute `vim` within command prompt (press Win-R, type `cmd`, press Enter) and you’ll see the default vim page.

## Adding new plugins

Create `~/.vimrc.bundles.local` for any additional bundles.

To add a new bundle, just add one line for each bundle you want to install. The line should start with the word "Bundle" followed by a string of either the vim.org project name or the githubusername/githubprojectname. For example, the github project [spf13/vim-colors](https://github.com/spf13/vim-colors) can be added with the following command

```bash
    echo Bundle \'spf13/vim-colors\' >> ~/.vimrc.bundles.local
```

Once new plugins are added, they have to be installed.

```bash
    vim +BundleInstall! +BundleClean +q
```

## Removing (disabling) an included plugin

Create `~/.vimrc.local` if it doesn't already exist.

Add the UnBundle command to this line. It takes the same input as the Bundle line, so simply copy the line you want to disable and add 'Un' to the beginning.

For example, disabling the 'AutoClose' and 'scrooloose/syntastic' plugins

```bash
    echo UnBundle \'AutoClose\' >> ~/.vimrc.bundles.local
    echo UnBundle \'scrooloose/syntastic\' >> ~/.vimrc.bundles.local
```

**Remember to run ':BundleClean!' after this to remove the existing directories**
