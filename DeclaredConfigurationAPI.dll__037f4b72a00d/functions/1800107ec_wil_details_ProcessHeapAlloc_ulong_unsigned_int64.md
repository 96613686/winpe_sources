# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800107ec`
- end: `0x18001088a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f5cc`
- `0x180010278`
- `0x1800103a8`
- `0x180011880`
- `0x180011d10`
- `0x18001300c`

## callees

- `0x1800107ec`
- `0x180139010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001084a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001084a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010835`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010835`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010811`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010811`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010800`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010800`

## string_xrefs

- `0x18001082e`: `ntdll.dll`

## pseudocode

```c

```
