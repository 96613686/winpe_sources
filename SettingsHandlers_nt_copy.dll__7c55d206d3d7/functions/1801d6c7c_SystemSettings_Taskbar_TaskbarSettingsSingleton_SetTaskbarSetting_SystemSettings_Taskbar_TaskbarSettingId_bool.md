# SystemSettings::Taskbar::TaskbarSettingsSingleton::SetTaskbarSetting(SystemSettings::Taskbar::TaskbarSettingId,bool)

- ea: `0x1801d6c7c`
- end: `0x1801d6f28`
- name: `?SetTaskbarSetting@TaskbarSettingsSingleton@Taskbar@SystemSettings@@QEAAJW4TaskbarSettingId@23@_N@Z`
- size: `684`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1801d5060`
- `0x1801d50d0`
- `0x1801d5230`
- `0x1801d5540`
- `0x1801d5580`
- `0x1801d55a0`
- `0x1801d56b0`

## callees

- `0x180019a20`
- `0x18001e6c4`
- `0x180041004`
- `0x1800504dc`
- `0x1801d661c`
- `0x1801d6758`
- `0x1801d6c7c`
- `0x180289010`

## import_xrefs

- `USER32!SendMessageW` at `0x1801d6eba`
- `USER32!SendMessageW` at `0x1801d6f0c`
- `USER32!SendMessageW` at `0x1801d6eba`
- `USER32!SendMessageW` at `0x1801d6f0c`
- `SHLWAPI!SHSetValueW` at `0x1801d6d67`
- `SHLWAPI!SHSetValueW` at `0x1801d6dfa`
- `SHLWAPI!SHSetValueW` at `0x1801d6e5f`
- `SHLWAPI!SHSetValueW` at `0x1801d6d67`
- `SHLWAPI!SHSetValueW` at `0x1801d6dfa`
- `SHLWAPI!SHSetValueW` at `0x1801d6e5f`

## string_xrefs

- `0x1801d6e47`: `MMTaskbarEnabled`
- `0x1801d6de2`: `TaskbarSmallIcons`
- `0x1801d6ca5`: `shell\systemsettingsthreshold\handlers\internal\taskbar\lib\taskbar.cpp`
- `0x1801d6e13`: `shell\systemsettingsthreshold\handlers\internal\taskbar\lib\taskbar.cpp`
- `0x1801d6e7a`: `shell\systemsettingsthreshold\handlers\internal\taskbar\lib\taskbar.cpp`

## pseudocode

```c

```
