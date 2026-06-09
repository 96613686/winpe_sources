# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14001bbe8`
- end: `0x14001bc7e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400199ec`
- `0x14001ad10`
- `0x14001ae74`
- `0x140025370`
- `0x140025800`
- `0x14002c090`

## callees

- `0x14000a260`
- `0x14001bbe8`
- `0x14007d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001bc31`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001bc31`
- `KERNEL32!GetProcessHeap` at `0x14001bbfc`
- `KERNEL32!GetProcessHeap` at `0x14001bbfc`
- `KERNEL32!HeapAlloc` at `0x14001bc0d`
- `KERNEL32!HeapAlloc` at `0x14001bc0d`

## string_xrefs

- `0x14001bc2a`: `ntdll.dll`

## pseudocode

```c

```
