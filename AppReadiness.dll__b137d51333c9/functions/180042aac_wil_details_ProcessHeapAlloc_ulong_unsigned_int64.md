# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180042aac`
- end: `0x180042b42`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003b200`
- `0x18004261c`
- `0x18004274c`
- `0x1800435e0`
- `0x180043a70`

## callees

- `0x180040928`
- `0x180042aac`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180042af5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180042af5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042ad1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042ad1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042ac0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042ac0`

## string_xrefs

- `0x180042aee`: `ntdll.dll`

## pseudocode

```c

```
