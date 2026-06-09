# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18016c518`
- end: `0x18016c5b6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800ef9a8`
- `0x18014d4c4`
- `0x18016be68`
- `0x180190ba4`
- `0x180190cd4`
- `0x1801915e0`

## callees

- `0x18016c518`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18016c561`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18016c561`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18016c576`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18016c576`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18016c53d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18016c53d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18016c52c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18016c52c`

## string_xrefs

- `0x18016c55a`: `ntdll.dll`

## pseudocode

```c

```
