# __scrt_initialize_thread_safe_statics

- ea: `0x180003920`
- end: `0x1800039f0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003728`
- `0x1800038f8`
- `0x180003920`
- `0x180004104`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180003970`
- `KERNEL32!GetProcAddress` at `0x180003983`
- `KERNEL32!GetProcAddress` at `0x180003970`
- `KERNEL32!GetProcAddress` at `0x180003983`
- `KERNEL32!GetModuleHandleW` at `0x180003943`
- `KERNEL32!GetModuleHandleW` at `0x180003958`
- `KERNEL32!GetModuleHandleW` at `0x180003943`
- `KERNEL32!GetModuleHandleW` at `0x180003958`
- `KERNEL32!CreateEventW` at `0x1800039af`
- `KERNEL32!CreateEventW` at `0x1800039af`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180003936`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180003936`

## string_xrefs

- `0x18000393c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180003951`: `kernel32.dll`

## pseudocode

```c

```
