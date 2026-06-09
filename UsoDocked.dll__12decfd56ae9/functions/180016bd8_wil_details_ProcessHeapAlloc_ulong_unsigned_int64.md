# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180016bd8`
- end: `0x180016c76`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180014938`
- `0x180014d08`
- `0x180015bb0`
- `0x180016180`
- `0x1800184e4`
- `0x180019f8c`

## callees

- `0x180016bd8`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016c36`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016c36`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016c21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016c21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016bec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016bec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016bfd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016bfd`

## string_xrefs

- `0x180016c1a`: `ntdll.dll`

## pseudocode

```c

```
