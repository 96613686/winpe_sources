# Broker::TimeBroker::QueryCEventData(Broker::ApplicationIdentity const &,_CBROKERED_EVENT_ID const &,_TbiTimeEventCreationParameters &)

- ea: `0x180015b10`
- end: `0x180015ca8`
- name: `?QueryCEventData@TimeBroker@Broker@@QEAAXAEBUApplicationIdentity@2@AEBU_CBROKERED_EVENT_ID@@AEAU_TbiTimeEventCreationParameters@@@Z`
- size: `408`
- prototype: `void __fastcall(Broker::TimeBroker *__hidden this, const struct Broker::ApplicationIdentity *, const struct _CBROKERED_EVENT_ID *, struct _TbiTimeEventCreationParameters *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800149d0`

## callees

- `0x180002400`
- `0x180004dd4`
- `0x180005b30`
- `0x180005b90`
- `0x180013978`
- `0x180015b10`
- `0x18001c010`

## import_xrefs

- `BrokerLib!BrFindBrokeredEvent2` at `0x180015bad`
- `BrokerLib!BrFindBrokeredEvent2` at `0x180015bad`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180015c26`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180015c26`

## pseudocode

```c
void __fastcall Broker::TimeBroker::QueryCEventData(
        Broker::TimeBroker *this,
        const struct Broker::ApplicationIdentity *a2,
        const struct _CBROKERED_EVENT_ID *a3,
        struct _TbiTimeEventCreationParameters *a4)
{
  int BrokeredEvent2; // eax
  _QWORD *v9; // [rsp+38h] [rbp-38h] BYREF
  std::_Ref_count_base *v10[2]; // [rsp+40h] [rbp-30h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-20h] BYREF
  __int128 v12; // [rsp+58h] [rbp-18h]
  int v13; // [rsp+68h] [rbp-8h]
  char v14; // [rsp+90h] [rbp+20h] BYREF

  v9 = 0;
  *(_OWORD *)v10 = 0;
  if ( !*((_QWORD *)this + 24) )
  {
    v12 = 0;
    v13 = 3;
    pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)&pExceptionObject;
  }
  Broker::TimeBroker::BrokerLock::BrokerLock((Broker::TimeBroker::BrokerLock *)&v14, 1);
  BrokeredEvent2 = BrFindBrokeredEvent2(*((_QWORD *)this + 24), *(_QWORD *)a3, *(_QWORD *)a2);
  if ( BrokeredEvent2 == 5 )
  {
    v12 = 0;
    v13 = 5;
    pExceptionObject = &Broker::AccessDenied::`vftable';
    throw (Broker::AccessDenied *)&pExceptionObject;
  }
  if ( BrokeredEvent2 )
  {
    v12 = 0;
    v13 = 3;
    pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)&pExceptionObject;
  }
  if ( (unsigned int)BrGetBrokeredEventInfo2(*((_QWORD *)this + 24), 0, 0, 0, &v9) )
  {
    v12 = 0;
    v13 = 3;
    pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)&pExceptionObject;
  }
  std::shared_ptr<Broker::TimeEvent>::operator=(v10, v9);
  (*(void (__fastcall **)(std::_Ref_count_base *, struct _TbiTimeEventCreationParameters *))(*(_QWORD *)v10[0] + 56LL))(
    v10[0],
    a4);
  Broker::TimeBroker::BrokerLock::~BrokerLock((Broker::TimeBroker::BrokerLock *)&v14);
  if ( v10[1] )
    std::_Ref_count_base::_Decref(v10[1]);
}

