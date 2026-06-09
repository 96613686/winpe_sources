# Broker::TimeBroker::UpdateCEvent(Broker::ApplicationIdentity const &,_CBROKERED_EVENT_ID const &,_TbiTimeEventCreationParameters &)

- ea: `0x180003868`
- end: `0x180003ab1`
- name: `?UpdateCEvent@TimeBroker@Broker@@QEAAXAEBUApplicationIdentity@2@AEBU_CBROKERED_EVENT_ID@@AEAU_TbiTimeEventCreationParameters@@@Z`
- size: `585`
- prototype: `void __fastcall(Broker::TimeBroker *__hidden this, const struct Broker::ApplicationIdentity *, const struct _CBROKERED_EVENT_ID *, struct _TbiTimeEventCreationParameters *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003ac0`

## callees

- `0x180002400`
- `0x180002500`
- `0x180003868`
- `0x180005b30`
- `0x180005b90`
- `0x1800061e0`
- `0x1800074c0`
- `0x180013978`
- `0x18001c010`

## import_xrefs

- `BrokerLib!BrFindBrokeredEvent2` at `0x18000390a`
- `BrokerLib!BrFindBrokeredEvent2` at `0x18000390a`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180003983`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180003983`

## pseudocode

```c
void __fastcall Broker::TimeBroker::UpdateCEvent(
        Broker::TimeBroker *this,
        const struct Broker::ApplicationIdentity *a2,
        const struct _CBROKERED_EVENT_ID *a3,
        struct _TbiTimeEventCreationParameters *a4)
{
  int BrokeredEvent2; // eax
  __int64 v9; // rbx
  __int64 v10; // rax
  _DWORD *v11; // rsi
  volatile signed __int32 *v12; // rbx
  __m128i v13; // xmm6
  __int64 v14; // [rsp+38h] [rbp-48h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-40h] BYREF
  int v16; // [rsp+58h] [rbp-28h]
  __m128i v17; // [rsp+60h] [rbp-20h] BYREF
  char v18; // [rsp+A0h] [rbp+20h] BYREF

  v14 = 0;
  v17 = 0;
  if ( !*((_QWORD *)this + 24) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v16 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  Broker::TimeBroker::BrokerLock::BrokerLock((Broker::TimeBroker::BrokerLock *)&v18, 0);
  BrokeredEvent2 = BrFindBrokeredEvent2(*((_QWORD *)this + 24), *(_QWORD *)a3, *(_QWORD *)a2);
  if ( BrokeredEvent2 == 5 )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v16 = 5;
    *(_QWORD *)pExceptionObject = &Broker::AccessDenied::`vftable';
    throw (Broker::AccessDenied *)pExceptionObject;
  }
  if ( BrokeredEvent2 )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v16 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  if ( (unsigned int)BrGetBrokeredEventInfo2(*((_QWORD *)this + 24), 0, 0, 0, &v14) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v16 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  v9 = v14;
  v10 = *(_QWORD *)(v14 + 8);
  if ( v10 )
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
  v11 = *(_DWORD **)v9;
  v12 = *(volatile signed __int32 **)(v9 + 8);
  v17.m128i_i64[0] = (__int64)v11;
  v17.m128i_i64[1] = (__int64)v12;
  if ( *(_DWORD *)a4 != v11[18] )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v16 = 4;
    *(_QWORD *)pExceptionObject = &Broker::InvalidParameter::`vftable';
    throw (Broker::InvalidParameter *)pExceptionObject;
  }
  Broker::TimeBroker::ValidateCreationParameters(this, a4, 0, 0);
  *(_OWORD *)pExceptionObject = 0;
  if ( v12 )
    _InterlockedIncrement(v12 + 2);
  v13 = _mm_load_si128(&v17);
  *(__m128i *)pExceptionObject = v13;
  Broker::TimeBroker::RemoveFromTimerWheel(this);
  (*(void (__fastcall **)(_DWORD *, struct _TbiTimeEventCreationParameters *, _QWORD))(*(_QWORD *)v11 + 40LL))(
    v11,
    a4,
    *((_QWORD *)this + 25));
  *(_OWORD *)pExceptionObject = 0;
  if ( v12 )
    _InterlockedIncrement(v12 + 2);
  *(__m128i *)pExceptionObject = v13;
  Broker::TimeBroker::InsertIntoTimerWheelIfNecessary(this, pExceptionObject);
  Broker::TimeBroker::BrokerLock::~BrokerLock((Broker::TimeBroker::BrokerLock *)&v18);
  if ( v12 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v12);
}

```

## disassembly

```asm
0x180003868  mov     [rsp-18h+arg_8], rbx
0x18000386d  mov     [rsp-18h+arg_10], rsi
0x180003872  push    rbp
0x180003873  push    rdi
0x180003874  push    r14
0x180003876  mov     rbp, rsp
0x180003879  sub     rsp, 80h
0x180003880  movaps  [rsp+80h+var_10], xmm6
0x180003885  mov     r14, r9
0x180003888  mov     rsi, r8
0x18000388b  mov     rbx, rdx
0x18000388e  mov     rdi, rcx
0x180003891  mov     [rbp+var_50], 0
0x180003899  mov     [rbp+var_48], 0
0x1800038a1  xorps   xmm0, xmm0
0x1800038a4  movdqa  [rbp+var_20], xmm0
0x1800038a9  cmp     qword ptr [rcx+0C0h], 0
0x1800038b1  jnz     short loc_1800038DA
0x1800038b3  movups  xmmword ptr [rbp+pExceptionObject+8], xmm0
0x1800038b7  mov     [rbp+var_28], 3
0x1800038be  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x1800038c5  mov     qword ptr [rbp+pExceptionObject], rax
0x1800038c9  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x1800038d0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800038d4  call    _CxxThrowException_0
0x1800038da  xor     edx, edx; int
0x1800038dc  lea     rcx, [rbp+arg_0]; this
0x1800038e0  call    ??0BrokerLock@TimeBroker@Broker@@QEAA@H@Z; Broker::TimeBroker::BrokerLock::BrokerLock(int)
0x1800038e5  nop
0x1800038e6  lea     r9, [rbx+18h]
0x1800038ea  cmp     qword ptr [r9+18h], 7
0x1800038ef  jbe     short loc_1800038F4
0x1800038f1  mov     r9, [r9]
0x1800038f4  lea     rax, [rbp+var_50]
0x1800038f8  mov     [rsp+80h+var_60], rax
0x1800038fd  mov     r8, [rbx]
0x180003900  mov     rdx, [rsi]
0x180003903  mov     rcx, [rdi+0C0h]
0x18000390a  call    cs:__imp_BrFindBrokeredEvent2
0x180003910  cmp     eax, 5
0x180003913  jnz     short loc_18000393B
0x180003915  xorps   xmm0, xmm0
0x180003918  movups  xmmword ptr [rbp+pExceptionObject+8], xmm0
0x18000391c  mov     [rbp+var_28], eax
0x18000391f  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x180003926  mov     qword ptr [rbp+pExceptionObject], rax
0x18000392a  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x180003931  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003935  call    _CxxThrowException_0
0x18000393b  test    eax, eax
0x18000393d  jz      short loc_180003969
0x18000393f  xorps   xmm0, xmm0
0x180003942  movups  xmmword ptr [rbp+pExceptionObject+8], xmm0
0x180003946  mov     [rbp+var_28], 3
0x18000394d  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180003954  mov     qword ptr [rbp+pExceptionObject], rax
0x180003958  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x18000395f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003963  call    _CxxThrowException_0
0x180003969  lea     rax, [rbp+var_48]
0x18000396d  mov     [rsp+80h+var_60], rax
0x180003972  xor     r9d, r9d
0x180003975  xor     r8d, r8d
0x180003978  mov     rdx, [rbp+var_50]
0x18000397c  mov     rcx, [rdi+0C0h]
0x180003983  call    cs:__imp_BrGetBrokeredEventInfo2
0x180003989  test    eax, eax
0x18000398b  jz      short loc_1800039B7
0x18000398d  xorps   xmm0, xmm0
0x180003990  movups  xmmword ptr [rbp+pExceptionObject+8], xmm0
0x180003994  mov     [rbp+var_28], 3
0x18000399b  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x1800039a2  mov     qword ptr [rbp+pExceptionObject], rax
0x1800039a6  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x1800039ad  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800039b1  call    _CxxThrowException_0
0x1800039b7  mov     rbx, [rbp+var_48]
0x1800039bb  mov     rax, [rbx+8]
0x1800039bf  test    rax, rax
0x1800039c2  jz      short loc_1800039C8
0x1800039c4  lock inc dword ptr [rax+8]
0x1800039c8  mov     rsi, [rbx]
0x1800039cb  mov     rbx, [rbx+8]
0x1800039cf  mov     qword ptr [rbp+var_20], rsi
0x1800039d3  mov     qword ptr [rbp+var_20+8], rbx
0x1800039d7  mov     eax, [rsi+48h]
0x1800039da  cmp     [r14], eax
0x1800039dd  jz      short loc_180003A09
0x1800039df  xorps   xmm0, xmm0
0x1800039e2  movups  xmmword ptr [rbp+pExceptionObject+8], xmm0
0x1800039e6  mov     [rbp+var_28], 4
0x1800039ed  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x1800039f4  mov     qword ptr [rbp+pExceptionObject], rax
0x1800039f8  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800039ff  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003a03  call    _CxxThrowException_0
0x180003a09  xor     r9d, r9d; bool
0x180003a0c  xor     r8d, r8d; bool
0x180003a0f  mov     rdx, r14; struct _TbiTimeEventCreationParameters *
0x180003a12  mov     rcx, rdi; this
0x180003a15  call    ?ValidateCreationParameters@TimeBroker@Broker@@AEAAXAEBU_TbiTimeEventCreationParameters@@_N1@Z; Broker::TimeBroker::ValidateCreationParameters(_TbiTimeEventCreationParameters const &,bool,bool)
0x180003a1a  xorps   xmm0, xmm0
0x180003a1d  movdqa  xmmword ptr [rbp+pExceptionObject], xmm0
0x180003a22  test    rbx, rbx
0x180003a25  jz      short loc_180003A2B
0x180003a27  lock inc dword ptr [rbx+8]
0x180003a2b  movdqa  xmm6, [rbp+var_20]
0x180003a30  movdqa  xmmword ptr [rbp+pExceptionObject], xmm6
0x180003a35  lea     rdx, [rbp+pExceptionObject]
0x180003a39  mov     rcx, rdi; this
0x180003a3c  call    ?RemoveFromTimerWheel@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z; Broker::TimeBroker::RemoveFromTimerWheel(std::shared_ptr<Broker::TimeEvent>)
0x180003a41  mov     rax, [rsi]
0x180003a44  mov     r8, [rdi+0C8h]
0x180003a4b  mov     rdx, r14
0x180003a4e  mov     rcx, rsi
0x180003a51  mov     rax, [rax+28h]
0x180003a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a5a  xorps   xmm0, xmm0
0x180003a5d  movdqa  xmmword ptr [rbp+pExceptionObject], xmm0
0x180003a62  test    rbx, rbx
0x180003a65  jz      short loc_180003A6B
0x180003a67  lock inc dword ptr [rbx+8]
0x180003a6b  movdqa  xmmword ptr [rbp+pExceptionObject], xmm6
0x180003a70  lea     rdx, [rbp+pExceptionObject]
0x180003a74  mov     rcx, rdi
0x180003a77  call    ?InsertIntoTimerWheelIfNecessary@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z; Broker::TimeBroker::InsertIntoTimerWheelIfNecessary(std::shared_ptr<Broker::TimeEvent>)
0x180003a7c  nop
0x180003a7d  lea     rcx, [rbp+arg_0]; this
0x180003a81  call    ??1BrokerLock@TimeBroker@Broker@@QEAA@XZ; Broker::TimeBroker::BrokerLock::~BrokerLock(void)
0x180003a86  nop
0x180003a87  test    rbx, rbx
0x180003a8a  jz      short loc_180003A94
0x180003a8c  mov     rcx, rbx; this
0x180003a8f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180003a94  lea     r11, [rsp+80h+var_s0]
0x180003a9c  mov     rbx, [r11+28h]
0x180003aa0  mov     rsi, [r11+30h]
0x180003aa4  movaps  xmm6, [rsp+80h+var_10]
0x180003aa9  mov     rsp, r11
0x180003aac  pop     r14
0x180003aae  pop     rdi
0x180003aaf  pop     rbp
0x180003ab0  retn
```
