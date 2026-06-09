# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180049ee8`
- end: `0x180049f9f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180049ce4`
- `0x180049db4`
- `0x180079090`
- `0x180079c14`
- `0x180079d60`

## callees

- `0x180049ee8`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180049f8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180049f8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180049f3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180049f3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049efc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049efc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049f13`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049f13`

## string_xrefs

- `0x180049f36`: `ntdll.dll`

## pseudocode

```c

```
