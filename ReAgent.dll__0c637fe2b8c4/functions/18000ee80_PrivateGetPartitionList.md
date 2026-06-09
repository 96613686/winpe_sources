# PrivateGetPartitionList

- ea: `0x18000ee80`
- end: `0x18000ef86`
- name: `PrivateGetPartitionList`
- size: `262`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180010010`
- `0x1800106d4`
- `0x1800193e8`
- `0x180019a90`
- `0x180031814`

## callees

- `0x1800059fc`
- `0x18000d67c`
- `0x18000ee80`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x18000ef72`
- `KERNEL32!TlsSetValue` at `0x18000ef72`
- `KERNEL32!HeapFree` at `0x18000ef5c`
- `KERNEL32!HeapFree` at `0x18000ef5c`
- `KERNEL32!HeapAlloc` at `0x18000eeca`
- `KERNEL32!HeapAlloc` at `0x18000eeca`
- `KERNEL32!GetProcessHeap` at `0x18000eeb6`
- `KERNEL32!GetProcessHeap` at `0x18000ef4e`
- `KERNEL32!GetProcessHeap` at `0x18000eeb6`
- `KERNEL32!GetProcessHeap` at `0x18000ef4e`
- `KERNEL32!TlsGetValue` at `0x18000eea1`
- `KERNEL32!TlsGetValue` at `0x18000eea1`

## string_xrefs

- `0x18000eed8`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18000ef1f`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`

## pseudocode

```c

```
