# AppInitializeDeviceRegistration(SERVICE_STATUS_HANDLE__ *,ulong)

- ea: `0x180019140`
- end: `0x180019219`
- name: `?AppInitializeDeviceRegistration@@YAXPEAUSERVICE_STATUS_HANDLE__@@K@Z`
- size: `217`
- prototype: `void __fastcall(struct SERVICE_STATUS_HANDLE__ *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180010f50`

## callees

- `0x180019140`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800191b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019201`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800191b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019201`
- `USER32!RegisterDeviceNotificationW` at `0x1800191a3`
- `USER32!RegisterDeviceNotificationW` at `0x1800191ef`
- `USER32!RegisterDeviceNotificationW` at `0x1800191a3`
- `USER32!RegisterDeviceNotificationW` at `0x1800191ef`

## pseudocode

```c

```
