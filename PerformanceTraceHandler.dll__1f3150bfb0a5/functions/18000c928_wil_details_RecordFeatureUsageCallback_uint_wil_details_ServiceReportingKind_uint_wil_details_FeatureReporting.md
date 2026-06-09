# wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)

- ea: `0x18000c928`
- end: `0x18000ca13`
- name: `?RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z`
- size: `235`
- prototype: `void __fastcall(__int64, __int64, __int64, struct wil_details_FeatureReportingCache *, RTL_SRWLOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000cd98`

## callees

- `0x18000490c`
- `0x180009044`
- `0x18000c848`
- `0x18000c928`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c9a9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c9a9`

## pseudocode

```c
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
      (char *)&wil::details::g_enabledStateManager,
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
    AcquireSRWLockExclusive(&SRWLock);
    a5 = &SRWLock;
    if ( !qword_1800276E0 )
    {
      qword_1800276E0 = 0;
      v9 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v9 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v9(&qword_1800276E0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&a5);
  }
}

```

## disassembly

```asm
0x18000c928  mov     [rsp+arg_0], rbx
0x18000c92d  mov     [rsp+arg_8], rsi
0x18000c932  push    rdi; char *
0x18000c933  sub     rsp, 20h
0x18000c937  mov     rsi, r9
0x18000c93a  mov     edi, ecx
0x18000c93c  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000c943  test    rax, rax
0x18000c946  jz      short loc_18000C961
0x18000c948  test    edx, edx
0x18000c94a  jz      short loc_18000C956
0x18000c94c  lea     r8d, [rdx-64h]
0x18000c950  cmp     r8d, 31h ; '1'
0x18000c954  ja      short loc_18000C961
0x18000c956  mov     r8d, 1
0x18000c95c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c961  mov     rbx, [rsp+28h+arg_20]
0x18000c966  cmp     dword ptr [rbx], 0
0x18000c969  jz      short loc_18000C97C
0x18000c96b  mov     r8, rsi; struct wil_details_FeatureReportingCache *
0x18000c96e  mov     edx, edi; unsigned int
0x18000c970  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000c977  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000c97c  mov     r8d, [rbx+4]; unsigned int
0x18000c980  test    r8d, r8d
0x18000c983  jz      short loc_18000C98F
0x18000c985  mov     edx, [rbx+8]; unsigned int
0x18000c988  mov     ecx, edi; this
0x18000c98a  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000c98f  cmp     dword ptr [rbx+10h], 0
0x18000c993  jnz     short loc_18000CA03
0x18000c995  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000c99b  test    eax, eax
0x18000c99d  jz      short loc_18000CA03
0x18000c99f  lea     rbx, SRWLock
0x18000c9a6  mov     rcx, rbx; SRWLock
0x18000c9a9  call    cs:__imp_AcquireSRWLockExclusive
0x18000c9af  mov     [rsp+28h+arg_20], rbx
0x18000c9b4  cmp     cs:qword_1800276E0, 0
0x18000c9bc  jnz     short loc_18000C9F8
0x18000c9be  mov     cs:qword_1800276E0, 0
0x18000c9c9  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000c9d0  test    rax, rax
0x18000c9d3  jnz     short loc_18000C9E1
0x18000c9d5  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000c9dc  test    rax, rax
0x18000c9df  jz      short loc_18000C9F8
0x18000c9e1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000c9e5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000c9ec  lea     rcx, qword_1800276E0
0x18000c9f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9f8  lea     rcx, [rsp+28h+arg_20]
0x18000c9fd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000ca02  nop
0x18000ca03  mov     rbx, [rsp+28h+arg_0]
0x18000ca08  mov     rsi, [rsp+28h+arg_8]
0x18000ca0d  add     rsp, 20h
0x18000ca11  pop     rdi
0x18000ca12  retn
```
