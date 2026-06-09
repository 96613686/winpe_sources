# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180041e88`
- end: `0x180041f26`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180035084`
- `0x180041ce4`
- `0x180042280`
- `0x180042618`
- `0x1800609bc`

## callees

- `0x180041e88`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041ee6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041ee6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180041ed1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180041ed1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180041ead`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180041ead`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041e9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041e9c`

## string_xrefs

- `0x180041eca`: `ntdll.dll`

## pseudocode

```c

```
