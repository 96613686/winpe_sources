# WnsCPLog::WnsReconnectTimerExpired::StartActivity(void)

- ea: `0x180006820`
- end: `0x180006af2`
- name: `?StartActivity@WnsReconnectTimerExpired@WnsCPLog@@QEAAXXZ`
- size: `722`
- prototype: `void __fastcall(WnsCPLog::WnsReconnectTimerExpired *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006770`

## callees

- `0x180006820`
- `0x18000d830`
- `0x18000d8f0`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000685f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000685f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006875`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000688d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800068cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006875`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000688d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800068cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069f9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006ac7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006ac7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800068b2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800068b2`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800069b1`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800069b1`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180006996`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180006996`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800068ee`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800068ee`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800069e0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800069e0`

## pseudocode

```c
void __fastcall WnsCPLog::WnsReconnectTimerExpired::StartActivity(WnsCPLog::WnsReconnectTimerExpired *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // rbx
  __int64 v4; // rsi
  ULONGLONG *v5; // rbx
  _QWORD *Ptr; // rbx
  __int64 v7; // r8
  const GUID *v8; // r9
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-59h] BYREF
  PSRWLOCK v10; // [rsp+38h] [rbp-51h] BYREF
  __int64 v11; // [rsp+40h] [rbp-49h] BYREF
  GUID ProviderId; // [rsp+48h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-29h] BYREF
  char *v14; // [rsp+70h] [rbp-19h]
  int v15; // [rsp+78h] [rbp-11h]
  int v16; // [rsp+7Ch] [rbp-Dh]
  __int64 *v17; // [rsp+80h] [rbp-9h]
  __int64 v18; // [rsp+88h] [rbp-1h]
  PSRWLOCK *v19; // [rsp+90h] [rbp+7h]
  __int64 v20; // [rsp+98h] [rbp+Fh]

  v2 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  if ( v2 )
  {
    v3 = v2 + 33;
    AcquireSRWLockExclusive(v3);
    SRWLock = 0;
  }
  else
  {
    v10 = 0;
    v3 = 0;
  }
  v4 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)WnsCPTracelogger::Provider() <= 5u )
    *(_OWORD *)(v4 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  *(_DWORD *)v4 = 1;
  if ( v3 )
    ReleaseSRWLockExclusive(v3);
  SRWLock = 0;
  LODWORD(v10) = 0;
  if ( InitOnceBeginInitialize(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, (PBOOL)&v10, (LPVOID *)&SRWLock)
    && (_DWORD)v10 )
  {
    SRWLock = (PSRWLOCK)&qword_18004A760;
    qword_18004A768 = 0;
    byte_18004A770 = 0;
    dword_18004A774 = 0;
    qword_18004A760 = (__int64)&wil::details::FeatureLogging::`vftable';
    CallbackContext = &`WnsCPTracelogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_633a74d489e420a2ff0e92495a1626f6_::_lambda_invoker_cdecl_);
    v5 = (ULONGLONG *)CallbackContext;
    qword_18004A768 = (__int64)CallbackContext;
    byte_18004A770 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    *((_QWORD *)CallbackContext + 5) = 0;
    v5[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v5, v5 + 4) )
      EventSetInformation(v5[4], 2, v5[1], *(unsigned __int16 *)v5[1]);
    dword_18004A774 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18004A760 + 8))(&qword_18004A760);
    InitOnceComplete(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &qword_18004A760);
  }
  Ptr = SRWLock[1].Ptr;
  if ( *(_DWORD *)Ptr > 5u )
  {
    LODWORD(v10) = GetCurrentThreadId();
    v11 = 0;
    v7 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v7 + 4)
      || (v8 = (const GUID *)(v7 + 24), !*(_DWORD *)(v7 + 24))
      && !*(_DWORD *)(v7 + 28)
      && !*(_DWORD *)(v7 + 32)
      && !*(_DWORD *)(v7 + 36) )
    {
      v8 = 0;
    }
    v19 = &v10;
    v20 = 4;
    v17 = &v11;
    v18 = 8;
    ProviderId.Data1 = 184549376;
    *(_DWORD *)&ProviderId.Data2 = 261;
    *(_QWORD *)ProviderId.Data4 = 0;
    UserData.Ptr = Ptr[1];
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v14 = &byte_18004142F;
    v15 = 68;
    v16 = 1;
    LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(Ptr[4], (PCEVENT_DESCRIPTOR)&ProviderId, (LPCGUID)(v7 + 8), v8, 4u, &UserData);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180006820  push    rbp
0x180006822  push    rbx
0x180006823  push    rsi
0x180006824  push    rdi
0x180006825  push    r14
0x180006827  push    r15
0x180006829  lea     rbp, [rsp-2Fh]
0x18000682e  sub     rsp, 0B8h
0x180006835  mov     rax, cs:__security_cookie
0x18000683c  xor     rax, rsp
0x18000683f  mov     [rbp+57h+var_40], rax
0x180006843  mov     rdi, rcx
0x180006846  xor     r14d, r14d
0x180006849  mov     rbx, [rcx+118h]
0x180006850  test    rbx, rbx
0x180006853  jz      short loc_18000687D
0x180006855  add     rbx, 108h
0x18000685c  mov     rcx, rbx; SRWLock
0x18000685f  call    cs:__imp_AcquireSRWLockExclusive
0x180006865  lea     rax, [rbp+57h+SRWLock]
0x180006869  mov     [rax], r14
0x18000686c  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180006870  test    rcx, rcx
0x180006873  jz      short loc_180006896
0x180006875  call    cs:__imp_ReleaseSRWLockExclusive
0x18000687b  jmp     short loc_180006896
0x18000687d  lea     rax, [rbp+57h+var_A8]
0x180006881  mov     [rax], r14
0x180006884  mov     rcx, [rbp+57h+var_A8]; SRWLock
0x180006888  test    rcx, rcx
0x18000688b  jz      short loc_180006893
0x18000688d  call    cs:__imp_ReleaseSRWLockExclusive
0x180006893  mov     rbx, r14
0x180006896  mov     rsi, [rdi+110h]
0x18000689d  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x1800068a2  mov     ecx, [rax]
0x1800068a4  cmp     ecx, 5
0x1800068a7  jbe     short loc_1800068BA
0x1800068a9  lea     rdx, [rsi+8]; ActivityId
0x1800068ad  mov     ecx, 3; ControlCode
0x1800068b2  call    cs:__imp_EventActivityIdControl
0x1800068b8  jmp     short loc_1800068C1
0x1800068ba  xorps   xmm0, xmm0
0x1800068bd  movups  xmmword ptr [rsi+8], xmm0
0x1800068c1  mov     dword ptr [rsi], 1
0x1800068c7  test    rbx, rbx
0x1800068ca  jz      short loc_1800068D5
0x1800068cc  mov     rcx, rbx; SRWLock
0x1800068cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800068d5  mov     [rbp+57h+SRWLock], r14
0x1800068d9  mov     dword ptr [rbp+57h+var_A8], r14d
0x1800068dd  lea     r9, [rbp+57h+SRWLock]; lpContext
0x1800068e1  lea     r8, [rbp+57h+var_A8]; fPending
0x1800068e5  xor     edx, edx; dwFlags
0x1800068e7  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x1800068ee  call    cs:__imp_InitOnceBeginInitialize
0x1800068f4  test    eax, eax
0x1800068f6  jz      loc_1800069E6
0x1800068fc  cmp     dword ptr [rbp+57h+var_A8], r14d
0x180006900  jz      loc_1800069E6
0x180006906  lea     r15, qword_18004A760
0x18000690d  mov     [rbp+57h+SRWLock], r15
0x180006911  mov     cs:qword_18004A768, r14
0x180006918  mov     cs:byte_18004A770, r14b
0x18000691f  mov     cs:dword_18004A774, r14d
0x180006926  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18000692d  mov     cs:qword_18004A760, rax
0x180006934  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000693b  mov     cs:CallbackContext, rax
0x180006942  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x180006949  call    atexit
0x18000694e  mov     rbx, cs:CallbackContext
0x180006955  mov     cs:qword_18004A768, rbx
0x18000695c  mov     cs:byte_18004A770, 1
0x180006963  mov     rax, [rbx+8]
0x180006967  movups  xmm0, xmmword ptr [rax-10h]
0x18000696b  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x18000696f  cmp     [rbx+20h], r14
0x180006973  jz      short loc_18000697C
0x180006975  mov     ecx, 5
0x18000697a  int     29h; Win8: RtlFailFast(ecx)
0x18000697c  mov     [rbx+28h], r14
0x180006980  mov     [rbx+30h], r14
0x180006984  lea     r9, [rbx+20h]; RegHandle
0x180006988  mov     r8, rbx; CallbackContext
0x18000698b  lea     rdx, _tlgEnableCallback; EnableCallback
0x180006992  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x180006996  call    cs:__imp_EventRegister
0x18000699c  test    eax, eax
0x18000699e  jnz     short loc_1800069B7
0x1800069a0  mov     r8, [rbx+8]
0x1800069a4  movzx   r9d, word ptr [r8]
0x1800069a8  mov     edx, 2
0x1800069ad  mov     rcx, [rbx+20h]
0x1800069b1  call    cs:__imp_EventSetInformation
0x1800069b7  mov     cs:dword_18004A774, 1
0x1800069c1  mov     rax, cs:qword_18004A760
0x1800069c8  mov     rcx, r15
0x1800069cb  mov     rax, [rax+8]
0x1800069cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069d4  mov     r8, r15; lpContext
0x1800069d7  xor     edx, edx; dwFlags
0x1800069d9  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x1800069e0  call    cs:__imp_InitOnceComplete
0x1800069e6  mov     rax, [rbp+57h+SRWLock]
0x1800069ea  mov     rbx, [rax+8]
0x1800069ee  mov     eax, [rbx]
0x1800069f0  cmp     eax, 5
0x1800069f3  jbe     loc_180006ACD
0x1800069f9  call    cs:__imp_GetCurrentThreadId
0x1800069ff  mov     dword ptr [rbp+57h+var_A8], eax
0x180006a02  mov     [rbp+57h+var_A0], r14
0x180006a06  mov     r8, [rdi+110h]
0x180006a0d  cmp     [r8+4], r14b
0x180006a11  jz      short loc_180006A2E
0x180006a13  lea     r9, [r8+18h]
0x180006a17  cmp     [r9], r14d
0x180006a1a  jnz     short loc_180006A31
0x180006a1c  cmp     [r9+4], r14d
0x180006a20  jnz     short loc_180006A31
0x180006a22  cmp     [r9+8], r14d
0x180006a26  jnz     short loc_180006A31
0x180006a28  cmp     [r9+0Ch], r14d
0x180006a2c  jnz     short loc_180006A31
0x180006a2e  mov     r9, r14; RelatedActivityId
0x180006a31  lea     rax, [rbp+57h+var_A8]
0x180006a35  mov     [rbp+57h+var_50], rax
0x180006a39  mov     [rbp+57h+var_48], 4
0x180006a41  lea     rax, [rbp+57h+var_A0]
0x180006a45  mov     [rbp+57h+var_60], rax
0x180006a49  mov     [rbp+57h+var_58], 8
0x180006a51  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x180006a58  movzx   eax, cs:word_180041425
0x180006a5f  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x180006a62  mov     qword ptr [rbp+57h+ProviderId.Data4], r14
0x180006a66  mov     rax, [rbx+8]
0x180006a6a  mov     [rbp+57h+var_80.Ptr], rax
0x180006a6e  movzx   eax, word ptr [rax]
0x180006a71  mov     [rbp+57h+var_80.Size], eax
0x180006a74  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x180006a7b  lea     rax, byte_18004142F
0x180006a82  mov     [rbp+57h+var_70], rax
0x180006a86  mov     [rbp+57h+var_68], 44h ; 'D'
0x180006a8d  mov     [rbp+57h+var_64], 1
0x180006a94  lea     rax, _TraceLoggingMetadataEnd
0x180006a9b  lea     rcx, _TraceLoggingMetadata
0x180006aa2  sub     eax, ecx
0x180006aa4  mov     dword ptr [rbp+57h+SRWLock], eax
0x180006aa7  mov     eax, dword ptr [rbp+57h+SRWLock]
0x180006aaa  add     r8, 8; ActivityId
0x180006aae  lea     rax, [rbp+57h+var_80]
0x180006ab2  mov     [rsp+0E0h+UserData], rax; UserData
0x180006ab7  mov     [rsp+0E0h+UserDataCount], 4; UserDataCount
0x180006abf  lea     rdx, [rbp+57h+ProviderId]; EventDescriptor
0x180006ac3  mov     rcx, [rbx+20h]; RegHandle
0x180006ac7  call    cs:__imp_EventWriteTransfer
0x180006acd  mov     rcx, rdi
0x180006ad0  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180006ad5  nop
0x180006ad6  mov     rcx, [rbp+57h+var_40]
0x180006ada  xor     rcx, rsp; StackCookie
0x180006add  call    __security_check_cookie
0x180006ae2  add     rsp, 0B8h
0x180006ae9  pop     r15
0x180006aeb  pop     r14
0x180006aed  pop     rdi
0x180006aee  pop     rsi
0x180006aef  pop     rbx
0x180006af0  pop     rbp
0x180006af1  retn
```
