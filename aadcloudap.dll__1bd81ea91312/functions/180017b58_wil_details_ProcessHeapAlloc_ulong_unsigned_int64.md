# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180017b58`
- end: `0x180017bf6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180016a6c`
- `0x180016bc8`
- `0x1800190c0`
- `0x180019600`
- `0x18001b938`

## callees

- `0x180017b58`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017ba1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017ba1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017bb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017bb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017b6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017b6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017b7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017b7d`

## string_xrefs

- `0x180017b9a`: `ntdll.dll`

## pseudocode

```c

```
