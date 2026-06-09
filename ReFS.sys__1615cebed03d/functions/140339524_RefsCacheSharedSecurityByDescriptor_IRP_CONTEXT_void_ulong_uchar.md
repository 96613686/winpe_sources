# RefsCacheSharedSecurityByDescriptor(_IRP_CONTEXT *,void *,ulong,uchar)

- ea: `0x140339524`
- end: `0x140339677`
- name: `?RefsCacheSharedSecurityByDescriptor@@YAPEAU_SHARED_SECURITY@@PEAU_IRP_CONTEXT@@PEAXKE@Z`
- size: `339`
- prototype: `struct _SHARED_SECURITY *__fastcall(struct _IRP_CONTEXT *, PSECURITY_DESCRIPTOR SecurityDescriptor, size_t Size, unsigned __int8)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400d01b0`
- `0x140291234`
- `0x1402d5d14`
- `0x1403063e0`
- `0x140330f04`

## callees

- `0x1400ffdb0`
- `0x14028c13c`
- `0x1402d5970`
- `0x1402d59b4`
- `0x140302e10`
- `0x140339524`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x140339576`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140339618`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140344d96`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140339576`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140339618`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140344d96`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140339589`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033962b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140344da9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140339589`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033962b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140344da9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403395cd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140339657`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140344df2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403395cd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140339657`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140344df2`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403395d9`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140339663`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140344dfe`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403395d9`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140339663`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140344dfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344dc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344dc8`

## pseudocode

```c

```
