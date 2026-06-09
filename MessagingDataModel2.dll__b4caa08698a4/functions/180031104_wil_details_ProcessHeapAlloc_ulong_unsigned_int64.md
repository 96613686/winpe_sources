# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180031104`
- end: `0x1800311a2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180030f98`
- `0x180031430`
- `0x1800315a8`
- `0x18008c658`
- `0x18008e674`

## callees

- `0x180031104`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031162`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031162`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003114d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003114d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031118`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031118`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031129`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031129`

## string_xrefs

- `0x180031146`: `ntdll.dll`

## pseudocode

```c

```
