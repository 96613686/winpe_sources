# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800681e8`
- end: `0x180068286`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180044fd8`
- `0x18004fe60`
- `0x180067158`
- `0x180067cd0`
- `0x180067e00`
- `0x1800691c0`
- `0x180069558`

## callees

- `0x1800681e8`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800681fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800681fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006820d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006820d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180068231`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180068231`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068246`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068246`

## string_xrefs

- `0x18006822a`: `ntdll.dll`

## pseudocode

```c

```
