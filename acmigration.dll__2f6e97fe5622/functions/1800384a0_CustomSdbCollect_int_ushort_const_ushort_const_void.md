# CustomSdbCollect(int *,ushort const *,ushort const *,void *)

- ea: `0x1800384a0`
- end: `0x1800385d1`
- name: `?CustomSdbCollect@@YAJPEAHPEBG1PEAX@Z`
- size: `305`
- prototype: `__int64 __fastcall(int *, const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callees

- `0x180037760`
- `0x1800377f0`
- `0x180037eb8`
- `0x1800384a0`
- `0x180039508`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800384c5`
- `KERNEL32!GetProcessHeap` at `0x1800384c5`
- `KERNEL32!HeapFree` at `0x1800385c0`
- `KERNEL32!HeapFree` at `0x1800385c0`

## string_xrefs

- `0x180038504`: `Failed to collect data on installed SDBs [0x%x]`
- `0x180038545`: `Failed to copy SDB files [0x%x]`

## pseudocode

```c

```
