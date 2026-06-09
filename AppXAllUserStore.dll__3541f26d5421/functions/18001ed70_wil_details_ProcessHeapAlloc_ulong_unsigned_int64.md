# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001ed70`
- end: `0x18001ee06`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180012abc`
- `0x180019338`
- `0x1800194a0`
- `0x180024ed4`
- `0x180025010`

## callees

- `0x18001ed70`
- `0x1800234c8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18001edb9`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18001edb9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ed95`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ed95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ed84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ed84`

## string_xrefs

- `0x18001edb2`: `ntdll.dll`

## pseudocode

```c

```
