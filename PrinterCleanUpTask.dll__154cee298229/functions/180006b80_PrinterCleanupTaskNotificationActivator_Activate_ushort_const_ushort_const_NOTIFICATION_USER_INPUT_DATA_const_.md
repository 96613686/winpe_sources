# PrinterCleanupTaskNotificationActivator::Activate(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)

- ea: `0x180006b80`
- end: `0x180006b88`
- name: `?Activate@PrinterCleanupTaskNotificationActivator@@UEAAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z`
- size: `8`
- prototype: `__int64 __fastcall(PrinterCleanupTaskNotificationActivator *this, const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180015bc4`

## pseudocode

```c
__int64 __fastcall PrinterCleanupTaskNotificationActivator::Activate(
        PrinterCleanupTaskNotificationActivator *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct NOTIFICATION_USER_INPUT_DATA *a4)
{
  return ToastManager::NotificationActivator(
           (const unsigned __int16 *)this,
           a3,
           (const struct NOTIFICATION_USER_INPUT_DATA *)a3);
}

```

## disassembly

```asm
0x180006b80  mov     rdx, r8; unsigned __int16 *
0x180006b83  jmp     ?NotificationActivator@ToastManager@@SAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z; ToastManager::NotificationActivator(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)
```
