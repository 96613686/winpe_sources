# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002fb04`
- end: `0x18002fba2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180019f94`
- `0x18002f698`
- `0x18002f7c8`
- `0x1800307e4`
- `0x180030a0c`

## callees

- `0x18002fb04`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fb18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fb18`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002fb29`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002fb29`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fb62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fb62`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002fb4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002fb4d`

## string_xrefs

- `0x18002fb46`: `ntdll.dll`

## pseudocode

```c

```
