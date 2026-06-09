# UpdateTitlebarForTheme(HWND__ *)

- ea: `0x18002c544`
- end: `0x18002c5e7`
- name: `?UpdateTitlebarForTheme@@YAXPEAUHWND__@@@Z`
- size: `163`
- prototype: `void __fastcall(HWND hwnd)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180027d50`
- `0x180027e20`
- `0x180028e10`
- `0x180028f10`

## callees

- `0x180002b20`
- `0x18002c544`

## import_xrefs

- `dwmapi!DwmSetWindowAttribute` at `0x18002c5ce`
- `dwmapi!DwmSetWindowAttribute` at `0x18002c5ce`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c5a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c5a1`

## pseudocode

```c

```
