# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000b7e8`
- end: `0x18000b886`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009f58`
- `0x18000a6f0`
- `0x18000acc0`
- `0x18000bcc4`
- `0x180011864`
- `0x18001d754`

## callees

- `0x18000b7e8`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b846`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b846`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b831`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b831`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b80d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b80d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7fc`

## string_xrefs

- `0x18000b82a`: `ntdll.dll`

## pseudocode

```c

```
