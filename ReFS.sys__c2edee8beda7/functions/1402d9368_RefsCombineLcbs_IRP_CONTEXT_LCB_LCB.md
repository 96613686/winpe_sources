# RefsCombineLcbs(_IRP_CONTEXT &,_LCB *,_LCB *)

- ea: `0x1402d9368`
- end: `0x1402d9551`
- name: `?RefsCombineLcbs@@YAXAEAU_IRP_CONTEXT@@PEAU_LCB@@1@Z`
- size: `489`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _LCB *, struct _LCB *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14031fa40`

## callees

- `0x1400a2890`
- `0x1400cedec`
- `0x1402d9368`
- `0x140322730`
- `0x140328080`
- `0x14032a5d0`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d9397`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d9478`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d9397`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402d9478`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d93a7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d9488`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d93a7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402d9488`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d944a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d94ed`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d944a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402d94ed`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d9456`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d94f9`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d9456`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402d94f9`

## pseudocode

```c

```
