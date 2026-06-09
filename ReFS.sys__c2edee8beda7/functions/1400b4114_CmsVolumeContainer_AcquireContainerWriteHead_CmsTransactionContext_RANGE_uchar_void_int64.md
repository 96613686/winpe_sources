# CmsVolumeContainer::AcquireContainerWriteHead(CmsTransactionContext *,_RANGE,uchar,void * *,__int64 *)

- ea: `0x1400b4114`
- end: `0x1400b46f6`
- name: `?AcquireContainerWriteHead@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@U_RANGE@@EPEAPEAXPEA_J@Z`
- size: `1506`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x1400b4114`
- `0x1400d2024`
- `0x14013802c`

## callees

- `0x1400103b0`
- `0x140079da0`
- `0x140088db0`
- `0x1400b4114`
- `0x1400d1634`
- `0x1400fc8a4`
- `0x14013bea0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b4453`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b4541`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b4453`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b4541`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b44f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b457d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b46ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b44f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b457d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b46ab`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b451b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b451b`
- `ntoskrnl!KeInitializeEvent` at `0x1400b42a2`
- `ntoskrnl!KeInitializeEvent` at `0x1400b42a2`
- `HAL!KeQueryPerformanceCounter` at `0x1400b42d1`
- `HAL!KeQueryPerformanceCounter` at `0x1400b4636`
- `HAL!KeQueryPerformanceCounter` at `0x1400b42d1`
- `HAL!KeQueryPerformanceCounter` at `0x1400b4636`

## pseudocode

```c

```
