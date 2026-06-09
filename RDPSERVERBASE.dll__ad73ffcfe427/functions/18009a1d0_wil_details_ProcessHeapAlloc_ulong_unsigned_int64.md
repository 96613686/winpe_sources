# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18009a1d0`
- end: `0x18009a266`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800766cc`
- `0x18009860c`
- `0x18009cd6c`
- `0x18009cea8`

## callees

- `0x18008a19c`
- `0x18009a1d0`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18009a219`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18009a219`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009a1f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009a1f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009a1e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009a1e4`

## string_xrefs

- `0x18009a212`: `ntdll.dll`

## pseudocode

```c

```
