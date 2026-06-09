# WnsCPLog::ConnectActivity::StartActivity(__int64,uint,__MIDL___MIDL_itf_wpnplatform_0000_0000_0002)

- ea: `0x18000c990`
- end: `0x18000cd7f`
- name: `?StartActivity@ConnectActivity@WnsCPLog@@QEAAX_JIW4__MIDL___MIDL_itf_wpnplatform_0000_0000_0002@@@Z`
- size: `1007`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000b720`

## callees

- `0x18000c990`
- `0x18000d1f0`
- `0x18000d830`
- `0x180014e50`
- `0x1800166ac`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c9dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c9dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c9f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ca0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ca72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c9f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ca0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ca72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc15`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cd47`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cd47`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ca55`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ca55`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000cb5c`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000cb5c`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000cb41`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000cb41`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ca95`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ca95`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000cb93`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000cb93`

## pseudocode

```c
void __fastcall WnsCPLog::ConnectActivity::StartActivity(__int64 a1, __int64 a2, int a3, int a4)
{
  RTL_SRWLOCK *v4; // rbx
  RTL_SRWLOCK *v9; // rbx
  __int64 v10; // rdi
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  _QWORD *v14; // rbx
  ULONGLONG *v15; // r9
  _QWORD *Ptr; // rbx
  __int64 v17; // rdx
  DWORD CurrentThreadId; // eax
  __int64 v19; // r8
  const GUID *v20; // r9
  WINBOOL fPending; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+44h] [rbp-BCh] BYREF
  int v25; // [rsp+48h] [rbp-B8h] BYREF
  PSRWLOCK v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  GUID ProviderId; // [rsp+68h] [rbp-98h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-80h] BYREF
  __int16 *v31; // [rsp+90h] [rbp-70h]
  int v32; // [rsp+98h] [rbp-68h]
  int v33; // [rsp+9Ch] [rbp-64h]
  __int64 *v34; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  PSRWLOCK *v36; // [rsp+B0h] [rbp-50h]
  __int64 v37; // [rsp+B8h] [rbp-48h]
  __int64 *v38; // [rsp+C0h] [rbp-40h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  int *v40; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  int *v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  int *v44; // [rsp+F0h] [rbp-10h]
  __int64 v45; // [rsp+F8h] [rbp-8h]
  WINBOOL *p_fPending; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+108h] [rbp+8h]

  v4 = *(RTL_SRWLOCK **)(a1 + 280);
  if ( v4 )
  {
    v9 = v4 + 33;
    AcquireSRWLockExclusive(v9);
    SRWLock = 0;
  }
  else
  {
    v26 = 0;
    v9 = 0;
  }
  v10 = *(_QWORD *)(a1 + 272);
  v11 = WnsCPTracelogger::Provider();
  if ( *(_DWORD *)v11 > 5u
    && (*((_QWORD *)v11 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v11 + 3) & 0x400000000000LL) == *((_QWORD *)v11 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v10 + 8));
  }
  else
  {
    *(_OWORD *)(v10 + 8) = 0;
  }
  *(_DWORD *)v10 = 1;
  if ( v9 )
    ReleaseSRWLockExclusive(v9);
  SRWLock = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock)
    && fPending )
  {
    qword_18004A768 = 0;
    SRWLock = (PSRWLOCK)&qword_18004A760;
    qword_18004A760 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_18004A770 = 0;
    dword_18004A774 = 0;
    CallbackContext = &`WnsCPTracelogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_633a74d489e420a2ff0e92495a1626f6_::_lambda_invoker_cdecl_);
    v14 = CallbackContext;
    qword_18004A768 = (__int64)CallbackContext;
    byte_18004A770 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    v15 = (ULONGLONG *)((char *)CallbackContext + 32);
    *((_QWORD *)CallbackContext + 5) = 0;
    v14[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v14, v15) )
      EventSetInformation(v14[4], 2, v14[1], *(unsigned __int16 *)v14[1]);
    dword_18004A774 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18004A760 + 8))(&qword_18004A760);
    InitOnceComplete(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &qword_18004A760);
  }
  Ptr = SRWLock[1].Ptr;
  if ( *(_DWORD *)Ptr > 5u && (Ptr[2] & 0x400000000000LL) != 0 && (Ptr[3] & 0x400000000000LL) == Ptr[3] )
  {
    LOBYTE(v13) = 3;
    LOBYTE(v12) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_40007690>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_40007690>::GetImpl'::`2'::impl,
      v12,
      v13);
    fPending = 1;
    LOBYTE(v17) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WNS_40745204>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_WNS_40745204>::GetImpl'::`2'::impl,
      v17);
    v23 = 1;
    v24 = a4;
    v25 = a3;
    v27 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v19 = *(_QWORD *)(a1 + 272);
    LODWORD(v26) = CurrentThreadId;
    v28 = 0x1000000;
    if ( !*(_BYTE *)(v19 + 4)
      || (v20 = (const GUID *)(v19 + 24), !*(_DWORD *)(v19 + 24))
      && !*(_DWORD *)(v19 + 28)
      && !*(_DWORD *)(v19 + 32)
      && !*(_DWORD *)(v19 + 36) )
    {
      v20 = 0;
    }
    v47 = 4;
    p_fPending = &fPending;
    v45 = 4;
    v44 = &v23;
    v43 = 4;
    v42 = &v24;
    v41 = 4;
    v40 = &v25;
    v38 = &v27;
    v36 = &v26;
    v34 = &v28;
    *(_DWORD *)&ProviderId.Data2 = 261;
    UserData.Ptr = Ptr[1];
    v39 = 8;
    v37 = 4;
    v35 = 8;
    ProviderId.Data1 = 184549376;
    *(_QWORD *)ProviderId.Data4 = 0x400000000000LL;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v31 = word_180041172;
    UserData.Reserved = 2;
    v32 = 155;
    v33 = 1;
    LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(Ptr[4], (PCEVENT_DESCRIPTOR)&ProviderId, (LPCGUID)(v19 + 8), v20, 9u, &UserData);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x18000c990  push    rbp
