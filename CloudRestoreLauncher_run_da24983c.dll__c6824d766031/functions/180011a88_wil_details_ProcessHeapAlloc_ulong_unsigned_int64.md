# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180011a88`
- end: `0x180011b1e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010cdc`
- `0x180010d80`
- `0x1800117a8`
- `0x180011f84`
- `0x18001231c`
- `0x180018c18`
- `0x18001d924`

## callees

- `0x18000f3f4`
- `0x180011a88`
- `0x18012d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180011ad1`
- `KERNEL32!GetModuleHandleW` at `0x180011ad1`
- `KERNEL32!GetProcessHeap` at `0x180011a9c`
- `KERNEL32!GetProcessHeap` at `0x180011a9c`
- `KERNEL32!HeapAlloc` at `0x180011aad`
- `KERNEL32!HeapAlloc` at `0x180011aad`

## string_xrefs

- `0x180011aca`: `ntdll.dll`

## pseudocode

```c

```
