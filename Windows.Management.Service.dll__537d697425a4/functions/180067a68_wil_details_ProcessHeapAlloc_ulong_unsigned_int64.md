# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180067a68`
- end: `0x180067b11`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180066c94`
- `0x1800677dc`
- `0x180067f04`
- `0x1800682b8`
- `0x180073864`
- `0x1800785d0`

## callees

- `0x180064f34`
- `0x180067a68`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180067abd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180067abd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180067a93`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180067a93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067a7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067a7c`

## string_xrefs

- `0x180067ab6`: `ntdll.dll`

## pseudocode

```c

```
