# WnsCPLog::WnsCPTClearBufferedRequestsForUser::StartActivity(unsigned __int64)

- ea: `0x180007f00`
- end: `0x180008207`
- name: `?StartActivity@WnsCPTClearBufferedRequestsForUser@WnsCPLog@@QEAAX_K@Z`
- size: `775`
- prototype: `void __fastcall(WnsCPLog::WnsCPTClearBufferedRequestsForUser *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008cc0`
- `0x1800157bc`

## callees

- `0x180007f00`
- `0x18000d830`
- `0x18000d8f0`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007f49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007f49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007f5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007f77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007fb9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007f5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007f77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007fb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800080ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800080ff`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800081de`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800081de`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180007f9c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180007f9c`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800080a3`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800080a3`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008088`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008088`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180007fd8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180007fd8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800080d2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800080d2`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCPTClearBufferedRequestsForUser::StartActivity(
        WnsCPLog::WnsCPTClearBufferedRequestsForUser *this,
        __int64 a2)
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
    v19 = &byte_180040617;
    UserData.Reserved = 2;
    v20 = 86;
    v21 = 1;
    LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(Ptr[4], (PCEVENT_DESCRIPTOR)&ProviderId, (LPCGUID)(v11 + 8), v12, 5u, &UserData);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180007f00  push    rbp
0x180007f02  push    rbx
0x180007f03  push    rdi
0x180007f04  push    r14
0x180007f06  push    r15
0x180007f08  lea     rbp, [rsp-37h]
0x180007f0d  sub     rsp, 0C0h
0x180007f14  mov     rax, cs:__security_cookie
0x180007f1b  xor     rax, rsp
0x180007f1e  mov     [rbp+57h+var_30], rax
0x180007f22  mov     rbx, [rcx+118h]
0x180007f29  xor     r15d, r15d
0x180007f2c  mov     [rsp+0E0h+arg_8], rsi
0x180007f34  mov     r14, rdx
0x180007f37  mov     rdi, rcx
0x180007f3a  test    rbx, rbx
0x180007f3d  jz      short loc_180007F67
0x180007f3f  add     rbx, 108h
0x180007f46  mov     rcx, rbx; SRWLock
0x180007f49  call    cs:__imp_AcquireSRWLockExclusive
0x180007f4f  lea     rax, [rbp+57h+SRWLock]
0x180007f53  mov     [rax], r15
0x180007f56  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180007f5a  test    rcx, rcx
0x180007f5d  jz      short loc_180007F80
0x180007f5f  call    cs:__imp_ReleaseSRWLockExclusive
0x180007f65  jmp     short loc_180007F80
0x180007f67  lea     rax, [rbp+57h+var_A8]
0x180007f6b  mov     [rax], r15
0x180007f6e  mov     rcx, [rbp+57h+var_A8]; SRWLock
0x180007f72  test    rcx, rcx
0x180007f75  jz      short loc_180007F7D
0x180007f77  call    cs:__imp_ReleaseSRWLockExclusive
0x180007f7d  mov     rbx, r15
0x180007f80  mov     rsi, [rdi+110h]
0x180007f87  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180007f8c  mov     ecx, [rax]
0x180007f8e  cmp     ecx, 5
0x180007f91  jbe     short loc_180007FA4
0x180007f93  lea     rdx, [rsi+8]; ActivityId
0x180007f97  mov     ecx, 3; ControlCode
0x180007f9c  call    cs:__imp_EventActivityIdControl
0x180007fa2  jmp     short loc_180007FAB
0x180007fa4  xorps   xmm0, xmm0
0x180007fa7  movups  xmmword ptr [rsi+8], xmm0
0x180007fab  mov     dword ptr [rsi], 1
0x180007fb1  test    rbx, rbx
0x180007fb4  jz      short loc_180007FBF
0x180007fb6  mov     rcx, rbx; SRWLock
0x180007fb9  call    cs:__imp_ReleaseSRWLockExclusive
0x180007fbf  lea     r9, [rbp+57h+SRWLock]; lpContext
0x180007fc3  mov     [rbp+57h+SRWLock], r15
0x180007fc7  lea     r8, [rbp+57h+var_A8]; fPending
0x180007fcb  mov     dword ptr [rbp+57h+var_A8], r15d
0x180007fcf  xor     edx, edx; dwFlags
0x180007fd1  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x180007fd8  call    cs:__imp_InitOnceBeginInitialize
0x180007fde  test    eax, eax
0x180007fe0  jz      loc_1800080E0
0x180007fe6  cmp     dword ptr [rbp+57h+var_A8], r15d
0x180007fea  jz      loc_1800080E0
0x180007ff0  mov     [rsp+0E0h+arg_10], r12
0x180007ff8  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180007fff  lea     r12, qword_18004A760
0x180008006  mov     cs:qword_18004A768, r15
0x18000800d  mov     [rbp+57h+SRWLock], r12
0x180008011  mov     cs:byte_18004A770, r15b
0x180008018  mov     cs:dword_18004A774, r15d
0x18000801f  mov     cs:qword_18004A760, rax
0x180008026  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000802d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x180008034  mov     cs:CallbackContext, rax
0x18000803b  call    atexit
0x180008040  mov     rbx, cs:CallbackContext
0x180008047  mov     cs:qword_18004A768, rbx
0x18000804e  mov     cs:byte_18004A770, 1
0x180008055  mov     rax, [rbx+8]
0x180008059  movups  xmm0, xmmword ptr [rax-10h]
0x18000805d  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x180008061  cmp     [rbx+20h], r15
0x180008065  jz      short loc_18000806E
0x180008067  mov     ecx, 5
0x18000806c  int     29h; Win8: RtlFailFast(ecx)
0x18000806e  lea     r9, [rbx+20h]; RegHandle
0x180008072  mov     [rbx+28h], r15
0x180008076  mov     r8, rbx; CallbackContext
0x180008079  mov     [rbx+30h], r15
0x18000807d  lea     rdx, _tlgEnableCallback; EnableCallback
0x180008084  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x180008088  call    cs:__imp_EventRegister
0x18000808e  test    eax, eax
0x180008090  jnz     short loc_1800080A9
0x180008092  mov     r8, [rbx+8]
0x180008096  mov     edx, 2
0x18000809b  mov     rcx, [rbx+20h]
0x18000809f  movzx   r9d, word ptr [r8]
0x1800080a3  call    cs:__imp_EventSetInformation
0x1800080a9  mov     rax, cs:qword_18004A760
0x1800080b0  mov     rcx, r12
0x1800080b3  mov     cs:dword_18004A774, 1
0x1800080bd  mov     rax, [rax+8]
0x1800080c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080c6  mov     r8, r12; lpContext
0x1800080c9  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x1800080d0  xor     edx, edx; dwFlags
0x1800080d2  call    cs:__imp_InitOnceComplete
0x1800080d8  mov     r12, [rsp+0E0h+arg_10]
0x1800080e0  mov     rax, [rbp+57h+SRWLock]
0x1800080e4  mov     rsi, [rsp+0E0h+arg_8]
0x1800080ec  mov     rbx, [rax+8]
0x1800080f0  mov     eax, [rbx]
0x1800080f2  cmp     eax, 5
0x1800080f5  jbe     loc_1800081E4
0x1800080fb  mov     [rbp+57h+var_A0], r14
0x1800080ff  call    cs:__imp_GetCurrentThreadId
0x180008105  mov     r8, [rdi+110h]
0x18000810c  mov     dword ptr [rbp+57h+var_A8], eax
0x18000810f  mov     [rbp+57h+var_98], r15
0x180008113  cmp     [r8+4], r15b
0x180008117  jz      short loc_180008135
0x180008119  cmp     [r8+18h], r15d
0x18000811d  lea     r9, [r8+18h]
0x180008121  jnz     short loc_180008138
0x180008123  cmp     [r9+4], r15d
0x180008127  jnz     short loc_180008138
0x180008129  cmp     [r9+8], r15d
0x18000812d  jnz     short loc_180008138
0x18000812f  cmp     [r9+0Ch], r15d
0x180008133  jnz     short loc_180008138
0x180008135  mov     r9, r15; RelatedActivityId
0x180008138  mov     [rbp+57h+var_38], 8
0x180008140  lea     rax, [rbp+57h+var_A0]
0x180008144  mov     [rbp+57h+var_40], rax
0x180008148  lea     rcx, _TraceLoggingMetadata
0x18000814f  mov     [rbp+57h+var_48], 4
0x180008157  lea     rax, [rbp+57h+var_A8]
0x18000815b  mov     [rbp+57h+var_50], rax
0x18000815f  lea     rdx, [rbp+57h+ProviderId]; EventDescriptor
0x180008163  lea     rax, [rbp+57h+var_98]
0x180008167  mov     [rbp+57h+var_58], 8
0x18000816f  mov     [rbp+57h+var_60], rax
0x180008173  add     r8, 8; ActivityId
0x180008177  movzx   eax, cs:word_18004060D
0x18000817e  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x180008181  mov     rax, [rbx+8]
0x180008185  mov     [rbp+57h+var_80.Ptr], rax
0x180008189  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x180008190  mov     qword ptr [rbp+57h+ProviderId.Data4], r15
0x180008194  movzx   eax, word ptr [rax]
0x180008197  mov     [rbp+57h+var_80.Size], eax
0x18000819a  lea     rax, byte_180040617
0x1800081a1  mov     [rbp+57h+var_70], rax
0x1800081a5  lea     rax, _TraceLoggingMetadataEnd
0x1800081ac  sub     eax, ecx
0x1800081ae  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x1800081b5  mov     [rbp+57h+var_68], 56h ; 'V'
0x1800081bc  mov     [rbp+57h+var_64], 1
0x1800081c3  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800081c6  mov     eax, dword ptr [rbp+57h+SRWLock]
0x1800081c9  mov     rcx, [rbx+20h]; RegHandle
0x1800081cd  lea     rax, [rbp+57h+var_80]
0x1800081d1  mov     [rsp+0E0h+UserData], rax; UserData
0x1800081d6  mov     [rsp+0E0h+UserDataCount], 5; UserDataCount
0x1800081de  call    cs:__imp_EventWriteTransfer
0x1800081e4  mov     rcx, rdi
0x1800081e7  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800081ec  mov     rcx, [rbp+57h+var_30]
0x1800081f0  xor     rcx, rsp; StackCookie
0x1800081f3  call    __security_check_cookie
0x1800081f8  add     rsp, 0C0h
0x1800081ff  pop     r15
0x180008201  pop     r14
0x180008203  pop     rdi
0x180008204  pop     rbx
0x180008205  pop     rbp
0x180008206  retn
```
