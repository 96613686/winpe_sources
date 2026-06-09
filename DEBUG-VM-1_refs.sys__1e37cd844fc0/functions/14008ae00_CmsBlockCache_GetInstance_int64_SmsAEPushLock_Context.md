# CmsBlockCache::GetInstance(__int64,SmsAEPushLock::Context &)

- ea: `0x14008ae00`
- end: `0x14008b057`
- name: `?GetInstance@CmsBlockCache@@AEAAPEAU_SmsCacheInstance@@_JAEAUContext@SmsAEPushLock@@@Z`
- size: `599`
- prototype: `struct _SmsCacheInstance *__fastcall(CmsBlockCache *__hidden this, __int64, struct SmsAEPushLock::Context *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001712c`

## callees

- `0x14008ae00`
- `0x1400ac390`
- `0x1401f4100`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14008af23`
- `ntoskrnl!ExAllocatePool2` at `0x14008af98`
- `ntoskrnl!ExAllocatePool2` at `0x14008af23`
- `ntoskrnl!ExAllocatePool2` at `0x14008af98`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x14008ae48`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x14008ae48`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14008aea1`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14008b044`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14008aea1`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14008b044`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x14008aec1`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x14008aec1`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14008aee7`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14008aff4`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14008b02e`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14008aee7`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14008aff4`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14008b02e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b007`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201166`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201188`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b007`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201166`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201188`

## pseudocode

```c

```
