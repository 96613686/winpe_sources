# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000afe8`
- end: `0x18000b088`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `160`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000aa60`
- `0x18000abb0`
- `0x18000c01c`
- `0x18000c49c`
- `0x18000dd94`

## callees

- `0x180007a8c`
- `0x18000afe8`
- `0x18005f010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000b017`
- `KERNEL32!HeapAlloc` at `0x18000b017`
- `KERNEL32!GetProcessHeap` at `0x18000b006`
- `KERNEL32!GetProcessHeap` at `0x18000b006`
- `KERNEL32!GetModuleHandleW` at `0x18000b03b`
- `KERNEL32!GetModuleHandleW` at `0x18000b03b`

## string_xrefs

- `0x18000b034`: `ntdll.dll`

## pseudocode

```c

```
