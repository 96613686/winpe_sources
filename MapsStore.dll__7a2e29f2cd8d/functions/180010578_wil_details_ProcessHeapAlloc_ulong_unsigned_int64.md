# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180010578`
- end: `0x18001060e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010304`
- `0x1800109fc`
- `0x180010d94`

## callees

- `0x18000e418`
- `0x180010578`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800105c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800105c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001059d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001059d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001058c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001058c`

## string_xrefs

- `0x1800105ba`: `ntdll.dll`

## pseudocode

```c

```
