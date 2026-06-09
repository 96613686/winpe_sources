# RefsOpenFileHighLevel

- ea: `0x14033c460`
- end: `0x14033d7ab`
- name: `RefsOpenFileHighLevel`
- size: `4939`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, __int64, __int64, __int16, struct _CREATE_CONTEXT *, __int64)`
- caller_count: `1`
- callee_count: `50`
- tags: ``

## callers

- `0x14030d820`

## callees

- `0x140037820`
- `0x14004ffc0`
- `0x140071500`
- `0x140071ba0`
- `0x140076ad0`
- `0x140085ab0`
- `0x1400862c0`
- `0x14008ad80`
- `0x14008b7b0`
- `0x14008ec60`
- `0x140093bc0`
- `0x140095370`
- `0x14009df40`
- `0x14009e59c`
- `0x14009e670`
- `0x1400bdcd0`
- `0x1400d0fd8`
- `0x1400e6524`
- `0x1401016c4`
- `0x14011b524`
- `0x1401f3f92`
- `0x1401f3fc0`
- `0x1401f4920`
- `0x14028e8a4`
- `0x140293c2c`
- `0x140298464`
- `0x140299cf0`
- `0x14029b80c`
- `0x140301fb0`
- `0x1403025b0`
- `0x140302e10`
- `0x140303400`
- `0x140303818`
- `0x1403078a0`
- `0x140309cb0`
- `0x1403141f0`
- `0x140322310`
- `0x140322730`
- `0x140322820`
- `0x140322ec0`
- `0x140323140`
- `0x140329e20`
- `0x14032a5d0`
- `0x14032ac50`
- `0x14032b300`
- `0x1403349e4`
- `0x1403378e0`
- `0x14033afa0`
- `0x14033c460`
- `0x14033d7c0`

## import_xrefs

- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14033c7ae`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14033c88c`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14033c8c5`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14033d35f`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14034614d`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14034618a`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1403461f0`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14033c7ae`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14033c88c`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14033c8c5`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14033d35f`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14034614d`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14034618a`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1403461f0`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033c97c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033cb26`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033d3ab`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140346262`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033c97c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033cb26`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033d3ab`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140346262`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033c98b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033cb35`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033d3ba`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140346271`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033c98b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033cb35`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033d3ba`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140346271`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033c9b9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033cb63`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033d3e6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403462a5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033c9b9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033cb63`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033d3e6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403462a5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033c9c5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033cb6f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033d3f2`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403462b1`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033c9c5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033cb6f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033d3f2`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403462b1`
- `ntoskrnl!ExReleaseFastResource` at `0x14033c7cb`
- `ntoskrnl!ExReleaseFastResource` at `0x14033c8a9`
- `ntoskrnl!ExReleaseFastResource` at `0x14033c8e2`
- `ntoskrnl!ExReleaseFastResource` at `0x14033d37c`
- `ntoskrnl!ExReleaseFastResource` at `0x14034616a`
- `ntoskrnl!ExReleaseFastResource` at `0x1403461a7`
- `ntoskrnl!ExReleaseFastResource` at `0x14034620d`
- `ntoskrnl!ExReleaseFastResource` at `0x14033c7cb`
- `ntoskrnl!ExReleaseFastResource` at `0x14033c8a9`
- `ntoskrnl!ExReleaseFastResource` at `0x14033c8e2`
- `ntoskrnl!ExReleaseFastResource` at `0x14033d37c`
- `ntoskrnl!ExReleaseFastResource` at `0x14034616a`
- `ntoskrnl!ExReleaseFastResource` at `0x1403461a7`
- `ntoskrnl!ExReleaseFastResource` at `0x14034620d`

## string_xrefs

- `0x14033c580`: `Create.c`
- `0x14033d334`: `Create.c`
- `0x14033d521`: `Create.c`
- `0x14033d594`: `Create.c`
- `0x14033d611`: `Create.c`
- `0x14033d6fc`: `Create.c`
- `0x14033d765`: `Create.c`

## pseudocode

```c

```
