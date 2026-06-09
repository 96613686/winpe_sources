# RefsPurgeKernelEA(_IRP_CONTEXT *,_FCB *)

- ea: `0x140036800`
- end: `0x140036e89`
- name: `?RefsPurgeKernelEA@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z`
- size: `1673`
- prototype: `unsigned __int8 __fastcall(struct _IRP_CONTEXT *, struct _FCB *)`
- caller_count: `2`
- callee_count: `22`
- tags: ``

## callers

- `0x14009c3f0`
- `0x140295afc`

## callees

- `0x140028c20`
- `0x140029990`
- `0x140029a60`
- `0x14002b870`
- `0x140036670`
- `0x140036800`
- `0x140037820`
- `0x140048010`
- `0x140076ad0`
- `0x1400862c0`
- `0x1400d0fd8`
- `0x1400ebde0`
- `0x1401f3fc0`
- `0x1401f4100`
- `0x1401f4400`
- `0x14029d5e8`
- `0x1402a26e0`
- `0x140302e10`
- `0x140306290`
- `0x140315f30`
- `0x14032f6b0`
- `0x140333dd0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14003692e`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003692e`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140036906`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140036906`
- `ntoskrnl!RtlPrefixString` at `0x140036c18`
- `ntoskrnl!RtlPrefixString` at `0x140036c18`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140036d16`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140036d16`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140036d26`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140036d26`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036d3e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036d3e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140036d4a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140036d4a`

## pseudocode

```c

```
