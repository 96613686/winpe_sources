# RefsReleaseAllResources(_IRP_CONTEXT *)

- ea: `0x14000c9b0`
- end: `0x14000cf38`
- name: `?RefsReleaseAllResources@@YAXPEAU_IRP_CONTEXT@@@Z`
- size: `1416`
- prototype: `void __fastcall(struct _IRP_CONTEXT *)`
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000c3c0`
- `0x14000d0c0`
- `0x140293570`
- `0x1402b0838`
- `0x14030bca0`
- `0x14031f390`
- `0x140324914`
- `0x140332720`

## callees

- `0x14000c9b0`
- `0x1400cedec`
- `0x140323140`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000cc26`
- `ntoskrnl!KeSetEvent` at `0x14000cc26`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000cdca`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000cdca`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000cbdb`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000cd0d`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000cbdb`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000cd0d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000cbea`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000cd1c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000cbea`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000cd1c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000cc36`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000cd5a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000cc36`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000cd5a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000cc42`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000cd66`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000cc42`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000cd66`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14000cb0d`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14000cb0d`
- `ntoskrnl!ExReleaseFastResource` at `0x14000cb30`
- `ntoskrnl!ExReleaseFastResource` at `0x14000cb8c`
- `ntoskrnl!ExReleaseFastResource` at `0x14000cc94`
- `ntoskrnl!ExReleaseFastResource` at `0x14000cf0b`
- `ntoskrnl!ExReleaseFastResource` at `0x14000cb30`
- `ntoskrnl!ExReleaseFastResource` at `0x14000cb8c`
- `ntoskrnl!ExReleaseFastResource` at `0x14000cc94`
- `ntoskrnl!ExReleaseFastResource` at `0x14000cf0b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cdf2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cf27`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cdf2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cf27`

## pseudocode

```c

```
