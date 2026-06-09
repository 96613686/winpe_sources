# Broker::TimeBroker::SimulateExpireEvent(_GUID const &)

- ea: `0x180014568`
- end: `0x1800146b8`
- name: `?SimulateExpireEvent@TimeBroker@Broker@@QEAAXAEBU_GUID@@@Z`
- size: `336`
- prototype: `void __fastcall(Broker::TimeBroker *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800148a0`

## callees

- `0x180002400`
- `0x180004dd4`
- `0x180005b30`
- `0x180005b90`
- `0x18000b990`
- `0x18000fe70`
- `0x180013978`
- `0x180014568`

## import_xrefs

- `BrokerLib!BrFindBrokeredEvent` at `0x1800145f0`
- `BrokerLib!BrFindBrokeredEvent` at `0x1800145f0`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x18001463e`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x18001463e`

## pseudocode

```c
void __fastcall Broker::TimeBroker::SimulateExpireEvent(Broker::TimeBroker *this, const struct _GUID *a2)
{
  EVENT_DESCRIPTOR *v4; // rax
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-30h] BYREF
  int v6; // [rsp+48h] [rbp-18h]
  std::_Ref_count_base *v7[2]; // [rsp+50h] [rbp-10h] BYREF
  char v8; // [rsp+80h] [rbp+20h] BYREF
  __int64 v9; // [rsp+90h] [rbp+30h]
  _QWORD *v10; // [rsp+98h] [rbp+38h] BYREF

  v9 = 0;
  v10 = 0;
  *(_OWORD *)v7 = 0;
  if ( !*((_QWORD *)this + 24) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v6 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  Broker::TimeBroker::BrokerLock::BrokerLock((Broker::TimeBroker::BrokerLock *)&v8, 0);
  *(struct _GUID *)pExceptionObject = *a2;
  if ( (unsigned int)BrFindBrokeredEvent(*((_QWORD *)this + 24), pExceptionObject, 0) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v6 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  if ( (unsigned int)BrGetBrokeredEventInfo2(*((_QWORD *)this + 24), v9, 0, 0, &v10) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v6 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  std::shared_ptr<Broker::TimeEvent>::operator=(v7, v10);
  v4 = (EVENT_DESCRIPTOR *)std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(pExceptionObject, v7);
  Broker::TimeBroker::SignalEvent(this, v4);
  Broker::TimeBroker::BrokerLock::~BrokerLock((Broker::TimeBroker::BrokerLock *)&v8);
  if ( v7[1] )
    std::_Ref_count_base::_Decref(v7[1]);
}

```

## disassembly

```asm
0x180014568  push    rbp
0x18001456a  push    rbx
0x18001456b  push    rdi
0x18001456c  mov     rbp, rsp
0x18001456f  sub     rsp, 60h
0x180014573  mov     rdi, rdx
0x180014576  mov     rbx, rcx
0x180014579  mov     [rbp+arg_10], 0
0x180014581  mov     [rbp+arg_18], 0
0x180014589  xorps   xmm0, xmm0
0x18001458c  movdqu  xmmword ptr [rbp+var_10], xmm0
0x180014591  cmp     qword ptr [rcx+0C0h], 0
0x180014599  jnz     short loc_1800145C2
0x18001459b  movups  xmmword ptr [rbp+pExceptionObject+8], xmm0
0x18001459f  mov     [rbp+var_18], 3
0x1800145a6  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x1800145ad  mov     qword ptr [rbp+pExceptionObject], rax
0x1800145b1  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x1800145b8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800145bc  call    _CxxThrowException_0
0x1800145c2  xor     edx, edx; int
0x1800145c4  lea     rcx, [rbp+arg_0]; this
0x1800145c8  call    ??0BrokerLock@TimeBroker@Broker@@QEAA@H@Z; Broker::TimeBroker::BrokerLock::BrokerLock(int)
0x1800145cd  nop
0x1800145ce  movups  xmm0, xmmword ptr [rdi]
0x1800145d1  movdqu  xmmword ptr [rbp+pExceptionObject], xmm0
0x1800145d6  lea     rax, [rbp+arg_10]
0x1800145da  mov     [rsp+60h+var_40], rax
0x1800145df  xor     r9d, r9d
0x1800145e2  xor     r8d, r8d
0x1800145e5  lea     rdx, [rbp+pExceptionObject]
0x1800145e9  mov     rcx, [rbx+0C0h]
0x1800145f0  call    cs:__imp_BrFindBrokeredEvent
0x1800145f6  test    eax, eax
0x1800145f8  jz      short loc_180014624
0x1800145fa  xorps   xmm0, xmm0
0x1800145fd  movups  xmmword ptr [rbp+pExceptionObject+8], xmm0
0x180014601  mov     [rbp+var_18], 3
0x180014608  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x18001460f  mov     qword ptr [rbp+pExceptionObject], rax
0x180014613  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x18001461a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001461e  call    _CxxThrowException_0
0x180014624  lea     rax, [rbp+arg_18]
0x180014628  mov     [rsp+60h+var_40], rax
0x18001462d  xor     r9d, r9d
0x180014630  xor     r8d, r8d
0x180014633  mov     rdx, [rbp+arg_10]
0x180014637  mov     rcx, [rbx+0C0h]
0x18001463e  call    cs:__imp_BrGetBrokeredEventInfo2
0x180014644  test    eax, eax
0x180014646  jz      short loc_180014672
0x180014648  xorps   xmm0, xmm0
0x18001464b  movups  xmmword ptr [rbp+pExceptionObject+8], xmm0
0x18001464f  mov     [rbp+var_18], 3
0x180014656  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x18001465d  mov     qword ptr [rbp+pExceptionObject], rax
0x180014661  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180014668  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001466c  call    _CxxThrowException_0
0x180014672  mov     rdx, [rbp+arg_18]
0x180014676  lea     rcx, [rbp+var_10]
0x18001467a  call    ??4?$shared_ptr@VTimeEvent@Broker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Broker::TimeEvent>::operator=(std::shared_ptr<Broker::TimeEvent> const &)
0x18001467f  lea     rdx, [rbp+var_10]
0x180014683  lea     rcx, [rbp+pExceptionObject]
0x180014687  call    ??0?$shared_ptr@VTimeEvent@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(std::shared_ptr<Broker::TimeEvent> const &)
0x18001468c  mov     rdx, rax
0x18001468f  mov     rcx, rbx; this
0x180014692  call    ?SignalEvent@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z; Broker::TimeBroker::SignalEvent(std::shared_ptr<Broker::TimeEvent>)
0x180014697  nop
0x180014698  lea     rcx, [rbp+arg_0]; this
0x18001469c  call    ??1BrokerLock@TimeBroker@Broker@@QEAA@XZ; Broker::TimeBroker::BrokerLock::~BrokerLock(void)
0x1800146a1  nop
0x1800146a2  mov     rcx, [rbp+var_10+8]; this
0x1800146a6  test    rcx, rcx
0x1800146a9  jz      short loc_1800146B0
0x1800146ab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800146b0  add     rsp, 60h
0x1800146b4  pop     rdi
0x1800146b5  pop     rbx
0x1800146b6  pop     rbp
0x1800146b7  retn
```
