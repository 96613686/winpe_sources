# ShieldProvider::ShieldManagementProvider::UnregisterForNotifications(void)

- ea: `0x180086168`
- end: `0x180086208`
- name: `?UnregisterForNotifications@ShieldManagementProvider@ShieldProvider@@AEAAXXZ`
- size: `160`
- prototype: `void __fastcall(ShieldProvider::ShieldManagementProvider *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180085db0`

## callees

- `0x180017194`
- `0x18001a2a8`
- `0x180086168`
- `0x1800e7010`

## import_xrefs

- `KERNEL32!UnregisterWaitEx` at `0x1800861ca`
- `KERNEL32!UnregisterWaitEx` at `0x1800861ca`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800861e7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800861e7`
- `USERENV!UnregisterGPNotification` at `0x1800861b4`
- `USERENV!UnregisterGPNotification` at `0x1800861b4`

## pseudocode

```c

```
