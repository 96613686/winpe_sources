# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000985c`
- end: `0x1800098f2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000843c`
- `0x180009220`
- `0x180009384`
- `0x18000ab20`
- `0x18000afb0`
- `0x18000c590`

## callees

- `0x180005af8`
- `0x18000985c`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800098a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800098a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009881`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009881`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009870`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009870`

## string_xrefs

- `0x18000989e`: `ntdll.dll`

## pseudocode

```c

```
