# wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)

- ea: `0x180004970`
- end: `0x180004b87`
- name: `?RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z`
- size: `535`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000b580`

## callees

- `0x1800043f0`
- `0x180004970`
- `0x180008eb0`
- `0x180012de0`
- `0x1800181b0`
- `0x18001cdf0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004a3a`
- `KERNEL32!GetLastError` at `0x180004a3a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180004a01`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180004b0e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180004a01`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180004b0e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004aad`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004b68`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004aad`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004b68`
- `KERNEL32!SetThreadpoolTimer` at `0x180004a99`
- `KERNEL32!SetThreadpoolTimer` at `0x180004a99`
- `KERNEL32!SetLastError` at `0x180004a6a`
- `KERNEL32!SetLastError` at `0x180004a6a`
- `KERNEL32!CreateThreadpoolTimer` at `0x180004a53`
- `KERNEL32!CreateThreadpoolTimer` at `0x180004a53`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::RecordFeatureUsageCallback(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  unsigned __int64 v6; // r8
  struct _TP_TIMER *v7; // rcx
  DWORD LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
  __int64 v10; // r8
  __int64 v11; // rdx
  _QWORD *v12; // rax
  void (__fastcall *v13)(_QWORD *, __int64 (__fastcall *)(void *), __int64); // r9
  _FILETIME pftDueTime; // [rsp+30h] [rbp-28h] BYREF
  __int64 v15; // [rsp+38h] [rbp-20h]

  if ( g_wil_details_RecordSRUMFeatureUsage && (!(_DWORD)a2 || (unsigned int)(a2 - 100) <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(55709058, a2, 1);
  if ( *a5
    && wil::details::g_enabledStateManager
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(&SRWLock);
    pftDueTime.dwLowDateTime = 55709058;
    v15 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002D350, &pftDueTime, v6);
    if ( !byte_18002D338 )
    {
      v7 = pti;
      if ( pti
        || (LastError = GetLastError(),
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                &wil::details::g_enabledStateManager,
                                0),
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pti,
              ThreadpoolTimer),
            SetLastError(LastError),
            (v7 = pti) != 0) )
      {
        pftDueTime = (_FILETIME)-3000000000LL;
        SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
        byte_18002D338 = 1;
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  v10 = (unsigned int)a5[1];
  if ( (_DWORD)v10 )
  {
    v11 = (unsigned int)a5[2];
    if ( g_wil_details_internalRecordFeatureUsage )
    {
      _mm_lfence();
      ((void (__fastcall *)(__int64, __int64, __int64, _QWORD))g_wil_details_internalRecordFeatureUsage)(
        55709058,
        v11,
        v10,
        0);
    }
    else if ( g_wil_details_apiRecordFeatureUsage )
    {
      _mm_lfence();
      ((void (__fastcall *)(__int64, __int64, __int64, _QWORD))g_wil_details_apiRecordFeatureUsage)(
        55709058,
        v11,
        v10,
        0);
    }
  }
  if ( !a5[4] && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_18002D348 )
    {
      v12 = (_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,void (*)(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),&void wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),wistd::integral_constant<unsigned __int64,0>,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,0,std::nullptr_t>>>::operator&(&qword_18002D348);
      v13 = (void (__fastcall *)(_QWORD *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v13 = (void (__fastcall *)(_QWORD *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v13(v12, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
      else
      {
        *v12 = 0;
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x180004970  mov     [rsp+arg_0], rbx
0x180004975  push    rdi
0x180004976  sub     rsp, 50h
0x18000497a  mov     rax, cs:__security_cookie
0x180004981  xor     rax, rsp
0x180004984  mov     [rsp+58h+var_18], rax
0x180004989  mov     rbx, r9
0x18000498c  mov     rdi, [rsp+58h+arg_20]
0x180004994  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000499b  test    rax, rax
0x18000499e  jz      short loc_1800049BD
0x1800049a0  test    edx, edx
0x1800049a2  jz      short loc_1800049AC
0x1800049a4  lea     ecx, [rdx-64h]
0x1800049a7  cmp     ecx, 31h ; '1'
0x1800049aa  ja      short loc_1800049BD
0x1800049ac  mov     ecx, 3520D82h
0x1800049b1  mov     r8d, 1
0x1800049b7  call    cs:__guard_dispatch_icall_fptr
0x1800049bd  cmp     dword ptr [rdi], 0
0x1800049c0  jz      loc_180004AB4
0x1800049c6  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800049cd  jz      loc_180004AB4
0x1800049d3  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800049da  jnz     loc_180004AB4
0x1800049e0  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800049e7  test    rax, rax
0x1800049ea  jz      short loc_1800049FA
0x1800049ec  call    cs:__guard_dispatch_icall_fptr
0x1800049f2  test    al, al
0x1800049f4  jnz     loc_180004AB4
0x1800049fa  lea     rcx, SRWLock; SRWLock
0x180004a01  call    cs:__imp_AcquireSRWLockExclusive
0x180004a07  mov     [rsp+58h+pftDueTime.dwLowDateTime], 3520D82h
0x180004a0f  mov     [rsp+58h+var_20], rbx
0x180004a14  lea     rdx, [rsp+58h+pftDueTime]; void *
0x180004a19  lea     rcx, qword_18002D350; this
0x180004a20  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180004a25  cmp     cs:byte_18002D338, 0
0x180004a2c  jnz     short loc_180004AA6
0x180004a2e  mov     rcx, cs:pti
0x180004a35  test    rcx, rcx
0x180004a38  jnz     short loc_180004A7C
0x180004a3a  call    cs:__imp_GetLastError
0x180004a40  mov     ebx, eax
0x180004a42  xor     r8d, r8d; pcbe
0x180004a45  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180004a4c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180004a53  call    cs:__imp_CreateThreadpoolTimer
0x180004a59  mov     rdx, rax
0x180004a5c  lea     rcx, pti
0x180004a63  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180004a68  mov     ecx, ebx; dwErrCode
0x180004a6a  call    cs:__imp_SetLastError
0x180004a70  mov     rcx, cs:pti; pti
0x180004a77  test    rcx, rcx
0x180004a7a  jz      short loc_180004AA6
0x180004a7c  mov     rax, 0FFFFFFFF4D2FA200h
0x180004a86  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180004a8b  mov     r9d, 124F8h; msWindowLength
0x180004a91  xor     r8d, r8d; msPeriod
0x180004a94  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180004a99  call    cs:__imp_SetThreadpoolTimer
0x180004a9f  mov     cs:byte_18002D338, 1
0x180004aa6  lea     rcx, SRWLock; SRWLock
0x180004aad  call    cs:__imp_ReleaseSRWLockExclusive
0x180004ab3  nop
0x180004ab4  mov     r8d, [rdi+4]
0x180004ab8  test    r8d, r8d
0x180004abb  jz      short loc_180004AF8
0x180004abd  mov     edx, [rdi+8]
0x180004ac0  cmp     cs:g_wil_details_internalRecordFeatureUsage, 0
0x180004ac8  jz      short loc_180004AD6
0x180004aca  lfence
0x180004acd  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180004ad4  jmp     short loc_180004AEA
0x180004ad6  cmp     cs:g_wil_details_apiRecordFeatureUsage, 0
0x180004ade  jz      short loc_180004AF8
0x180004ae0  lfence
0x180004ae3  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180004aea  xor     r9d, r9d
0x180004aed  mov     ecx, 3520D82h
0x180004af2  call    cs:__guard_dispatch_icall_fptr
0x180004af8  cmp     dword ptr [rdi+10h], 0
0x180004afc  jnz     short loc_180004B6F
0x180004afe  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004b05  jz      short loc_180004B6F
0x180004b07  lea     rcx, SRWLock; SRWLock
0x180004b0e  call    cs:__imp_AcquireSRWLockExclusive
0x180004b14  cmp     cs:qword_18002D348, 0
0x180004b1c  jnz     short loc_180004B61
0x180004b1e  lea     rcx, qword_18002D348
0x180004b25  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAU1@@Z$1?WilApi_UnsubscribeFeatureStateChangeNotification@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,void (*)(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),&wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),wistd::integral_constant<unsigned __int64,0>,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,0,std::nullptr_t>>>::operator&(void)
0x180004b2a  mov     r9, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180004b31  test    r9, r9
0x180004b34  jz      short loc_180004B52
0x180004b36  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180004b3d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180004b44  mov     rcx, rax
0x180004b47  mov     rax, r9
0x180004b4a  call    cs:__guard_dispatch_icall_fptr
0x180004b50  jmp     short loc_180004B61
0x180004b52  mov     r9, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180004b59  test    r9, r9
0x180004b5c  jnz     short loc_180004B36
0x180004b5e  mov     [rax], r9
0x180004b61  lea     rcx, SRWLock; SRWLock
0x180004b68  call    cs:__imp_ReleaseSRWLockExclusive
0x180004b6e  nop
0x180004b6f  mov     rcx, [rsp+58h+var_18]
0x180004b74  xor     rcx, rsp; StackCookie
0x180004b77  call    __security_check_cookie
0x180004b7c  mov     rbx, [rsp+58h+arg_0]
0x180004b81  add     rsp, 50h
0x180004b85  pop     rdi
0x180004b86  retn
```
