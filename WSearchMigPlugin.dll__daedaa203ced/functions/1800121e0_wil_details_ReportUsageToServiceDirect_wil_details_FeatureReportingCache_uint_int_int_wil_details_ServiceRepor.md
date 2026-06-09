# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1800121e0`
- end: `0x180012387`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `423`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800120a8`

## callees

- `0x180011ab0`
- `0x1800121e0`
- `0x180014c88`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800122b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800122b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800122ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800122ff`

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
  __int64 v22; // [rsp+38h] [rbp-50h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(&v22, a1, a5);
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
    if ( !qword_180025BA0 )
    {
      qword_180025BA0 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180025BA0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x1800121e0  mov     rax, rsp
0x1800121e3  mov     [rax+20h], r9d
0x1800121e7  mov     [rax+18h], r8d
0x1800121eb  push    rbp
0x1800121ec  push    rsi
0x1800121ed  push    rdi
0x1800121ee  push    r12
0x1800121f0  push    r13
0x1800121f2  push    r14
0x1800121f4  push    r15
0x1800121f6  sub     rsp, 50h
0x1800121fa  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x180012202  mov     [rax+8], rbx
0x180012206  mov     edi, edx
0x180012208  mov     r14, rcx
0x18001220b  mov     ebx, [rsp+88h+arg_20]
0x180012212  mov     r8d, ebx
0x180012215  mov     rdx, rcx
0x180012218  lea     rcx, [rax-50h]
0x18001221c  call    wil_details_FeatureReporting_RecordUsageInCache
0x180012221  mov     r15d, [rax]
0x180012224  mov     esi, [rax+4]
0x180012227  mov     r12d, [rax+8]
0x18001222b  mov     r13d, [rax+10h]
0x18001222f  mov     ebp, 1
0x180012234  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18001223b  test    rax, rax
0x18001223e  jz      short loc_180012258
0x180012240  test    ebx, ebx
0x180012242  jz      short loc_18001224C
0x180012244  lea     ecx, [rbx-64h]
0x180012247  cmp     ecx, 31h ; '1'
0x18001224a  ja      short loc_180012258
0x18001224c  mov     r8d, ebp
0x18001224f  mov     edx, ebx
0x180012251  mov     ecx, edi
0x180012253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012258  test    r15d, r15d
0x18001225b  jz      short loc_18001226E
0x18001225d  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x180012260  mov     edx, edi; unsigned int
0x180012262  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180012269  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18001226e  xor     r14d, r14d
0x180012271  test    esi, esi
0x180012273  jz      short loc_18001229D
0x180012275  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001227c  test    rax, rax
0x18001227f  jnz     short loc_18001228D
0x180012281  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180012288  test    rax, rax
0x18001228b  jz      short loc_18001229D
0x18001228d  xor     r9d, r9d
0x180012290  mov     r8d, esi
0x180012293  mov     edx, r12d
0x180012296  mov     ecx, edi
0x180012298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001229d  test    r13d, r13d
0x1800122a0  jnz     short loc_180012306
0x1800122a2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800122a8  test    eax, eax
0x1800122aa  jz      short loc_180012306
0x1800122ac  lea     rcx, SRWLock; SRWLock
0x1800122b3  call    cs:__imp_AcquireSRWLockExclusive
0x1800122b9  cmp     cs:qword_180025BA0, r14
0x1800122c0  jnz     short loc_1800122F8
0x1800122c2  mov     cs:qword_180025BA0, r14
0x1800122c9  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800122d0  test    rax, rax
0x1800122d3  jnz     short loc_1800122E1
0x1800122d5  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800122dc  test    rax, rax
0x1800122df  jz      short loc_1800122F8
0x1800122e1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800122e5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x1800122ec  lea     rcx, qword_180025BA0
0x1800122f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122f8  lea     rcx, SRWLock; SRWLock
0x1800122ff  call    cs:__imp_ReleaseSRWLockExclusive
0x180012305  nop
0x180012306  cmp     [rsp+88h+arg_10], r14d
0x18001230e  jz      short loc_180012346
0x180012310  mov     edx, ebx
0x180012312  bts     edx, 1Fh
0x180012316  cmp     [rsp+88h+arg_18], r14d
0x18001231e  cmovz   edx, ebx
0x180012321  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180012328  test    rax, rax
0x18001232b  jnz     short loc_180012339
0x18001232d  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180012334  test    rax, rax
0x180012337  jz      short loc_180012346
0x180012339  xor     r9d, r9d
0x18001233c  xor     r8d, r8d
0x18001233f  mov     ecx, edi
0x180012341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012346  test    r13d, r13d
0x180012349  jnz     short loc_18001236A
0x18001234b  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180012352  test    rax, rax
0x180012355  jz      short loc_18001236D
0x180012357  mov     r8b, [rsp+88h+arg_38]
0x18001235f  mov     edx, ebx
0x180012361  mov     ecx, edi
0x180012363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012368  jmp     short loc_18001236D
0x18001236a  mov     ebp, r14d
0x18001236d  mov     eax, ebp
0x18001236f  mov     rbx, [rsp+88h+arg_0]
0x180012377  add     rsp, 50h
0x18001237b  pop     r15
0x18001237d  pop     r14
0x18001237f  pop     r13
0x180012381  pop     r12
0x180012383  pop     rdi
0x180012384  pop     rsi
0x180012385  pop     rbp
0x180012386  retn
```
