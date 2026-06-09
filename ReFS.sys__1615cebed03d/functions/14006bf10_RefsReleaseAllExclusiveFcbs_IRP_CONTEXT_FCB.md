# RefsReleaseAllExclusiveFcbs(_IRP_CONTEXT &,_FCB *)

- ea: `0x14006bf10`
- end: `0x14006c391`
- name: `?RefsReleaseAllExclusiveFcbs@@YAXAEAU_IRP_CONTEXT@@PEAU_FCB@@@Z`
- size: `1153`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _FCB *)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1402ae30c`
- `0x1403058c0`
- `0x140333e98`
- `0x140334b60`
- `0x14033de50`

## callees

- `0x14006bf10`
- `0x1400cedec`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006c256`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006c256`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14006c194`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14006c194`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14006c1a3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14006c1a3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14006c1e3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14006c1e3`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14006c1ef`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14006c1ef`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14006c055`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14006c0b0`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14006c055`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14006c0b0`
- `ntoskrnl!ExReleaseFastResource` at `0x14006c07c`
- `ntoskrnl!ExReleaseFastResource` at `0x14006c0ec`
- `ntoskrnl!ExReleaseFastResource` at `0x14006c07c`
- `ntoskrnl!ExReleaseFastResource` at `0x14006c0ec`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006c380`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006c380`

## pseudocode

```c

```
