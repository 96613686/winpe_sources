# TimeBrokerPowerStateChangeCallback(void *,ulong,void *)

- ea: `0x18000e740`
- end: `0x18000e7b7`
- name: `?TimeBrokerPowerStateChangeCallback@@YAKPEAXK0@Z`
- size: `119`
- prototype: `__int64 __fastcall(void *, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001f78`
- `0x180005b30`
- `0x18000e740`

## pseudocode

```c
__int64 __fastcall TimeBrokerPowerStateChangeCallback(void *a1, __int64 a2, _QWORD *a3)
{
  int v3; // edx
  std::_Ref_count_base *v4; // rbx
  __int64 v5; // rax

  v3 = 1;
  v4 = *(&Broker::TimeBroker::Instance + 1);
  if ( *(&Broker::TimeBroker::Instance + 1) )
  {
    _InterlockedAdd((volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1) + 2, 1u);
    v4 = *(&Broker::TimeBroker::Instance + 1);
  }
  if ( Broker::TimeBroker::Instance )
  {
    v5 = *a3 - *(_QWORD *)&GUID_LOW_POWER_EPOCH.Data1;
    if ( *a3 == *(_QWORD *)&GUID_LOW_POWER_EPOCH.Data1 )
      v5 = a3[1] - *(_QWORD *)GUID_LOW_POWER_EPOCH.Data4;
    if ( !v5 )
    {
      if ( *((_DWORD *)a3 + 5) == 1 )
        v3 = 0;
      Broker::TimeBroker::OnPowerStateChange((__int64)Broker::TimeBroker::Instance, v3);
    }
  }
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  return 0;
}

```

## disassembly

```asm
0x18000e740  push    rbx
0x18000e742  sub     rsp, 30h
0x18000e746  mov     edx, 1
0x18000e74b  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18000e752  test    rbx, rbx
0x18000e755  jz      short loc_18000E762
0x18000e757  lock add [rbx+8], edx
0x18000e75b  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18000e762  mov     rcx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18000e769  mov     [rsp+38h+var_18], rcx
0x18000e76e  mov     [rsp+38h+var_10], rbx
0x18000e773  test    rcx, rcx
0x18000e776  jz      short loc_18000E7A2
0x18000e778  mov     rax, [r8]
0x18000e77b  sub     rax, qword ptr cs:GUID_LOW_POWER_EPOCH.Data1
0x18000e782  jnz     short loc_18000E78F
0x18000e784  mov     rax, [r8+8]
0x18000e788  sub     rax, qword ptr cs:GUID_LOW_POWER_EPOCH.Data4
0x18000e78f  test    rax, rax
0x18000e792  jnz     short loc_18000E7A2
0x18000e794  cmp     [r8+14h], edx
0x18000e798  jnz     short loc_18000E79C
0x18000e79a  xor     edx, edx
0x18000e79c  call    ?OnPowerStateChange@TimeBroker@Broker@@QEAAXW4PowerState@TimeEvent@2@@Z; Broker::TimeBroker::OnPowerStateChange(Broker::TimeEvent::PowerState)
0x18000e7a1  nop
0x18000e7a2  test    rbx, rbx
0x18000e7a5  jz      short loc_18000E7AF
0x18000e7a7  mov     rcx, rbx; this
0x18000e7aa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000e7af  xor     eax, eax
0x18000e7b1  add     rsp, 30h
0x18000e7b5  pop     rbx
0x18000e7b6  retn
```
