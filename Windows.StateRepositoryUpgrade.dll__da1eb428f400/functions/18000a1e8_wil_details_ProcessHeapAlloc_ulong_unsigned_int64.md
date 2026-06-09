# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a1e8`
- end: `0x18000a27e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000963c`
- `0x180009fdc`
- `0x18000a474`
- `0x18000a5b0`
- `0x1800102d8`
- `0x180012290`

## callees

- `0x1800082bc`
- `0x18000a1e8`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a231`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a231`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a20d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a20d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1fc`

## string_xrefs

- `0x18000a22a`: `ntdll.dll`

## pseudocode

```c

```
