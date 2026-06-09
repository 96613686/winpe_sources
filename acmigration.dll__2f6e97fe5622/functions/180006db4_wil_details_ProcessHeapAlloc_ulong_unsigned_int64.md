# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006db4`
- end: `0x180006e5c`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `168`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004a28`
- `0x180004df8`
- `0x180005b00`
- `0x1800086d0`
- `0x180009e2c`

## callees

- `0x180006db4`
- `0x18006a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180006e07`
- `KERNEL32!GetModuleHandleW` at `0x180006e07`
- `KERNEL32!GetProcessHeap` at `0x180006dd2`
- `KERNEL32!GetProcessHeap` at `0x180006dd2`
- `KERNEL32!GetProcAddress` at `0x180006e1c`
- `KERNEL32!GetProcAddress` at `0x180006e1c`
- `KERNEL32!HeapAlloc` at `0x180006de3`
- `KERNEL32!HeapAlloc` at `0x180006de3`

## string_xrefs

- `0x180006e00`: `ntdll.dll`

## pseudocode

```c

```
