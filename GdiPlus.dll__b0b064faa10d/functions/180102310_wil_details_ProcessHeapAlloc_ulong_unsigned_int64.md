# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180102310`
- end: `0x1801023ae`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800fdb0c`
- `0x180101e34`
- `0x180101f58`
- `0x180102cd4`
- `0x180102f38`

## callees

- `0x180102310`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180102359`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180102359`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010236e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010236e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180102335`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180102335`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180102324`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180102324`

## string_xrefs

- `0x180102352`: `ntdll.dll`

## pseudocode

```c

```
