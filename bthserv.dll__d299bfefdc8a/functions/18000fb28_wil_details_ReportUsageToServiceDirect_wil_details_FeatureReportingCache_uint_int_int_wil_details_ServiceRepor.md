# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000fb28`
- end: `0x18000fcca`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `418`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000f9f0`

## callees

- `0x18000f830`
- `0x18000fb28`
- `0x180011b14`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fc42`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fc42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fbf6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fbf6`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  int *v10; // rax
  __int64 v11; // r8
  int v12; // r15d
  unsigned int v13; // esi
  unsigned int v14; // r12d
  int v15; // r13d
  unsigned int v16; // ebp
  void (__fastcall *v17)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v18)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v19; // rdx
  void (__fastcall *v20)(_QWORD, __int64, _QWORD, _QWORD); // rax
  __int64 v22; // [rsp+30h] [rbp-58h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(&v22, a1, a5, 0);
  v12 = *v10;
  v13 = v10[1];
  v14 = v10[2];
  v15 = v10[4];
  v16 = 1;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v12 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      a2,
      a1);
  if ( v13 )
  {
    v17 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v17 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v17(a2, v14, v13, 0);
    }
  }
  if ( !v15 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_180044528 )
    {
      qword_180044528 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180044528, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v19 = a5;
    LODWORD(v19) = a5 | 0x80000000;
    if ( !a4 )
      v19 = a5;
    v20 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v20 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v20(a2, v19, 0, 0);
    }
  }
  if ( v15 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v11) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v11);
  }
  return v16;
}

```

## disassembly

```asm
0x18000fb28  mov     rax, rsp
0x18000fb2b  mov     [rax+8], rbx
0x18000fb2f  mov     [rax+20h], r9d
0x18000fb33  mov     [rax+18h], r8d
0x18000fb37  push    rbp
0x18000fb38  push    rsi
0x18000fb39  push    rdi
0x18000fb3a  push    r12
0x18000fb3c  push    r13
0x18000fb3e  push    r14
0x18000fb40  push    r15
0x18000fb42  sub     rsp, 50h
0x18000fb46  mov     ebx, edx
0x18000fb48  mov     r14, rcx
0x18000fb4b  xor     r9d, r9d
0x18000fb4e  mov     edi, [rsp+88h+arg_20]
0x18000fb55  mov     r8d, edi
0x18000fb58  mov     rdx, rcx
0x18000fb5b  lea     rcx, [rax-58h]
0x18000fb5f  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000fb64  mov     r15d, [rax]
0x18000fb67  mov     esi, [rax+4]
0x18000fb6a  mov     r12d, [rax+8]
0x18000fb6e  mov     r13d, [rax+10h]
0x18000fb72  mov     ebp, 1
0x18000fb77  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000fb7e  test    rax, rax
0x18000fb81  jz      short loc_18000FB9B
0x18000fb83  test    edi, edi
0x18000fb85  jz      short loc_18000FB8F
0x18000fb87  lea     ecx, [rdi-64h]
0x18000fb8a  cmp     ecx, 31h ; '1'
0x18000fb8d  ja      short loc_18000FB9B
0x18000fb8f  mov     r8d, ebp
0x18000fb92  mov     edx, edi
0x18000fb94  mov     ecx, ebx
0x18000fb96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb9b  test    r15d, r15d
0x18000fb9e  jz      short loc_18000FBB1
0x18000fba0  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18000fba3  mov     edx, ebx; unsigned int
0x18000fba5  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000fbac  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000fbb1  xor     r14d, r14d
0x18000fbb4  test    esi, esi
0x18000fbb6  jz      short loc_18000FBE0
0x18000fbb8  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000fbbf  test    rax, rax
0x18000fbc2  jnz     short loc_18000FBD0
0x18000fbc4  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000fbcb  test    rax, rax
0x18000fbce  jz      short loc_18000FBE0
0x18000fbd0  xor     r9d, r9d
0x18000fbd3  mov     r8d, esi
0x18000fbd6  mov     edx, r12d
0x18000fbd9  mov     ecx, ebx
0x18000fbdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbe0  test    r13d, r13d
0x18000fbe3  jnz     short loc_18000FC49
0x18000fbe5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000fbeb  test    eax, eax
0x18000fbed  jz      short loc_18000FC49
0x18000fbef  lea     rcx, SRWLock; SRWLock
0x18000fbf6  call    cs:__imp_AcquireSRWLockExclusive
0x18000fbfc  cmp     cs:qword_180044528, r14
0x18000fc03  jnz     short loc_18000FC3B
0x18000fc05  mov     cs:qword_180044528, r14
0x18000fc0c  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000fc13  test    rax, rax
0x18000fc16  jnz     short loc_18000FC24
0x18000fc18  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000fc1f  test    rax, rax
0x18000fc22  jz      short loc_18000FC3B
0x18000fc24  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000fc28  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000fc2f  lea     rcx, qword_180044528
0x18000fc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc3b  lea     rcx, SRWLock; SRWLock
0x18000fc42  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fc48  nop
0x18000fc49  cmp     [rsp+88h+arg_10], r14d
0x18000fc51  jz      short loc_18000FC89
0x18000fc53  mov     edx, edi
0x18000fc55  bts     edx, 1Fh
0x18000fc59  cmp     [rsp+88h+arg_18], r14d
0x18000fc61  cmovz   edx, edi
0x18000fc64  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000fc6b  test    rax, rax
0x18000fc6e  jnz     short loc_18000FC7C
0x18000fc70  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000fc77  test    rax, rax
0x18000fc7a  jz      short loc_18000FC89
0x18000fc7c  xor     r9d, r9d
0x18000fc7f  xor     r8d, r8d
0x18000fc82  mov     ecx, ebx
0x18000fc84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc89  test    r13d, r13d
0x18000fc8c  jnz     short loc_18000FCAD
0x18000fc8e  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000fc95  test    rax, rax
0x18000fc98  jz      short loc_18000FCB0
0x18000fc9a  mov     r8b, [rsp+88h+arg_38]
0x18000fca2  mov     edx, edi
0x18000fca4  mov     ecx, ebx
0x18000fca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcab  jmp     short loc_18000FCB0
0x18000fcad  mov     ebp, r14d
0x18000fcb0  mov     eax, ebp
0x18000fcb2  mov     rbx, [rsp+88h+arg_0]
0x18000fcba  add     rsp, 50h
0x18000fcbe  pop     r15
0x18000fcc0  pop     r14
0x18000fcc2  pop     r13
0x18000fcc4  pop     r12
0x18000fcc6  pop     rdi
0x18000fcc7  pop     rsi
0x18000fcc8  pop     rbp
0x18000fcc9  retn
```
