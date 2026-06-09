# Broker::TimeBroker::QueryEventData(Broker::ApplicationIdentity const &,_GUID const &,_TbiTimeEventCreationParameters &)

- ea: `0x180011d00`
- end: `0x180011ea1`
- name: `?QueryEventData@TimeBroker@Broker@@QEAAXAEBUApplicationIdentity@2@AEBU_GUID@@AEAU_TbiTimeEventCreationParameters@@@Z`
- size: `417`
- prototype: `void __fastcall(Broker::TimeBroker *__hidden this, const struct Broker::ApplicationIdentity *, const struct _GUID *, struct _TbiTimeEventCreationParameters *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180011c20`

## callees

- `0x180002400`
- `0x180004dd4`
- `0x180005b30`
- `0x180005b90`
- `0x180011d00`
- `0x180013978`
- `0x18001c010`

## import_xrefs

- `BrokerLib!BrFindBrokeredEvent` at `0x180011da6`
- `BrokerLib!BrFindBrokeredEvent` at `0x180011da6`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180011e1f`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180011e1f`

## pseudocode

```c
void __fastcall Broker::TimeBroker::QueryEventData(
        Broker::TimeBroker *this,
        const struct Broker::ApplicationIdentity *a2,
        const struct _GUID *a3,
        struct _TbiTimeEventCreationParameters *a4)
{
  int BrokeredEvent; // eax
  _QWORD *v9; // [rsp+38h] [rbp-38h] BYREF
  std::_Ref_count_base *v10[2]; // [rsp+40h] [rbp-30h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+50h] [rbp-20h] BYREF
  int v12; // [rsp+68h] [rbp-8h]
  char v13; // [rsp+90h] [rbp+20h] BYREF

  v9 = 0;
  *(_OWORD *)v10 = 0;
  if ( !*((_QWORD *)this + 24) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v12 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  Broker::TimeBroker::BrokerLock::BrokerLock((Broker::TimeBroker::BrokerLock *)&v13, 1);
  *(struct _GUID *)pExceptionObject = *a3;
  BrokeredEvent = BrFindBrokeredEvent(*((_QWORD *)this + 24), pExceptionObject, *(_QWORD *)a2);
  if ( BrokeredEvent == 5 )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v12 = 5;
    *(_QWORD *)pExceptionObject = &Broker::AccessDenied::`vftable';
    throw (Broker::AccessDenied *)pExceptionObject;
  }
  if ( BrokeredEvent )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v12 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  if ( (unsigned int)BrGetBrokeredEventInfo2(*((_QWORD *)this + 24), 0, 0, 0, &v9) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v12 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  std::shared_ptr<Broker::TimeEvent>::operator=(v10, v9);
  (*(void (__fastcall **)(std::_Ref_count_base *, struct _TbiTimeEventCreationParameters *))(*(_QWORD *)v10[0] + 56LL))(
    v10[0],
    a4);
  Broker::TimeBroker::BrokerLock::~BrokerLock((Broker::TimeBroker::BrokerLock *)&v13);
  if ( v10[1] )
    std::_Ref_count_base::_Decref(v10[1]);
}

