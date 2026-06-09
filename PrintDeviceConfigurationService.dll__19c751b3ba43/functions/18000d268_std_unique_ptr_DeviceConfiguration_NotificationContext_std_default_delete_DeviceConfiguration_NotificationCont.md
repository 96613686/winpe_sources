# std::unique_ptr<DeviceConfiguration::NotificationContext,std::default_delete<DeviceConfiguration::NotificationContext>>::~unique_ptr<DeviceConfiguration::NotificationContext,std::default_delete<DeviceConfiguration::NotificationContext>>(void)

- ea: `0x18000d268`
- end: `0x18000d27e`
- name: `??1?$unique_ptr@UNotificationContext@DeviceConfiguration@@U?$default_delete@UNotificationContext@DeviceConfiguration@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000de10`
- `0x180016c75`

## callees

- `0x18000d268`
- `0x18000d3e0`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<DeviceConfiguration::NotificationContext>::~unique_ptr<DeviceConfiguration::NotificationContext>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<DeviceConfiguration::NotificationContext>::operator()();
  return result;
}

```

## disassembly

```asm
0x18000d268  sub     rsp, 28h
0x18000d26c  mov     rdx, [rcx]
0x18000d26f  test    rdx, rdx
0x18000d272  jz      short loc_18000D279
0x18000d274  call    ??R?$default_delete@UNotificationContext@DeviceConfiguration@@@std@@QEBAXPEAUNotificationContext@DeviceConfiguration@@@Z; std::default_delete<DeviceConfiguration::NotificationContext>::operator()(DeviceConfiguration::NotificationContext *)
0x18000d279  add     rsp, 28h
0x18000d27d  retn
```
