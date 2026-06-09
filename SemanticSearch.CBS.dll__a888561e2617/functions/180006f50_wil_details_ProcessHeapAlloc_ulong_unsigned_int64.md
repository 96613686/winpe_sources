# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006f50`
- end: `0x180006fef`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006ff0`
- `0x18001a570`
- `0x180042830`
- `0x180042de0`
- `0x1800439f0`

## callees

- `0x180006f50`
- `0x18005e260`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180006f64`
- `KERNEL32!GetProcessHeap` at `0x180006f64`
- `KERNEL32!GetProcAddress` at `0x180006fae`
- `KERNEL32!GetProcAddress` at `0x180006fae`
- `KERNEL32!GetModuleHandleW` at `0x180006f99`
- `KERNEL32!GetModuleHandleW` at `0x180006f99`
- `KERNEL32!HeapAlloc` at `0x180006f75`
- `KERNEL32!HeapAlloc` at `0x180006f75`

## string_xrefs

- `0x180006f92`: `ntdll.dll`

## pseudocode

```c

```
