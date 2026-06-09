# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180003df8`
- end: `0x180003e96`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005380`
- `0x1800057e0`
- `0x180006230`
- `0x180007cc0`

## callees

- `0x180003df8`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003e41`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003e41`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003e56`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003e56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e0c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003e1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003e1d`

## string_xrefs

- `0x180003e3a`: `ntdll.dll`

## pseudocode

```c

```
