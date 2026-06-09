# RefsReleaseFcb(_IRP_CONTEXT *,_FCB *)

- ea: `0x140037820`
- end: `0x140037bb3`
- name: `?RefsReleaseFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z`
- size: `915`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _FCB *)`
- caller_count: `89`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140036800`
- `0x140036e90`
- `0x140094ea0`
- `0x14009a77c`
- `0x14009c3f0`
- `0x1400a2c60`
- `0x1400b5ba0`
- `0x1400daa80`
- `0x1400dc76c`
- `0x1400dd944`
- `0x1400ec8a4`
- `0x1400ee708`
- `0x1400f966c`
- `0x1400ffdb0`
- `0x1401019b0`
- `0x1401027f4`
- `0x140102884`
- `0x140103530`
- `0x1401098a0`
- `0x140113384`
- `0x14028f17c`
- `0x14028f944`
- `0x140293c2c`
- `0x140295fb0`
- `0x1402977e8`
- `0x140297d70`
- `0x1402986f0`
- `0x14029a0bc`
- `0x14029bf9c`
- `0x14029c90c`
- `0x14029cd7c`
- `0x14029ddd4`
- `0x1402a19c4`
- `0x1402a2e00`
- `0x1402a3f80`
- `0x1402a8c9c`
- `0x1402a9038`
- `0x1402ae1c8`
- `0x1402ae30c`
- `0x1402af580`
- `0x1402af8dc`
- `0x1402b39ec`
- `0x1402b4908`
- `0x1402b6e80`
- `0x1402b7ab0`
- `0x1402baa4c`
- `0x1402bc148`
- `0x1402be9b4`
- `0x1402bf1f8`
- `0x1402bf6b8`

## callees

- `0x140037820`
- `0x1400cedec`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140037ad0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140037ad0`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140037a1b`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140037a1b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140037a2a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140037a2a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140037a66`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140037a66`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140037a72`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140037a72`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140037908`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140037950`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140037908`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140037950`
- `ntoskrnl!ExReleaseFastResource` at `0x14003792f`
- `ntoskrnl!ExReleaseFastResource` at `0x140037984`
- `ntoskrnl!ExReleaseFastResource` at `0x14003792f`
- `ntoskrnl!ExReleaseFastResource` at `0x140037984`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037ba2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037ba2`

## pseudocode

```c

```
