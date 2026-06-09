# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140061154`
- end: `0x1400611f2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140060f54`
- `0x1400619b0`
- `0x140061d48`
- `0x1400622c0`
- `0x140089320`

## callees

- `0x140061154`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400611b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400611b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14006119d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14006119d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140061179`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140061179`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140061168`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140061168`

## string_xrefs

- `0x140061196`: `ntdll.dll`

## pseudocode

```c

```
