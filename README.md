# logo.nvim
Extremely minimalistic intro screen for Neovim

## Motivation
Neovim intro screen can be extremely buggy and forced to close automatically by plugins installed such as 
[nvim-tree](https://github.com/nvim-tree/nvim-tree.lua), 
[bufferline](https://github.com/akinsho/bufferline.nvim), 
[lualine](https://github.com/nvim-lualine/lualine.nvim) and many more.  
`logo.nvim` hijects `no-name` and `directory` buffer and draws a simple intro logo.
If you just want a simple and lightweight startup intro that works, this plugin is for you.

## Screenshot
![logo-screenshot](screenshots/screenshot.png)

## Installation
```lua
-- Lazy
{
  "yifever/logo.nvim",
  config = true,
  lazy = false,
  dependencies = {
    "3rd/image.nvim",
  }
}
```

```lua
-- Packer
use {
    "eoh-bse/minintro.nvim",
    config = function() require("logo").setup() end
}
```

### installing image.nvim
Please see [image.nvim](https://github.com/3rd/image.nvim/tree/master) to see how to install it. You need to install use GUI compatible terminal and install magick outside of vim.


## Configuration
There are no configuration available.

```

## Things to be aware of
If you have some sort of `tabline` plugin such as [bufferline](https://github.com/akinsho/bufferline.nvim),
`vim.opt.showtabline` will be overridden to `1`. This forces display of a buffer tab even when there is only
one. If you do not wanna see the tab, you can modify `bufferline`'s configuration like the following:
```lua
require("bufferline").setup({
    options = {
        always_show_bufferline = false
    }
})
```
The above configuration will effectively set `vim.opt.showtabline` to 2, meaning the tabs will only start to
display when there is more than one buffer open

## Reference Configuration
If you want to see a reference neovim configuration, please refer to [this
nvim-setup](https://github.com/eoh-bse/nvim-setup)
