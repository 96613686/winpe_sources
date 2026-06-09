# Broker::TimeBroker::QueryEventState(_GUID const &,Broker::TimeEvent::States &,__int64 &,__int64 &)

- ea: `0x180015cb0`
- end: `0x180015e23`
- name: `?QueryEventState@TimeBroker@Broker@@QEAAXAEBU_GUID@@AEAW4States@TimeEvent@2@AEA_J2@Z`
- size: `371`
- prototype: `void __fastcall(Broker::TimeBroker *__hidden this, const struct _GUID *, enum Broker::TimeEvent::States *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180014750`

## callees

- `0x180002400`
- `0x180004dd4`
- `0x180005b30`
- `0x180005b90`
- `0x180013978`
- `0x180015cb0`

## import_xrefs

- `BrokerLib!BrFindBrokeredEvent` at `0x180015d4b`
- `BrokerLib!BrFindBrokeredEvent` at `0x180015d4b`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180015d99`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180015d99`

## pseudocode

```c
void __fastcall Broker::TimeBroker::QueryEventState(
        Broker::TimeBroker *this,
        const struct _GUID *a2,
        enum Broker::TimeEvent::States *a3,
        __int64 *a4,
        __int64 *a5)
{
  std::_Ref_count_base *v9; // rcx
  _QWORD *v10; // [rsp+38h] [rbp-38h] BYREF
  std::_Ref_count_base *v11[2]; // [rsp+40h] [rbp-30h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+50h] [rbp-20h] BYREF
  int v13; // [rsp+68h] [rbp-8h]
  char v14; // [rsp+90h] [rbp+20h] BYREF

  v10 = 0;
  *(_OWORD *)v11 = 0;
  if ( !*((_QWORD *)this + 24) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v13 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  Broker::TimeBroker::BrokerLock::BrokerLock((Broker::TimeBroker::BrokerLock *)&v14, 1);
  *(struct _GUID *)pExceptionObject = *a2;
  if ( (unsigned int)BrFindBrokeredEvent(*((_QWORD *)this + 24), pExceptionObject, 0) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v13 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  if ( (unsigned int)BrGetBrokeredEventInfo2(*((_QWORD *)this + 24), 0, 0, 0, &v10) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v13 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  std::shared_ptr<Broker::TimeEvent>::operator=(v11, v10);
  v9 = v11[0];
  *(_DWORD *)a3 = *((_DWORD *)v11[0] + 22);
  *a4 = *((_QWORD *)v9 + 3);
  *a5 = *((_QWORD *)v9 + 4);
  Broker::TimeBroker::BrokerLock::~BrokerLock((Broker::TimeBroker::BrokerLock *)&v14);
  if ( v11[1] )
    std::_Ref_count_base::_Decref(v11[1]);
}

```

## disassembly

