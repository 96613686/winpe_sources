# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180025240`
- end: `0x1800253a9`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `361`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180014e50`
- `0x1800166ac`
- `0x180023cac`

## callees

- `0x18001ef18`
- `0x18001f404`
- `0x180025240`
- `0x1800253b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800252f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800252f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002533c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002533c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  unsigned int v12; // r9d
  int v13; // r12d
  unsigned int v14; // ebp
  unsigned int v15; // r13d
  int v16; // r14d
  unsigned int v17; // esi
  void (__fastcall *v18)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  unsigned int v19; // edx
  const char *v21; // [rsp+20h] [rbp-68h]
  __int64 v22; // [rsp+30h] [rbp-58h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(&v22, a1, a5);
  v13 = *v10;
  v14 = v10[1];
  v15 = v10[2];
  v16 = v10[4];
  v17 = 1;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v13 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (char *)&wil::details::g_enabledStateManager,
      a2,
      a1);
  if ( v14 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v15, v14, v12, v21);
  if ( !v16 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_18004A340 )
    {
      qword_18004A340 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_18004A340, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v19 = a5 | 0x80000000;
    if ( !a4 )
      v19 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v19, 0, v12, v21);
  }
  if ( v16 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v11) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v11);
  }
  return v17;
}

```

## disassembly

```asm
0x180025240  mov     rax, rsp
0x180025243  mov     [rax+8], rbx
0x180025247  mov     [rax+20h], r9d
0x18002524b  mov     [rax+18h], r8d
0x18002524f  push    rbp
0x180025250  push    rsi
0x180025251  push    rdi
0x180025252  push    r12
0x180025254  push    r13
0x180025256  push    r14
0x180025258  push    r15
0x18002525a  sub     rsp, 50h
0x18002525e  mov     edi, edx
0x180025260  mov     r15, rcx
0x180025263  mov     ebx, [rsp+88h+arg_20]
0x18002526a  mov     r8d, ebx
0x18002526d  mov     rdx, rcx
0x180025270  lea     rcx, [rax-58h]
0x180025274  call    wil_details_FeatureReporting_RecordUsageInCache
0x180025279  mov     r12d, [rax]
0x18002527c  mov     ebp, [rax+4]
0x18002527f  mov     r13d, [rax+8]
0x180025283  mov     r14d, [rax+10h]
0x180025287  mov     esi, 1
0x18002528c  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180025293  test    rax, rax
0x180025296  jz      short loc_1800252B0
0x180025298  test    ebx, ebx
0x18002529a  jz      short loc_1800252A4
0x18002529c  lea     ecx, [rbx-64h]
0x18002529f  cmp     ecx, 31h ; '1'
0x1800252a2  ja      short loc_1800252B0
0x1800252a4  mov     r8d, esi
0x1800252a7  mov     edx, ebx
0x1800252a9  mov     ecx, edi
0x1800252ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252b0  test    r12d, r12d
0x1800252b3  jz      short loc_1800252C6
0x1800252b5  mov     r8, r15; struct wil_details_FeatureReportingCache *
0x1800252b8  mov     edx, edi; unsigned int
0x1800252ba  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800252c1  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1800252c6  xor     r15d, r15d
0x1800252c9  test    ebp, ebp
0x1800252cb  jz      short loc_1800252DA
0x1800252cd  mov     r8d, ebp; unsigned int
0x1800252d0  mov     edx, r13d; unsigned int
0x1800252d3  mov     ecx, edi; this
0x1800252d5  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800252da  test    r14d, r14d
0x1800252dd  jnz     short loc_180025343
0x1800252df  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800252e5  test    eax, eax
0x1800252e7  jz      short loc_180025343
0x1800252e9  lea     rcx, SRWLock; SRWLock
0x1800252f0  call    cs:__imp_AcquireSRWLockExclusive
0x1800252f6  cmp     cs:qword_18004A340, r15
0x1800252fd  jnz     short loc_180025335
0x1800252ff  mov     cs:qword_18004A340, r15
0x180025306  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18002530d  test    rax, rax
0x180025310  jnz     short loc_18002531E
0x180025312  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180025319  test    rax, rax
0x18002531c  jz      short loc_180025335
0x18002531e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180025322  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180025329  lea     rcx, qword_18004A340
0x180025330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025335  lea     rcx, SRWLock; SRWLock
0x18002533c  call    cs:__imp_ReleaseSRWLockExclusive
0x180025342  nop
0x180025343  cmp     [rsp+88h+arg_10], r15d
0x18002534b  jz      short loc_180025368
0x18002534d  mov     edx, ebx
0x18002534f  bts     edx, 1Fh
0x180025353  cmp     [rsp+88h+arg_18], r15d
0x18002535b  cmovz   edx, ebx; unsigned int
0x18002535e  xor     r8d, r8d; unsigned int
0x180025361  mov     ecx, edi; this
0x180025363  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180025368  test    r14d, r14d
0x18002536b  jnz     short loc_18002538C
0x18002536d  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180025374  test    rax, rax
0x180025377  jz      short loc_18002538F
0x180025379  mov     r8b, [rsp+88h+arg_38]
0x180025381  mov     edx, ebx
0x180025383  mov     ecx, edi
0x180025385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002538a  jmp     short loc_18002538F
0x18002538c  mov     esi, r15d
0x18002538f  mov     eax, esi
0x180025391  mov     rbx, [rsp+88h+arg_0]
0x180025399  add     rsp, 50h
0x18002539d  pop     r15
0x18002539f  pop     r14
0x1800253a1  pop     r13
0x1800253a3  pop     r12
0x1800253a5  pop     rdi
0x1800253a6  pop     rsi
0x1800253a7  pop     rbp
0x1800253a8  retn
```
