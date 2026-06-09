# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180010fbc`
- end: `0x180011052`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000f57c`
- `0x1800108fc`
- `0x180010a60`
- `0x180013424`
- `0x1800138b4`
- `0x180014d84`

## callees

- `0x18000922c`
- `0x180010fbc`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011005`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011005`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010fd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010fd0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010fe1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010fe1`

## string_xrefs

- `0x180010ffe`: `ntdll.dll`

## pseudocode

```c

```
