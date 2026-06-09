# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800179e4`
- end: `0x180017a7a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001602c`
- `0x18001618c`
- `0x18001b264`
- `0x18001b6f8`
- `0x1800247b4`

## callees

- `0x18000a1d0`
- `0x1800179e4`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017a2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017a2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800179f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800179f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017a09`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017a09`

## string_xrefs

- `0x180017a26`: `ntdll.dll`

## pseudocode

```c

```
