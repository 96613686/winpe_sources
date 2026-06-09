# WnsCPLog::WnsCMDestroy::StartActivity(unsigned __int64)

- ea: `0x180005ae0`
- end: `0x180005de7`
- name: `?StartActivity@WnsCMDestroy@WnsCPLog@@QEAAX_K@Z`
- size: `775`
- prototype: `void __fastcall(WnsCPLog::WnsCMDestroy *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800058d4`

## callees

- `0x180005ae0`
- `0x18000d830`
- `0x18000d8f0`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005b29`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005b29`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005b3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005b57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005b99`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005b3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005b57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005b99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005cdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005cdf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005dbe`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005dbe`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180005b7c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180005b7c`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180005c83`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180005c83`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180005c68`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180005c68`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180005bb8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180005bb8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180005cb2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180005cb2`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMDestroy::StartActivity(WnsCPLog::WnsCMDestroy *this, __int64 a2)
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
    v19 = byte_18003E205;
    UserData.Reserved = 2;
    v20 = 64;
    v21 = 1;
    LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(Ptr[4], (PCEVENT_DESCRIPTOR)&ProviderId, (LPCGUID)(v11 + 8), v12, 5u, &UserData);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180005ae0  push    rbp
0x180005ae2  push    rbx
0x180005ae3  push    rdi
0x180005ae4  push    r14
0x180005ae6  push    r15
0x180005ae8  lea     rbp, [rsp-37h]
0x180005aed  sub     rsp, 0C0h
0x180005af4  mov     rax, cs:__security_cookie
0x180005afb  xor     rax, rsp
0x180005afe  mov     [rbp+57h+var_30], rax
0x180005b02  mov     rbx, [rcx+118h]
0x180005b09  xor     r15d, r15d
0x180005b0c  mov     [rsp+0E0h+arg_8], rsi
0x180005b14  mov     r14, rdx
0x180005b17  mov     rdi, rcx
0x180005b1a  test    rbx, rbx
0x180005b1d  jz      short loc_180005B47
0x180005b1f  add     rbx, 108h
0x180005b26  mov     rcx, rbx; SRWLock
0x180005b29  call    cs:__imp_AcquireSRWLockExclusive
0x180005b2f  lea     rax, [rbp+57h+SRWLock]
0x180005b33  mov     [rax], r15
0x180005b36  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180005b3a  test    rcx, rcx
0x180005b3d  jz      short loc_180005B60
0x180005b3f  call    cs:__imp_ReleaseSRWLockExclusive
0x180005b45  jmp     short loc_180005B60
0x180005b47  lea     rax, [rbp+57h+var_A8]
0x180005b4b  mov     [rax], r15
0x180005b4e  mov     rcx, [rbp+57h+var_A8]; SRWLock
0x180005b52  test    rcx, rcx
0x180005b55  jz      short loc_180005B5D
0x180005b57  call    cs:__imp_ReleaseSRWLockExclusive
0x180005b5d  mov     rbx, r15
0x180005b60  mov     rsi, [rdi+110h]
0x180005b67  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180005b6c  mov     ecx, [rax]
0x180005b6e  cmp     ecx, 5
0x180005b71  jbe     short loc_180005B84
0x180005b73  lea     rdx, [rsi+8]; ActivityId
0x180005b77  mov     ecx, 3; ControlCode
0x180005b7c  call    cs:__imp_EventActivityIdControl
0x180005b82  jmp     short loc_180005B8B
0x180005b84  xorps   xmm0, xmm0
0x180005b87  movups  xmmword ptr [rsi+8], xmm0
0x180005b8b  mov     dword ptr [rsi], 1
0x180005b91  test    rbx, rbx
0x180005b94  jz      short loc_180005B9F
0x180005b96  mov     rcx, rbx; SRWLock
0x180005b99  call    cs:__imp_ReleaseSRWLockExclusive
0x180005b9f  lea     r9, [rbp+57h+SRWLock]; lpContext
0x180005ba3  mov     [rbp+57h+SRWLock], r15
0x180005ba7  lea     r8, [rbp+57h+var_A8]; fPending
0x180005bab  mov     dword ptr [rbp+57h+var_A8], r15d
0x180005baf  xor     edx, edx; dwFlags
0x180005bb1  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x180005bb8  call    cs:__imp_InitOnceBeginInitialize
0x180005bbe  test    eax, eax
0x180005bc0  jz      loc_180005CC0
0x180005bc6  cmp     dword ptr [rbp+57h+var_A8], r15d
0x180005bca  jz      loc_180005CC0
0x180005bd0  mov     [rsp+0E0h+arg_10], r12
0x180005bd8  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180005bdf  lea     r12, qword_18004A760
0x180005be6  mov     cs:qword_18004A768, r15
0x180005bed  mov     [rbp+57h+SRWLock], r12
0x180005bf1  mov     cs:byte_18004A770, r15b
0x180005bf8  mov     cs:dword_18004A774, r15d
0x180005bff  mov     cs:qword_18004A760, rax
0x180005c06  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180005c0d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x180005c14  mov     cs:CallbackContext, rax
0x180005c1b  call    atexit
0x180005c20  mov     rbx, cs:CallbackContext
0x180005c27  mov     cs:qword_18004A768, rbx
0x180005c2e  mov     cs:byte_18004A770, 1
0x180005c35  mov     rax, [rbx+8]
0x180005c39  movups  xmm0, xmmword ptr [rax-10h]
0x180005c3d  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x180005c41  cmp     [rbx+20h], r15
0x180005c45  jz      short loc_180005C4E
0x180005c47  mov     ecx, 5
0x180005c4c  int     29h; Win8: RtlFailFast(ecx)
0x180005c4e  lea     r9, [rbx+20h]; RegHandle
0x180005c52  mov     [rbx+28h], r15
0x180005c56  mov     r8, rbx; CallbackContext
0x180005c59  mov     [rbx+30h], r15
0x180005c5d  lea     rdx, _tlgEnableCallback; EnableCallback
0x180005c64  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x180005c68  call    cs:__imp_EventRegister
0x180005c6e  test    eax, eax
0x180005c70  jnz     short loc_180005C89
0x180005c72  mov     r8, [rbx+8]
0x180005c76  mov     edx, 2
0x180005c7b  mov     rcx, [rbx+20h]
0x180005c7f  movzx   r9d, word ptr [r8]
0x180005c83  call    cs:__imp_EventSetInformation
0x180005c89  mov     rax, cs:qword_18004A760
0x180005c90  mov     rcx, r12
0x180005c93  mov     cs:dword_18004A774, 1
0x180005c9d  mov     rax, [rax+8]
0x180005ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ca6  mov     r8, r12; lpContext
0x180005ca9  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x180005cb0  xor     edx, edx; dwFlags
0x180005cb2  call    cs:__imp_InitOnceComplete
0x180005cb8  mov     r12, [rsp+0E0h+arg_10]
0x180005cc0  mov     rax, [rbp+57h+SRWLock]
0x180005cc4  mov     rsi, [rsp+0E0h+arg_8]
0x180005ccc  mov     rbx, [rax+8]
0x180005cd0  mov     eax, [rbx]
0x180005cd2  cmp     eax, 5
0x180005cd5  jbe     loc_180005DC4
0x180005cdb  mov     [rbp+57h+var_A0], r14
0x180005cdf  call    cs:__imp_GetCurrentThreadId
0x180005ce5  mov     r8, [rdi+110h]
0x180005cec  mov     dword ptr [rbp+57h+var_A8], eax
0x180005cef  mov     [rbp+57h+var_98], r15
0x180005cf3  cmp     [r8+4], r15b
0x180005cf7  jz      short loc_180005D15
0x180005cf9  cmp     [r8+18h], r15d
0x180005cfd  lea     r9, [r8+18h]
0x180005d01  jnz     short loc_180005D18
0x180005d03  cmp     [r9+4], r15d
0x180005d07  jnz     short loc_180005D18
0x180005d09  cmp     [r9+8], r15d
0x180005d0d  jnz     short loc_180005D18
0x180005d0f  cmp     [r9+0Ch], r15d
0x180005d13  jnz     short loc_180005D18
0x180005d15  mov     r9, r15; RelatedActivityId
0x180005d18  mov     [rbp+57h+var_38], 8
0x180005d20  lea     rax, [rbp+57h+var_A0]
0x180005d24  mov     [rbp+57h+var_40], rax
0x180005d28  lea     rcx, _TraceLoggingMetadata
0x180005d2f  mov     [rbp+57h+var_48], 4
0x180005d37  lea     rax, [rbp+57h+var_A8]
0x180005d3b  mov     [rbp+57h+var_50], rax
0x180005d3f  lea     rdx, [rbp+57h+ProviderId]; EventDescriptor
0x180005d43  lea     rax, [rbp+57h+var_98]
0x180005d47  mov     [rbp+57h+var_58], 8
0x180005d4f  mov     [rbp+57h+var_60], rax
0x180005d53  add     r8, 8; ActivityId
0x180005d57  movzx   eax, cs:word_18003E1FB
0x180005d5e  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x180005d61  mov     rax, [rbx+8]
0x180005d65  mov     [rbp+57h+var_80.Ptr], rax
0x180005d69  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x180005d70  mov     qword ptr [rbp+57h+ProviderId.Data4], r15
0x180005d74  movzx   eax, word ptr [rax]
0x180005d77  mov     [rbp+57h+var_80.Size], eax
0x180005d7a  lea     rax, byte_18003E205
0x180005d81  mov     [rbp+57h+var_70], rax
0x180005d85  lea     rax, _TraceLoggingMetadataEnd
0x180005d8c  sub     eax, ecx
0x180005d8e  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x180005d95  mov     [rbp+57h+var_68], 40h ; '@'
0x180005d9c  mov     [rbp+57h+var_64], 1
0x180005da3  mov     dword ptr [rbp+57h+SRWLock], eax
0x180005da6  mov     eax, dword ptr [rbp+57h+SRWLock]
0x180005da9  mov     rcx, [rbx+20h]; RegHandle
0x180005dad  lea     rax, [rbp+57h+var_80]
0x180005db1  mov     [rsp+0E0h+UserData], rax; UserData
0x180005db6  mov     [rsp+0E0h+UserDataCount], 5; UserDataCount
0x180005dbe  call    cs:__imp_EventWriteTransfer
0x180005dc4  mov     rcx, rdi
0x180005dc7  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180005dcc  mov     rcx, [rbp+57h+var_30]
0x180005dd0  xor     rcx, rsp; StackCookie
0x180005dd3  call    __security_check_cookie
0x180005dd8  add     rsp, 0C0h
0x180005ddf  pop     r15
0x180005de1  pop     r14
0x180005de3  pop     rdi
0x180005de4  pop     rbx
0x180005de5  pop     rbp
0x180005de6  retn
```
