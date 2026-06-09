# HCI_AddStoredDeviceToList(HCI_INTERFACE *,_BTH_DEVICE_INFO_V3 *,_HCI_PHY_TYPE,DibStoreInfoType)

- ea: `0x1400515b0`
- end: `0x14005254c`
- name: `?HCI_AddStoredDeviceToList@@YAEPEAUHCI_INTERFACE@@PEAU_BTH_DEVICE_INFO_V3@@W4_HCI_PHY_TYPE@@W4DibStoreInfoType@@@Z`
- size: `3996`
- prototype: ``
- caller_count: `1`
- callee_count: `47`
- tags: ``

## callers

- `0x140064d4c`

## callees

- `0x14000113c`
- `0x140001af4`
- `0x1400043d0`
- `0x140005504`
- `0x140005608`
- `0x140005748`
- `0x140005b4c`
- `0x14000764c`
- `0x14000bdb8`
- `0x140013820`
- `0x1400515b0`
- `0x140052db8`
- `0x140055238`
- `0x140055874`
- `0x1400592e4`
- `0x1400594d8`
- `0x14005a290`
- `0x14005b478`
- `0x14005efc4`
- `0x14005eff8`
- `0x14005f234`
- `0x14005f448`
- `0x14005fc60`
- `0x14005fcf4`
- `0x14005fe30`
- `0x14006405c`
- `0x1400640fc`
- `0x14006415c`
- `0x140078444`
- `0x14014d70c`
- `0x140155dd0`
- `0x14015ce38`
- `0x140161a44`
- `0x140161d7c`
- `0x14016319c`
- `0x140165540`
- `0x140165e60`
- `0x1401bec04`
- `0x1401bf730`
- `0x1401bfdb8`
- `0x1401c005c`
- `0x1401e629c`
- `0x1401e76ec`
- `0x1401f965c`
- `0x1401fa610`
- `0x1401fb804`
- `0x140206478`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140052216`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005225d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140052292`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005230d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140052216`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005225d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140052292`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005230d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005220a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140052251`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140052286`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140052301`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005220a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140052251`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140052286`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140052301`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140051ac3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140051b03`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400522db`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140051ac3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140051b03`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400522db`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140051ab0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140051af0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400522cc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140051ab0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140051af0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400522cc`
- `ntoskrnl!_ui64tow_s` at `0x140051974`
- `ntoskrnl!_ui64tow_s` at `0x140051974`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140051b16`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140051b16`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400521d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400521d9`

## string_xrefs

- `0x140051647`: `Adding secondary linked device from store is not supported`

## pseudocode

```c

```
