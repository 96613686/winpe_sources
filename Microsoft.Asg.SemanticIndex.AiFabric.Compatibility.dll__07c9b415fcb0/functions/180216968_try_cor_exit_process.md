# try_cor_exit_process

- ea: `0x180216968`
- end: `0x1802169cc`
- name: `try_cor_exit_process`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180216854`
- `0x180216938`

## callees

- `0x180216968`
- `0x180242160`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1802169a3`
- `KERNEL32!GetProcAddress` at `0x1802169a3`
- `KERNEL32!GetModuleHandleExW` at `0x18021698d`
- `KERNEL32!GetModuleHandleExW` at `0x18021698d`
- `KERNEL32!FreeLibrary` at `0x1802169bf`
- `KERNEL32!FreeLibrary` at `0x1802169bf`

## string_xrefs

- `0x180216984`: `mscoree.dll`

## pseudocode

```c

```
