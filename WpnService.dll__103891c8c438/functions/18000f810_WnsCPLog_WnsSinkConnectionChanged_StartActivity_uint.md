# WnsCPLog::WnsSinkConnectionChanged::StartActivity(uint)

- ea: `0x18000f810`
- end: `0x18000fb17`
- name: `?StartActivity@WnsSinkConnectionChanged@WnsCPLog@@QEAAXI@Z`
- size: `775`
- prototype: `void __fastcall(WnsCPLog::WnsSinkConnectionChanged *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000f690`

## callees

- `0x18000d830`
- `0x18000d8f0`
- `0x18000f810`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f859`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f859`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f86f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f887`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f8c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f86f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f887`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f8c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fa0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fa0f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000faee`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000faee`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000f8ac`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000f8ac`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000f9b3`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000f9b3`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000f998`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000f998`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f8e8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f8e8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f9e2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f9e2`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkConnectionChanged::StartActivity(WnsCPLog::WnsSinkConnectionChanged *this, WINBOOL a2)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v5; // rbx
  __int64 v6; // rsi
  _QWORD *v7; // rbx
  ULONGLONG *v8; // r9
  _QWORD *Ptr; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  const GUID *v12; // r9
  WINBOOL fPending; // [rsp+30h] [rbp-59h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-51h] BYREF
  PSRWLOCK v15; // [rsp+40h] [rbp-49h] BYREF
  __int64 v16; // [rsp+48h] [rbp-41h] BYREF
  GUID ProviderId; // [rsp+50h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-29h] BYREF
  __int16 *v19; // [rsp+70h] [rbp-19h]
  int v20; // [rsp+78h] [rbp-11h]
  int v21; // [rsp+7Ch] [rbp-Dh]
  __int64 *v22; // [rsp+80h] [rbp-9h]
  __int64 v23; // [rsp+88h] [rbp-1h]
  PSRWLOCK *v24; // [rsp+90h] [rbp+7h]
  __int64 v25; // [rsp+98h] [rbp+Fh]
  WINBOOL *p_fPending; // [rsp+A0h] [rbp+17h]
  __int64 v27; // [rsp+A8h] [rbp+1Fh]

  v2 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  if ( v2 )
  {
    v5 = v2 + 33;
    AcquireSRWLockExclusive(v5);
    SRWLock = 0;
  }
  else
  {
    v15 = 0;
    v5 = 0;
  }
  v6 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)WnsCPTracelogger::Provider() <= 5u )
    *(_OWORD *)(v6 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v6 + 8));
  *(_DWORD *)v6 = 1;
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
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
    v7 = CallbackContext;
    qword_18004A768 = (__int64)CallbackContext;
    byte_18004A770 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    v8 = (ULONGLONG *)((char *)CallbackContext + 32);
    *((_QWORD *)CallbackContext + 5) = 0;
    v7[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v7, v8) )
      EventSetInformation(v7[4], 2, v7[1], *(unsigned __int16 *)v7[1]);
    dword_18004A774 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18004A760 + 8))(&qword_18004A760);
    InitOnceComplete(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &qword_18004A760);
  }
  Ptr = SRWLock[1].Ptr;
  if ( *(_DWORD *)Ptr > 5u )
  {
    fPending = a2;
    CurrentThreadId = GetCurrentThreadId();
    v11 = *((_QWORD *)this + 34);
    LODWORD(v15) = CurrentThreadId;
    v16 = 0;
    if ( !*(_BYTE *)(v11 + 4)
      || (v12 = (const GUID *)(v11 + 24), !*(_DWORD *)(v11 + 24))
      && !*(_DWORD *)(v11 + 28)
      && !*(_DWORD *)(v11 + 32)
      && !*(_DWORD *)(v11 + 36) )
    {
      v12 = 0;
    }
    v27 = 4;
    p_fPending = &fPending;
    v25 = 4;
    v24 = &v15;
    v23 = 8;
    v22 = &v16;
    *(_DWORD *)&ProviderId.Data2 = 261;
    UserData.Ptr = Ptr[1];
    ProviderId.Data1 = 184549376;
    *(_QWORD *)ProviderId.Data4 = 0;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v19 = &word_180042F16;
    UserData.Reserved = 2;
    v20 = 76;
    v21 = 1;
    LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(Ptr[4], (PCEVENT_DESCRIPTOR)&ProviderId, (LPCGUID)(v11 + 8), v12, 5u, &UserData);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000f810  push    rbp
0x18000f812  push    rbx
0x18000f813  push    rdi
0x18000f814  push    r14
0x18000f816  push    r15
0x18000f818  lea     rbp, [rsp-37h]
0x18000f81d  sub     rsp, 0C0h
0x18000f824  mov     rax, cs:__security_cookie
0x18000f82b  xor     rax, rsp
0x18000f82e  mov     [rbp+57h+var_30], rax
0x18000f832  mov     rbx, [rcx+118h]
0x18000f839  xor     r15d, r15d
0x18000f83c  mov     [rsp+0E0h+arg_8], rsi
0x18000f844  mov     r14d, edx
0x18000f847  mov     rdi, rcx
0x18000f84a  test    rbx, rbx
0x18000f84d  jz      short loc_18000F877
0x18000f84f  add     rbx, 108h
0x18000f856  mov     rcx, rbx; SRWLock
0x18000f859  call    cs:__imp_AcquireSRWLockExclusive
0x18000f85f  lea     rax, [rbp+57h+SRWLock]
0x18000f863  mov     [rax], r15
0x18000f866  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000f86a  test    rcx, rcx
0x18000f86d  jz      short loc_18000F890
0x18000f86f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f875  jmp     short loc_18000F890
0x18000f877  lea     rax, [rbp+57h+var_A0]
0x18000f87b  mov     [rax], r15
0x18000f87e  mov     rcx, [rbp+57h+var_A0]; SRWLock
0x18000f882  test    rcx, rcx
0x18000f885  jz      short loc_18000F88D
0x18000f887  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f88d  mov     rbx, r15
0x18000f890  mov     rsi, [rdi+110h]
0x18000f897  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18000f89c  mov     ecx, [rax]
0x18000f89e  cmp     ecx, 5
0x18000f8a1  jbe     short loc_18000F8B4
0x18000f8a3  lea     rdx, [rsi+8]; ActivityId
0x18000f8a7  mov     ecx, 3; ControlCode
0x18000f8ac  call    cs:__imp_EventActivityIdControl
0x18000f8b2  jmp     short loc_18000F8BB
0x18000f8b4  xorps   xmm0, xmm0
0x18000f8b7  movups  xmmword ptr [rsi+8], xmm0
0x18000f8bb  mov     dword ptr [rsi], 1
0x18000f8c1  test    rbx, rbx
0x18000f8c4  jz      short loc_18000F8CF
0x18000f8c6  mov     rcx, rbx; SRWLock
0x18000f8c9  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f8cf  lea     r9, [rbp+57h+SRWLock]; lpContext
0x18000f8d3  mov     [rbp+57h+SRWLock], r15
0x18000f8d7  lea     r8, [rbp+57h+fPending]; fPending
0x18000f8db  mov     [rbp+57h+fPending], r15d
0x18000f8df  xor     edx, edx; dwFlags
0x18000f8e1  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18000f8e8  call    cs:__imp_InitOnceBeginInitialize
0x18000f8ee  test    eax, eax
0x18000f8f0  jz      loc_18000F9F0
0x18000f8f6  cmp     [rbp+57h+fPending], r15d
0x18000f8fa  jz      loc_18000F9F0
0x18000f900  mov     [rsp+0E0h+arg_10], r12
0x18000f908  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18000f90f  lea     r12, qword_18004A760
0x18000f916  mov     cs:qword_18004A768, r15
0x18000f91d  mov     [rbp+57h+SRWLock], r12
0x18000f921  mov     cs:byte_18004A770, r15b
0x18000f928  mov     cs:dword_18004A774, r15d
0x18000f92f  mov     cs:qword_18004A760, rax
0x18000f936  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000f93d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x18000f944  mov     cs:CallbackContext, rax
0x18000f94b  call    atexit
0x18000f950  mov     rbx, cs:CallbackContext
0x18000f957  mov     cs:qword_18004A768, rbx
0x18000f95e  mov     cs:byte_18004A770, 1
0x18000f965  mov     rax, [rbx+8]
0x18000f969  movups  xmm0, xmmword ptr [rax-10h]
0x18000f96d  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x18000f971  cmp     [rbx+20h], r15
0x18000f975  jz      short loc_18000F97E
0x18000f977  mov     ecx, 5
0x18000f97c  int     29h; Win8: RtlFailFast(ecx)
0x18000f97e  lea     r9, [rbx+20h]; RegHandle
0x18000f982  mov     [rbx+28h], r15
0x18000f986  mov     r8, rbx; CallbackContext
0x18000f989  mov     [rbx+30h], r15
0x18000f98d  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000f994  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x18000f998  call    cs:__imp_EventRegister
0x18000f99e  test    eax, eax
0x18000f9a0  jnz     short loc_18000F9B9
0x18000f9a2  mov     r8, [rbx+8]
0x18000f9a6  mov     edx, 2
0x18000f9ab  mov     rcx, [rbx+20h]
0x18000f9af  movzx   r9d, word ptr [r8]
0x18000f9b3  call    cs:__imp_EventSetInformation
0x18000f9b9  mov     rax, cs:qword_18004A760
0x18000f9c0  mov     rcx, r12
0x18000f9c3  mov     cs:dword_18004A774, 1
0x18000f9cd  mov     rax, [rax+8]
0x18000f9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9d6  mov     r8, r12; lpContext
0x18000f9d9  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18000f9e0  xor     edx, edx; dwFlags
0x18000f9e2  call    cs:__imp_InitOnceComplete
0x18000f9e8  mov     r12, [rsp+0E0h+arg_10]
0x18000f9f0  mov     rax, [rbp+57h+SRWLock]
0x18000f9f4  mov     rsi, [rsp+0E0h+arg_8]
0x18000f9fc  mov     rbx, [rax+8]
0x18000fa00  mov     eax, [rbx]
0x18000fa02  cmp     eax, 5
0x18000fa05  jbe     loc_18000FAF4
0x18000fa0b  mov     [rbp+57h+fPending], r14d
0x18000fa0f  call    cs:__imp_GetCurrentThreadId
0x18000fa15  mov     r8, [rdi+110h]
0x18000fa1c  mov     dword ptr [rbp+57h+var_A0], eax
0x18000fa1f  mov     [rbp+57h+var_98], r15
0x18000fa23  cmp     [r8+4], r15b
0x18000fa27  jz      short loc_18000FA45
0x18000fa29  cmp     [r8+18h], r15d
0x18000fa2d  lea     r9, [r8+18h]
0x18000fa31  jnz     short loc_18000FA48
0x18000fa33  cmp     [r9+4], r15d
0x18000fa37  jnz     short loc_18000FA48
0x18000fa39  cmp     [r9+8], r15d
0x18000fa3d  jnz     short loc_18000FA48
0x18000fa3f  cmp     [r9+0Ch], r15d
0x18000fa43  jnz     short loc_18000FA48
0x18000fa45  mov     r9, r15; RelatedActivityId
0x18000fa48  mov     [rbp+57h+var_38], 4
0x18000fa50  lea     rax, [rbp+57h+fPending]
0x18000fa54  mov     [rbp+57h+var_40], rax
0x18000fa58  lea     rcx, _TraceLoggingMetadata
0x18000fa5f  mov     [rbp+57h+var_48], 4
0x18000fa67  lea     rax, [rbp+57h+var_A0]
0x18000fa6b  mov     [rbp+57h+var_50], rax
0x18000fa6f  lea     rdx, [rbp+57h+ProviderId]; EventDescriptor
0x18000fa73  lea     rax, [rbp+57h+var_98]
0x18000fa77  mov     [rbp+57h+var_58], 8
0x18000fa7f  mov     [rbp+57h+var_60], rax
0x18000fa83  add     r8, 8; ActivityId
0x18000fa87  movzx   eax, cs:word_180042F0C
0x18000fa8e  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x18000fa91  mov     rax, [rbx+8]
0x18000fa95  mov     [rbp+57h+var_80.Ptr], rax
0x18000fa99  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x18000faa0  mov     qword ptr [rbp+57h+ProviderId.Data4], r15
0x18000faa4  movzx   eax, word ptr [rax]
0x18000faa7  mov     [rbp+57h+var_80.Size], eax
0x18000faaa  lea     rax, word_180042F16
0x18000fab1  mov     [rbp+57h+var_70], rax
0x18000fab5  lea     rax, _TraceLoggingMetadataEnd
0x18000fabc  sub     eax, ecx
0x18000fabe  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x18000fac5  mov     [rbp+57h+var_68], 4Ch ; 'L'
0x18000facc  mov     [rbp+57h+var_64], 1
0x18000fad3  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000fad6  mov     eax, dword ptr [rbp+57h+SRWLock]
0x18000fad9  mov     rcx, [rbx+20h]; RegHandle
0x18000fadd  lea     rax, [rbp+57h+var_80]
0x18000fae1  mov     [rsp+0E0h+UserData], rax; UserData
0x18000fae6  mov     [rsp+0E0h+UserDataCount], 5; UserDataCount
0x18000faee  call    cs:__imp_EventWriteTransfer
0x18000faf4  mov     rcx, rdi
0x18000faf7  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18000fafc  mov     rcx, [rbp+57h+var_30]
0x18000fb00  xor     rcx, rsp; StackCookie
0x18000fb03  call    __security_check_cookie
0x18000fb08  add     rsp, 0C0h
0x18000fb0f  pop     r15
0x18000fb11  pop     r14
0x18000fb13  pop     rdi
0x18000fb14  pop     rbx
0x18000fb15  pop     rbp
0x18000fb16  retn
```
