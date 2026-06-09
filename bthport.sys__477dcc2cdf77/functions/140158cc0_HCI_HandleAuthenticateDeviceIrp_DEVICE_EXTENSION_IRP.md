# HCI_HandleAuthenticateDeviceIrp(DEVICE_EXTENSION *,_IRP *)

- ea: `0x140158cc0`
- end: `0x140159881`
- name: `?HCI_HandleAuthenticateDeviceIrp@@YAJPEAUDEVICE_EXTENSION@@PEAU_IRP@@@Z`
- size: `3009`
- prototype: `__int64 __fastcall(struct DEVICE_EXTENSION *, PIRP Irp)`
- caller_count: `1`
- callee_count: `25`
- tags: `loader_planting`

## callers

- `0x14001e010`

## callees

- `0x140004368`
- `0x140005608`
- `0x140005690`
- `0x140005748`
- `0x140005b4c`
- `0x140010bf8`
- `0x14001d1c0`
- `0x14001dc88`
- `0x140028938`
- `0x140041f28`
- `0x140058f78`
- `0x1400594d8`
- `0x14005f234`
- `0x140065b40`
- `0x1400a7fb4`
- `0x1400af954`
- `0x14014fe7c`
- `0x140158760`
- `0x140158cc0`
- `0x140161d7c`
- `0x140162008`
- `0x140162f44`
- `0x140165108`
- `0x140165540`
- `0x1401f2b50`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1401596c2`
- `ntoskrnl!ObfDereferenceObject` at `0x1401596c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015921a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140159492`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401594e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015921a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140159492`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401594e3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14015920e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140159486`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401594d7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14015920e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140159486`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401594d7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401591eb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401593bb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401591eb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401593bb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401591d2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401593a8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401591d2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401593a8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140158f74`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140158f74`
- `ntoskrnl!IoGetRequestorProcess` at `0x140158e76`
- `ntoskrnl!IoGetRequestorProcess` at `0x140158e76`
- `ntoskrnl!SeLocateProcessImageName` at `0x140158e8e`
- `ntoskrnl!SeLocateProcessImageName` at `0x140158e8e`
- `ntoskrnl!ExEventObjectType` at `0x140158f4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140159726`
- `ntoskrnl!ExFreePoolWithTag` at `0x140159726`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140159531`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140159531`
- `ntoskrnl!KeReleaseSpinLock` at `0x140159580`
- `ntoskrnl!KeReleaseSpinLock` at `0x140159580`

## pseudocode

```c

```
