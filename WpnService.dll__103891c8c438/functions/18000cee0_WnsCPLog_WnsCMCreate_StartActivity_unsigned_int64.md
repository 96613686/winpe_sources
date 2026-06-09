# WnsCPLog::WnsCMCreate::StartActivity(unsigned __int64)

- ea: `0x18000cee0`
- end: `0x18000d1e7`
- name: `?StartActivity@WnsCMCreate@WnsCPLog@@QEAAX_K@Z`
- size: `775`
- prototype: `void __fastcall(WnsCPLog::WnsCMCreate *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800074f0`
- `0x18000d3f4`

## callees

- `0x18000cee0`
- `0x18000d830`
- `0x18000d8f0`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cf29`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cf29`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cf3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cf57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cf99`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cf3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cf57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cf99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d0df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d0df`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d1be`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d1be`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000cf7c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000cf7c`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000d083`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000d083`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000d068`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000d068`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000cfb8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000cfb8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000d0b2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000d0b2`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMCreate::StartActivity(WnsCPLog::WnsCMCreate *this, __int64 a2)
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
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-59h] BYREF
  PSRWLOCK v14; // [rsp+38h] [rbp-51h] BYREF
  __int64 v15; // [rsp+40h] [rbp-49h] BYREF
  __int64 v16; // [rsp+48h] [rbp-41h] BYREF
  GUID ProviderId; // [rsp+50h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-29h] BYREF
  char *v19; // [rsp+70h] [rbp-19h]
  int v20; // [rsp+78h] [rbp-11h]
  int v21; // [rsp+7Ch] [rbp-Dh]
  __int64 *v22; // [rsp+80h] [rbp-9h]
  __int64 v23; // [rsp+88h] [rbp-1h]
  PSRWLOCK *v24; // [rsp+90h] [rbp+7h]
  __int64 v25; // [rsp+98h] [rbp+Fh]
  __int64 *v26; // [rsp+A0h] [rbp+17h]
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
    v14 = 0;
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
  LODWORD(v14) = 0;
  if ( InitOnceBeginInitialize(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, (PBOOL)&v14, (LPVOID *)&SRWLock)
    && (_DWORD)v14 )
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
    v15 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v11 = *((_QWORD *)this + 34);
    LODWORD(v14) = CurrentThreadId;
    v16 = 0;
    if ( !*(_BYTE *)(v11 + 4)
      || (v12 = (const GUID *)(v11 + 24), !*(_DWORD *)(v11 + 24))
      && !*(_DWORD *)(v11 + 28)
      && !*(_DWORD *)(v11 + 32)
      && !*(_DWORD *)(v11 + 36) )
    {
      v12 = 0;
    }
    v27 = 8;
    v26 = &v15;
    v25 = 4;
    v24 = &v14;
    v23 = 8;
    v22 = &v16;
    *(_DWORD *)&ProviderId.Data2 = 261;
    UserData.Ptr = Ptr[1];
    ProviderId.Data1 = 184549376;
    *(_QWORD *)ProviderId.Data4 = 0;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v19 = byte_18003FA5D;
    UserData.Reserved = 2;
    v20 = 63;
    v21 = 1;
    LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(Ptr[4], (PCEVENT_DESCRIPTOR)&ProviderId, (LPCGUID)(v11 + 8), v12, 5u, &UserData);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000cee0  push    rbp
