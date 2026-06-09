# CmsBPlusTable::BuildWritePlanListsParallel(CmsTransactionContext *,CmsHashTable *,ulong,ulong,SmsWritePlan *)

- ea: `0x140052db0`
- end: `0x1400539e3`
- name: `?BuildWritePlanListsParallel@CmsBPlusTable@@SAXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAUSmsWritePlan@@@Z`
- size: `3123`
- prototype: `void __usercall(struct CmsTransactionContext *@<rcx>, struct CmsHashTable *this@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, struct SmsWritePlan *)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x140016440`
- `0x14003b6a0`
- `0x14004c7a0`
- `0x140051e70`
- `0x140052db0`
- `0x140053fe0`
- `0x140068ef0`
- `0x14006caf0`
- `0x140088ce0`
- `0x1400a2af0`
- `0x1400cfe9c`
- `0x1400d25c8`
- `0x1401f3fc0`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x14005344d`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x14005373c`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x14005344d`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x14005373c`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140053518`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14005378c`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140053518`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14005378c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400532d5`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400535fd`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400532d5`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400535fd`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005312b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400535bf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005312b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400535bf`

## pseudocode

```c

```