```

## disassembly

```asm
0x180011d00  mov     [rsp-18h+arg_8], rbx
0x180011d05  mov     [rsp-18h+arg_10], rsi
0x180011d0a  push    rbp
0x180011d0b  push    rdi
0x180011d0c  push    r14
0x180011d0e  mov     rbp, rsp
0x180011d11  sub     rsp, 70h
0x180011d15  mov     r14, r9
0x180011d18  mov     rsi, r8
0x180011d1b  mov     rdi, rdx
0x180011d1e  mov     rbx, rcx
0x180011d21  mov     [rbp+var_40], 0
0x180011d29  mov     [rbp+var_38], 0
0x180011d31  xorps   xmm0, xmm0
0x180011d34  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180011d39  cmp     qword ptr [rcx+0C0h], 0
0x180011d41  jnz     short loc_180011D6A
0x180011d43  movups  xmmword ptr [rbp+pExceptionObject+8], xmm0
0x180011d47  mov     [rbp+var_8], 3
0x180011d4e  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180011d55  mov     qword ptr [rbp+pExceptionObject], rax
0x180011d59  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180011d60  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011d64  call    _CxxThrowException_0
0x180011d6a  mov     edx, 1; int
0x180011d6f  lea     rcx, [rbp+arg_0]; this
0x180011d73  call    ??0BrokerLock@TimeBroker@Broker@@QEAA@H@Z; Broker::TimeBroker::BrokerLock::BrokerLock(int)
0x180011d78  nop
0x180011d79  lea     r9, [rdi+18h]
0x180011d7d  cmp     qword ptr [r9+18h], 7
0x180011d82  jbe     short loc_180011D87
0x180011d84  mov     r9, [r9]
0x180011d87  movups  xmm0, xmmword ptr [rsi]
0x180011d8a  movdqu  xmmword ptr [rbp+pExceptionObject], xmm0
0x180011d8f  lea     rax, [rbp+var_40]
0x180011d93  mov     [rsp+70h+var_50], rax
0x180011d98  mov     r8, [rdi]
0x180011d9b  lea     rdx, [rbp+pExceptionObject]
0x180011d9f  mov     rcx, [rbx+0C0h]
0x180011da6  call    cs:__imp_BrFindBrokeredEvent
0x180011dac  cmp     eax, 5
0x180011daf  jnz     short loc_180011DD7
0x180011db1  xorps   xmm0, xmm0
0x180011db4  movups  xmmword ptr [rbp+pExceptionObject+8], xmm0
0x180011db8  mov     [rbp+var_8], eax
0x180011dbb  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x180011dc2  mov     qword ptr [rbp+pExceptionObject], rax
0x180011dc6  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x180011dcd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011dd1  call    _CxxThrowException_0
0x180011dd7  test    eax, eax
0x180011dd9  jz      short loc_180011E05
0x180011ddb  xorps   xmm0, xmm0
0x180011dde  movups  xmmword ptr [rbp+pExceptionObject+8], xmm0
0x180011de2  mov     [rbp+var_8], 3
0x180011de9  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180011df0  mov     qword ptr [rbp+pExceptionObject], rax
0x180011df4  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180011dfb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011dff  call    _CxxThrowException_0
0x180011e05  lea     rax, [rbp+var_38]
0x180011e09  mov     [rsp+70h+var_50], rax
0x180011e0e  xor     r9d, r9d
0x180011e11  xor     r8d, r8d
0x180011e14  mov     rdx, [rbp+var_40]
0x180011e18  mov     rcx, [rbx+0C0h]
0x180011e1f  call    cs:__imp_BrGetBrokeredEventInfo2
0x180011e25  test    eax, eax
0x180011e27  jz      short loc_180011E53
0x180011e29  xorps   xmm0, xmm0
0x180011e2c  movups  xmmword ptr [rbp+pExceptionObject+8], xmm0
0x180011e30  mov     [rbp+var_8], 3
0x180011e37  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180011e3e  mov     qword ptr [rbp+pExceptionObject], rax
0x180011e42  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180011e49  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011e4d  call    _CxxThrowException_0
0x180011e53  mov     rdx, [rbp+var_38]
0x180011e57  lea     rcx, [rbp+var_30]
0x180011e5b  call    ??4?$shared_ptr@VTimeEvent@Broker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Broker::TimeEvent>::operator=(std::shared_ptr<Broker::TimeEvent> const &)
0x180011e60  mov     rcx, [rbp+var_30]
0x180011e64  mov     rax, [rcx]
0x180011e67  mov     rdx, r14
0x180011e6a  mov     rax, [rax+38h]
0x180011e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e73  nop
0x180011e74  lea     rcx, [rbp+arg_0]; this
0x180011e78  call    ??1BrokerLock@TimeBroker@Broker@@QEAA@XZ; Broker::TimeBroker::BrokerLock::~BrokerLock(void)
0x180011e7d  nop
0x180011e7e  mov     rcx, [rbp+var_30+8]; this
0x180011e82  test    rcx, rcx
0x180011e85  jz      short loc_180011E8C
0x180011e87  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011e8c  lea     r11, [rsp+70h+var_s0]
0x180011e91  mov     rbx, [r11+28h]
0x180011e95  mov     rsi, [r11+30h]
0x180011e99  mov     rsp, r11
0x180011e9c  pop     r14
0x180011e9e  pop     rdi
0x180011e9f  pop     rbp
0x180011ea0  retn
```
