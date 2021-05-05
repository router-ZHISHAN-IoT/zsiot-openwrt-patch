# About

This is a Openwrt patch collection powered by ZHISHAN-IoT for routers which don't have official support. These models of router need change on-board RAM or ROM firstly for making sure that they can run Openwrt successfully. However, if use firmware of compatible models, user may not use button or LEDs normally. So we provide patches to generate fitted firmware manually.

# Get patch

## location

Patches are stored under different directories according to arch type of SoC/CPU. It's same with Openwrt source tree. Such as targets/rampis/m7620.

## name rule

Every patch has a recognizable name to help people search wanted one. The name rule is

`openwrt-[version]-[model]-[ROM]+[RAM]-[feature].patch`

For example, `openwrt-19.07.7-bl-d9103-16mb+32mb-locale_cn.patch` means this is a patch for B-link BL-D9103 and it requires size of ROM is 16MB or more(Sometimes, if you use 8MB or 4MB, Openwrt can also run successfully).

# Apply Patch

User need download a source tree and switch to specified version via `git checkout` command firstly. Then execute following command for applying patch.
`patch -p1 < openwrt.patch`
If you want to uninstall patch, you can also execute following command.
`patch -R -p1 < openwrt.patch`
After all works done, rebuild the project for generating expected firmware under `bin` directory.