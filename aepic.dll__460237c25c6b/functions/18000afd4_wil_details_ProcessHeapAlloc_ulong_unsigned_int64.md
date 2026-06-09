# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000afd4`
- end: `0x18000b072`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000aa0c`
- `0x18000ab3c`
- `0x18000c420`
- `0x18000c8a4`
- `0x18000dbbc`

## callees

- `0x18000afd4`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b01d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b01d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b032`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b032`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aff9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aff9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000afe8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000afe8`

## string_xrefs

- `0x18000b016`: `ntdll.dll`

## pseudocode

```c

```