0x18000c992  push    rbx
0x18000c993  push    rsi
0x18000c994  push    rdi
0x18000c995  push    r12
0x18000c997  push    r13
0x18000c999  push    r14
0x18000c99b  push    r15
0x18000c99d  lea     rbp, [rsp-28h]
0x18000c9a2  sub     rsp, 128h
0x18000c9a9  mov     rax, cs:__security_cookie
0x18000c9b0  xor     rax, rsp
0x18000c9b3  mov     [rbp+60h+var_50], rax
0x18000c9b7  mov     rbx, [rcx+118h]
0x18000c9be  xor     r13d, r13d
0x18000c9c1  mov     r14d, r9d
0x18000c9c4  mov     r15d, r8d
0x18000c9c7  mov     r12, rdx
0x18000c9ca  mov     rsi, rcx
0x18000c9cd  test    rbx, rbx
0x18000c9d0  jz      short loc_18000C9FC
0x18000c9d2  add     rbx, 108h
0x18000c9d9  mov     rcx, rbx; SRWLock
0x18000c9dc  call    cs:__imp_AcquireSRWLockExclusive
0x18000c9e2  lea     rax, [rsp+160h+SRWLock]
0x18000c9e7  mov     [rax], r13
0x18000c9ea  mov     rcx, [rsp+160h+SRWLock]; SRWLock
0x18000c9ef  test    rcx, rcx
0x18000c9f2  jz      short loc_18000CA17
0x18000c9f4  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c9fa  jmp     short loc_18000CA17
0x18000c9fc  lea     rax, [rsp+160h+var_110]
0x18000ca01  mov     [rax], r13
0x18000ca04  mov     rcx, [rsp+160h+var_110]; SRWLock
0x18000ca09  test    rcx, rcx
0x18000ca0c  jz      short loc_18000CA14
0x18000ca0e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ca14  mov     rbx, r13
0x18000ca17  mov     rdi, [rsi+110h]
0x18000ca1e  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18000ca23  mov     rdx, 400000000000h
0x18000ca2d  mov     ecx, [rax]
0x18000ca2f  cmp     ecx, 5
0x18000ca32  jbe     short loc_18000CA5D
0x18000ca34  mov     rcx, [rax+18h]
0x18000ca38  mov     rax, [rax+10h]
0x18000ca3c  test    rdx, rax
0x18000ca3f  jz      short loc_18000CA5D
0x18000ca41  mov     rax, rcx
0x18000ca44  and     rax, rdx
0x18000ca47  cmp     rax, rcx
0x18000ca4a  jnz     short loc_18000CA5D
0x18000ca4c  lea     rdx, [rdi+8]; ActivityId
0x18000ca50  mov     ecx, 3; ControlCode
0x18000ca55  call    cs:__imp_EventActivityIdControl
0x18000ca5b  jmp     short loc_18000CA64
0x18000ca5d  xorps   xmm0, xmm0
0x18000ca60  movups  xmmword ptr [rdi+8], xmm0
0x18000ca64  mov     dword ptr [rdi], 1
0x18000ca6a  test    rbx, rbx
0x18000ca6d  jz      short loc_18000CA78
0x18000ca6f  mov     rcx, rbx; SRWLock
0x18000ca72  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ca78  lea     r9, [rsp+160h+SRWLock]; lpContext
0x18000ca7d  mov     [rsp+160h+SRWLock], r13
0x18000ca82  lea     r8, [rsp+160h+fPending]; fPending
0x18000ca87  mov     [rsp+160h+fPending], r13d
0x18000ca8c  xor     edx, edx; dwFlags
0x18000ca8e  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18000ca95  call    cs:__imp_InitOnceBeginInitialize
0x18000ca9b  test    eax, eax
0x18000ca9d  jz      loc_18000CB99
0x18000caa3  cmp     [rsp+160h+fPending], r13d
0x18000caa8  jz      loc_18000CB99
0x18000caae  lea     rax, qword_18004A760
0x18000cab5  mov     cs:qword_18004A768, r13
0x18000cabc  mov     [rsp+160h+SRWLock], rax
0x18000cac1  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18000cac8  mov     cs:qword_18004A760, rax
0x18000cacf  mov     cs:byte_18004A770, r13b
0x18000cad6  mov     cs:dword_18004A774, r13d
0x18000cadd  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000cae4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x18000caeb  mov     cs:CallbackContext, rax
0x18000caf2  call    atexit
0x18000caf7  mov     rbx, cs:CallbackContext
0x18000cafe  mov     cs:qword_18004A768, rbx
0x18000cb05  mov     cs:byte_18004A770, 1
0x18000cb0c  mov     rax, [rbx+8]
0x18000cb10  movups  xmm0, xmmword ptr [rax-10h]
0x18000cb14  movups  xmmword ptr [rsp+160h+ProviderId.Data1], xmm0
0x18000cb19  cmp     [rbx+20h], r13
0x18000cb1d  jz      short loc_18000CB26
0x18000cb1f  mov     ecx, 5
0x18000cb24  int     29h; Win8: RtlFailFast(ecx)
0x18000cb26  lea     r9, [rbx+20h]; RegHandle
0x18000cb2a  mov     [rbx+28h], r13
0x18000cb2e  mov     r8, rbx; CallbackContext
0x18000cb31  mov     [rbx+30h], r13
0x18000cb35  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000cb3c  lea     rcx, [rsp+160h+ProviderId]; ProviderId
0x18000cb41  call    cs:__imp_EventRegister
0x18000cb47  test    eax, eax
0x18000cb49  jnz     short loc_18000CB62
0x18000cb4b  mov     r8, [rbx+8]
0x18000cb4f  mov     edx, 2
0x18000cb54  mov     rcx, [rbx+20h]
0x18000cb58  movzx   r9d, word ptr [r8]
0x18000cb5c  call    cs:__imp_EventSetInformation
0x18000cb62  mov     rax, cs:qword_18004A760
0x18000cb69  lea     rcx, qword_18004A760
0x18000cb70  mov     cs:dword_18004A774, 1
0x18000cb7a  mov     rax, [rax+8]
0x18000cb7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb83  lea     r8, qword_18004A760; lpContext
0x18000cb8a  xor     edx, edx; dwFlags
0x18000cb8c  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18000cb93  call    cs:__imp_InitOnceComplete
0x18000cb99  mov     rax, [rsp+160h+SRWLock]
0x18000cb9e  mov     rbx, [rax+8]
0x18000cba2  mov     eax, [rbx]
0x18000cba4  cmp     eax, 5
0x18000cba7  jbe     loc_18000CD4D
0x18000cbad  mov     rcx, [rbx+18h]
0x18000cbb1  mov     rdi, 400000000000h
0x18000cbbb  mov     rax, [rbx+10h]
0x18000cbbf  test    rdi, rax
0x18000cbc2  jz      loc_18000CD4D
0x18000cbc8  mov     rax, rcx
0x18000cbcb  and     rax, rdi
0x18000cbce  cmp     rax, rcx
0x18000cbd1  jnz     loc_18000CD4D
0x18000cbd7  mov     r8b, 3
0x18000cbda  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_40007690@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_40007690@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40007690> `wil::Feature<__WilFeatureTraits_Feature_40007690>::GetImpl(void)'::`2'::impl
0x18000cbe1  mov     dl, 1
0x18000cbe3  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_40007690@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40007690>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000cbe8  mov     [rsp+160h+fPending], 1
0x18000cbf0  mov     dl, 1
0x18000cbf2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WNS_40745204@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WNS_40745204@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WNS_40745204> `wil::Feature<__WilFeatureTraits_Feature_WNS_40745204>::GetImpl(void)'::`2'::impl
0x18000cbf9  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WNS_40745204@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WNS_40745204>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000cbfe  mov     [rsp+160h+var_120], 1
0x18000cc06  mov     [rsp+160h+var_11C], r14d
0x18000cc0b  mov     [rsp+160h+var_118], r15d
0x18000cc10  mov     [rsp+160h+var_108], r12
0x18000cc15  call    cs:__imp_GetCurrentThreadId
0x18000cc1b  mov     r8, [rsi+110h]
0x18000cc22  mov     dword ptr [rsp+160h+var_110], eax
0x18000cc26  mov     [rsp+160h+var_100], 1000000h
0x18000cc2f  cmp     [r8+4], r13b
0x18000cc33  jz      short loc_18000CC51
0x18000cc35  cmp     [r8+18h], r13d
0x18000cc39  lea     r9, [r8+18h]
0x18000cc3d  jnz     short loc_18000CC54
0x18000cc3f  cmp     [r9+4], r13d
0x18000cc43  jnz     short loc_18000CC54
0x18000cc45  cmp     [r9+8], r13d
0x18000cc49  jnz     short loc_18000CC54
0x18000cc4b  cmp     [r9+0Ch], r13d
0x18000cc4f  jnz     short loc_18000CC54
0x18000cc51  mov     r9, r13; RelatedActivityId
0x18000cc54  mov     [rbp+60h+var_58], 4
0x18000cc5c  lea     rax, [rsp+160h+fPending]
0x18000cc61  mov     [rbp+60h+var_60], rax
0x18000cc65  lea     rcx, _TraceLoggingMetadata
0x18000cc6c  mov     [rbp+60h+var_68], 4
0x18000cc74  lea     rax, [rsp+160h+var_120]
0x18000cc79  mov     [rbp+60h+var_70], rax
0x18000cc7d  lea     rdx, [rsp+160h+ProviderId]; EventDescriptor
0x18000cc82  mov     [rbp+60h+var_78], 4
0x18000cc8a  lea     rax, [rsp+160h+var_11C]
0x18000cc8f  mov     [rbp+60h+var_80], rax
0x18000cc93  add     r8, 8; ActivityId
0x18000cc97  mov     [rbp+60h+var_88], 4
0x18000cc9f  lea     rax, [rsp+160h+var_118]
0x18000cca4  mov     [rbp+60h+var_90], rax
0x18000cca8  lea     rax, [rsp+160h+var_108]
0x18000ccad  mov     [rbp+60h+var_A0], rax
0x18000ccb1  lea     rax, [rsp+160h+var_110]
0x18000ccb6  mov     [rbp+60h+var_B0], rax
0x18000ccba  lea     rax, [rsp+160h+var_100]
0x18000ccbf  mov     [rbp+60h+var_C0], rax
0x18000ccc3  movzx   eax, cs:word_180041168
0x18000ccca  mov     dword ptr [rsp+160h+ProviderId.Data2], eax
0x18000ccce  mov     rax, [rbx+8]
0x18000ccd2  mov     [rbp+60h+var_E0.Ptr], rax
0x18000ccd6  mov     [rbp+60h+var_98], 8
0x18000ccde  mov     [rbp+60h+var_A8], 4
0x18000cce6  mov     [rbp+60h+var_B8], 8
0x18000ccee  mov     [rsp+160h+ProviderId.Data1], 0B000000h
0x18000ccf6  mov     qword ptr [rsp+160h+ProviderId.Data4], rdi
0x18000ccfb  movzx   eax, word ptr [rax]
0x18000ccfe  mov     [rbp+60h+var_E0.Size], eax
0x18000cd01  lea     rax, word_180041172
0x18000cd08  mov     [rbp+60h+var_D0], rax
0x18000cd0c  lea     rax, _TraceLoggingMetadataEnd
0x18000cd13  sub     eax, ecx
0x18000cd15  mov     dword ptr [rbp+60h+var_E0.0Ch], 2
0x18000cd1c  mov     [rbp+60h+var_C8], 9Bh
0x18000cd23  mov     [rbp+60h+var_C4], 1
0x18000cd2a  mov     dword ptr [rsp+160h+SRWLock], eax
0x18000cd2e  mov     eax, dword ptr [rsp+160h+SRWLock]
0x18000cd32  mov     rcx, [rbx+20h]; RegHandle
0x18000cd36  lea     rax, [rbp+60h+var_E0]
0x18000cd3a  mov     [rsp+160h+UserData], rax; UserData
0x18000cd3f  mov     [rsp+160h+UserDataCount], 9; UserDataCount
0x18000cd47  call    cs:__imp_EventWriteTransfer
0x18000cd4d  lea     rcx, [rsi+120h]; this
0x18000cd54  cmp     [rcx+18h], r13d
0x18000cd58  jnz     short loc_18000CD5F
0x18000cd5a  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000cd5f  mov     rcx, [rbp+60h+var_50]
0x18000cd63  xor     rcx, rsp; StackCookie
0x18000cd66  call    __security_check_cookie
0x18000cd6b  add     rsp, 128h
0x18000cd72  pop     r15
0x18000cd74  pop     r14
0x18000cd76  pop     r13
0x18000cd78  pop     r12
0x18000cd7a  pop     rdi
0x18000cd7b  pop     rsi
0x18000cd7c  pop     rbx
0x18000cd7d  pop     rbp
0x18000cd7e  retn
```