```asm
0x180015cb0  mov     [rsp-18h+arg_8], rbx
0x180015cb5  mov     [rsp-18h+arg_10], rsi
0x180015cba  push    rbp
0x180015cbb  push    rdi
0x180015cbc  push    r14
0x180015cbe  mov     rbp, rsp
0x180015cc1  sub     rsp, 70h
0x180015cc5  mov     rsi, r9
0x180015cc8  mov     r14, r8
0x180015ccb  mov     rdi, rdx
0x180015cce  mov     rbx, rcx
0x180015cd1  mov     [rbp+var_40], 0
0x180015cd9  mov     [rbp+var_38], 0
0x180015ce1  xorps   xmm0, xmm0
0x180015ce4  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180015ce9  cmp     qword ptr [rcx+0C0h], 0
0x180015cf1  jnz     short loc_180015D1A
0x180015cf3  movups  xmmword ptr [rbp+pExceptionObject+8], xmm0
0x180015cf7  mov     [rbp+var_8], 3
0x180015cfe  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180015d05  mov     qword ptr [rbp+pExceptionObject], rax
0x180015d09  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180015d10  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015d14  call    _CxxThrowException_0
0x180015d1a  mov     edx, 1; int
0x180015d1f  lea     rcx, [rbp+arg_0]; this
0x180015d23  call    ??0BrokerLock@TimeBroker@Broker@@QEAA@H@Z; Broker::TimeBroker::BrokerLock::BrokerLock(int)
0x180015d28  nop
0x180015d29  movups  xmm0, xmmword ptr [rdi]
0x180015d2c  movdqu  xmmword ptr [rbp+pExceptionObject], xmm0
0x180015d31  lea     rax, [rbp+var_40]
0x180015d35  mov     [rsp+70h+var_50], rax
0x180015d3a  xor     r9d, r9d
0x180015d3d  xor     r8d, r8d
0x180015d40  lea     rdx, [rbp+pExceptionObject]
0x180015d44  mov     rcx, [rbx+0C0h]
0x180015d4b  call    cs:__imp_BrFindBrokeredEvent
0x180015d51  test    eax, eax
0x180015d53  jz      short loc_180015D7F
0x180015d55  xorps   xmm0, xmm0
0x180015d58  movups  xmmword ptr [rbp+pExceptionObject+8], xmm0
0x180015d5c  mov     [rbp+var_8], 3
0x180015d63  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180015d6a  mov     qword ptr [rbp+pExceptionObject], rax
0x180015d6e  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180015d75  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015d79  call    _CxxThrowException_0
0x180015d7f  lea     rax, [rbp+var_38]
0x180015d83  mov     [rsp+70h+var_50], rax
0x180015d88  xor     r9d, r9d
0x180015d8b  xor     r8d, r8d
0x180015d8e  mov     rdx, [rbp+var_40]
0x180015d92  mov     rcx, [rbx+0C0h]
0x180015d99  call    cs:__imp_BrGetBrokeredEventInfo2
0x180015d9f  test    eax, eax
0x180015da1  jz      short loc_180015DCD
0x180015da3  xorps   xmm0, xmm0
0x180015da6  movups  xmmword ptr [rbp+pExceptionObject+8], xmm0
0x180015daa  mov     [rbp+var_8], 3
0x180015db1  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180015db8  mov     qword ptr [rbp+pExceptionObject], rax
0x180015dbc  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180015dc3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015dc7  call    _CxxThrowException_0
0x180015dcd  mov     rdx, [rbp+var_38]
0x180015dd1  lea     rcx, [rbp+var_30]
0x180015dd5  call    ??4?$shared_ptr@VTimeEvent@Broker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Broker::TimeEvent>::operator=(std::shared_ptr<Broker::TimeEvent> const &)
0x180015dda  mov     rcx, [rbp+var_30]
0x180015dde  mov     eax, [rcx+58h]
0x180015de1  mov     [r14], eax
0x180015de4  mov     rax, [rcx+18h]
0x180015de8  mov     [rsi], rax
0x180015deb  mov     rcx, [rcx+20h]
0x180015def  mov     rax, [rbp+arg_20]
0x180015df3  mov     [rax], rcx
0x180015df6  lea     rcx, [rbp+arg_0]; this
0x180015dfa  call    ??1BrokerLock@TimeBroker@Broker@@QEAA@XZ; Broker::TimeBroker::BrokerLock::~BrokerLock(void)
0x180015dff  nop
0x180015e00  mov     rcx, [rbp+var_30+8]; this
0x180015e04  test    rcx, rcx
0x180015e07  jz      short loc_180015E0E
0x180015e09  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015e0e  lea     r11, [rsp+70h+var_s0]
0x180015e13  mov     rbx, [r11+28h]
0x180015e17  mov     rsi, [r11+30h]
0x180015e1b  mov     rsp, r11
0x180015e1e  pop     r14
0x180015e20  pop     rdi
0x180015e21  pop     rbp
0x180015e22  retn
```
