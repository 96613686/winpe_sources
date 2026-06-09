# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140008ca8`
- end: `0x140008d46`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140006298`
- `0x140006668`
- `0x140007790`
- `0x14000aab4`
- `0x14000ca4c`

## callees

- `0x140008ca8`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008cf1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008cf1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008d06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008d06`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008ccd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008ccd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008cbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008cbc`

## string_xrefs

- `0x140008cea`: `ntdll.dll`

## pseudocode

```c

```
