# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000c93c`
- end: `0x18000cadb`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000c804`

## callees

- `0x18000c494`
- `0x18000c93c`
- `0x18000e3f4`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ca07`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ca07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ca53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ca53`

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
  void (__fastcall *v18)(__int64 *, __int64 (__fastcall *)(), __int64); // rax
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
    if ( !qword_1800153C0 )
    {
      qword_1800153C0 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_1800153C0, `wil::details::RecordFeatureUsageCallback'::`17'::_lambda_1_::_lambda_invoker_cdecl_, -1);
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
0x18000c93c  mov     rax, rsp
0x18000c93f  mov     [rax+8], rbx
0x18000c943  mov     [rax+20h], r9d
0x18000c947  mov     [rax+18h], r8d
0x18000c94b  push    rbp
0x18000c94c  push    rsi
0x18000c94d  push    rdi
0x18000c94e  push    r12
0x18000c950  push    r13
0x18000c952  push    r14
0x18000c954  push    r15
0x18000c956  sub     rsp, 50h
0x18000c95a  mov     edi, edx
0x18000c95c  mov     r14, rcx
0x18000c95f  mov     ebx, [rsp+88h+arg_20]
0x18000c966  mov     r8d, ebx
0x18000c969  mov     rdx, rcx
0x18000c96c  lea     rcx, [rax-58h]
0x18000c970  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000c975  mov     r15d, [rax]
0x18000c978  mov     esi, [rax+4]
0x18000c97b  mov     r12d, [rax+8]
0x18000c97f  mov     r13d, [rax+10h]
0x18000c983  mov     ebp, 1
0x18000c988  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000c98f  test    rax, rax
0x18000c992  jz      short loc_18000C9AC
0x18000c994  test    ebx, ebx
0x18000c996  jz      short loc_18000C9A0
0x18000c998  lea     ecx, [rbx-64h]
0x18000c99b  cmp     ecx, 31h ; '1'
0x18000c99e  ja      short loc_18000C9AC
0x18000c9a0  mov     r8d, ebp
0x18000c9a3  mov     edx, ebx
0x18000c9a5  mov     ecx, edi
0x18000c9a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9ac  test    r15d, r15d
0x18000c9af  jz      short loc_18000C9C2
0x18000c9b1  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18000c9b4  mov     edx, edi; unsigned int
0x18000c9b6  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000c9bd  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000c9c2  xor     r14d, r14d
0x18000c9c5  test    esi, esi
0x18000c9c7  jz      short loc_18000C9F1
0x18000c9c9  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000c9d0  test    rax, rax
0x18000c9d3  jnz     short loc_18000C9E1
0x18000c9d5  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000c9dc  test    rax, rax
0x18000c9df  jz      short loc_18000C9F1
0x18000c9e1  xor     r9d, r9d
0x18000c9e4  mov     r8d, esi
0x18000c9e7  mov     edx, r12d
0x18000c9ea  mov     ecx, edi
0x18000c9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9f1  test    r13d, r13d
0x18000c9f4  jnz     short loc_18000CA5A
0x18000c9f6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000c9fc  test    eax, eax
0x18000c9fe  jz      short loc_18000CA5A
0x18000ca00  lea     rcx, SRWLock; SRWLock
0x18000ca07  call    cs:__imp_AcquireSRWLockExclusive
0x18000ca0d  cmp     cs:qword_1800153C0, r14
0x18000ca14  jnz     short loc_18000CA4C
0x18000ca16  mov     cs:qword_1800153C0, r14
0x18000ca1d  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000ca24  test    rax, rax
0x18000ca27  jnz     short loc_18000CA35
0x18000ca29  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000ca30  test    rax, rax
0x18000ca33  jz      short loc_18000CA4C
0x18000ca35  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ca39  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?BB@??RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z@SA@PEAX@Z; `wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)'::`17'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18000ca40  lea     rcx, qword_1800153C0
0x18000ca47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca4c  lea     rcx, SRWLock; SRWLock
0x18000ca53  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ca59  nop
0x18000ca5a  cmp     [rsp+88h+arg_10], r14d
0x18000ca62  jz      short loc_18000CA9A
0x18000ca64  mov     edx, ebx
0x18000ca66  bts     edx, 1Fh
0x18000ca6a  cmp     [rsp+88h+arg_18], r14d
0x18000ca72  cmovz   edx, ebx
0x18000ca75  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000ca7c  test    rax, rax
0x18000ca7f  jnz     short loc_18000CA8D
0x18000ca81  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000ca88  test    rax, rax
0x18000ca8b  jz      short loc_18000CA9A
0x18000ca8d  xor     r9d, r9d
0x18000ca90  xor     r8d, r8d
0x18000ca93  mov     ecx, edi
0x18000ca95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca9a  test    r13d, r13d
0x18000ca9d  jnz     short loc_18000CABE
0x18000ca9f  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000caa6  test    rax, rax
0x18000caa9  jz      short loc_18000CAC1
0x18000caab  mov     r8b, [rsp+88h+arg_38]
0x18000cab3  mov     edx, ebx
0x18000cab5  mov     ecx, edi
0x18000cab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cabc  jmp     short loc_18000CAC1
0x18000cabe  mov     ebp, r14d
0x18000cac1  mov     eax, ebp
0x18000cac3  mov     rbx, [rsp+88h+arg_0]
0x18000cacb  add     rsp, 50h
0x18000cacf  pop     r15
0x18000cad1  pop     r14
0x18000cad3  pop     r13
0x18000cad5  pop     r12
0x18000cad7  pop     rdi
0x18000cad8  pop     rsi
0x18000cad9  pop     rbp
0x18000cada  retn
```
