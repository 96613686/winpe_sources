# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000c670`
- end: `0x18000c70e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000bfc0`
- `0x18000c114`
- `0x1800117b4`
- `0x180011d48`
- `0x180014524`

## callees

- `0x18000c670`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000c6ce`
- `KERNEL32!GetProcAddress` at `0x18000c6ce`
- `KERNEL32!GetModuleHandleW` at `0x18000c6b9`
- `KERNEL32!GetModuleHandleW` at `0x18000c6b9`
- `KERNEL32!HeapAlloc` at `0x18000c695`
- `KERNEL32!HeapAlloc` at `0x18000c695`
- `KERNEL32!GetProcessHeap` at `0x18000c684`
- `KERNEL32!GetProcessHeap` at `0x18000c684`

## string_xrefs

- `0x18000c6b2`: `ntdll.dll`

## pseudocode

```c

```
