# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140012f30`
- end: `0x140012fce`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140011fb0`
- `0x140012984`
- `0x140012ad4`
- `0x140013da0`
- `0x140014220`
- `0x140014f8c`

## callees

- `0x140012f30`
- `0x140071010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140012f55`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140012f55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012f44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012f44`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012f8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012f8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012f79`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012f79`

## string_xrefs

- `0x140012f72`: `ntdll.dll`

## pseudocode

```c

```
