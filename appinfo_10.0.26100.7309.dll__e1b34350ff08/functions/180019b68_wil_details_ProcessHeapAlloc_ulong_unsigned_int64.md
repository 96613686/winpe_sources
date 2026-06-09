# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180019b68`
- end: `0x180019c1f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b2b0`
- `0x18000b520`
- `0x1800139d0`
- `0x18002027c`
- `0x1800203dc`
- `0x180021980`
- `0x180021bf0`

## callees

- `0x180019b68`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019bbd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019bbd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019bd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019bd8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019b93`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019b93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019b7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019b7c`

## string_xrefs

- `0x180019bb6`: `ntdll.dll`

## pseudocode

```c

```
