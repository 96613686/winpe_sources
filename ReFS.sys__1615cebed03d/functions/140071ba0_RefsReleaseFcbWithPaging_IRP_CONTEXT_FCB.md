# RefsReleaseFcbWithPaging(_IRP_CONTEXT *,_FCB *)

- ea: `0x140071ba0`
- end: `0x140071fde`
- name: `?RefsReleaseFcbWithPaging@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z`
- size: `1086`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _FCB *)`
- caller_count: `21`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400dbe04`
- `0x1400eb52c`
- `0x1400f01fc`
- `0x1400f6650`
- `0x1400fbdd8`
- `0x1400ffd64`
- `0x1401098a0`
- `0x140298564`
- `0x1402b0518`
- `0x1402b412c`
- `0x1402ba50c`
- `0x1402c3664`
- `0x1402c90a0`
- `0x1402ff3f0`
- `0x140300990`
- `0x1403058c0`
- `0x14030d820`
- `0x140327af0`
- `0x14032afc0`
- `0x1403387e8`
- `0x14033c460`

## callees

- `0x140071ba0`
- `0x1400cedec`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140071ed7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140071ed7`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140071e22`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140071e22`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140071e31`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140071e31`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140071e6d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140071e6d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140071e79`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140071e79`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140071c9b`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140071c9b`
- `ntoskrnl!ExReleaseFastResource` at `0x140071c04`
- `ntoskrnl!ExReleaseFastResource` at `0x140071cc2`
- `ntoskrnl!ExReleaseFastResource` at `0x140071d78`
- `ntoskrnl!ExReleaseFastResource` at `0x140071c04`
- `ntoskrnl!ExReleaseFastResource` at `0x140071cc2`
- `ntoskrnl!ExReleaseFastResource` at `0x140071d78`
- `ntoskrnl!ExReleaseResourceLite` at `0x140071c12`
- `ntoskrnl!ExReleaseResourceLite` at `0x140071fcd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140071c12`
- `ntoskrnl!ExReleaseResourceLite` at `0x140071fcd`

## pseudocode

```c

```
