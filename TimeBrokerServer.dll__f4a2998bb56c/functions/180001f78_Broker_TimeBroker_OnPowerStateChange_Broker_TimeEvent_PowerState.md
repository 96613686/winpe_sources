# Broker::TimeBroker::OnPowerStateChange(Broker::TimeEvent::PowerState)

- ea: `0x180001f78`
- end: `0x180001fec`
- name: `?OnPowerStateChange@TimeBroker@Broker@@QEAAXW4PowerState@TimeEvent@2@@Z`
- size: `116`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000e740`
- `0x180014900`

## callees

- `0x180001f78`
- `0x180002400`
- `0x180005b90`
- `0x180007c60`
- `0x18000eddc`

## pseudocode

```c
void __fastcall Broker::TimeBroker::OnPowerStateChange(__int64 a1, int a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  char v6; // [rsp+40h] [rbp+8h] BYREF

  if ( *(_QWORD *)(a1 + 192) )
  {
    Broker::TimeBroker::BrokerLock::BrokerLock((Broker::TimeBroker::BrokerLock *)&v6, 0);
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_ll(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v5, *(unsigned int *)(a1 + 168), a2);
    *(_DWORD *)(a1 + 168) = a2;
    Broker::TimeBroker::SetSytemTimer((Broker::TimeBroker *)a1);
    Broker::TimeBroker::BrokerLock::~BrokerLock((Broker::TimeBroker::BrokerLock *)&v6);
  }
}

```

## disassembly

```asm
0x180001f78  mov     [rsp+arg_8], rbx
0x180001f7d  push    rdi
0x180001f7e  sub     rsp, 30h
0x180001f82  mov     edi, edx
0x180001f84  mov     rbx, rcx
0x180001f87  cmp     qword ptr [rcx+0C0h], 0
0x180001f8f  jz      short loc_180001FE1
0x180001f91  xor     edx, edx; int
0x180001f93  lea     rcx, [rsp+38h+arg_0]; this
0x180001f98  call    ??0BrokerLock@TimeBroker@Broker@@QEAA@H@Z; Broker::TimeBroker::BrokerLock::BrokerLock(int)
0x180001f9d  nop
0x180001f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001fa5  test    dword ptr [rcx+1Ch], 100h
0x180001fac  jz      short loc_180001FC8
0x180001fae  cmp     byte ptr [rcx+19h], 4
0x180001fb2  jb      short loc_180001FC8
0x180001fb4  mov     [rsp+38h+var_18], edi
0x180001fb8  mov     r9d, [rbx+0A8h]
0x180001fbf  mov     rcx, [rcx+10h]
0x180001fc3  call    WPP_SF_ll
0x180001fc8  mov     [rbx+0A8h], edi
0x180001fce  mov     rcx, rbx; this
0x180001fd1  call    ?SetSytemTimer@TimeBroker@Broker@@AEAAXXZ; Broker::TimeBroker::SetSytemTimer(void)
0x180001fd6  nop
0x180001fd7  lea     rcx, [rsp+38h+arg_0]; this
0x180001fdc  call    ??1BrokerLock@TimeBroker@Broker@@QEAA@XZ; Broker::TimeBroker::BrokerLock::~BrokerLock(void)
0x180001fe1  mov     rbx, [rsp+38h+arg_8]
0x180001fe6  add     rsp, 30h
0x180001fea  pop     rdi
0x180001feb  retn
```
