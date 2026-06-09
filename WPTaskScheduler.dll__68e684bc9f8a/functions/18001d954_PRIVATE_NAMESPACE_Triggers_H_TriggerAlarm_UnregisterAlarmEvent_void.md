# PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::UnregisterAlarmEvent(void)

- ea: `0x18001d954`
- end: `0x18001d9b8`
- name: `?UnregisterAlarmEvent@TriggerAlarm@PRIVATE_NAMESPACE_Triggers_H@@AEAAJXZ`
- size: `100`
- prototype: `__int64 __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm *this, __int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b764`
- `0x18001cd60`
- `0x18001d650`

## callees

- `0x18001d954`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001d978`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001d978`
- `TimeBrokerClient!TbDeleteCEvent` at `0x18001d99a`
- `TimeBrokerClient!TbDeleteCEvent` at `0x18001d99a`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::UnregisterAlarmEvent(
        PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm *this,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // edi
  __int64 v5; // rcx

  v3 = 0;
  if ( *((_QWORD *)this + 22) )
  {
    v5 = *((_QWORD *)this + 39);
    if ( v5 )
    {
      RtlUnsubscribeWnfNotificationWaitForCompletion(v5);
      *((_QWORD *)this + 39) = 0;
    }
  }
  if ( *((_QWORD *)this + 38) )
  {
    v3 = TbDeleteCEvent(*((_QWORD *)this + 38), a2, a3);
    *((_QWORD *)this + 38) = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x18001d954  mov     [rsp+arg_0], rbx
0x18001d959  push    rdi
0x18001d95a  sub     rsp, 20h
0x18001d95e  xor     edi, edi
0x18001d960  mov     rbx, rcx
0x18001d963  cmp     [rcx+0B0h], rdi
0x18001d96a  jz      short loc_18001D985
0x18001d96c  mov     rcx, [rcx+138h]
0x18001d973  test    rcx, rcx
0x18001d976  jz      short loc_18001D985
0x18001d978  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001d97e  mov     [rbx+138h], rdi
0x18001d985  mov     eax, [rbx+134h]
0x18001d98b  or      eax, [rbx+130h]
0x18001d991  jz      short loc_18001D9AB
0x18001d993  mov     rcx, [rbx+130h]
0x18001d99a  call    cs:__imp_TbDeleteCEvent
0x18001d9a0  mov     edi, eax
0x18001d9a2  xor     eax, eax
0x18001d9a4  mov     [rbx+130h], rax
0x18001d9ab  mov     rbx, [rsp+28h+arg_0]
0x18001d9b0  mov     eax, edi
0x18001d9b2  add     rsp, 20h
0x18001d9b6  pop     rdi
0x18001d9b7  retn
```
