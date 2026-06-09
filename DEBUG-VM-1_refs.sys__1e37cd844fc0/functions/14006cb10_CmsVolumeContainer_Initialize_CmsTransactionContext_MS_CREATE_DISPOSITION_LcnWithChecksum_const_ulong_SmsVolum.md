# CmsVolumeContainer::Initialize(CmsTransactionContext *,_MS_CREATE_DISPOSITION,LcnWithChecksum * * const,ulong,_SmsVolumeContainerKsrContext *)

- ea: `0x14006cb10`
- end: `0x14006d7c5`
- name: `?Initialize@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@W4_MS_CREATE_DISPOSITION@@QEAPEAULcnWithChecksum@@KPEAU_SmsVolumeContainerKsrContext@@@Z`
- size: `3253`
- prototype: `int __high(struct CmsTransactionContext *, enum _MS_CREATE_DISPOSITION, struct LcnWithChecksum **const, unsigned int, struct _SmsVolumeContainerKsrContext *)`
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x140124ab4`

## callees

- `0x1400130c0`
- `0x1400147e0`
- `0x140016440`
- `0x14002b680`
- `0x14005bed0`
- `0x14006c91c`
- `0x14006cb10`
- `0x14006d7cc`
- `0x14006dfec`
- `0x14008f5f0`
- `0x140097ba0`
- `0x1400cf510`
- `0x140122940`
- `0x14013c558`
- `0x1401f3fc0`
- `0x1401f40a0`
- `0x1401f4100`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1401fe825`
- `ntoskrnl!DbgPrintEx` at `0x1401fe897`
- `ntoskrnl!DbgPrintEx` at `0x1401fe825`
- `ntoskrnl!DbgPrintEx` at `0x1401fe897`
- `ntoskrnl!KdDebuggerEnabled` at `0x14006d5ec`
- `ntoskrnl!KdDebuggerEnabled` at `0x14006d602`
- `ntoskrnl!KdDebuggerEnabled` at `0x14006d658`
- `ntoskrnl!ExAllocatePool2` at `0x14006cbbd`
- `ntoskrnl!ExAllocatePool2` at `0x14006cc40`
- `ntoskrnl!ExAllocatePool2` at `0x14006ccec`
- `ntoskrnl!ExAllocatePool2` at `0x14006d27f`
- `ntoskrnl!ExAllocatePool2` at `0x1401fe74a`
- `ntoskrnl!ExAllocatePool2` at `0x14006cbbd`
- `ntoskrnl!ExAllocatePool2` at `0x14006cc40`
- `ntoskrnl!ExAllocatePool2` at `0x14006ccec`
- `ntoskrnl!ExAllocatePool2` at `0x14006d27f`
- `ntoskrnl!ExAllocatePool2` at `0x1401fe74a`
- `ntoskrnl!RtlCreateHashTableEx` at `0x14006cbfd`
- `ntoskrnl!RtlCreateHashTableEx` at `0x14006cbfd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d2d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d2d7`
- `HAL!KeQueryPerformanceCounter` at `0x14006d713`
- `HAL!KeQueryPerformanceCounter` at `0x1401fe7f5`
- `HAL!KeQueryPerformanceCounter` at `0x1401fe858`
- `HAL!KeQueryPerformanceCounter` at `0x14006d713`
- `HAL!KeQueryPerformanceCounter` at `0x1401fe7f5`
- `HAL!KeQueryPerformanceCounter` at `0x1401fe858`

## pseudocode

```c

```
