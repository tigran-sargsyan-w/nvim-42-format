# 🚀 nvim-42-format

A Neovim plugin to format C/C++ code according to the 42 school **norm**.

---

## ✨ Features
- Use `:Format` to format the current buffer.
- Automatically formats `.c`, `.h`, `.cpp`, `.hpp` files.
- Simple integration with popular plugin managers.

---

## ⚡ Requirements
- NVIM v0.10+
- [C Formatter 42](https://github.com/dawnbeen/c_formatter_42) package installed and available in your `$PATH`.

---

## 🛠️ Setup

### 📦 Packer.nvim
```lua
use { "tigran-sargsyan-w/nvim-42-format"" }
```

### 😴 Lazy.nvim
```lua
{
    "tigran-sargsyan-w/nvim-42-format",
  	cmd = "Format",
    config = function()
    local formatter = require "nvim-42-format"
    formatter.setup({
      formatter = 'c_formatter_42',
      filetypes = { c = true, h = true, cpp = true, hpp = true },
    })
  end
  },
```

### 🔌 Vim-plug 
```lua
call plug#begin()
  Plug 'tigran-sargsyan-w/nvim-42-format'
call plug#end()
```
## ⚡ Quick format
- Format on save:
```lua
local formatgrp = vim.api.nvim_create_augroup("nvim_42_format", {})

vim.api.nvim_create_autocmd("BufWritePre", {
  command = "Format",
  group = formatgrp,
})
```
- Format using keybindings:
```lua
vim.api.nvim_set_keymap('n', '<F2>', ':Format<CR>', { noremap = true, silent = true })
```
