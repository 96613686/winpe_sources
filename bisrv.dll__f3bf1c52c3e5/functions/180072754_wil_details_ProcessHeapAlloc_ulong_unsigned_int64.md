# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180072754`
- end: `0x1800727f2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18006bd4c`
- `0x1800723b0`
- `0x1800724e0`
- `0x1800730a4`
- `0x18007321c`

## callees

- `0x180072754`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800727b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800727b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007279d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007279d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180072779`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180072779`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072768`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072768`

## string_xrefs

- `0x180072796`: `ntdll.dll`

## pseudocode

```c

```
