# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180025dd0`
- end: `0x180025e79`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `11`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002087c`
- `0x18003e0c0`
- `0x18003e550`
- `0x18003e9d0`
- `0x18003f998`
- `0x18003fac4`
- `0x1800401c0`
- `0x180040904`
- `0x180040cb8`
- `0x18004c180`
- `0x18004d610`

## callees

- `0x180025dd0`
- `0x18003d1e0`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025e25`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025e25`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025dfb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025dfb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025de4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025de4`

## string_xrefs

- `0x180025e1e`: `ntdll.dll`

## pseudocode

```c

```
