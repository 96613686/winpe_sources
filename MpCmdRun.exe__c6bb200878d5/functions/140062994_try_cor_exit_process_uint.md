# try_cor_exit_process(uint)

- ea: `0x140062994`
- end: `0x1400629f8`
- name: `?try_cor_exit_process@@YAXI@Z`
- size: `100`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140062880`
- `0x140062964`

## callees

- `0x140062994`
- `0x140120380`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1400629eb`
- `KERNEL32!FreeLibrary` at `0x1400629eb`
- `KERNEL32!GetProcAddress` at `0x1400629cf`
- `KERNEL32!GetProcAddress` at `0x1400629cf`
- `KERNEL32!GetModuleHandleExW` at `0x1400629b9`
- `KERNEL32!GetModuleHandleExW` at `0x1400629b9`

## string_xrefs

- `0x1400629b0`: `mscoree.dll`

## pseudocode

```c

```
