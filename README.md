# Roblox UI Autocomplete
Provides completions for Vide/Fusion constructors.

https://github.com/user-attachments/assets/3167e5ce-e849-46a6-9e7c-202eb0af9769

## Installation

With Lazy:
```lua
return {
    { "sweetboss12512/rbx-ui-autocomplete.nvim", dependencies = { "nvim-treesitter/nvim-treesitter" }, lazy = true },
    { -- blink.cmp config
        "saghen/blink.cmp",
        opts = {
            sources = {
                default = { "rbx_ui" },
                providers = {
                    rbx_ui = {
                        name = "RBX",
                        module = "rbx-ui-autocomplete",
                        ---@type rbx-ui.Config
                        opts = {},
                    },
                },
            },
        },
    },
}
```

You can change the completions for certain datatypes:
```lua
opts = {
    complete_snippets = {
        enabled = true, -- Enable/disable snippets for datatypes
        completions = {
            UDim2 = "UDim2.fromScale($0)",
            Color3 = "Color3.fromRGB($0)",
            CFrame = "", -- Disable completion for specific datatype
        },
    },
}
```
