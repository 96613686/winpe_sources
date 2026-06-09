# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000b338`
- end: `0x18000b3ce`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000a6cc`
- `0x18000b0b0`
- `0x18000b760`
- `0x18000baf8`
- `0x18001b554`
- `0x18002083c`

## callees

- `0x1800090d4`
- `0x18000b338`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b381`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b381`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b34c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b34c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b35d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b35d`

## string_xrefs

- `0x18000b37a`: `ntdll.dll`

## pseudocode

```c

```
