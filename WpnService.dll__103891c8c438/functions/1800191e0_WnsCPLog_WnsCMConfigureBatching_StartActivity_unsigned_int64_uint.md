# WnsCPLog::WnsCMConfigureBatching::StartActivity(unsigned __int64,uint)

- ea: `0x1800191e0`
- end: `0x18001950c`
- name: `?StartActivity@WnsCMConfigureBatching@WnsCPLog@@QEAAX_KI@Z`
- size: `812`
- prototype: `void __fastcall(WnsCPLog::WnsCMConfigureBatching *__hidden this, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025730`

## callees

- `0x18000d830`
- `0x18000d8f0`
- `0x1800191e0`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019231`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019231`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019247`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001925f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800192a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019247`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001925f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800192a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800193eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800193eb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800194da`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800194da`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019284`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019284`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001938b`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001938b`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180019370`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180019370`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800192c0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800192c0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800193ba`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800193ba`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMConfigureBatching::StartActivity(
        WnsCPLog::WnsCMConfigureBatching *this,
        __int64 a2,
        WINBOOL a3)
{
  RTL_SRWLOCK *v3; // rbx
  RTL_SRWLOCK *v7; // rbx
  __int64 v8; // rsi
  _QWORD *v9; // rbx
  ULONGLONG *v10; // r9
  _QWORD *Ptr; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  const GUID *v14; // r9
  WINBOOL fPending; // [rsp+30h] [rbp-79h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-71h] BYREF
  PSRWLOCK v17; // [rsp+40h] [rbp-69h] BYREF
  __int64 v18; // [rsp+48h] [rbp-61h] BYREF
  __int64 v19; // [rsp+50h] [rbp-59h] BYREF
  GUID ProviderId; // [rsp+58h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-39h] BYREF
  char *v22; // [rsp+80h] [rbp-29h]
  int v23; // [rsp+88h] [rbp-21h]
  int v24; // [rsp+8Ch] [rbp-1Dh]
  __int64 *v25; // [rsp+90h] [rbp-19h]
  __int64 v26; // [rsp+98h] [rbp-11h]
  PSRWLOCK *v27; // [rsp+A0h] [rbp-9h]
  __int64 v28; // [rsp+A8h] [rbp-1h]
  __int64 *v29; // [rsp+B0h] [rbp+7h]
  __int64 v30; // [rsp+B8h] [rbp+Fh]
  WINBOOL *p_fPending; // [rsp+C0h] [rbp+17h]
  __int64 v32; // [rsp+C8h] [rbp+1Fh]

  v3 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  if ( v3 )
  {
    v7 = v3 + 33;
    AcquireSRWLockExclusive(v7);
    SRWLock = 0;
  }
  else
  {
    v17 = 0;
    v7 = 0;
  }
  v8 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)WnsCPTracelogger::Provider() <= 5u )
    *(_OWORD *)(v8 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v8 + 8));
  *(_DWORD *)v8 = 1;
  if ( v7 )
    ReleaseSRWLockExclusive(v7);
  SRWLock = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock)
    && fPending )
  {
    qword_18004A768 = 0;
    SRWLock = (PSRWLOCK)&qword_18004A760;
    byte_18004A770 = 0;
    dword_18004A774 = 0;
    qword_18004A760 = (__int64)&wil::details::FeatureLogging::`vftable';
    CallbackContext = &`WnsCPTracelogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_633a74d489e420a2ff0e92495a1626f6_::_lambda_invoker_cdecl_);
    v9 = CallbackContext;
    qword_18004A768 = (__int64)CallbackContext;
    byte_18004A770 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    v10 = (ULONGLONG *)((char *)CallbackContext + 32);
    *((_QWORD *)CallbackContext + 5) = 0;
    v9[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v9, v10) )
      EventSetInformation(v9[4], 2, v9[1], *(unsigned __int16 *)v9[1]);
    dword_18004A774 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18004A760 + 8))(&qword_18004A760);
    InitOnceComplete(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &qword_18004A760);
  }
  Ptr = SRWLock[1].Ptr;
  if ( *(_DWORD *)Ptr > 5u )
  {
    fPending = a3;
    v18 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v13 = *((_QWORD *)this + 34);
    LODWORD(v17) = CurrentThreadId;
    v19 = 0;
    if ( !*(_BYTE *)(v13 + 4)
      || (v14 = (const GUID *)(v13 + 24), !*(_DWORD *)(v13 + 24))
      && !*(_DWORD *)(v13 + 28)
      && !*(_DWORD *)(v13 + 32)
      && !*(_DWORD *)(v13 + 36) )
    {
      v14 = 0;
    }
    v32 = 4;
    p_fPending = &fPending;
    v30 = 8;
    v29 = &v18;
    v28 = 4;
    v27 = &v17;
    v26 = 8;
    v25 = &v19;
    *(_DWORD *)&ProviderId.Data2 = 261;
    UserData.Ptr = Ptr[1];
    ProviderId.Data1 = 184549376;
    *(_QWORD *)ProviderId.Data4 = 0;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v22 = byte_18003F475;
    UserData.Reserved = 2;
    v23 = 89;
    v24 = 1;
    LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(Ptr[4], (PCEVENT_DESCRIPTOR)&ProviderId, (LPCGUID)(v13 + 8), v14, 6u, &UserData);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800191e0  mov     [rsp-8+arg_18], rbx
0x1800191e5  push    rbp
0x1800191e6  push    rdi
0x1800191e7  push    r12
0x1800191e9  push    r14
0x1800191eb  push    r15
0x1800191ed  lea     rbp, [rsp-37h]
0x1800191f2  sub     rsp, 0E0h
0x1800191f9  mov     rax, cs:__security_cookie
0x180019200  xor     rax, rsp
0x180019203  mov     [rbp+57h+var_30], rax
0x180019207  mov     rbx, [rcx+118h]
0x18001920e  xor     r12d, r12d
0x180019211  mov     [rsp+100h+arg_8], rsi
0x180019219  mov     r14d, r8d
0x18001921c  mov     r15, rdx
0x18001921f  mov     rdi, rcx
0x180019222  test    rbx, rbx
0x180019225  jz      short loc_18001924F
0x180019227  add     rbx, 108h
0x18001922e  mov     rcx, rbx; SRWLock
0x180019231  call    cs:__imp_AcquireSRWLockExclusive
0x180019237  lea     rax, [rbp+57h+SRWLock]
0x18001923b  mov     [rax], r12
0x18001923e  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180019242  test    rcx, rcx
0x180019245  jz      short loc_180019268
0x180019247  call    cs:__imp_ReleaseSRWLockExclusive
0x18001924d  jmp     short loc_180019268
0x18001924f  lea     rax, [rbp+57h+var_C0]
0x180019253  mov     [rax], r12
0x180019256  mov     rcx, [rbp+57h+var_C0]; SRWLock
0x18001925a  test    rcx, rcx
0x18001925d  jz      short loc_180019265
0x18001925f  call    cs:__imp_ReleaseSRWLockExclusive
0x180019265  mov     rbx, r12
0x180019268  mov     rsi, [rdi+110h]
0x18001926f  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180019274  mov     ecx, [rax]
0x180019276  cmp     ecx, 5
0x180019279  jbe     short loc_18001928C
0x18001927b  lea     rdx, [rsi+8]; ActivityId
0x18001927f  mov     ecx, 3; ControlCode
0x180019284  call    cs:__imp_EventActivityIdControl
0x18001928a  jmp     short loc_180019293
0x18001928c  xorps   xmm0, xmm0
0x18001928f  movups  xmmword ptr [rsi+8], xmm0
0x180019293  mov     dword ptr [rsi], 1
0x180019299  test    rbx, rbx
0x18001929c  jz      short loc_1800192A7
0x18001929e  mov     rcx, rbx; SRWLock
0x1800192a1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800192a7  lea     r9, [rbp+57h+SRWLock]; lpContext
0x1800192ab  mov     [rbp+57h+SRWLock], r12
0x1800192af  lea     r8, [rbp+57h+fPending]; fPending
0x1800192b3  mov     [rbp+57h+fPending], r12d
0x1800192b7  xor     edx, edx; dwFlags
0x1800192b9  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x1800192c0  call    cs:__imp_InitOnceBeginInitialize
0x1800192c6  test    eax, eax
0x1800192c8  jz      loc_1800193C8
0x1800192ce  cmp     [rbp+57h+fPending], r12d
0x1800192d2  jz      loc_1800193C8
0x1800192d8  mov     [rsp+100h+arg_10], r13
0x1800192e0  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x1800192e7  lea     r13, qword_18004A760
0x1800192ee  mov     cs:qword_18004A768, r12
0x1800192f5  mov     [rbp+57h+SRWLock], r13
0x1800192f9  mov     cs:byte_18004A770, r12b
0x180019300  mov     cs:dword_18004A774, r12d
0x180019307  mov     cs:qword_18004A760, rax
0x18001930e  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180019315  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x18001931c  mov     cs:CallbackContext, rax
0x180019323  call    atexit
0x180019328  mov     rbx, cs:CallbackContext
0x18001932f  mov     cs:qword_18004A768, rbx
0x180019336  mov     cs:byte_18004A770, 1
0x18001933d  mov     rax, [rbx+8]
0x180019341  movups  xmm0, xmmword ptr [rax-10h]
0x180019345  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x180019349  cmp     [rbx+20h], r12
0x18001934d  jz      short loc_180019356
0x18001934f  mov     ecx, 5
0x180019354  int     29h; Win8: RtlFailFast(ecx)
0x180019356  lea     r9, [rbx+20h]; RegHandle
0x18001935a  mov     [rbx+28h], r12
0x18001935e  mov     r8, rbx; CallbackContext
0x180019361  mov     [rbx+30h], r12
0x180019365  lea     rdx, _tlgEnableCallback; EnableCallback
0x18001936c  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x180019370  call    cs:__imp_EventRegister
0x180019376  test    eax, eax
0x180019378  jnz     short loc_180019391
0x18001937a  mov     r8, [rbx+8]
0x18001937e  mov     edx, 2
0x180019383  mov     rcx, [rbx+20h]
0x180019387  movzx   r9d, word ptr [r8]
0x18001938b  call    cs:__imp_EventSetInformation
0x180019391  mov     rax, cs:qword_18004A760
0x180019398  mov     rcx, r13
0x18001939b  mov     cs:dword_18004A774, 1
0x1800193a5  mov     rax, [rax+8]
0x1800193a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193ae  mov     r8, r13; lpContext
0x1800193b1  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x1800193b8  xor     edx, edx; dwFlags
0x1800193ba  call    cs:__imp_InitOnceComplete
0x1800193c0  mov     r13, [rsp+100h+arg_10]
0x1800193c8  mov     rax, [rbp+57h+SRWLock]
0x1800193cc  mov     rsi, [rsp+100h+arg_8]
0x1800193d4  mov     rbx, [rax+8]
0x1800193d8  mov     eax, [rbx]
0x1800193da  cmp     eax, 5
0x1800193dd  jbe     loc_1800194E0
0x1800193e3  mov     [rbp+57h+fPending], r14d
0x1800193e7  mov     [rbp+57h+var_B8], r15
0x1800193eb  call    cs:__imp_GetCurrentThreadId
0x1800193f1  mov     r8, [rdi+110h]
0x1800193f8  mov     dword ptr [rbp+57h+var_C0], eax
0x1800193fb  mov     [rbp+57h+var_B0], r12
0x1800193ff  cmp     [r8+4], r12b
0x180019403  jz      short loc_180019421
0x180019405  cmp     [r8+18h], r12d
0x180019409  lea     r9, [r8+18h]
0x18001940d  jnz     short loc_180019424
0x18001940f  cmp     [r9+4], r12d
0x180019413  jnz     short loc_180019424
0x180019415  cmp     [r9+8], r12d
0x180019419  jnz     short loc_180019424
0x18001941b  cmp     [r9+0Ch], r12d
0x18001941f  jnz     short loc_180019424
0x180019421  mov     r9, r12; RelatedActivityId
0x180019424  mov     [rbp+57h+var_38], 4
0x18001942c  lea     rax, [rbp+57h+fPending]
0x180019430  mov     [rbp+57h+var_40], rax
0x180019434  lea     rcx, _TraceLoggingMetadata
0x18001943b  mov     [rbp+57h+var_48], 8
0x180019443  lea     rax, [rbp+57h+var_B8]
0x180019447  mov     [rbp+57h+var_50], rax
0x18001944b  lea     rdx, [rbp+57h+ProviderId]; EventDescriptor
0x18001944f  mov     [rbp+57h+var_58], 4
0x180019457  lea     rax, [rbp+57h+var_C0]
0x18001945b  mov     [rbp+57h+var_60], rax
0x18001945f  add     r8, 8; ActivityId
0x180019463  lea     rax, [rbp+57h+var_B0]
0x180019467  mov     [rbp+57h+var_68], 8
0x18001946f  mov     [rbp+57h+var_70], rax
0x180019473  movzx   eax, cs:word_18003F46B
0x18001947a  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x18001947d  mov     rax, [rbx+8]
0x180019481  mov     [rbp+57h+var_90.Ptr], rax
0x180019485  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x18001948c  mov     qword ptr [rbp+57h+ProviderId.Data4], r12
0x180019490  movzx   eax, word ptr [rax]
0x180019493  mov     [rbp+57h+var_90.Size], eax
0x180019496  lea     rax, byte_18003F475
0x18001949d  mov     [rbp+57h+var_80], rax
0x1800194a1  lea     rax, _TraceLoggingMetadataEnd
0x1800194a8  sub     eax, ecx
0x1800194aa  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x1800194b1  mov     [rbp+57h+var_78], 59h ; 'Y'
0x1800194b8  mov     [rbp+57h+var_74], 1
0x1800194bf  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800194c2  mov     eax, dword ptr [rbp+57h+SRWLock]
0x1800194c5  mov     rcx, [rbx+20h]; RegHandle
0x1800194c9  lea     rax, [rbp+57h+var_90]
0x1800194cd  mov     [rsp+100h+UserData], rax; UserData
0x1800194d2  mov     [rsp+100h+UserDataCount], 6; UserDataCount
0x1800194da  call    cs:__imp_EventWriteTransfer
0x1800194e0  mov     rcx, rdi
0x1800194e3  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800194e8  mov     rcx, [rbp+57h+var_30]
0x1800194ec  xor     rcx, rsp; StackCookie
0x1800194ef  call    __security_check_cookie
0x1800194f4  mov     rbx, [rsp+100h+arg_18]
0x1800194fc  add     rsp, 0E0h
0x180019503  pop     r15
0x180019505  pop     r14
0x180019507  pop     r12
0x180019509  pop     rdi
0x18001950a  pop     rbp
0x18001950b  retn
```
