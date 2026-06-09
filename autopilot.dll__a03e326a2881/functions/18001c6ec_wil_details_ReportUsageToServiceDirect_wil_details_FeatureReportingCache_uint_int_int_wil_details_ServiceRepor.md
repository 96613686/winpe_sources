# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18001c6ec`
- end: `0x18001c88b`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001c5b4`

## callees

- `0x18001c074`
- `0x18001c6ec`
- `0x18001cdf8`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c803`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c803`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c7b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c7b7`

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
    if ( !qword_180042960 )
    {
      qword_180042960 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180042960, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18001c6ec  mov     rax, rsp
0x18001c6ef  mov     [rax+8], rbx
0x18001c6f3  mov     [rax+20h], r9d
0x18001c6f7  mov     [rax+18h], r8d
0x18001c6fb  push    rbp
0x18001c6fc  push    rsi
0x18001c6fd  push    rdi
0x18001c6fe  push    r12
0x18001c700  push    r13
0x18001c702  push    r14
0x18001c704  push    r15
0x18001c706  sub     rsp, 50h
0x18001c70a  mov     edi, edx
0x18001c70c  mov     r14, rcx
0x18001c70f  mov     ebx, [rsp+88h+arg_20]
0x18001c716  mov     r8d, ebx
0x18001c719  mov     rdx, rcx
0x18001c71c  lea     rcx, [rax-58h]
0x18001c720  call    wil_details_FeatureReporting_RecordUsageInCache
0x18001c725  mov     r15d, [rax]
0x18001c728  mov     esi, [rax+4]
0x18001c72b  mov     r12d, [rax+8]
0x18001c72f  mov     r13d, [rax+10h]
0x18001c733  mov     ebp, 1
0x18001c738  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18001c73f  test    rax, rax
0x18001c742  jz      short loc_18001C75C
0x18001c744  test    ebx, ebx
0x18001c746  jz      short loc_18001C750
0x18001c748  lea     ecx, [rbx-64h]
0x18001c74b  cmp     ecx, 31h ; '1'
0x18001c74e  ja      short loc_18001C75C
0x18001c750  mov     r8d, ebp
0x18001c753  mov     edx, ebx
0x18001c755  mov     ecx, edi
0x18001c757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c75c  test    r15d, r15d
0x18001c75f  jz      short loc_18001C772
0x18001c761  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18001c764  mov     edx, edi; unsigned int
0x18001c766  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18001c76d  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18001c772  xor     r14d, r14d
0x18001c775  test    esi, esi
0x18001c777  jz      short loc_18001C7A1
0x18001c779  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001c780  test    rax, rax
0x18001c783  jnz     short loc_18001C791
0x18001c785  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001c78c  test    rax, rax
0x18001c78f  jz      short loc_18001C7A1
0x18001c791  xor     r9d, r9d
0x18001c794  mov     r8d, esi
0x18001c797  mov     edx, r12d
0x18001c79a  mov     ecx, edi
0x18001c79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7a1  test    r13d, r13d
0x18001c7a4  jnz     short loc_18001C80A
0x18001c7a6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001c7ac  test    eax, eax
0x18001c7ae  jz      short loc_18001C80A
0x18001c7b0  lea     rcx, SRWLock; SRWLock
0x18001c7b7  call    cs:__imp_AcquireSRWLockExclusive
0x18001c7bd  cmp     cs:qword_180042960, r14
0x18001c7c4  jnz     short loc_18001C7FC
0x18001c7c6  mov     cs:qword_180042960, r14
0x18001c7cd  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001c7d4  test    rax, rax
0x18001c7d7  jnz     short loc_18001C7E5
0x18001c7d9  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001c7e0  test    rax, rax
0x18001c7e3  jz      short loc_18001C7FC
0x18001c7e5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c7e9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18001c7f0  lea     rcx, qword_180042960
0x18001c7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7fc  lea     rcx, SRWLock; SRWLock
0x18001c803  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c809  nop
0x18001c80a  cmp     [rsp+88h+arg_10], r14d
0x18001c812  jz      short loc_18001C84A
0x18001c814  mov     edx, ebx
0x18001c816  bts     edx, 1Fh
0x18001c81a  cmp     [rsp+88h+arg_18], r14d
0x18001c822  cmovz   edx, ebx
0x18001c825  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001c82c  test    rax, rax
0x18001c82f  jnz     short loc_18001C83D
0x18001c831  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001c838  test    rax, rax
0x18001c83b  jz      short loc_18001C84A
0x18001c83d  xor     r9d, r9d
0x18001c840  xor     r8d, r8d
0x18001c843  mov     ecx, edi
0x18001c845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c84a  test    r13d, r13d
0x18001c84d  jnz     short loc_18001C86E
0x18001c84f  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18001c856  test    rax, rax
0x18001c859  jz      short loc_18001C871
0x18001c85b  mov     r8b, [rsp+88h+arg_38]
0x18001c863  mov     edx, ebx
0x18001c865  mov     ecx, edi
0x18001c867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c86c  jmp     short loc_18001C871
0x18001c86e  mov     ebp, r14d
0x18001c871  mov     eax, ebp
0x18001c873  mov     rbx, [rsp+88h+arg_0]
0x18001c87b  add     rsp, 50h
0x18001c87f  pop     r15
0x18001c881  pop     r14
0x18001c883  pop     r13
0x18001c885  pop     r12
0x18001c887  pop     rdi
0x18001c888  pop     rsi
0x18001c889  pop     rbp
0x18001c88a  retn
```
