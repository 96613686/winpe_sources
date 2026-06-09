# wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)

- ea: `0x180015394`
- end: `0x18001547f`
- name: `?RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800163d4`

## callees

- `0x18000bc80`
- `0x180014e58`
- `0x180015394`
- `0x1800179b8`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015415`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015415`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::RecordFeatureUsageCallback(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct wil_details_FeatureReportingCache *a4,
        RTL_SRWLOCK *a5)
{
  unsigned int v6; // edi
  RTL_SRWLOCK *v7; // rbx
  unsigned int Ptr_high; // r8d
  void (__fastcall *v9)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  const char *v10; // [rsp+20h] [rbp-8h]

  v6 = a1;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!(_DWORD)a2 || (unsigned int)(a2 - 100) <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a1, a2, 1);
  v7 = a5;
  if ( LODWORD(a5->Ptr) )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      v6,
      a4);
  Ptr_high = HIDWORD(v7->Ptr);
  if ( Ptr_high )
    wil::details::WilApi_RecordFeatureUsage(
      (wil::details *)v6,
      (unsigned int)v7[1].Ptr,
      Ptr_high,
      (unsigned int)a4,
      v10);
  if ( !LODWORD(v7[2].Ptr) && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&stru_18003B5D8);
    a5 = &stru_18003B5D8;
    if ( !qword_18003B638 )
    {
      qword_18003B638 = 0;
      v9 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v9 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v9(&qword_18003B638, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&a5);
  }
}

```

## disassembly

```asm
0x180015394  mov     [rsp+arg_0], rbx
0x180015399  mov     [rsp+arg_8], rsi
0x18001539e  push    rdi; char *
0x18001539f  sub     rsp, 20h
0x1800153a3  mov     rsi, r9
0x1800153a6  mov     edi, ecx
0x1800153a8  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800153af  test    rax, rax
0x1800153b2  jz      short loc_1800153CD
0x1800153b4  test    edx, edx
0x1800153b6  jz      short loc_1800153C2
0x1800153b8  lea     r8d, [rdx-64h]
0x1800153bc  cmp     r8d, 31h ; '1'
0x1800153c0  ja      short loc_1800153CD
0x1800153c2  mov     r8d, 1
0x1800153c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153cd  mov     rbx, [rsp+28h+arg_20]
0x1800153d2  cmp     dword ptr [rbx], 0
0x1800153d5  jz      short loc_1800153E8
0x1800153d7  mov     r8, rsi; struct wil_details_FeatureReportingCache *
0x1800153da  mov     edx, edi; unsigned int
0x1800153dc  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800153e3  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1800153e8  mov     r8d, [rbx+4]; unsigned int
0x1800153ec  test    r8d, r8d
0x1800153ef  jz      short loc_1800153FB
0x1800153f1  mov     edx, [rbx+8]; unsigned int
0x1800153f4  mov     ecx, edi; this
0x1800153f6  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800153fb  cmp     dword ptr [rbx+10h], 0
0x1800153ff  jnz     short loc_18001546F
0x180015401  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015407  test    eax, eax
0x180015409  jz      short loc_18001546F
0x18001540b  lea     rbx, stru_18003B5D8
0x180015412  mov     rcx, rbx; SRWLock
0x180015415  call    cs:__imp_AcquireSRWLockExclusive
0x18001541b  mov     [rsp+28h+arg_20], rbx
0x180015420  cmp     cs:qword_18003B638, 0
0x180015428  jnz     short loc_180015464
0x18001542a  mov     cs:qword_18003B638, 0
0x180015435  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001543c  test    rax, rax
0x18001543f  jnz     short loc_18001544D
0x180015441  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180015448  test    rax, rax
0x18001544b  jz      short loc_180015464
0x18001544d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180015451  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180015458  lea     rcx, qword_18003B638
0x18001545f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015464  lea     rcx, [rsp+28h+arg_20]
0x180015469  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001546e  nop
0x18001546f  mov     rbx, [rsp+28h+arg_0]
0x180015474  mov     rsi, [rsp+28h+arg_8]
0x180015479  add     rsp, 20h
0x18001547d  pop     rdi
0x18001547e  retn
```
