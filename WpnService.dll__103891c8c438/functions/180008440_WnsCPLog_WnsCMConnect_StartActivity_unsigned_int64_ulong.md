# WnsCPLog::WnsCMConnect::StartActivity(unsigned __int64,ulong)

- ea: `0x180008440`
- end: `0x18000876c`
- name: `?StartActivity@WnsCMConnect@WnsCPLog@@QEAAX_KK@Z`
- size: `812`
- prototype: `void __fastcall(WnsCPLog::WnsCMConnect *__hidden this, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008780`

## callees

- `0x180008440`
- `0x18000d830`
- `0x18000d8f0`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008491`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008491`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008501`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008501`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000864b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000864b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000873a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000873a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800084e4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800084e4`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800085eb`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800085eb`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800085d0`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800085d0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008520`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008520`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000861a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000861a`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMConnect::StartActivity(WnsCPLog::WnsCMConnect *this, __int64 a2, WINBOOL a3)
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
  int *v22; // [rsp+80h] [rbp-29h]
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
    v22 = &dword_18003F874;
    UserData.Reserved = 2;
    v23 = 73;
    v24 = 1;
    LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(Ptr[4], (PCEVENT_DESCRIPTOR)&ProviderId, (LPCGUID)(v13 + 8), v14, 6u, &UserData);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180008440  mov     [rsp-8+arg_18], rbx
0x180008445  push    rbp
0x180008446  push    rdi
0x180008447  push    r12
0x180008449  push    r14
0x18000844b  push    r15
0x18000844d  lea     rbp, [rsp-37h]
0x180008452  sub     rsp, 0E0h
0x180008459  mov     rax, cs:__security_cookie
0x180008460  xor     rax, rsp
0x180008463  mov     [rbp+57h+var_30], rax
0x180008467  mov     rbx, [rcx+118h]
0x18000846e  xor     r12d, r12d
0x180008471  mov     [rsp+100h+arg_8], rsi
0x180008479  mov     r14d, r8d
0x18000847c  mov     r15, rdx
0x18000847f  mov     rdi, rcx
0x180008482  test    rbx, rbx
0x180008485  jz      short loc_1800084AF
0x180008487  add     rbx, 108h
0x18000848e  mov     rcx, rbx; SRWLock
0x180008491  call    cs:__imp_AcquireSRWLockExclusive
0x180008497  lea     rax, [rbp+57h+SRWLock]
0x18000849b  mov     [rax], r12
0x18000849e  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800084a2  test    rcx, rcx
0x1800084a5  jz      short loc_1800084C8
0x1800084a7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800084ad  jmp     short loc_1800084C8
0x1800084af  lea     rax, [rbp+57h+var_C0]
0x1800084b3  mov     [rax], r12
0x1800084b6  mov     rcx, [rbp+57h+var_C0]; SRWLock
0x1800084ba  test    rcx, rcx
0x1800084bd  jz      short loc_1800084C5
0x1800084bf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800084c5  mov     rbx, r12
0x1800084c8  mov     rsi, [rdi+110h]
0x1800084cf  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x1800084d4  mov     ecx, [rax]
0x1800084d6  cmp     ecx, 5
0x1800084d9  jbe     short loc_1800084EC
0x1800084db  lea     rdx, [rsi+8]; ActivityId
0x1800084df  mov     ecx, 3; ControlCode
0x1800084e4  call    cs:__imp_EventActivityIdControl
0x1800084ea  jmp     short loc_1800084F3
0x1800084ec  xorps   xmm0, xmm0
0x1800084ef  movups  xmmword ptr [rsi+8], xmm0
0x1800084f3  mov     dword ptr [rsi], 1
0x1800084f9  test    rbx, rbx
0x1800084fc  jz      short loc_180008507
0x1800084fe  mov     rcx, rbx; SRWLock
0x180008501  call    cs:__imp_ReleaseSRWLockExclusive
0x180008507  lea     r9, [rbp+57h+SRWLock]; lpContext
0x18000850b  mov     [rbp+57h+SRWLock], r12
0x18000850f  lea     r8, [rbp+57h+fPending]; fPending
0x180008513  mov     [rbp+57h+fPending], r12d
0x180008517  xor     edx, edx; dwFlags
0x180008519  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x180008520  call    cs:__imp_InitOnceBeginInitialize
0x180008526  test    eax, eax
0x180008528  jz      loc_180008628
0x18000852e  cmp     [rbp+57h+fPending], r12d
0x180008532  jz      loc_180008628
0x180008538  mov     [rsp+100h+arg_10], r13
0x180008540  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180008547  lea     r13, qword_18004A760
0x18000854e  mov     cs:qword_18004A768, r12
0x180008555  mov     [rbp+57h+SRWLock], r13
0x180008559  mov     cs:byte_18004A770, r12b
0x180008560  mov     cs:dword_18004A774, r12d
0x180008567  mov     cs:qword_18004A760, rax
0x18000856e  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180008575  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x18000857c  mov     cs:CallbackContext, rax
0x180008583  call    atexit
0x180008588  mov     rbx, cs:CallbackContext
0x18000858f  mov     cs:qword_18004A768, rbx
0x180008596  mov     cs:byte_18004A770, 1
0x18000859d  mov     rax, [rbx+8]
0x1800085a1  movups  xmm0, xmmword ptr [rax-10h]
0x1800085a5  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x1800085a9  cmp     [rbx+20h], r12
0x1800085ad  jz      short loc_1800085B6
0x1800085af  mov     ecx, 5
0x1800085b4  int     29h; Win8: RtlFailFast(ecx)
0x1800085b6  lea     r9, [rbx+20h]; RegHandle
0x1800085ba  mov     [rbx+28h], r12
0x1800085be  mov     r8, rbx; CallbackContext
0x1800085c1  mov     [rbx+30h], r12
0x1800085c5  lea     rdx, _tlgEnableCallback; EnableCallback
0x1800085cc  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x1800085d0  call    cs:__imp_EventRegister
0x1800085d6  test    eax, eax
0x1800085d8  jnz     short loc_1800085F1
0x1800085da  mov     r8, [rbx+8]
0x1800085de  mov     edx, 2
0x1800085e3  mov     rcx, [rbx+20h]
0x1800085e7  movzx   r9d, word ptr [r8]
0x1800085eb  call    cs:__imp_EventSetInformation
0x1800085f1  mov     rax, cs:qword_18004A760
0x1800085f8  mov     rcx, r13
0x1800085fb  mov     cs:dword_18004A774, 1
0x180008605  mov     rax, [rax+8]
0x180008609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000860e  mov     r8, r13; lpContext
0x180008611  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x180008618  xor     edx, edx; dwFlags
0x18000861a  call    cs:__imp_InitOnceComplete
0x180008620  mov     r13, [rsp+100h+arg_10]
0x180008628  mov     rax, [rbp+57h+SRWLock]
0x18000862c  mov     rsi, [rsp+100h+arg_8]
0x180008634  mov     rbx, [rax+8]
0x180008638  mov     eax, [rbx]
0x18000863a  cmp     eax, 5
0x18000863d  jbe     loc_180008740
0x180008643  mov     [rbp+57h+fPending], r14d
0x180008647  mov     [rbp+57h+var_B8], r15
0x18000864b  call    cs:__imp_GetCurrentThreadId
0x180008651  mov     r8, [rdi+110h]
0x180008658  mov     dword ptr [rbp+57h+var_C0], eax
0x18000865b  mov     [rbp+57h+var_B0], r12
0x18000865f  cmp     [r8+4], r12b
0x180008663  jz      short loc_180008681
0x180008665  cmp     [r8+18h], r12d
0x180008669  lea     r9, [r8+18h]
0x18000866d  jnz     short loc_180008684
0x18000866f  cmp     [r9+4], r12d
0x180008673  jnz     short loc_180008684
0x180008675  cmp     [r9+8], r12d
0x180008679  jnz     short loc_180008684
0x18000867b  cmp     [r9+0Ch], r12d
0x18000867f  jnz     short loc_180008684
0x180008681  mov     r9, r12; RelatedActivityId
0x180008684  mov     [rbp+57h+var_38], 4
0x18000868c  lea     rax, [rbp+57h+fPending]
0x180008690  mov     [rbp+57h+var_40], rax
0x180008694  lea     rcx, _TraceLoggingMetadata
0x18000869b  mov     [rbp+57h+var_48], 8
0x1800086a3  lea     rax, [rbp+57h+var_B8]
0x1800086a7  mov     [rbp+57h+var_50], rax
0x1800086ab  lea     rdx, [rbp+57h+ProviderId]; EventDescriptor
0x1800086af  mov     [rbp+57h+var_58], 4
0x1800086b7  lea     rax, [rbp+57h+var_C0]
0x1800086bb  mov     [rbp+57h+var_60], rax
0x1800086bf  add     r8, 8; ActivityId
0x1800086c3  lea     rax, [rbp+57h+var_B0]
0x1800086c7  mov     [rbp+57h+var_68], 8
0x1800086cf  mov     [rbp+57h+var_70], rax
0x1800086d3  movzx   eax, cs:word_18003F86A
0x1800086da  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x1800086dd  mov     rax, [rbx+8]
0x1800086e1  mov     [rbp+57h+var_90.Ptr], rax
0x1800086e5  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x1800086ec  mov     qword ptr [rbp+57h+ProviderId.Data4], r12
0x1800086f0  movzx   eax, word ptr [rax]
0x1800086f3  mov     [rbp+57h+var_90.Size], eax
0x1800086f6  lea     rax, dword_18003F874
0x1800086fd  mov     [rbp+57h+var_80], rax
0x180008701  lea     rax, _TraceLoggingMetadataEnd
0x180008708  sub     eax, ecx
0x18000870a  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x180008711  mov     [rbp+57h+var_78], 49h ; 'I'
0x180008718  mov     [rbp+57h+var_74], 1
0x18000871f  mov     dword ptr [rbp+57h+SRWLock], eax
0x180008722  mov     eax, dword ptr [rbp+57h+SRWLock]
0x180008725  mov     rcx, [rbx+20h]; RegHandle
0x180008729  lea     rax, [rbp+57h+var_90]
0x18000872d  mov     [rsp+100h+UserData], rax; UserData
0x180008732  mov     [rsp+100h+UserDataCount], 6; UserDataCount
0x18000873a  call    cs:__imp_EventWriteTransfer
0x180008740  mov     rcx, rdi
0x180008743  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180008748  mov     rcx, [rbp+57h+var_30]
0x18000874c  xor     rcx, rsp; StackCookie
0x18000874f  call    __security_check_cookie
0x180008754  mov     rbx, [rsp+100h+arg_18]
0x18000875c  add     rsp, 0E0h
0x180008763  pop     r15
0x180008765  pop     r14
0x180008767  pop     r12
0x180008769  pop     rdi
0x18000876a  pop     rbp
0x18000876b  retn
```
