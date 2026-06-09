# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000cfd0`
- end: `0x18000d066`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000b44c`
- `0x18000c8c0`
- `0x18000ca24`
- `0x18000e004`
- `0x18000e4b4`
- `0x18000fe90`

## callees

- `0x180007d8c`
- `0x18000cfd0`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cff5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cff5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cfe4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cfe4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d019`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d019`

## string_xrefs

- `0x18000d012`: `ntdll.dll`

## pseudocode

```c

```
