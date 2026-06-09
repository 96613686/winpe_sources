# DeviceConfiguration::PrintDeviceConfigurationService::AcquireSpoolerLock(void)

- ea: `0x18000ece4`
- end: `0x18000ed0f`
- name: `?AcquireSpoolerLock@PrintDeviceConfigurationService@DeviceConfiguration@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `43`
- prototype: `struct _RTL_CRITICAL_SECTION **__fastcall(struct _RTL_CRITICAL_SECTION *, struct _RTL_CRITICAL_SECTION **)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, service_task`

## callers

- `0x18000ed18`
- `0x180011c38`
- `0x1800121c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ecf8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ecf8`

## pseudocode

```c

```
