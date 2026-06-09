# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000aff8`
- end: `0x18000b096`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800088b8`
- `0x180008c94`
- `0x180009b60`
- `0x18000a150`
- `0x18000ca54`
- `0x18000e60c`

## callees

- `0x18000aff8`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b056`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b056`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b041`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b041`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b00c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b00c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b01d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b01d`

## string_xrefs

- `0x18000b03a`: `ntdll.dll`

## pseudocode

```c

```
