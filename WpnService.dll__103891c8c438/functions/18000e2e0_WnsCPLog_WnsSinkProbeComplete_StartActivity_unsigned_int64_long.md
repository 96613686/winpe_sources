# WnsCPLog::WnsSinkProbeComplete::StartActivity(unsigned __int64,long)

- ea: `0x18000e2e0`
- end: `0x18000e60c`
- name: `?StartActivity@WnsSinkProbeComplete@WnsCPLog@@QEAAX_KJ@Z`
- size: `812`
- prototype: `void __fastcall(WnsCPLog::WnsSinkProbeComplete *__hidden this, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000e010`

## callees

- `0x18000d830`
- `0x18000d8f0`
- `0x18000e2e0`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e331`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e331`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e347`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e35f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e3a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e347`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e35f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e3a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e4eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e4eb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e5da`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e5da`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000e384`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000e384`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000e48b`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000e48b`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000e470`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000e470`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e3c0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e3c0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e4ba`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e4ba`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkProbeComplete::StartActivity(
        WnsCPLog::WnsSinkProbeComplete *this,
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
    v22 = byte_180041685;
    UserData.Reserved = 2;
    v23 = 76;
    v24 = 1;
    LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(Ptr[4], (PCEVENT_DESCRIPTOR)&ProviderId, (LPCGUID)(v13 + 8), v14, 6u, &UserData);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000e2e0  mov     [rsp-8+arg_18], rbx
0x18000e2e5  push    rbp
0x18000e2e6  push    rdi
0x18000e2e7  push    r12
0x18000e2e9  push    r14
0x18000e2eb  push    r15
0x18000e2ed  lea     rbp, [rsp-37h]
0x18000e2f2  sub     rsp, 0E0h
0x18000e2f9  mov     rax, cs:__security_cookie
0x18000e300  xor     rax, rsp
0x18000e303  mov     [rbp+57h+var_30], rax
0x18000e307  mov     rbx, [rcx+118h]
0x18000e30e  xor     r12d, r12d
0x18000e311  mov     [rsp+100h+arg_8], rsi
0x18000e319  mov     r14d, r8d
0x18000e31c  mov     r15, rdx
0x18000e31f  mov     rdi, rcx
0x18000e322  test    rbx, rbx
0x18000e325  jz      short loc_18000E34F
0x18000e327  add     rbx, 108h
0x18000e32e  mov     rcx, rbx; SRWLock
0x18000e331  call    cs:__imp_AcquireSRWLockExclusive
0x18000e337  lea     rax, [rbp+57h+SRWLock]
0x18000e33b  mov     [rax], r12
0x18000e33e  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000e342  test    rcx, rcx
0x18000e345  jz      short loc_18000E368
0x18000e347  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e34d  jmp     short loc_18000E368
0x18000e34f  lea     rax, [rbp+57h+var_C0]
0x18000e353  mov     [rax], r12
0x18000e356  mov     rcx, [rbp+57h+var_C0]; SRWLock
0x18000e35a  test    rcx, rcx
0x18000e35d  jz      short loc_18000E365
0x18000e35f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e365  mov     rbx, r12
0x18000e368  mov     rsi, [rdi+110h]
0x18000e36f  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18000e374  mov     ecx, [rax]
0x18000e376  cmp     ecx, 5
0x18000e379  jbe     short loc_18000E38C
0x18000e37b  lea     rdx, [rsi+8]; ActivityId
0x18000e37f  mov     ecx, 3; ControlCode
0x18000e384  call    cs:__imp_EventActivityIdControl
0x18000e38a  jmp     short loc_18000E393
0x18000e38c  xorps   xmm0, xmm0
0x18000e38f  movups  xmmword ptr [rsi+8], xmm0
0x18000e393  mov     dword ptr [rsi], 1
0x18000e399  test    rbx, rbx
0x18000e39c  jz      short loc_18000E3A7
0x18000e39e  mov     rcx, rbx; SRWLock
0x18000e3a1  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e3a7  lea     r9, [rbp+57h+SRWLock]; lpContext
0x18000e3ab  mov     [rbp+57h+SRWLock], r12
0x18000e3af  lea     r8, [rbp+57h+fPending]; fPending
0x18000e3b3  mov     [rbp+57h+fPending], r12d
0x18000e3b7  xor     edx, edx; dwFlags
0x18000e3b9  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18000e3c0  call    cs:__imp_InitOnceBeginInitialize
0x18000e3c6  test    eax, eax
0x18000e3c8  jz      loc_18000E4C8
0x18000e3ce  cmp     [rbp+57h+fPending], r12d
0x18000e3d2  jz      loc_18000E4C8
0x18000e3d8  mov     [rsp+100h+arg_10], r13
0x18000e3e0  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18000e3e7  lea     r13, qword_18004A760
0x18000e3ee  mov     cs:qword_18004A768, r12
0x18000e3f5  mov     [rbp+57h+SRWLock], r13
0x18000e3f9  mov     cs:byte_18004A770, r12b
0x18000e400  mov     cs:dword_18004A774, r12d
0x18000e407  mov     cs:qword_18004A760, rax
0x18000e40e  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000e415  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x18000e41c  mov     cs:CallbackContext, rax
0x18000e423  call    atexit
0x18000e428  mov     rbx, cs:CallbackContext
0x18000e42f  mov     cs:qword_18004A768, rbx
0x18000e436  mov     cs:byte_18004A770, 1
0x18000e43d  mov     rax, [rbx+8]
0x18000e441  movups  xmm0, xmmword ptr [rax-10h]
0x18000e445  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x18000e449  cmp     [rbx+20h], r12
0x18000e44d  jz      short loc_18000E456
0x18000e44f  mov     ecx, 5
0x18000e454  int     29h; Win8: RtlFailFast(ecx)
0x18000e456  lea     r9, [rbx+20h]; RegHandle
0x18000e45a  mov     [rbx+28h], r12
0x18000e45e  mov     r8, rbx; CallbackContext
0x18000e461  mov     [rbx+30h], r12
0x18000e465  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000e46c  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x18000e470  call    cs:__imp_EventRegister
0x18000e476  test    eax, eax
0x18000e478  jnz     short loc_18000E491
0x18000e47a  mov     r8, [rbx+8]
0x18000e47e  mov     edx, 2
0x18000e483  mov     rcx, [rbx+20h]
0x18000e487  movzx   r9d, word ptr [r8]
0x18000e48b  call    cs:__imp_EventSetInformation
0x18000e491  mov     rax, cs:qword_18004A760
0x18000e498  mov     rcx, r13
0x18000e49b  mov     cs:dword_18004A774, 1
0x18000e4a5  mov     rax, [rax+8]
0x18000e4a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4ae  mov     r8, r13; lpContext
0x18000e4b1  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18000e4b8  xor     edx, edx; dwFlags
0x18000e4ba  call    cs:__imp_InitOnceComplete
0x18000e4c0  mov     r13, [rsp+100h+arg_10]
0x18000e4c8  mov     rax, [rbp+57h+SRWLock]
0x18000e4cc  mov     rsi, [rsp+100h+arg_8]
0x18000e4d4  mov     rbx, [rax+8]
0x18000e4d8  mov     eax, [rbx]
0x18000e4da  cmp     eax, 5
0x18000e4dd  jbe     loc_18000E5E0
0x18000e4e3  mov     [rbp+57h+fPending], r14d
0x18000e4e7  mov     [rbp+57h+var_B8], r15
0x18000e4eb  call    cs:__imp_GetCurrentThreadId
0x18000e4f1  mov     r8, [rdi+110h]
0x18000e4f8  mov     dword ptr [rbp+57h+var_C0], eax
0x18000e4fb  mov     [rbp+57h+var_B0], r12
0x18000e4ff  cmp     [r8+4], r12b
0x18000e503  jz      short loc_18000E521
0x18000e505  cmp     [r8+18h], r12d
0x18000e509  lea     r9, [r8+18h]
0x18000e50d  jnz     short loc_18000E524
0x18000e50f  cmp     [r9+4], r12d
0x18000e513  jnz     short loc_18000E524
0x18000e515  cmp     [r9+8], r12d
0x18000e519  jnz     short loc_18000E524
0x18000e51b  cmp     [r9+0Ch], r12d
0x18000e51f  jnz     short loc_18000E524
0x18000e521  mov     r9, r12; RelatedActivityId
0x18000e524  mov     [rbp+57h+var_38], 4
0x18000e52c  lea     rax, [rbp+57h+fPending]
0x18000e530  mov     [rbp+57h+var_40], rax
0x18000e534  lea     rcx, _TraceLoggingMetadata
0x18000e53b  mov     [rbp+57h+var_48], 8
0x18000e543  lea     rax, [rbp+57h+var_B8]
0x18000e547  mov     [rbp+57h+var_50], rax
0x18000e54b  lea     rdx, [rbp+57h+ProviderId]; EventDescriptor
0x18000e54f  mov     [rbp+57h+var_58], 4
0x18000e557  lea     rax, [rbp+57h+var_C0]
0x18000e55b  mov     [rbp+57h+var_60], rax
0x18000e55f  add     r8, 8; ActivityId
0x18000e563  lea     rax, [rbp+57h+var_B0]
0x18000e567  mov     [rbp+57h+var_68], 8
0x18000e56f  mov     [rbp+57h+var_70], rax
0x18000e573  movzx   eax, cs:word_18004167B
0x18000e57a  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x18000e57d  mov     rax, [rbx+8]
0x18000e581  mov     [rbp+57h+var_90.Ptr], rax
0x18000e585  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x18000e58c  mov     qword ptr [rbp+57h+ProviderId.Data4], r12
0x18000e590  movzx   eax, word ptr [rax]
0x18000e593  mov     [rbp+57h+var_90.Size], eax
0x18000e596  lea     rax, byte_180041685
0x18000e59d  mov     [rbp+57h+var_80], rax
0x18000e5a1  lea     rax, _TraceLoggingMetadataEnd
0x18000e5a8  sub     eax, ecx
0x18000e5aa  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x18000e5b1  mov     [rbp+57h+var_78], 4Ch ; 'L'
0x18000e5b8  mov     [rbp+57h+var_74], 1
0x18000e5bf  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000e5c2  mov     eax, dword ptr [rbp+57h+SRWLock]
0x18000e5c5  mov     rcx, [rbx+20h]; RegHandle
0x18000e5c9  lea     rax, [rbp+57h+var_90]
0x18000e5cd  mov     [rsp+100h+UserData], rax; UserData
0x18000e5d2  mov     [rsp+100h+UserDataCount], 6; UserDataCount
0x18000e5da  call    cs:__imp_EventWriteTransfer
0x18000e5e0  mov     rcx, rdi
0x18000e5e3  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18000e5e8  mov     rcx, [rbp+57h+var_30]
0x18000e5ec  xor     rcx, rsp; StackCookie
0x18000e5ef  call    __security_check_cookie
0x18000e5f4  mov     rbx, [rsp+100h+arg_18]
0x18000e5fc  add     rsp, 0E0h
0x18000e603  pop     r15
0x18000e605  pop     r14
0x18000e607  pop     r12
0x18000e609  pop     rdi
0x18000e60a  pop     rbp
0x18000e60b  retn
```
