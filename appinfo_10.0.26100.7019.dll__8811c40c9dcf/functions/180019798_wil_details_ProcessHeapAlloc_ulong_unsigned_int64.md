# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180019798`
- end: `0x18001984f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b2b0`
- `0x18000b520`
- `0x180013970`
- `0x1800214f0`
- `0x180021650`
- `0x1800231d0`
- `0x180023440`

## callees

- `0x180019798`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019808`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019808`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800197ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800197ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800197ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800197ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800197c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800197c3`

## string_xrefs

- `0x1800197e6`: `ntdll.dll`

## pseudocode

```c

```
