# wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)

- ea: `0x18000c270`
- end: `0x18000c46a`
- name: `?RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z`
- size: `506`
- prototype: ``
- caller_count: `11`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000b2f0`
- `0x18000b490`
- `0x18000b630`
- `0x18000c470`
- `0x180011710`
- `0x1800118b0`
- `0x18003c190`
- `0x18003d410`
- `0x18003df60`
- `0x18003e100`
- `0x18003e2e0`

## callees

- `0x180007430`
- `0x18000c270`
- `0x18000c740`
- `0x18000c950`
- `0x180242120`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000c358`
- `KERNEL32!SetLastError` at `0x18000c358`
- `KERNEL32!GetLastError` at `0x18000c328`
- `KERNEL32!GetLastError` at `0x18000c328`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c387`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c387`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c39b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c453`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c39b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c453`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c2ed`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c3f9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c2ed`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c3f9`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000c341`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000c341`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::RecordFeatureUsageCallback(
        unsigned int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        _FILETIME pftDueTime)
{
  unsigned int *v7; // rdi
  struct _TP_TIMER *v8; // rcx
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  __int64 v11; // r8
  __int64 v12; // rdx
  _QWORD *v13; // rax
  void (__fastcall *v14)(_QWORD *, __int64 (__fastcall *)(), __int64); // r9
  unsigned int v15; // [rsp+30h] [rbp-18h] BYREF
  __int64 v16; // [rsp+38h] [rbp-10h]

  if ( g_wil_details_RecordSRUMFeatureUsage && (!a2 || (unsigned int)(a2 - 100) <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage();
  v7 = (unsigned int *)pftDueTime;
  if ( *(_DWORD *)pftDueTime.dwLowDateTime
    && wil::details::g_enabledStateManager
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v15 = a1;
    v16 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18033CC30, &v15, 0x10u);
    if ( !byte_18033CC18 )
    {
      v8 = pti;
      if ( pti
        || (LastError = GetLastError(),
            ThreadpoolTimer = CreateThreadpoolTimer(
                                `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                                &wil::details::g_enabledStateManager,
                                0),
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pti,
              ThreadpoolTimer),
            SetLastError(LastError),
            (v8 = pti) != 0) )
      {
        pftDueTime = (_FILETIME)-3000000000LL;
        SetThreadpoolTimer(v8, &pftDueTime, 0, 0x124F8u);
        byte_18033CC18 = 1;
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  v11 = v7[1];
  if ( (_DWORD)v11 )
  {
    v12 = v7[2];
    if ( g_wil_details_internalRecordFeatureUsage )
    {
      _mm_lfence();
      ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD))g_wil_details_internalRecordFeatureUsage)(a1, v12, v11, 0);
    }
    else if ( g_wil_details_apiRecordFeatureUsage )
    {
      _mm_lfence();
      ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD))g_wil_details_apiRecordFeatureUsage)(a1, v12, v11, 0);
    }
  }
  if ( !v7[4] && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_18033CC28 )
    {
      v13 = (_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,void (*)(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),&void wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),wistd::integral_constant<unsigned __int64,0>,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,0,std::nullptr_t>>>::operator&(&qword_18033CC28);
      v14 = (void (__fastcall *)(_QWORD *, __int64 (__fastcall *)(), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v14 = (void (__fastcall *)(_QWORD *, __int64 (__fastcall *)(), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v14(v13, `wil::details::RecordFeatureUsageCallback'::`17'::_lambda_1_::_lambda_invoker_cdecl_, -1);
      }
      else
      {
        *v13 = 0;
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x18000c270  mov     [rsp+arg_0], rbx
0x18000c275  mov     [rsp+arg_8], rsi
0x18000c27a  push    rdi
0x18000c27b  sub     rsp, 40h
0x18000c27f  mov     rbx, r9
0x18000c282  mov     esi, ecx
0x18000c284  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000c28b  test    rax, rax
0x18000c28e  jz      short loc_18000C2A4
0x18000c290  test    edx, edx
0x18000c292  jz      short loc_18000C29E
0x18000c294  lea     r10d, [rdx-64h]
0x18000c298  cmp     r10d, 31h ; '1'
0x18000c29c  ja      short loc_18000C2A4
0x18000c29e  call    cs:__guard_dispatch_icall_fptr
0x18000c2a4  mov     rdi, qword ptr [rsp+48h+pftDueTime.dwLowDateTime]
0x18000c2a9  cmp     dword ptr [rdi], 0
0x18000c2ac  jz      loc_18000C3A2
0x18000c2b2  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000c2b9  jz      loc_18000C3A2
0x18000c2bf  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000c2c6  jnz     loc_18000C3A2
0x18000c2cc  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c2d3  test    rax, rax
0x18000c2d6  jz      short loc_18000C2E6
0x18000c2d8  call    cs:__guard_dispatch_icall_fptr
0x18000c2de  test    al, al
0x18000c2e0  jnz     loc_18000C3A2
0x18000c2e6  lea     rcx, SRWLock; SRWLock
0x18000c2ed  call    cs:__imp_AcquireSRWLockExclusive
0x18000c2f3  mov     [rsp+48h+var_18], esi
0x18000c2f7  mov     [rsp+48h+var_10], rbx
0x18000c2fc  mov     r8d, 10h; unsigned __int64
0x18000c302  lea     rdx, [rsp+48h+var_18]; void *
0x18000c307  lea     rcx, qword_18033CC30; this
0x18000c30e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000c313  cmp     cs:byte_18033CC18, 0
0x18000c31a  jnz     short loc_18000C394
0x18000c31c  mov     rcx, cs:pti
0x18000c323  test    rcx, rcx
0x18000c326  jnz     short loc_18000C36A
0x18000c328  call    cs:__imp_GetLastError
0x18000c32e  mov     ebx, eax
0x18000c330  xor     r8d, r8d; pcbe
0x18000c333  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000c33a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000c341  call    cs:__imp_CreateThreadpoolTimer
0x18000c347  mov     rdx, rax
0x18000c34a  lea     rcx, pti
0x18000c351  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000c356  mov     ecx, ebx; dwErrCode
0x18000c358  call    cs:__imp_SetLastError
0x18000c35e  mov     rcx, cs:pti; pti
0x18000c365  test    rcx, rcx
0x18000c368  jz      short loc_18000C394
0x18000c36a  mov     rax, 0FFFFFFFF4D2FA200h
0x18000c374  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18000c379  mov     r9d, 124F8h; msWindowLength
0x18000c37f  xor     r8d, r8d; msPeriod
0x18000c382  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18000c387  call    cs:__imp_SetThreadpoolTimer
0x18000c38d  mov     cs:byte_18033CC18, 1
0x18000c394  lea     rcx, SRWLock; SRWLock
0x18000c39b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c3a1  nop
0x18000c3a2  mov     r8d, [rdi+4]
0x18000c3a6  test    r8d, r8d
0x18000c3a9  jz      short loc_18000C3E3
0x18000c3ab  mov     edx, [rdi+8]
0x18000c3ae  cmp     cs:g_wil_details_internalRecordFeatureUsage, 0
0x18000c3b6  jz      short loc_18000C3C4
0x18000c3b8  lfence
0x18000c3bb  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000c3c2  jmp     short loc_18000C3D8
0x18000c3c4  cmp     cs:g_wil_details_apiRecordFeatureUsage, 0
0x18000c3cc  jz      short loc_18000C3E3
0x18000c3ce  lfence
0x18000c3d1  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000c3d8  xor     r9d, r9d
0x18000c3db  mov     ecx, esi
0x18000c3dd  call    cs:__guard_dispatch_icall_fptr
0x18000c3e3  cmp     dword ptr [rdi+10h], 0
0x18000c3e7  jnz     short loc_18000C45A
0x18000c3e9  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000c3f0  jz      short loc_18000C45A
0x18000c3f2  lea     rcx, SRWLock; SRWLock
0x18000c3f9  call    cs:__imp_AcquireSRWLockExclusive
0x18000c3ff  cmp     cs:qword_18033CC28, 0
0x18000c407  jnz     short loc_18000C44C
0x18000c409  lea     rcx, qword_18033CC28
0x18000c410  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAU1@@Z$1?WilApi_UnsubscribeFeatureStateChangeNotification@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,void (*)(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),&wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),wistd::integral_constant<unsigned __int64,0>,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,0,std::nullptr_t>>>::operator&(void)
0x18000c415  mov     r9, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000c41c  test    r9, r9
0x18000c41f  jz      short loc_18000C43D
0x18000c421  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000c428  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?BB@??RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z@SA@PEAX@Z; `wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)'::`17'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18000c42f  mov     rcx, rax
0x18000c432  mov     rax, r9
0x18000c435  call    cs:__guard_dispatch_icall_fptr
0x18000c43b  jmp     short loc_18000C44C
0x18000c43d  mov     r9, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000c444  test    r9, r9
0x18000c447  jnz     short loc_18000C421
0x18000c449  mov     [rax], r9
0x18000c44c  lea     rcx, SRWLock; SRWLock
0x18000c453  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c459  nop
0x18000c45a  mov     rbx, [rsp+48h+arg_0]
0x18000c45f  mov     rsi, [rsp+48h+arg_8]
0x18000c464  add     rsp, 40h
0x18000c468  pop     rdi
0x18000c469  retn
```
