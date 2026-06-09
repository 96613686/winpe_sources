# CmsBPlusTable::MakeBoundSetLogDurable(CmsTransactionContext *,SmsWritePlan *)

- ea: `0x1400c4b60`
- end: `0x1400c4e83`
- name: `?MakeBoundSetLogDurable@CmsBPlusTable@@SAXPEAVCmsTransactionContext@@PEAUSmsWritePlan@@@Z`
- size: `803`
- prototype: `void __fastcall(struct CmsTransactionContext *, struct SmsWritePlan *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140147c6c`

## callees

- `0x1400c4b60`
- `0x1400c77f0`
- `0x1400c7bf0`
- `0x1400c7fcc`
- `0x1401f40a0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400c4d03`
- `ntoskrnl!KeSetEvent` at `0x1400c4d03`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c4c49`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c4d7d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c4dd8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c4c49`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c4d7d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c4dd8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c4d1a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c4e11`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c4d1a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c4e11`
- `ntoskrnl!KeClearEvent` at `0x1400c4c33`
- `ntoskrnl!KeClearEvent` at `0x1400c4c33`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c4d3f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c4d3f`
- `ntoskrnl!KeInitializeEvent` at `0x1400c4c18`
- `ntoskrnl!KeInitializeEvent` at `0x1400c4c18`

## pseudocode

```c

```
