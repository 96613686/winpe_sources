# AhcLockAcquireSharedWait

- ea: `0x140043f10`
- end: `0x140043f80`
- name: `AhcLockAcquireSharedWait`
- size: `112`
- prototype: `__int64 __fastcall(PERESOURCE Resource)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140024b68`
- `0x140043a7c`
- `0x140043bb0`

## callees

- `0x14003e364`
- `0x140043f10`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140043f1e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140043f1e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140043f4f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140043f4f`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x140043f2f`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x140043f2f`

## string_xrefs

- `0x140043f5b`: `Failed to acquire a lock supporting shared access`

## pseudocode

```c

```
