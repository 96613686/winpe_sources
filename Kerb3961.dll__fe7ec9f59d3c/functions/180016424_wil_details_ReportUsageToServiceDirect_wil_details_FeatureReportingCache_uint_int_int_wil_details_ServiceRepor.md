# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180016424`
- end: `0x1800165c2`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800162ec`

## callees

- `0x180014f74`
- `0x180016424`
- `0x180018830`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800164ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800164ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001653b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001653b`

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
  unsigned int v12; // ebp
  int v13; // r15d
  unsigned int v14; // esi
  unsigned int v15; // r13d
  int v16; // r12d
  void (__fastcall *v17)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v18)(__int64 *, __int64 (__fastcall *)(), __int64); // rax
  void (__fastcall *v19)(_QWORD, __int64, _QWORD, _QWORD); // rax
  __int64 v20; // rdx
  __int64 v22; // [rsp+30h] [rbp-58h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(&v22, a1, a5);
  v12 = 1;
  v13 = *v10;
  v14 = v10[1];
  v15 = v10[2];
  v16 = v10[4];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v13 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      a2,
      a1);
  if ( v14 )
  {
    v17 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v17 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v17(a2, v15, v14, 0);
    }
  }
  if ( !v16 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_180029838 )
    {
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_180029838 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180029838, `wil::details::RecordFeatureUsageCallback'::`17'::_lambda_1_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v19 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    v20 = a5;
    LODWORD(v20) = a5 | 0x80000000;
    if ( !a4 )
      v20 = a5;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v19 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v19(a2, v20, 0, 0);
    }
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
  return v12;
}

```

## disassembly

```asm
0x180016424  mov     rax, rsp
0x180016427  mov     [rax+8], rbx
0x18001642b  mov     [rax+20h], r9d
0x18001642f  mov     [rax+18h], r8d
0x180016433  push    rbp
0x180016434  push    rsi
0x180016435  push    rdi
0x180016436  push    r12
0x180016438  push    r13
0x18001643a  push    r14
0x18001643c  push    r15
0x18001643e  sub     rsp, 50h
0x180016442  mov     ebx, [rsp+88h+arg_20]
0x180016449  mov     edi, edx
0x18001644b  mov     rdx, rcx
0x18001644e  mov     r14, rcx
0x180016451  lea     rcx, [rax-58h]
0x180016455  mov     r8d, ebx
0x180016458  call    wil_details_FeatureReporting_RecordUsageInCache
0x18001645d  mov     ebp, 1
0x180016462  mov     r15d, [rax]
0x180016465  mov     esi, [rax+4]
0x180016468  mov     r13d, [rax+8]
0x18001646c  mov     r12d, [rax+10h]
0x180016470  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180016477  test    rax, rax
0x18001647a  jz      short loc_180016494
0x18001647c  test    ebx, ebx
0x18001647e  jz      short loc_180016488
0x180016480  lea     ecx, [rbx-64h]
0x180016483  cmp     ecx, 31h ; '1'
0x180016486  ja      short loc_180016494
0x180016488  mov     r8d, ebp
0x18001648b  mov     edx, ebx
0x18001648d  mov     ecx, edi
0x18001648f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016494  test    r15d, r15d
0x180016497  jz      short loc_1800164AA
0x180016499  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18001649c  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800164a3  mov     edx, edi; unsigned int
0x1800164a5  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1800164aa  xor     r14d, r14d
0x1800164ad  test    esi, esi
0x1800164af  jz      short loc_1800164D9
0x1800164b1  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800164b8  test    rax, rax
0x1800164bb  jnz     short loc_1800164C9
0x1800164bd  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800164c4  test    rax, rax
0x1800164c7  jz      short loc_1800164D9
0x1800164c9  xor     r9d, r9d
0x1800164cc  mov     r8d, esi
0x1800164cf  mov     edx, r13d
0x1800164d2  mov     ecx, edi
0x1800164d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164d9  test    r12d, r12d
0x1800164dc  jnz     short loc_180016541
0x1800164de  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800164e4  test    eax, eax
0x1800164e6  jz      short loc_180016541
0x1800164e8  lea     rcx, SRWLock; SRWLock
0x1800164ef  call    cs:__imp_AcquireSRWLockExclusive
0x1800164f5  cmp     cs:qword_180029838, r14
0x1800164fc  jnz     short loc_180016534
0x1800164fe  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180016505  mov     cs:qword_180029838, r14
0x18001650c  test    rax, rax
0x18001650f  jnz     short loc_18001651D
0x180016511  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180016518  test    rax, rax
0x18001651b  jz      short loc_180016534
0x18001651d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180016521  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?BB@??RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z@SA@PEAX@Z; `wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)'::`17'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x180016528  lea     rcx, qword_180029838
0x18001652f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016534  lea     rcx, SRWLock; SRWLock
0x18001653b  call    cs:__imp_ReleaseSRWLockExclusive
0x180016541  cmp     [rsp+88h+arg_10], r14d
0x180016549  jz      short loc_180016581
0x18001654b  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180016552  mov     edx, ebx
0x180016554  bts     edx, 1Fh
0x180016558  cmp     [rsp+88h+arg_18], r14d
0x180016560  cmovz   edx, ebx
0x180016563  test    rax, rax
0x180016566  jnz     short loc_180016574
0x180016568  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001656f  test    rax, rax
0x180016572  jz      short loc_180016581
0x180016574  xor     r9d, r9d
0x180016577  xor     r8d, r8d
0x18001657a  mov     ecx, edi
0x18001657c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016581  test    r12d, r12d
0x180016584  jnz     short loc_1800165A5
0x180016586  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18001658d  test    rax, rax
0x180016590  jz      short loc_1800165A8
0x180016592  mov     r8b, [rsp+88h+arg_38]
0x18001659a  mov     edx, ebx
0x18001659c  mov     ecx, edi
0x18001659e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165a3  jmp     short loc_1800165A8
0x1800165a5  mov     ebp, r14d
0x1800165a8  mov     rbx, [rsp+88h+arg_0]
0x1800165b0  mov     eax, ebp
0x1800165b2  add     rsp, 50h
0x1800165b6  pop     r15
0x1800165b8  pop     r14
0x1800165ba  pop     r13
0x1800165bc  pop     r12
0x1800165be  pop     rdi
0x1800165bf  pop     rsi
0x1800165c0  pop     rbp
0x1800165c1  retn
```
