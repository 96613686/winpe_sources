# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18005cb40`
- end: `0x18005cbde`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180054aac`
- `0x18005c674`
- `0x18005c7ac`
- `0x18005d4f0`
- `0x18005d974`

## callees

- `0x18005cb40`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005cb89`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005cb89`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005cb9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005cb9e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005cb65`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005cb65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005cb54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005cb54`

## string_xrefs

- `0x18005cb82`: `ntdll.dll`

## pseudocode

```c

```
