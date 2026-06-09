# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000b470`
- end: `0x18000b50e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000aed0`
- `0x18000c8b0`
- `0x18000cc48`
- `0x1800122e0`
- `0x180013f50`

## callees

- `0x18000b470`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b484`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b484`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b495`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b495`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b4ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b4ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b4b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b4b9`

## string_xrefs

- `0x18000b4b2`: `ntdll.dll`

## pseudocode

```c

```
