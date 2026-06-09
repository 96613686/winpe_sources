# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180074634`
- end: `0x1800746d2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180017e64`
- `0x180032f28`
- `0x180036658`
- `0x180073c8c`
- `0x180080fec`

## callees

- `0x180074634`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180074692`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180074692`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007467d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007467d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074659`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074659`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074648`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074648`

## string_xrefs

- `0x180074676`: `ntdll.dll`

## pseudocode

```c

```
