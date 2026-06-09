# WnsCPLog::WnsSinkNotificationReceived::StartActivity(void)

- ea: `0x180003590`
- end: `0x1800038c3`
- name: `?StartActivity@WnsSinkNotificationReceived@WnsCPLog@@QEAAXXZ`
- size: `819`
- prototype: `void __fastcall(WnsCPLog::WnsSinkNotificationReceived *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003320`

## callees

- `0x180003590`
- `0x18000d1f0`
- `0x18000d830`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800035d8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800035d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800035ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003606`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000366a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800035ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003606`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000366a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037b4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180003882`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180003882`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000364d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000364d`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000374c`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000374c`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003731`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180003731`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180003689`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180003689`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000377b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000377b`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkNotificationReceived::StartActivity(WnsCPLog::WnsSinkNotificationReceived *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // rbx
  __int64 v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  ULONGLONG *v6; // rbx
  _QWORD *Ptr; // rbx
  __int64 v8; // r8
  const GUID *v9; // r9
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-49h] BYREF
  PSRWLOCK v11; // [rsp+38h] [rbp-41h] BYREF
  __int64 v12; // [rsp+40h] [rbp-39h] BYREF
  GUID ProviderId; // [rsp+48h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-19h] BYREF
  char *v15; // [rsp+70h] [rbp-9h]
  int v16; // [rsp+78h] [rbp-1h]
  int v17; // [rsp+7Ch] [rbp+3h]
  __int64 *v18; // [rsp+80h] [rbp+7h]
  __int64 v19; // [rsp+88h] [rbp+Fh]
  PSRWLOCK *v20; // [rsp+90h] [rbp+17h]
  __int64 v21; // [rsp+98h] [rbp+1Fh]

  v2 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  if ( v2 )
  {
    v3 = v2 + 33;
    AcquireSRWLockExclusive(v3);
    SRWLock = 0;
  }
  else
  {
    v11 = 0;
    v3 = 0;
  }
  v4 = *((_QWORD *)this + 34);
  v5 = WnsCPTracelogger::Provider();
  if ( *(_DWORD *)v5 > 5u
    && (*((_QWORD *)v5 + 2) & 0x200000000000LL) != 0
    && (*((_QWORD *)v5 + 3) & 0x200000000000LL) == *((_QWORD *)v5 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  }
  else
  {
    *(_OWORD *)(v4 + 8) = 0;
  }
  *(_DWORD *)v4 = 1;
  if ( v3 )
    ReleaseSRWLockExclusive(v3);
  SRWLock = 0;
  LODWORD(v11) = 0;
  if ( InitOnceBeginInitialize(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, (PBOOL)&v11, (LPVOID *)&SRWLock)
    && (_DWORD)v11 )
  {
    SRWLock = (PSRWLOCK)&qword_18004A760;
    qword_18004A768 = 0;
    byte_18004A770 = 0;
    dword_18004A774 = 0;
    qword_18004A760 = (__int64)&wil::details::FeatureLogging::`vftable';
    CallbackContext = &`WnsCPTracelogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_633a74d489e420a2ff0e92495a1626f6_::_lambda_invoker_cdecl_);
    v6 = (ULONGLONG *)CallbackContext;
    qword_18004A768 = (__int64)CallbackContext;
    byte_18004A770 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    *((_QWORD *)CallbackContext + 5) = 0;
    v6[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v6, v6 + 4) )
      EventSetInformation(v6[4], 2, v6[1], *(unsigned __int16 *)v6[1]);
    dword_18004A774 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18004A760 + 8))(&qword_18004A760);
    InitOnceComplete(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &qword_18004A760);
  }
  Ptr = SRWLock[1].Ptr;
  if ( *(_DWORD *)Ptr > 5u && (Ptr[2] & 0x200000000000LL) != 0 && (Ptr[3] & 0x200000000000LL) == Ptr[3] )
  {
    LODWORD(v11) = GetCurrentThreadId();
    v12 = 0;
    v8 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v8 + 4)
      || (v9 = (const GUID *)(v8 + 24), !*(_DWORD *)(v8 + 24))
      && !*(_DWORD *)(v8 + 28)
      && !*(_DWORD *)(v8 + 32)
      && !*(_DWORD *)(v8 + 36) )
    {
      v9 = 0;
    }
    v20 = &v11;
    v21 = 4;
    v18 = &v12;
    v19 = 8;
    ProviderId.Data1 = 184549376;
    *(_DWORD *)&ProviderId.Data2 = 261;
    *(_QWORD *)ProviderId.Data4 = 0x200000000000LL;
    UserData.Ptr = Ptr[1];
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v15 = byte_1800426BD;
    v16 = 71;
    v17 = 1;
    LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(Ptr[4], (PCEVENT_DESCRIPTOR)&ProviderId, (LPCGUID)(v8 + 8), v9, 4u, &UserData);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((WnsCPLog::WnsSinkNotificationReceived *)((char *)this + 288));
}

