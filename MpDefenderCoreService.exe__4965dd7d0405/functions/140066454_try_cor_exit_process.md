# try_cor_exit_process

- ea: `0x140066454`
- end: `0x1400664b8`
- name: `try_cor_exit_process`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140066340`
- `0x140066424`

## callees

- `0x140066454`
- `0x140166290`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1400664ab`
- `KERNEL32!FreeLibrary` at `0x1400664ab`
- `KERNEL32!GetProcAddress` at `0x14006648f`
- `KERNEL32!GetProcAddress` at `0x14006648f`
- `KERNEL32!GetModuleHandleExW` at `0x140066479`
- `KERNEL32!GetModuleHandleExW` at `0x140066479`

## string_xrefs

- `0x140066470`: `mscoree.dll`

## pseudocode

```c

```
