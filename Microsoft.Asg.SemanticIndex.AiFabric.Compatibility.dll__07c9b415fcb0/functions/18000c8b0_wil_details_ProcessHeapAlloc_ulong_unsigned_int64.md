# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000c8b0`
- end: `0x18000c94f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c950`
- `0x1800726b0`
- `0x180072a30`
- `0x180072d00`
- `0x180073c10`

## callees

- `0x18000c8b0`
- `0x180242120`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000c8c4`
- `KERNEL32!GetProcessHeap` at `0x18000c8c4`
- `KERNEL32!GetProcAddress` at `0x18000c90e`
- `KERNEL32!GetProcAddress` at `0x18000c90e`
- `KERNEL32!GetModuleHandleW` at `0x18000c8f9`
- `KERNEL32!GetModuleHandleW` at `0x18000c8f9`
- `KERNEL32!HeapAlloc` at `0x18000c8d5`
- `KERNEL32!HeapAlloc` at `0x18000c8d5`

## string_xrefs

- `0x18000c8f2`: `ntdll.dll`

## pseudocode

```c

```
