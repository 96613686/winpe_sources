# WnsCPLog::WnsCMStatus::StartActivity(unsigned __int64)

- ea: `0x18000a600`
- end: `0x18000a907`
- name: `?StartActivity@WnsCMStatus@WnsCPLog@@QEAAX_K@Z`
- size: `775`
- prototype: `void __fastcall(WnsCPLog::WnsCMStatus *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800099f0`

## callees

- `0x18000a600`
- `0x18000d830`
- `0x18000d8f0`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a649`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a649`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a65f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a677`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a6b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a65f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a677`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a6b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a7ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a7ff`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a8de`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a8de`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000a69c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000a69c`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000a7a3`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000a7a3`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a788`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a788`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a6d8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a6d8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a7d2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a7d2`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMStatus::StartActivity(WnsCPLog::WnsCMStatus *this, __int64 a2)
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
    v19 = byte_18003E3E5;
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
0x18000a600  push    rbp
0x18000a602  push    rbx
0x18000a603  push    rdi
0x18000a604  push    r14
0x18000a606  push    r15
0x18000a608  lea     rbp, [rsp-37h]
0x18000a60d  sub     rsp, 0C0h
0x18000a614  mov     rax, cs:__security_cookie
0x18000a61b  xor     rax, rsp
0x18000a61e  mov     [rbp+57h+var_30], rax
0x18000a622  mov     rbx, [rcx+118h]
0x18000a629  xor     r15d, r15d
0x18000a62c  mov     [rsp+0E0h+arg_8], rsi
0x18000a634  mov     r14, rdx
0x18000a637  mov     rdi, rcx
0x18000a63a  test    rbx, rbx
0x18000a63d  jz      short loc_18000A667
0x18000a63f  add     rbx, 108h
0x18000a646  mov     rcx, rbx; SRWLock
0x18000a649  call    cs:__imp_AcquireSRWLockExclusive
0x18000a64f  lea     rax, [rbp+57h+SRWLock]
0x18000a653  mov     [rax], r15
0x18000a656  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000a65a  test    rcx, rcx
0x18000a65d  jz      short loc_18000A680
0x18000a65f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a665  jmp     short loc_18000A680
0x18000a667  lea     rax, [rbp+57h+var_A8]
0x18000a66b  mov     [rax], r15
0x18000a66e  mov     rcx, [rbp+57h+var_A8]; SRWLock
0x18000a672  test    rcx, rcx
0x18000a675  jz      short loc_18000A67D
0x18000a677  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a67d  mov     rbx, r15
0x18000a680  mov     rsi, [rdi+110h]
0x18000a687  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18000a68c  mov     ecx, [rax]
0x18000a68e  cmp     ecx, 5
0x18000a691  jbe     short loc_18000A6A4
0x18000a693  lea     rdx, [rsi+8]; ActivityId
0x18000a697  mov     ecx, 3; ControlCode
0x18000a69c  call    cs:__imp_EventActivityIdControl
0x18000a6a2  jmp     short loc_18000A6AB
0x18000a6a4  xorps   xmm0, xmm0
0x18000a6a7  movups  xmmword ptr [rsi+8], xmm0
0x18000a6ab  mov     dword ptr [rsi], 1
0x18000a6b1  test    rbx, rbx
0x18000a6b4  jz      short loc_18000A6BF
0x18000a6b6  mov     rcx, rbx; SRWLock
0x18000a6b9  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a6bf  lea     r9, [rbp+57h+SRWLock]; lpContext
0x18000a6c3  mov     [rbp+57h+SRWLock], r15
0x18000a6c7  lea     r8, [rbp+57h+var_A8]; fPending
0x18000a6cb  mov     dword ptr [rbp+57h+var_A8], r15d
0x18000a6cf  xor     edx, edx; dwFlags
0x18000a6d1  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18000a6d8  call    cs:__imp_InitOnceBeginInitialize
0x18000a6de  test    eax, eax
0x18000a6e0  jz      loc_18000A7E0
0x18000a6e6  cmp     dword ptr [rbp+57h+var_A8], r15d
0x18000a6ea  jz      loc_18000A7E0
0x18000a6f0  mov     [rsp+0E0h+arg_10], r12
0x18000a6f8  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18000a6ff  lea     r12, qword_18004A760
0x18000a706  mov     cs:qword_18004A768, r15
0x18000a70d  mov     [rbp+57h+SRWLock], r12
0x18000a711  mov     cs:byte_18004A770, r15b
0x18000a718  mov     cs:dword_18004A774, r15d
0x18000a71f  mov     cs:qword_18004A760, rax
0x18000a726  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000a72d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x18000a734  mov     cs:CallbackContext, rax
0x18000a73b  call    atexit
0x18000a740  mov     rbx, cs:CallbackContext
0x18000a747  mov     cs:qword_18004A768, rbx
0x18000a74e  mov     cs:byte_18004A770, 1
0x18000a755  mov     rax, [rbx+8]
0x18000a759  movups  xmm0, xmmword ptr [rax-10h]
0x18000a75d  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x18000a761  cmp     [rbx+20h], r15
0x18000a765  jz      short loc_18000A76E
0x18000a767  mov     ecx, 5
0x18000a76c  int     29h; Win8: RtlFailFast(ecx)
0x18000a76e  lea     r9, [rbx+20h]; RegHandle
0x18000a772  mov     [rbx+28h], r15
0x18000a776  mov     r8, rbx; CallbackContext
0x18000a779  mov     [rbx+30h], r15
0x18000a77d  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000a784  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x18000a788  call    cs:__imp_EventRegister
0x18000a78e  test    eax, eax
0x18000a790  jnz     short loc_18000A7A9
0x18000a792  mov     r8, [rbx+8]
0x18000a796  mov     edx, 2
0x18000a79b  mov     rcx, [rbx+20h]
0x18000a79f  movzx   r9d, word ptr [r8]
0x18000a7a3  call    cs:__imp_EventSetInformation
0x18000a7a9  mov     rax, cs:qword_18004A760
0x18000a7b0  mov     rcx, r12
0x18000a7b3  mov     cs:dword_18004A774, 1
0x18000a7bd  mov     rax, [rax+8]
0x18000a7c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7c6  mov     r8, r12; lpContext
0x18000a7c9  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18000a7d0  xor     edx, edx; dwFlags
0x18000a7d2  call    cs:__imp_InitOnceComplete
0x18000a7d8  mov     r12, [rsp+0E0h+arg_10]
0x18000a7e0  mov     rax, [rbp+57h+SRWLock]
0x18000a7e4  mov     rsi, [rsp+0E0h+arg_8]
0x18000a7ec  mov     rbx, [rax+8]
0x18000a7f0  mov     eax, [rbx]
0x18000a7f2  cmp     eax, 5
0x18000a7f5  jbe     loc_18000A8E4
0x18000a7fb  mov     [rbp+57h+var_A0], r14
0x18000a7ff  call    cs:__imp_GetCurrentThreadId
0x18000a805  mov     r8, [rdi+110h]
0x18000a80c  mov     dword ptr [rbp+57h+var_A8], eax
0x18000a80f  mov     [rbp+57h+var_98], r15
0x18000a813  cmp     [r8+4], r15b
0x18000a817  jz      short loc_18000A835
0x18000a819  cmp     [r8+18h], r15d
0x18000a81d  lea     r9, [r8+18h]
0x18000a821  jnz     short loc_18000A838
0x18000a823  cmp     [r9+4], r15d
0x18000a827  jnz     short loc_18000A838
0x18000a829  cmp     [r9+8], r15d
0x18000a82d  jnz     short loc_18000A838
0x18000a82f  cmp     [r9+0Ch], r15d
0x18000a833  jnz     short loc_18000A838
0x18000a835  mov     r9, r15; RelatedActivityId
0x18000a838  mov     [rbp+57h+var_38], 8
0x18000a840  lea     rax, [rbp+57h+var_A0]
0x18000a844  mov     [rbp+57h+var_40], rax
0x18000a848  lea     rcx, _TraceLoggingMetadata
0x18000a84f  mov     [rbp+57h+var_48], 4
0x18000a857  lea     rax, [rbp+57h+var_A8]
0x18000a85b  mov     [rbp+57h+var_50], rax
0x18000a85f  lea     rdx, [rbp+57h+ProviderId]; EventDescriptor
0x18000a863  lea     rax, [rbp+57h+var_98]
0x18000a867  mov     [rbp+57h+var_58], 8
0x18000a86f  mov     [rbp+57h+var_60], rax
0x18000a873  add     r8, 8; ActivityId
0x18000a877  movzx   eax, cs:word_18003E3DB
0x18000a87e  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x18000a881  mov     rax, [rbx+8]
0x18000a885  mov     [rbp+57h+var_80.Ptr], rax
0x18000a889  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x18000a890  mov     qword ptr [rbp+57h+ProviderId.Data4], r15
0x18000a894  movzx   eax, word ptr [rax]
0x18000a897  mov     [rbp+57h+var_80.Size], eax
0x18000a89a  lea     rax, byte_18003E3E5
0x18000a8a1  mov     [rbp+57h+var_70], rax
0x18000a8a5  lea     rax, _TraceLoggingMetadataEnd
0x18000a8ac  sub     eax, ecx
0x18000a8ae  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x18000a8b5  mov     [rbp+57h+var_68], 3Fh ; '?'
0x18000a8bc  mov     [rbp+57h+var_64], 1
0x18000a8c3  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000a8c6  mov     eax, dword ptr [rbp+57h+SRWLock]
0x18000a8c9  mov     rcx, [rbx+20h]; RegHandle
0x18000a8cd  lea     rax, [rbp+57h+var_80]
0x18000a8d1  mov     [rsp+0E0h+UserData], rax; UserData
0x18000a8d6  mov     [rsp+0E0h+UserDataCount], 5; UserDataCount
0x18000a8de  call    cs:__imp_EventWriteTransfer
0x18000a8e4  mov     rcx, rdi
0x18000a8e7  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18000a8ec  mov     rcx, [rbp+57h+var_30]
0x18000a8f0  xor     rcx, rsp; StackCookie
0x18000a8f3  call    __security_check_cookie
0x18000a8f8  add     rsp, 0C0h
0x18000a8ff  pop     r15
0x18000a901  pop     r14
0x18000a903  pop     rdi
0x18000a904  pop     rbx
0x18000a905  pop     rbp
0x18000a906  retn
```
