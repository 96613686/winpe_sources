# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800250f8`
- end: `0x180025196`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180012868`
- `0x180013358`
- `0x1800152a0`
- `0x180015f7c`
- `0x180030170`
- `0x180030474`
- `0x180030a50`
- `0x180030de8`
- `0x18003eac4`

## callees

- `0x1800250f8`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025141`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025141`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025156`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025156`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002510c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002510c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002511d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002511d`

## string_xrefs

- `0x18002513a`: `ntdll.dll`

## pseudocode

```c

```
