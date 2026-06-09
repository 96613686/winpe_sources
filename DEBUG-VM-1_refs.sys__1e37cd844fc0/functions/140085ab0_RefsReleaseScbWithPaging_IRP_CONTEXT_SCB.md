# RefsReleaseScbWithPaging(_IRP_CONTEXT *,_SCB *)

- ea: `0x140085ab0`
- end: `0x140085ee5`
- name: `?RefsReleaseScbWithPaging@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB@@@Z`
- size: `1077`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _SCB *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14029bf9c`
- `0x140300990`
- `0x140319010`
- `0x14033c460`

## callees

- `0x140085ab0`
- `0x1400cedec`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140085e00`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140085e00`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140085d4b`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140085d4b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140085d5a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140085d5a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140085d96`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140085d96`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140085da2`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140085da2`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140085baf`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140085baf`
- `ntoskrnl!ExReleaseFastResource` at `0x140085b18`
- `ntoskrnl!ExReleaseFastResource` at `0x140085bd6`
- `ntoskrnl!ExReleaseFastResource` at `0x140085c8c`
- `ntoskrnl!ExReleaseFastResource` at `0x140085b18`
- `ntoskrnl!ExReleaseFastResource` at `0x140085bd6`
- `ntoskrnl!ExReleaseFastResource` at `0x140085c8c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140085b26`
- `ntoskrnl!ExReleaseResourceLite` at `0x140085ed4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140085b26`
- `ntoskrnl!ExReleaseResourceLite` at `0x140085ed4`

## pseudocode

```c

```
