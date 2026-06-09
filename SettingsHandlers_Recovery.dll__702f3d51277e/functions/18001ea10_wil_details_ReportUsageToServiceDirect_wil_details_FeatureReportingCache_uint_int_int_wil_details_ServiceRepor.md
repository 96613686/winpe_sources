# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18001ea10`
- end: `0x18001ebb2`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001e8d8`

## callees

- `0x18001d410`
- `0x18001ea10`
- `0x180023678`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001eade`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001eade`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001eb2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001eb2a`

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
    if ( !qword_180059B10 )
    {
      qword_180059B10 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180059B10, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18001ea10  mov     rax, rsp
0x18001ea13  mov     [rax+8], rbx
0x18001ea17  mov     [rax+20h], r9d
0x18001ea1b  mov     [rax+18h], r8d
0x18001ea1f  push    rbp
0x18001ea20  push    rsi
0x18001ea21  push    rdi
0x18001ea22  push    r12
0x18001ea24  push    r13
0x18001ea26  push    r14
0x18001ea28  push    r15
0x18001ea2a  sub     rsp, 50h
0x18001ea2e  mov     ebx, edx
0x18001ea30  mov     r14, rcx
0x18001ea33  xor     r9d, r9d
0x18001ea36  mov     edi, [rsp+88h+arg_20]
0x18001ea3d  mov     r8d, edi
0x18001ea40  mov     rdx, rcx
0x18001ea43  lea     rcx, [rax-58h]
0x18001ea47  call    wil_details_FeatureReporting_RecordUsageInCache
0x18001ea4c  mov     r15d, [rax]
0x18001ea4f  mov     esi, [rax+4]
0x18001ea52  mov     r12d, [rax+8]
0x18001ea56  mov     r13d, [rax+10h]
0x18001ea5a  mov     ebp, 1
0x18001ea5f  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18001ea66  test    rax, rax
0x18001ea69  jz      short loc_18001EA83
0x18001ea6b  test    edi, edi
0x18001ea6d  jz      short loc_18001EA77
0x18001ea6f  lea     ecx, [rdi-64h]
0x18001ea72  cmp     ecx, 31h ; '1'
0x18001ea75  ja      short loc_18001EA83
0x18001ea77  mov     r8d, ebp
0x18001ea7a  mov     edx, edi
0x18001ea7c  mov     ecx, ebx
0x18001ea7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea83  test    r15d, r15d
0x18001ea86  jz      short loc_18001EA99
0x18001ea88  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18001ea8b  mov     edx, ebx; unsigned int
0x18001ea8d  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18001ea94  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18001ea99  xor     r14d, r14d
0x18001ea9c  test    esi, esi
0x18001ea9e  jz      short loc_18001EAC8
0x18001eaa0  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001eaa7  test    rax, rax
0x18001eaaa  jnz     short loc_18001EAB8
0x18001eaac  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001eab3  test    rax, rax
0x18001eab6  jz      short loc_18001EAC8
0x18001eab8  xor     r9d, r9d
0x18001eabb  mov     r8d, esi
0x18001eabe  mov     edx, r12d
0x18001eac1  mov     ecx, ebx
0x18001eac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eac8  test    r13d, r13d
0x18001eacb  jnz     short loc_18001EB31
0x18001eacd  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001ead3  test    eax, eax
0x18001ead5  jz      short loc_18001EB31
0x18001ead7  lea     rcx, SRWLock; SRWLock
0x18001eade  call    cs:__imp_AcquireSRWLockExclusive
0x18001eae4  cmp     cs:qword_180059B10, r14
0x18001eaeb  jnz     short loc_18001EB23
0x18001eaed  mov     cs:qword_180059B10, r14
0x18001eaf4  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001eafb  test    rax, rax
0x18001eafe  jnz     short loc_18001EB0C
0x18001eb00  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001eb07  test    rax, rax
0x18001eb0a  jz      short loc_18001EB23
0x18001eb0c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001eb10  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18001eb17  lea     rcx, qword_180059B10
0x18001eb1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb23  lea     rcx, SRWLock; SRWLock
0x18001eb2a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001eb30  nop
0x18001eb31  cmp     [rsp+88h+arg_10], r14d
0x18001eb39  jz      short loc_18001EB71
0x18001eb3b  mov     edx, edi
0x18001eb3d  bts     edx, 1Fh
0x18001eb41  cmp     [rsp+88h+arg_18], r14d
0x18001eb49  cmovz   edx, edi
0x18001eb4c  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001eb53  test    rax, rax
0x18001eb56  jnz     short loc_18001EB64
0x18001eb58  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001eb5f  test    rax, rax
0x18001eb62  jz      short loc_18001EB71
0x18001eb64  xor     r9d, r9d
0x18001eb67  xor     r8d, r8d
0x18001eb6a  mov     ecx, ebx
0x18001eb6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb71  test    r13d, r13d
0x18001eb74  jnz     short loc_18001EB95
0x18001eb76  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18001eb7d  test    rax, rax
0x18001eb80  jz      short loc_18001EB98
0x18001eb82  mov     r8b, [rsp+88h+arg_38]
0x18001eb8a  mov     edx, edi
0x18001eb8c  mov     ecx, ebx
0x18001eb8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb93  jmp     short loc_18001EB98
0x18001eb95  mov     ebp, r14d
0x18001eb98  mov     eax, ebp
0x18001eb9a  mov     rbx, [rsp+88h+arg_0]
0x18001eba2  add     rsp, 50h
0x18001eba6  pop     r15
0x18001eba8  pop     r14
0x18001ebaa  pop     r13
0x18001ebac  pop     r12
0x18001ebae  pop     rdi
0x18001ebaf  pop     rsi
0x18001ebb0  pop     rbp
0x18001ebb1  retn
```
