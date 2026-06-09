# Broker::TimeBroker::UpdateEvent(Broker::ApplicationIdentity const &,_GUID const &,_TbiTimeEventCreationParameters &)

- ea: `0x18000215c`
- end: `0x1800023eb`
- name: `?UpdateEvent@TimeBroker@Broker@@QEAAXAEBUApplicationIdentity@2@AEBU_GUID@@AEAU_TbiTimeEventCreationParameters@@@Z`
- size: `655`
- prototype: `void __fastcall(Broker::TimeBroker *__hidden this, const struct Broker::ApplicationIdentity *, const struct _GUID *, struct _TbiTimeEventCreationParameters *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003700`

## callees

- `0x18000215c`
- `0x180002400`
- `0x180002500`
- `0x180005b30`
- `0x180005b90`
- `0x1800061e0`
- `0x1800074c0`
- `0x180008280`
- `0x180013978`
- `0x18001c010`

## import_xrefs

- `BrokerLib!BrFindBrokeredEvent` at `0x1800021e2`
- `BrokerLib!BrFindBrokeredEvent` at `0x1800021e2`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180002231`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180002231`

## pseudocode

```c
void __fastcall Broker::TimeBroker::UpdateEvent(
        Broker::TimeBroker *this,
        const struct Broker::ApplicationIdentity *a2,
        const struct _GUID *a3,
        struct _TbiTimeEventCreationParameters *a4)
{
  int BrokeredEvent; // eax
  __int64 v9; // rbx
  __int64 v10; // rax
  _DWORD *v11; // r14
  volatile signed __int32 *v12; // rbx
  __int64 v13; // rdi
  __m128i v14; // xmm6
  __int64 v15; // [rsp+38h] [rbp-21h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-19h] BYREF
  int v17; // [rsp+58h] [rbp-1h]
  __m128i v18; // [rsp+60h] [rbp+7h] BYREF
  char v19; // [rsp+C0h] [rbp+67h] BYREF

  v15 = 0;
  v18 = 0;
  if ( !*((_QWORD *)this + 24) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v17 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  Broker::TimeBroker::BrokerLock::BrokerLock((Broker::TimeBroker::BrokerLock *)&v19, 0);
  *(struct _GUID *)pExceptionObject = *a3;
  BrokeredEvent = BrFindBrokeredEvent(*((_QWORD *)this + 24), pExceptionObject, *(_QWORD *)a2);
  if ( BrokeredEvent == 5 )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v17 = 5;
    *(_QWORD *)pExceptionObject = &Broker::AccessDenied::`vftable';
    throw (Broker::AccessDenied *)pExceptionObject;
  }
  if ( BrokeredEvent )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v17 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  if ( (unsigned int)BrGetBrokeredEventInfo2(*((_QWORD *)this + 24), 0, 0, 0, &v15) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v17 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  v9 = v15;
  v10 = *(_QWORD *)(v15 + 8);
  if ( v10 )
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
  v11 = *(_DWORD **)v9;
  v12 = *(volatile signed __int32 **)(v9 + 8);
  *(_OWORD *)pExceptionObject = 0u;
  v18.m128i_i64[0] = (__int64)v11;
  v18.m128i_i64[1] = (__int64)v12;
  std::shared_ptr<Broker::TimeEvent>::~shared_ptr<Broker::TimeEvent>(pExceptionObject);
  if ( *(_DWORD *)a4 != v11[18] )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v17 = 4;
    *(_QWORD *)pExceptionObject = &Broker::InvalidParameter::`vftable';
    throw (Broker::InvalidParameter *)pExceptionObject;
  }
  Broker::TimeBroker::ValidateCreationParameters(this, a4, 0, 0);
  *(_OWORD *)pExceptionObject = 0;
  if ( v12 )
  {
    v13 = (__int64)(v12 + 2);
    _InterlockedIncrement(v12 + 2);
  }
  else
  {
    v13 = 8;
  }
  v14 = _mm_load_si128(&v18);
  *(__m128i *)pExceptionObject = v14;
  Broker::TimeBroker::RemoveFromTimerWheel(this);
  (*(void (__fastcall **)(_DWORD *, struct _TbiTimeEventCreationParameters *, _QWORD))(*(_QWORD *)v11 + 40LL))(
    v11,
    a4,
    *((_QWORD *)this + 25));
  *(_OWORD *)pExceptionObject = 0;
  if ( v12 )
    _InterlockedIncrement((volatile signed __int32 *)v13);
  *(__m128i *)pExceptionObject = v14;
  Broker::TimeBroker::InsertIntoTimerWheelIfNecessary(this, pExceptionObject);
  Broker::TimeBroker::BrokerLock::~BrokerLock((Broker::TimeBroker::BrokerLock *)&v19);
  if ( v12 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v12);
}

```

## disassembly

```asm
0x18000215c  push    rbp
0x18000215e  push    rbx
0x18000215f  push    rsi
0x180002160  push    rdi
0x180002161  push    r14
0x180002163  push    r15
0x180002165  lea     rbp, [rsp-2Fh]
0x18000216a  sub     rsp, 88h
0x180002171  movaps  [rsp+0B0h+var_40], xmm6
0x180002176  mov     r15, r9
0x180002179  mov     rdi, r8
0x18000217c  mov     rbx, rdx
0x18000217f  mov     rsi, rcx
0x180002182  mov     [rbp+57h+var_80], 0
0x18000218a  mov     [rbp+57h+var_78], 0
0x180002192  xorps   xmm0, xmm0
0x180002195  movdqa  [rbp+57h+var_50], xmm0
0x18000219a  cmp     qword ptr [rcx+0C0h], 0
0x1800021a2  jz      loc_18000232B
0x1800021a8  xor     edx, edx; int
0x1800021aa  lea     rcx, [rbp+57h+arg_0]; this
0x1800021ae  call    ??0BrokerLock@TimeBroker@Broker@@QEAA@H@Z; Broker::TimeBroker::BrokerLock::BrokerLock(int)
0x1800021b3  nop
0x1800021b4  lea     r9, [rbx+18h]
0x1800021b8  cmp     qword ptr [r9+18h], 7
0x1800021bd  ja      loc_180002352
0x1800021c3  movups  xmm0, xmmword ptr [rdi]
0x1800021c6  movdqu  xmmword ptr [rbp+57h+pExceptionObject], xmm0
0x1800021cb  lea     rax, [rbp+57h+var_80]
0x1800021cf  mov     [rsp+0B0h+var_90], rax
0x1800021d4  mov     r8, [rbx]
0x1800021d7  lea     rdx, [rbp+57h+pExceptionObject]
0x1800021db  mov     rcx, [rsi+0C0h]
0x1800021e2  call    cs:__imp_BrFindBrokeredEvent
0x1800021e8  cmp     eax, 5
0x1800021eb  jnz     loc_18000235A
0x1800021f1  xorps   xmm0, xmm0
0x1800021f4  movups  xmmword ptr [rbp+57h+pExceptionObject+8], xmm0
0x1800021f8  mov     [rbp+57h+var_58], eax
0x1800021fb  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x180002202  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x180002206  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x18000220d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180002211  call    _CxxThrowException_0
0x180002217  lea     rax, [rbp+57h+var_78]
0x18000221b  mov     [rsp+0B0h+var_90], rax
0x180002220  xor     r9d, r9d
0x180002223  xor     r8d, r8d
0x180002226  mov     rdx, [rbp+57h+var_80]
0x18000222a  mov     rcx, [rsi+0C0h]
0x180002231  call    cs:__imp_BrGetBrokeredEventInfo2
0x180002237  test    eax, eax
0x180002239  jnz     loc_18000238C
0x18000223f  mov     rbx, [rbp+57h+var_78]
0x180002243  mov     rax, [rbx+8]
0x180002247  test    rax, rax
0x18000224a  jz      short loc_180002250
0x18000224c  lock inc dword ptr [rax+8]
0x180002250  mov     r14, [rbx]
0x180002253  mov     rbx, [rbx+8]
0x180002257  mov     qword ptr [rbp+57h+pExceptionObject], 0
0x18000225f  mov     qword ptr [rbp+57h+var_50], r14
0x180002263  mov     qword ptr [rbp+57h+pExceptionObject+8], 0
0x18000226b  mov     qword ptr [rbp+57h+var_50+8], rbx
0x18000226f  lea     rcx, [rbp+57h+pExceptionObject]
0x180002273  call    ??1?$shared_ptr@VTimeEvent@Broker@@@std@@QEAA@XZ; std::shared_ptr<Broker::TimeEvent>::~shared_ptr<Broker::TimeEvent>(void)
0x180002278  mov     eax, [r14+48h]
0x18000227c  cmp     [r15], eax
0x18000227f  jnz     loc_1800023B6
0x180002285  xor     r9d, r9d; bool
0x180002288  xor     r8d, r8d; bool
0x18000228b  mov     rdx, r15; struct _TbiTimeEventCreationParameters *
0x18000228e  mov     rcx, rsi; this
0x180002291  call    ?ValidateCreationParameters@TimeBroker@Broker@@AEAAXAEBU_TbiTimeEventCreationParameters@@_N1@Z; Broker::TimeBroker::ValidateCreationParameters(_TbiTimeEventCreationParameters const &,bool,bool)
0x180002296  xorps   xmm0, xmm0
0x180002299  movdqa  xmmword ptr [rbp+57h+pExceptionObject], xmm0
0x18000229e  test    rbx, rbx
0x1800022a1  jz      loc_1800023E0
0x1800022a7  lea     rdi, [rbx+8]
0x1800022ab  lock inc dword ptr [rdi]
0x1800022ae  movdqa  xmm6, [rbp+57h+var_50]
0x1800022b3  movdqa  xmmword ptr [rbp+57h+pExceptionObject], xmm6
0x1800022b8  lea     rdx, [rbp+57h+pExceptionObject]
0x1800022bc  mov     rcx, rsi; this
0x1800022bf  call    ?RemoveFromTimerWheel@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z; Broker::TimeBroker::RemoveFromTimerWheel(std::shared_ptr<Broker::TimeEvent>)
0x1800022c4  mov     rax, [r14]
0x1800022c7  mov     r8, [rsi+0C8h]
0x1800022ce  mov     rdx, r15
0x1800022d1  mov     rcx, r14
0x1800022d4  mov     rax, [rax+28h]
0x1800022d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022dd  xorps   xmm0, xmm0
0x1800022e0  movdqa  xmmword ptr [rbp+57h+pExceptionObject], xmm0
0x1800022e5  test    rbx, rbx
0x1800022e8  jz      short loc_1800022ED
0x1800022ea  lock inc dword ptr [rdi]
0x1800022ed  movdqa  xmmword ptr [rbp+57h+pExceptionObject], xmm6
0x1800022f2  lea     rdx, [rbp+57h+pExceptionObject]
0x1800022f6  mov     rcx, rsi
0x1800022f9  call    ?InsertIntoTimerWheelIfNecessary@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z; Broker::TimeBroker::InsertIntoTimerWheelIfNecessary(std::shared_ptr<Broker::TimeEvent>)
0x1800022fe  nop
0x1800022ff  lea     rcx, [rbp+57h+arg_0]; this
0x180002303  call    ??1BrokerLock@TimeBroker@Broker@@QEAA@XZ; Broker::TimeBroker::BrokerLock::~BrokerLock(void)
0x180002308  nop
0x180002309  test    rbx, rbx
0x18000230c  jz      short loc_180002316
0x18000230e  mov     rcx, rbx; this
0x180002311  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180002316  movaps  xmm6, [rsp+0B0h+var_40]
0x18000231b  add     rsp, 88h
0x180002322  pop     r15
0x180002324  pop     r14
0x180002326  pop     rdi
0x180002327  pop     rsi
0x180002328  pop     rbx
0x180002329  pop     rbp
0x18000232a  retn
0x18000232b  movups  xmmword ptr [rbp+57h+pExceptionObject+8], xmm0
0x18000232f  mov     [rbp+57h+var_58], 3
0x180002336  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x18000233d  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x180002341  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180002348  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000234c  call    _CxxThrowException_0
0x180002352  mov     r9, [r9]
0x180002355  jmp     loc_1800021C3
0x18000235a  test    eax, eax
0x18000235c  jz      loc_180002217
0x180002362  xorps   xmm0, xmm0
0x180002365  movups  xmmword ptr [rbp+57h+pExceptionObject+8], xmm0
0x180002369  mov     [rbp+57h+var_58], 3
0x180002370  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180002377  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x18000237b  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180002382  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180002386  call    _CxxThrowException_0
0x18000238c  xorps   xmm0, xmm0
0x18000238f  movups  xmmword ptr [rbp+57h+pExceptionObject+8], xmm0
0x180002393  mov     [rbp+57h+var_58], 3
0x18000239a  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x1800023a1  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x1800023a5  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x1800023ac  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800023b0  call    _CxxThrowException_0
0x1800023b6  xorps   xmm0, xmm0
0x1800023b9  movups  xmmword ptr [rbp+57h+pExceptionObject+8], xmm0
0x1800023bd  mov     [rbp+57h+var_58], 4
0x1800023c4  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x1800023cb  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x1800023cf  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800023d6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800023da  call    _CxxThrowException_0
0x1800023e0  mov     edi, 8
0x1800023e5  jmp     loc_1800022AE
```
