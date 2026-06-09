# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000f164`
- end: `0x18000f202`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800159c0`
- `0x18001eae4`
- `0x18001ec14`
- `0x18001fae0`
- `0x18001ff70`

## callees

- `0x18000f164`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f1ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f1ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f1c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f1c2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f189`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f189`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f178`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f178`

## string_xrefs

- `0x18000f1a6`: `ntdll.dll`

## pseudocode

```c

```
