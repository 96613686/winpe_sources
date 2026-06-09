# CServicesManager::CheckStartDeviceUpdateNotificationTimer(void)

- ea: `0x1400b8e88`
- end: `0x1400b906e`
- name: `?CheckStartDeviceUpdateNotificationTimer@CServicesManager@@QEAAXXZ`
- size: `486`
- prototype: `void __fastcall(CServicesManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x140082dc4`
- `0x1400bb8cc`

## callees

- `0x140023cf0`
- `0x140025d38`
- `0x140026490`
- `0x140034e04`
- `0x1400b8e88`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400b9056`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b9056`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b8ead`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b8ead`

## pseudocode

```c

```
