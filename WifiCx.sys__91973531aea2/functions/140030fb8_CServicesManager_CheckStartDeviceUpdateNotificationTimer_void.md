# CServicesManager::CheckStartDeviceUpdateNotificationTimer(void)

- ea: `0x140030fb8`
- end: `0x1400311b4`
- name: `?CheckStartDeviceUpdateNotificationTimer@CServicesManager@@QEAAXXZ`
- size: `508`
- prototype: `void __fastcall(CServicesManager *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x140097db8`
- `0x140097ebc`

## callees

- `0x14000cf40`
- `0x14000d054`
- `0x14001a1e0`
- `0x140024004`
- `0x140030fb8`
- `0x1400311bc`
- `0x140061544`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14003119c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003119c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030ff3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030ff3`

## pseudocode

```c

```