```

## disassembly

```asm
0x180015b10  mov     [rsp-18h+arg_8], rbx
0x180015b15  mov     [rsp-18h+arg_10], rsi
0x180015b1a  push    rbp
0x180015b1b  push    rdi
0x180015b1c  push    r14
0x180015b1e  mov     rbp, rsp
0x180015b21  sub     rsp, 70h
0x180015b25  mov     r14, r9
0x180015b28  mov     rsi, r8
0x180015b2b  mov     rdi, rdx
0x180015b2e  mov     rbx, rcx
0x180015b31  mov     [rbp+var_40], 0
0x180015b39  mov     [rbp+var_38], 0
0x180015b41  xorps   xmm0, xmm0
0x180015b44  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180015b49  cmp     qword ptr [rcx+0C0h], 0
0x180015b51  jnz     short loc_180015B7A
0x180015b53  movups  [rbp+var_18], xmm0
0x180015b57  mov     [rbp+var_8], 3
0x180015b5e  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180015b65  mov     [rbp+pExceptionObject], rax
0x180015b69  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180015b70  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015b74  call    _CxxThrowException_0
0x180015b7a  mov     edx, 1; int
0x180015b7f  lea     rcx, [rbp+arg_0]; this
0x180015b83  call    ??0BrokerLock@TimeBroker@Broker@@QEAA@H@Z; Broker::TimeBroker::BrokerLock::BrokerLock(int)
0x180015b88  nop
0x180015b89  lea     r9, [rdi+18h]
0x180015b8d  cmp     qword ptr [r9+18h], 7
0x180015b92  jbe     short loc_180015B97
0x180015b94  mov     r9, [r9]
0x180015b97  lea     rax, [rbp+var_40]
0x180015b9b  mov     [rsp+70h+var_50], rax
0x180015ba0  mov     r8, [rdi]
0x180015ba3  mov     rdx, [rsi]
0x180015ba6  mov     rcx, [rbx+0C0h]
0x180015bad  call    cs:__imp_BrFindBrokeredEvent2
0x180015bb3  cmp     eax, 5
0x180015bb6  jnz     short loc_180015BDE
0x180015bb8  xorps   xmm0, xmm0
0x180015bbb  movups  [rbp+var_18], xmm0
0x180015bbf  mov     [rbp+var_8], eax
0x180015bc2  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x180015bc9  mov     [rbp+pExceptionObject], rax
0x180015bcd  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x180015bd4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015bd8  call    _CxxThrowException_0
0x180015bde  test    eax, eax
0x180015be0  jz      short loc_180015C0C
0x180015be2  xorps   xmm0, xmm0
0x180015be5  movups  [rbp+var_18], xmm0
0x180015be9  mov     [rbp+var_8], 3
0x180015bf0  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180015bf7  mov     [rbp+pExceptionObject], rax
0x180015bfb  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180015c02  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015c06  call    _CxxThrowException_0
0x180015c0c  lea     rax, [rbp+var_38]
0x180015c10  mov     [rsp+70h+var_50], rax
0x180015c15  xor     r9d, r9d
0x180015c18  xor     r8d, r8d
0x180015c1b  mov     rdx, [rbp+var_40]
0x180015c1f  mov     rcx, [rbx+0C0h]
0x180015c26  call    cs:__imp_BrGetBrokeredEventInfo2
0x180015c2c  test    eax, eax
0x180015c2e  jz      short loc_180015C5A
0x180015c30  xorps   xmm0, xmm0
0x180015c33  movups  [rbp+var_18], xmm0
0x180015c37  mov     [rbp+var_8], 3
0x180015c3e  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180015c45  mov     [rbp+pExceptionObject], rax
0x180015c49  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180015c50  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015c54  call    _CxxThrowException_0
0x180015c5a  mov     rdx, [rbp+var_38]
0x180015c5e  lea     rcx, [rbp+var_30]
0x180015c62  call    ??4?$shared_ptr@VTimeEvent@Broker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Broker::TimeEvent>::operator=(std::shared_ptr<Broker::TimeEvent> const &)
0x180015c67  mov     rcx, [rbp+var_30]
0x180015c6b  mov     rax, [rcx]
0x180015c6e  mov     rdx, r14
0x180015c71  mov     rax, [rax+38h]
0x180015c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c7a  nop
0x180015c7b  lea     rcx, [rbp+arg_0]; this
0x180015c7f  call    ??1BrokerLock@TimeBroker@Broker@@QEAA@XZ; Broker::TimeBroker::BrokerLock::~BrokerLock(void)
0x180015c84  nop
0x180015c85  mov     rcx, [rbp+var_30+8]; this
0x180015c89  test    rcx, rcx
0x180015c8c  jz      short loc_180015C93
0x180015c8e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015c93  lea     r11, [rsp+70h+var_s0]
0x180015c98  mov     rbx, [r11+28h]
0x180015c9c  mov     rsi, [r11+30h]
0x180015ca0  mov     rsp, r11
0x180015ca3  pop     r14
0x180015ca5  pop     rdi
0x180015ca6  pop     rbp
0x180015ca7  retn
```
