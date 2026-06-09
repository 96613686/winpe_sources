# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180030180`
- end: `0x180030237`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001adb4`
- `0x180025b64`
- `0x18002fd50`
- `0x18002fe84`
- `0x180030a34`
- `0x180030ee0`

## callees

- `0x180030180`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800301f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800301f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800301d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800301d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030194`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030194`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800301ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800301ab`

## string_xrefs

- `0x1800301ce`: `ntdll.dll`

## pseudocode

```c

```
