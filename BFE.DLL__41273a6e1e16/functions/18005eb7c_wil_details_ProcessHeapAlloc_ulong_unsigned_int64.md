# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18005eb7c`
- end: `0x18005ec33`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180056914`
- `0x18005e69c`
- `0x18005e7d4`
- `0x18005f594`
- `0x18005fa34`

## callees

- `0x18005eb7c`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005ebd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005ebd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005ebec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005ebec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005eba7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005eba7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005eb90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005eb90`

## string_xrefs

- `0x18005ebca`: `ntdll.dll`

## pseudocode

```c

```