0x18000cee2  push    rbx
0x18000cee3  push    rdi
0x18000cee4  push    r14
0x18000cee6  push    r15
0x18000cee8  lea     rbp, [rsp-37h]
0x18000ceed  sub     rsp, 0C0h
0x18000cef4  mov     rax, cs:__security_cookie
0x18000cefb  xor     rax, rsp
0x18000cefe  mov     [rbp+57h+var_30], rax
0x18000cf02  mov     rbx, [rcx+118h]
0x18000cf09  xor     r15d, r15d
0x18000cf0c  mov     [rsp+0E0h+arg_8], rsi
0x18000cf14  mov     r14, rdx
0x18000cf17  mov     rdi, rcx
0x18000cf1a  test    rbx, rbx
0x18000cf1d  jz      short loc_18000CF47
0x18000cf1f  add     rbx, 108h
0x18000cf26  mov     rcx, rbx; SRWLock
0x18000cf29  call    cs:__imp_AcquireSRWLockExclusive
0x18000cf2f  lea     rax, [rbp+57h+SRWLock]
0x18000cf33  mov     [rax], r15
0x18000cf36  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000cf3a  test    rcx, rcx
0x18000cf3d  jz      short loc_18000CF60
0x18000cf3f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cf45  jmp     short loc_18000CF60
0x18000cf47  lea     rax, [rbp+57h+var_A8]
0x18000cf4b  mov     [rax], r15
0x18000cf4e  mov     rcx, [rbp+57h+var_A8]; SRWLock
0x18000cf52  test    rcx, rcx
0x18000cf55  jz      short loc_18000CF5D
0x18000cf57  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cf5d  mov     rbx, r15
0x18000cf60  mov     rsi, [rdi+110h]
0x18000cf67  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18000cf6c  mov     ecx, [rax]
0x18000cf6e  cmp     ecx, 5
0x18000cf71  jbe     short loc_18000CF84
0x18000cf73  lea     rdx, [rsi+8]; ActivityId
0x18000cf77  mov     ecx, 3; ControlCode
0x18000cf7c  call    cs:__imp_EventActivityIdControl
0x18000cf82  jmp     short loc_18000CF8B
0x18000cf84  xorps   xmm0, xmm0
0x18000cf87  movups  xmmword ptr [rsi+8], xmm0
0x18000cf8b  mov     dword ptr [rsi], 1
0x18000cf91  test    rbx, rbx
0x18000cf94  jz      short loc_18000CF9F
0x18000cf96  mov     rcx, rbx; SRWLock
0x18000cf99  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cf9f  lea     r9, [rbp+57h+SRWLock]; lpContext
0x18000cfa3  mov     [rbp+57h+SRWLock], r15
0x18000cfa7  lea     r8, [rbp+57h+var_A8]; fPending
0x18000cfab  mov     dword ptr [rbp+57h+var_A8], r15d
0x18000cfaf  xor     edx, edx; dwFlags
0x18000cfb1  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18000cfb8  call    cs:__imp_InitOnceBeginInitialize
0x18000cfbe  test    eax, eax
0x18000cfc0  jz      loc_18000D0C0
0x18000cfc6  cmp     dword ptr [rbp+57h+var_A8], r15d
0x18000cfca  jz      loc_18000D0C0
0x18000cfd0  mov     [rsp+0E0h+arg_10], r12
0x18000cfd8  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18000cfdf  lea     r12, qword_18004A760
0x18000cfe6  mov     cs:qword_18004A768, r15
0x18000cfed  mov     [rbp+57h+SRWLock], r12
0x18000cff1  mov     cs:byte_18004A770, r15b
0x18000cff8  mov     cs:dword_18004A774, r15d
0x18000cfff  mov     cs:qword_18004A760, rax
0x18000d006  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000d00d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x18000d014  mov     cs:CallbackContext, rax
0x18000d01b  call    atexit
0x18000d020  mov     rbx, cs:CallbackContext
0x18000d027  mov     cs:qword_18004A768, rbx
0x18000d02e  mov     cs:byte_18004A770, 1
0x18000d035  mov     rax, [rbx+8]
0x18000d039  movups  xmm0, xmmword ptr [rax-10h]
0x18000d03d  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x18000d041  cmp     [rbx+20h], r15
0x18000d045  jz      short loc_18000D04E
0x18000d047  mov     ecx, 5
0x18000d04c  int     29h; Win8: RtlFailFast(ecx)
0x18000d04e  lea     r9, [rbx+20h]; RegHandle
0x18000d052  mov     [rbx+28h], r15
0x18000d056  mov     r8, rbx; CallbackContext
0x18000d059  mov     [rbx+30h], r15
0x18000d05d  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000d064  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x18000d068  call    cs:__imp_EventRegister
0x18000d06e  test    eax, eax
0x18000d070  jnz     short loc_18000D089
0x18000d072  mov     r8, [rbx+8]
0x18000d076  mov     edx, 2
0x18000d07b  mov     rcx, [rbx+20h]
0x18000d07f  movzx   r9d, word ptr [r8]
0x18000d083  call    cs:__imp_EventSetInformation
0x18000d089  mov     rax, cs:qword_18004A760
0x18000d090  mov     rcx, r12
0x18000d093  mov     cs:dword_18004A774, 1
0x18000d09d  mov     rax, [rax+8]
0x18000d0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0a6  mov     r8, r12; lpContext
0x18000d0a9  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18000d0b0  xor     edx, edx; dwFlags
0x18000d0b2  call    cs:__imp_InitOnceComplete
0x18000d0b8  mov     r12, [rsp+0E0h+arg_10]
0x18000d0c0  mov     rax, [rbp+57h+SRWLock]
0x18000d0c4  mov     rsi, [rsp+0E0h+arg_8]
0x18000d0cc  mov     rbx, [rax+8]
0x18000d0d0  mov     eax, [rbx]
0x18000d0d2  cmp     eax, 5
0x18000d0d5  jbe     loc_18000D1C4
0x18000d0db  mov     [rbp+57h+var_A0], r14
0x18000d0df  call    cs:__imp_GetCurrentThreadId
0x18000d0e5  mov     r8, [rdi+110h]
0x18000d0ec  mov     dword ptr [rbp+57h+var_A8], eax
0x18000d0ef  mov     [rbp+57h+var_98], r15
0x18000d0f3  cmp     [r8+4], r15b
0x18000d0f7  jz      short loc_18000D115
0x18000d0f9  cmp     [r8+18h], r15d
0x18000d0fd  lea     r9, [r8+18h]
0x18000d101  jnz     short loc_18000D118
0x18000d103  cmp     [r9+4], r15d
0x18000d107  jnz     short loc_18000D118
0x18000d109  cmp     [r9+8], r15d
0x18000d10d  jnz     short loc_18000D118
0x18000d10f  cmp     [r9+0Ch], r15d
0x18000d113  jnz     short loc_18000D118
0x18000d115  mov     r9, r15; RelatedActivityId
0x18000d118  mov     [rbp+57h+var_38], 8
0x18000d120  lea     rax, [rbp+57h+var_A0]
0x18000d124  mov     [rbp+57h+var_40], rax
0x18000d128  lea     rcx, _TraceLoggingMetadata
0x18000d12f  mov     [rbp+57h+var_48], 4
0x18000d137  lea     rax, [rbp+57h+var_A8]
0x18000d13b  mov     [rbp+57h+var_50], rax
0x18000d13f  lea     rdx, [rbp+57h+ProviderId]; EventDescriptor
0x18000d143  lea     rax, [rbp+57h+var_98]
0x18000d147  mov     [rbp+57h+var_58], 8
0x18000d14f  mov     [rbp+57h+var_60], rax
0x18000d153  add     r8, 8; ActivityId
0x18000d157  movzx   eax, cs:word_18003FA53
0x18000d15e  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x18000d161  mov     rax, [rbx+8]
0x18000d165  mov     [rbp+57h+var_80.Ptr], rax
0x18000d169  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x18000d170  mov     qword ptr [rbp+57h+ProviderId.Data4], r15
0x18000d174  movzx   eax, word ptr [rax]
0x18000d177  mov     [rbp+57h+var_80.Size], eax
0x18000d17a  lea     rax, byte_18003FA5D
0x18000d181  mov     [rbp+57h+var_70], rax
0x18000d185  lea     rax, _TraceLoggingMetadataEnd
0x18000d18c  sub     eax, ecx
0x18000d18e  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x18000d195  mov     [rbp+57h+var_68], 3Fh ; '?'
0x18000d19c  mov     [rbp+57h+var_64], 1
0x18000d1a3  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000d1a6  mov     eax, dword ptr [rbp+57h+SRWLock]
0x18000d1a9  mov     rcx, [rbx+20h]; RegHandle
0x18000d1ad  lea     rax, [rbp+57h+var_80]
0x18000d1b1  mov     [rsp+0E0h+UserData], rax; UserData
0x18000d1b6  mov     [rsp+0E0h+UserDataCount], 5; UserDataCount
0x18000d1be  call    cs:__imp_EventWriteTransfer
0x18000d1c4  mov     rcx, rdi
0x18000d1c7  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18000d1cc  mov     rcx, [rbp+57h+var_30]
0x18000d1d0  xor     rcx, rsp; StackCookie
0x18000d1d3  call    __security_check_cookie
0x18000d1d8  add     rsp, 0C0h
0x18000d1df  pop     r15
0x18000d1e1  pop     r14
0x18000d1e3  pop     rdi
0x18000d1e4  pop     rbx
0x18000d1e5  pop     rbp
0x18000d1e6  retn
```
