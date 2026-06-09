# WnsCPLog::WnsCPTSetModeForUser::StartActivity(unsigned __int64,int)

- ea: `0x18000b380`
- end: `0x18000b6ac`
- name: `?StartActivity@WnsCPTSetModeForUser@WnsCPLog@@QEAAX_KH@Z`
- size: `812`
- prototype: `void __fastcall(WnsCPLog::WnsCPTSetModeForUser *__hidden this, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009250`

## callees

- `0x18000b380`
- `0x18000d830`
- `0x18000d8f0`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b3d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b3d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b3e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b3ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b441`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b3e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b3ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b441`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b58b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b58b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b67a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b67a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b424`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b424`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000b52b`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000b52b`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000b510`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000b510`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000b460`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000b460`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000b55a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000b55a`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCPTSetModeForUser::StartActivity(
        WnsCPLog::WnsCPTSetModeForUser *this,
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
    v22 = byte_180040A3B;
    UserData.Reserved = 2;
    v23 = 81;
    v24 = 1;
    LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(Ptr[4], (PCEVENT_DESCRIPTOR)&ProviderId, (LPCGUID)(v13 + 8), v14, 6u, &UserData);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000b380  mov     [rsp-8+arg_18], rbx
0x18000b385  push    rbp
0x18000b386  push    rdi
0x18000b387  push    r12
0x18000b389  push    r14
0x18000b38b  push    r15
0x18000b38d  lea     rbp, [rsp-37h]
0x18000b392  sub     rsp, 0E0h
0x18000b399  mov     rax, cs:__security_cookie
0x18000b3a0  xor     rax, rsp
0x18000b3a3  mov     [rbp+57h+var_30], rax
0x18000b3a7  mov     rbx, [rcx+118h]
0x18000b3ae  xor     r12d, r12d
0x18000b3b1  mov     [rsp+100h+arg_8], rsi
0x18000b3b9  mov     r14d, r8d
0x18000b3bc  mov     r15, rdx
0x18000b3bf  mov     rdi, rcx
0x18000b3c2  test    rbx, rbx
0x18000b3c5  jz      short loc_18000B3EF
0x18000b3c7  add     rbx, 108h
0x18000b3ce  mov     rcx, rbx; SRWLock
0x18000b3d1  call    cs:__imp_AcquireSRWLockExclusive
0x18000b3d7  lea     rax, [rbp+57h+SRWLock]
0x18000b3db  mov     [rax], r12
0x18000b3de  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000b3e2  test    rcx, rcx
0x18000b3e5  jz      short loc_18000B408
0x18000b3e7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b3ed  jmp     short loc_18000B408
0x18000b3ef  lea     rax, [rbp+57h+var_C0]
0x18000b3f3  mov     [rax], r12
0x18000b3f6  mov     rcx, [rbp+57h+var_C0]; SRWLock
0x18000b3fa  test    rcx, rcx
0x18000b3fd  jz      short loc_18000B405
0x18000b3ff  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b405  mov     rbx, r12
0x18000b408  mov     rsi, [rdi+110h]
0x18000b40f  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18000b414  mov     ecx, [rax]
0x18000b416  cmp     ecx, 5
0x18000b419  jbe     short loc_18000B42C
0x18000b41b  lea     rdx, [rsi+8]; ActivityId
0x18000b41f  mov     ecx, 3; ControlCode
0x18000b424  call    cs:__imp_EventActivityIdControl
0x18000b42a  jmp     short loc_18000B433
0x18000b42c  xorps   xmm0, xmm0
0x18000b42f  movups  xmmword ptr [rsi+8], xmm0
0x18000b433  mov     dword ptr [rsi], 1
0x18000b439  test    rbx, rbx
0x18000b43c  jz      short loc_18000B447
0x18000b43e  mov     rcx, rbx; SRWLock
0x18000b441  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b447  lea     r9, [rbp+57h+SRWLock]; lpContext
0x18000b44b  mov     [rbp+57h+SRWLock], r12
0x18000b44f  lea     r8, [rbp+57h+fPending]; fPending
0x18000b453  mov     [rbp+57h+fPending], r12d
0x18000b457  xor     edx, edx; dwFlags
0x18000b459  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18000b460  call    cs:__imp_InitOnceBeginInitialize
0x18000b466  test    eax, eax
0x18000b468  jz      loc_18000B568
0x18000b46e  cmp     [rbp+57h+fPending], r12d
0x18000b472  jz      loc_18000B568
0x18000b478  mov     [rsp+100h+arg_10], r13
0x18000b480  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18000b487  lea     r13, qword_18004A760
0x18000b48e  mov     cs:qword_18004A768, r12
0x18000b495  mov     [rbp+57h+SRWLock], r13
0x18000b499  mov     cs:byte_18004A770, r12b
0x18000b4a0  mov     cs:dword_18004A774, r12d
0x18000b4a7  mov     cs:qword_18004A760, rax
0x18000b4ae  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000b4b5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x18000b4bc  mov     cs:CallbackContext, rax
0x18000b4c3  call    atexit
0x18000b4c8  mov     rbx, cs:CallbackContext
0x18000b4cf  mov     cs:qword_18004A768, rbx
0x18000b4d6  mov     cs:byte_18004A770, 1
0x18000b4dd  mov     rax, [rbx+8]
0x18000b4e1  movups  xmm0, xmmword ptr [rax-10h]
0x18000b4e5  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x18000b4e9  cmp     [rbx+20h], r12
0x18000b4ed  jz      short loc_18000B4F6
0x18000b4ef  mov     ecx, 5
0x18000b4f4  int     29h; Win8: RtlFailFast(ecx)
0x18000b4f6  lea     r9, [rbx+20h]; RegHandle
0x18000b4fa  mov     [rbx+28h], r12
0x18000b4fe  mov     r8, rbx; CallbackContext
0x18000b501  mov     [rbx+30h], r12
0x18000b505  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000b50c  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x18000b510  call    cs:__imp_EventRegister
0x18000b516  test    eax, eax
0x18000b518  jnz     short loc_18000B531
0x18000b51a  mov     r8, [rbx+8]
0x18000b51e  mov     edx, 2
0x18000b523  mov     rcx, [rbx+20h]
0x18000b527  movzx   r9d, word ptr [r8]
0x18000b52b  call    cs:__imp_EventSetInformation
0x18000b531  mov     rax, cs:qword_18004A760
0x18000b538  mov     rcx, r13
0x18000b53b  mov     cs:dword_18004A774, 1
0x18000b545  mov     rax, [rax+8]
0x18000b549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b54e  mov     r8, r13; lpContext
0x18000b551  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18000b558  xor     edx, edx; dwFlags
0x18000b55a  call    cs:__imp_InitOnceComplete
0x18000b560  mov     r13, [rsp+100h+arg_10]
0x18000b568  mov     rax, [rbp+57h+SRWLock]
0x18000b56c  mov     rsi, [rsp+100h+arg_8]
0x18000b574  mov     rbx, [rax+8]
0x18000b578  mov     eax, [rbx]
0x18000b57a  cmp     eax, 5
0x18000b57d  jbe     loc_18000B680
0x18000b583  mov     [rbp+57h+fPending], r14d
0x18000b587  mov     [rbp+57h+var_B8], r15
0x18000b58b  call    cs:__imp_GetCurrentThreadId
0x18000b591  mov     r8, [rdi+110h]
0x18000b598  mov     dword ptr [rbp+57h+var_C0], eax
0x18000b59b  mov     [rbp+57h+var_B0], r12
0x18000b59f  cmp     [r8+4], r12b
0x18000b5a3  jz      short loc_18000B5C1
0x18000b5a5  cmp     [r8+18h], r12d
0x18000b5a9  lea     r9, [r8+18h]
0x18000b5ad  jnz     short loc_18000B5C4
0x18000b5af  cmp     [r9+4], r12d
0x18000b5b3  jnz     short loc_18000B5C4
0x18000b5b5  cmp     [r9+8], r12d
0x18000b5b9  jnz     short loc_18000B5C4
0x18000b5bb  cmp     [r9+0Ch], r12d
0x18000b5bf  jnz     short loc_18000B5C4
0x18000b5c1  mov     r9, r12; RelatedActivityId
0x18000b5c4  mov     [rbp+57h+var_38], 4
0x18000b5cc  lea     rax, [rbp+57h+fPending]
0x18000b5d0  mov     [rbp+57h+var_40], rax
0x18000b5d4  lea     rcx, _TraceLoggingMetadata
0x18000b5db  mov     [rbp+57h+var_48], 8
0x18000b5e3  lea     rax, [rbp+57h+var_B8]
0x18000b5e7  mov     [rbp+57h+var_50], rax
0x18000b5eb  lea     rdx, [rbp+57h+ProviderId]; EventDescriptor
0x18000b5ef  mov     [rbp+57h+var_58], 4
0x18000b5f7  lea     rax, [rbp+57h+var_C0]
0x18000b5fb  mov     [rbp+57h+var_60], rax
0x18000b5ff  add     r8, 8; ActivityId
0x18000b603  lea     rax, [rbp+57h+var_B0]
0x18000b607  mov     [rbp+57h+var_68], 8
0x18000b60f  mov     [rbp+57h+var_70], rax
0x18000b613  movzx   eax, cs:word_180040A31
0x18000b61a  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x18000b61d  mov     rax, [rbx+8]
0x18000b621  mov     [rbp+57h+var_90.Ptr], rax
0x18000b625  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x18000b62c  mov     qword ptr [rbp+57h+ProviderId.Data4], r12
0x18000b630  movzx   eax, word ptr [rax]
0x18000b633  mov     [rbp+57h+var_90.Size], eax
0x18000b636  lea     rax, byte_180040A3B
0x18000b63d  mov     [rbp+57h+var_80], rax
0x18000b641  lea     rax, _TraceLoggingMetadataEnd
0x18000b648  sub     eax, ecx
0x18000b64a  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x18000b651  mov     [rbp+57h+var_78], 51h ; 'Q'
0x18000b658  mov     [rbp+57h+var_74], 1
0x18000b65f  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000b662  mov     eax, dword ptr [rbp+57h+SRWLock]
0x18000b665  mov     rcx, [rbx+20h]; RegHandle
0x18000b669  lea     rax, [rbp+57h+var_90]
0x18000b66d  mov     [rsp+100h+UserData], rax; UserData
0x18000b672  mov     [rsp+100h+UserDataCount], 6; UserDataCount
0x18000b67a  call    cs:__imp_EventWriteTransfer
0x18000b680  mov     rcx, rdi
0x18000b683  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18000b688  mov     rcx, [rbp+57h+var_30]
0x18000b68c  xor     rcx, rsp; StackCookie
0x18000b68f  call    __security_check_cookie
0x18000b694  mov     rbx, [rsp+100h+arg_18]
0x18000b69c  add     rsp, 0E0h
0x18000b6a3  pop     r15
0x18000b6a5  pop     r14
0x18000b6a7  pop     r12
0x18000b6a9  pop     rdi
0x18000b6aa  pop     rbp
0x18000b6ab  retn
```
