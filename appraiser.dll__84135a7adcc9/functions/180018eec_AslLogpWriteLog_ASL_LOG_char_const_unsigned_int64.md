# AslLogpWriteLog(_ASL_LOG *,char const *,unsigned __int64)

- ea: `0x180018eec`
- end: `0x1800190ea`
- name: `?AslLogpWriteLog@@YAXPEAU_ASL_LOG@@PEBD_K@Z`
- size: `510`
- prototype: `void(struct _ASL_LOG *, const char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180019990`

## callees

- `0x1800092dc`
- `0x18000a927`
- `0x180018c30`
- `0x180018e28`
- `0x180018eec`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180019020`
- `ntdll!RtlLeaveCriticalSection` at `0x1800190d3`
- `ntdll!RtlLeaveCriticalSection` at `0x180019020`
- `ntdll!RtlLeaveCriticalSection` at `0x1800190d3`
- `ntdll!RtlEnterCriticalSection` at `0x180018f1b`
- `ntdll!RtlEnterCriticalSection` at `0x18001909d`
- `ntdll!RtlEnterCriticalSection` at `0x180018f1b`
- `ntdll!RtlEnterCriticalSection` at `0x18001909d`
- `ntdll!RtlReAllocateHeap` at `0x180018fc6`
- `ntdll!RtlReAllocateHeap` at `0x180018fc6`
- `ntdll!RtlAllocateHeap` at `0x180018fa6`
- `ntdll!RtlAllocateHeap` at `0x180018fa6`
- `KERNEL32!OutputDebugStringA` at `0x18001904f`
- `KERNEL32!OutputDebugStringA` at `0x18001904f`
- `KERNEL32!WriteFile` at `0x18001908b`
- `KERNEL32!WriteFile` at `0x18001908b`
- `KERNEL32!GetStdHandle` at `0x180019066`
- `KERNEL32!GetStdHandle` at `0x180019066`

## pseudocode

```c

```
