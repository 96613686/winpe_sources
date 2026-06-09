# BthPdoDestroyExtension(PDO_EXTENSION *,uchar)

- ea: `0x14001f3f8`
- end: `0x14001f593`
- name: `?BthPdoDestroyExtension@@YAXPEAUPDO_EXTENSION@@E@Z`
- size: `411`
- prototype: `void __fastcall(struct PDO_EXTENSION *, unsigned __int8)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14002a5b8`
- `0x14012d90c`
- `0x14012e3e0`

## callees

- `0x140005b4c`
- `0x14001f3f8`
- `0x14002a354`
- `0x1401b9344`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001f567`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f567`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f48b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f48b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f52d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f52d`

## pseudocode

```c

```