```

## disassembly

```asm
0x180003590  mov     [rsp-8+arg_8], rbx
0x180003595  mov     [rsp-8+arg_10], rsi
0x18000359a  push    rbp
0x18000359b  push    rdi
0x18000359c  push    r12
0x18000359e  push    r14
0x1800035a0  push    r15
0x1800035a2  lea     rbp, [rsp-37h]
0x1800035a7  sub     rsp, 0B0h
0x1800035ae  mov     rax, cs:__security_cookie
0x1800035b5  xor     rax, rsp
0x1800035b8  mov     [rbp+57h+var_30], rax
0x1800035bc  mov     rsi, rcx
0x1800035bf  xor     r14d, r14d
0x1800035c2  mov     rbx, [rcx+118h]
0x1800035c9  test    rbx, rbx
0x1800035cc  jz      short loc_1800035F6
0x1800035ce  add     rbx, 108h
0x1800035d5  mov     rcx, rbx; SRWLock
0x1800035d8  call    cs:__imp_AcquireSRWLockExclusive
0x1800035de  lea     rax, [rbp+57h+SRWLock]
0x1800035e2  mov     [rax], r14
0x1800035e5  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800035e9  test    rcx, rcx
0x1800035ec  jz      short loc_18000360F
0x1800035ee  call    cs:__imp_ReleaseSRWLockExclusive
0x1800035f4  jmp     short loc_18000360F
0x1800035f6  lea     rax, [rbp+57h+var_98]
0x1800035fa  mov     [rax], r14
0x1800035fd  mov     rcx, [rbp+57h+var_98]; SRWLock
0x180003601  test    rcx, rcx
0x180003604  jz      short loc_18000360C
0x180003606  call    cs:__imp_ReleaseSRWLockExclusive
0x18000360c  mov     rbx, r14
0x18000360f  mov     rdi, [rsi+110h]
0x180003616  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18000361b  mov     ecx, [rax]
0x18000361d  mov     r15, 200000000000h
0x180003627  cmp     ecx, 5
0x18000362a  jbe     short loc_180003655
0x18000362c  mov     rcx, [rax+18h]
0x180003630  mov     rax, [rax+10h]
0x180003634  test    r15, rax
0x180003637  jz      short loc_180003655
0x180003639  mov     rax, rcx
0x18000363c  and     rax, r15
0x18000363f  cmp     rax, rcx
0x180003642  jnz     short loc_180003655
0x180003644  lea     rdx, [rdi+8]; ActivityId
0x180003648  mov     ecx, 3; ControlCode
0x18000364d  call    cs:__imp_EventActivityIdControl
0x180003653  jmp     short loc_18000365C
0x180003655  xorps   xmm0, xmm0
0x180003658  movups  xmmword ptr [rdi+8], xmm0
0x18000365c  mov     dword ptr [rdi], 1
0x180003662  test    rbx, rbx
0x180003665  jz      short loc_180003670
0x180003667  mov     rcx, rbx; SRWLock
0x18000366a  call    cs:__imp_ReleaseSRWLockExclusive
0x180003670  mov     [rbp+57h+SRWLock], r14
0x180003674  mov     dword ptr [rbp+57h+var_98], r14d
0x180003678  lea     r9, [rbp+57h+SRWLock]; lpContext
0x18000367c  lea     r8, [rbp+57h+var_98]; fPending
0x180003680  xor     edx, edx; dwFlags
0x180003682  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x180003689  call    cs:__imp_InitOnceBeginInitialize
0x18000368f  test    eax, eax
0x180003691  jz      loc_180003781
0x180003697  cmp     dword ptr [rbp+57h+var_98], r14d
0x18000369b  jz      loc_180003781
0x1800036a1  lea     r12, qword_18004A760
0x1800036a8  mov     [rbp+57h+SRWLock], r12
0x1800036ac  mov     cs:qword_18004A768, r14
0x1800036b3  mov     cs:byte_18004A770, r14b
0x1800036ba  mov     cs:dword_18004A774, r14d
0x1800036c1  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x1800036c8  mov     cs:qword_18004A760, rax
0x1800036cf  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800036d6  mov     cs:CallbackContext, rax
0x1800036dd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x1800036e4  call    atexit
0x1800036e9  mov     rbx, cs:CallbackContext
0x1800036f0  mov     cs:qword_18004A768, rbx
0x1800036f7  mov     cs:byte_18004A770, 1
0x1800036fe  mov     rax, [rbx+8]
0x180003702  movups  xmm0, xmmword ptr [rax-10h]
0x180003706  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x18000370a  cmp     [rbx+20h], r14
0x18000370e  jz      short loc_180003717
0x180003710  mov     ecx, 5
0x180003715  int     29h; Win8: RtlFailFast(ecx)
0x180003717  mov     [rbx+28h], r14
0x18000371b  mov     [rbx+30h], r14
0x18000371f  lea     r9, [rbx+20h]; RegHandle
0x180003723  mov     r8, rbx; CallbackContext
0x180003726  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000372d  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x180003731  call    cs:__imp_EventRegister
0x180003737  test    eax, eax
0x180003739  jnz     short loc_180003752
0x18000373b  mov     r8, [rbx+8]
0x18000373f  movzx   r9d, word ptr [r8]
0x180003743  mov     edx, 2
0x180003748  mov     rcx, [rbx+20h]
0x18000374c  call    cs:__imp_EventSetInformation
0x180003752  mov     cs:dword_18004A774, 1
0x18000375c  mov     rax, cs:qword_18004A760
0x180003763  mov     rcx, r12
0x180003766  mov     rax, [rax+8]
0x18000376a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000376f  mov     r8, r12; lpContext
0x180003772  xor     edx, edx; dwFlags
0x180003774  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18000377b  call    cs:__imp_InitOnceComplete
0x180003781  mov     rax, [rbp+57h+SRWLock]
0x180003785  mov     rbx, [rax+8]
0x180003789  mov     eax, [rbx]
0x18000378b  cmp     eax, 5
0x18000378e  jbe     loc_180003888
0x180003794  mov     rcx, [rbx+18h]
0x180003798  mov     rax, [rbx+10h]
0x18000379c  test    r15, rax
0x18000379f  jz      loc_180003888
0x1800037a5  mov     rax, rcx
0x1800037a8  and     rax, r15
0x1800037ab  cmp     rax, rcx
0x1800037ae  jnz     loc_180003888
0x1800037b4  call    cs:__imp_GetCurrentThreadId
0x1800037ba  mov     dword ptr [rbp+57h+var_98], eax
0x1800037bd  mov     [rbp+57h+var_90], r14
0x1800037c1  mov     r8, [rsi+110h]
0x1800037c8  cmp     [r8+4], r14b
0x1800037cc  jz      short loc_1800037E9
0x1800037ce  lea     r9, [r8+18h]
0x1800037d2  cmp     [r9], r14d
0x1800037d5  jnz     short loc_1800037EC
0x1800037d7  cmp     [r9+4], r14d
0x1800037db  jnz     short loc_1800037EC
0x1800037dd  cmp     [r9+8], r14d
0x1800037e1  jnz     short loc_1800037EC
0x1800037e3  cmp     [r9+0Ch], r14d
0x1800037e7  jnz     short loc_1800037EC
0x1800037e9  mov     r9, r14; RelatedActivityId
0x1800037ec  lea     rax, [rbp+57h+var_98]
0x1800037f0  mov     [rbp+57h+var_40], rax
0x1800037f4  mov     [rbp+57h+var_38], 4
0x1800037fc  lea     rax, [rbp+57h+var_90]
0x180003800  mov     [rbp+57h+var_50], rax
0x180003804  mov     [rbp+57h+var_48], 8
0x18000380c  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x180003813  movzx   eax, cs:word_1800426B3
0x18000381a  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x18000381d  mov     qword ptr [rbp+57h+ProviderId.Data4], r15
0x180003821  mov     rax, [rbx+8]
0x180003825  mov     [rbp+57h+var_70.Ptr], rax
0x180003829  movzx   eax, word ptr [rax]
0x18000382c  mov     [rbp+57h+var_70.Size], eax
0x18000382f  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x180003836  lea     rax, byte_1800426BD
0x18000383d  mov     [rbp+57h+var_60], rax
0x180003841  mov     [rbp+57h+var_58], 47h ; 'G'
0x180003848  mov     [rbp+57h+var_54], 1
0x18000384f  lea     rax, _TraceLoggingMetadataEnd
0x180003856  lea     rcx, _TraceLoggingMetadata
0x18000385d  sub     eax, ecx
0x18000385f  mov     dword ptr [rbp+57h+SRWLock], eax
0x180003862  mov     eax, dword ptr [rbp+57h+SRWLock]
0x180003865  add     r8, 8; ActivityId
0x180003869  lea     rax, [rbp+57h+var_70]
0x18000386d  mov     [rsp+0D0h+UserData], rax; UserData
0x180003872  mov     [rsp+0D0h+UserDataCount], 4; UserDataCount
0x18000387a  lea     rdx, [rbp+57h+ProviderId]; EventDescriptor
0x18000387e  mov     rcx, [rbx+20h]; RegHandle
0x180003882  call    cs:__imp_EventWriteTransfer
0x180003888  lea     rcx, [rsi+120h]; this
0x18000388f  cmp     [rcx+18h], r14d
0x180003893  jnz     short loc_18000389B
0x180003895  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000389a  nop
0x18000389b  mov     rcx, [rbp+57h+var_30]
0x18000389f  xor     rcx, rsp; StackCookie
0x1800038a2  call    __security_check_cookie
0x1800038a7  lea     r11, [rsp+0D0h+var_20]
0x1800038af  mov     rbx, [r11+38h]
0x1800038b3  mov     rsi, [r11+40h]
0x1800038b7  mov     rsp, r11
0x1800038ba  pop     r15
0x1800038bc  pop     r14
0x1800038be  pop     r12
0x1800038c0  pop     rdi
0x1800038c1  pop     rbp
0x1800038c2  retn
```
