# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008e5c`
- end: `0x180008ef2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800079dc`
- `0x18000878c`
- `0x1800088f0`
- `0x18000a220`
- `0x18000a6a4`
- `0x18000b9bc`

## callees

- `0x180004f74`
- `0x180008e5c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008e81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008e81`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ea5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ea5`

## string_xrefs

- `0x180008e9e`: `ntdll.dll`

## pseudocode

```c

```
