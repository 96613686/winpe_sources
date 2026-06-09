# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18005697c`
- end: `0x180056a25`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180056318`
- `0x18005647c`
- `0x180057d24`
- `0x1800581d0`
- `0x180059490`

## callees

- `0x180053118`
- `0x18005697c`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800569d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800569d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800569a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800569a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056990`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056990`

## string_xrefs

- `0x1800569ca`: `ntdll.dll`

## pseudocode

```c

```
