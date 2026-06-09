# wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)

- ea: `0x18000f8f0`
- end: `0x18000fb09`
- name: `?RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z`
- size: `537`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000d9a0`
- `0x18000fb10`
- `0x180019d50`
- `0x180019f30`
- `0x18001a0e0`
- `0x180029ac0`
- `0x180029c70`

## callees

- `0x18000f590`
- `0x18000f8f0`
- `0x18000fdc0`
- `0x180010030`
- `0x180034ef0`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000f9ea`
- `KERNEL32!SetLastError` at `0x18000f9ea`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000fa2d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000fae5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000fa2d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000fae5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f985`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000fa8b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f985`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000fa8b`
- `KERNEL32!SetThreadpoolTimer` at `0x18000fa19`
- `KERNEL32!SetThreadpoolTimer` at `0x18000fa19`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000f9d3`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000f9d3`
- `KERNEL32!GetLastError` at `0x18000f9ba`
- `KERNEL32!GetLastError` at `0x18000f9ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::RecordFeatureUsageCallback(DWORD a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  unsigned __int64 v7; // r8
  struct _TP_TIMER *v8; // rcx
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  __int64 v11; // r8
  __int64 v12; // rdx
  _QWORD *v13; // rax
  void (__fastcall *v14)(_QWORD *, __int64 (__fastcall *)(void *), __int64); // r9
  _FILETIME pftDueTime; // [rsp+30h] [rbp-28h] BYREF
  __int64 v16; // [rsp+38h] [rbp-20h]

  if ( g_wil_details_RecordSRUMFeatureUsage && (!(_DWORD)a2 || (unsigned int)(a2 - 100) <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a1, a2, 1);
  if ( *a5
    && wil::details::g_enabledStateManager
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(&SRWLock);
    pftDueTime.dwLowDateTime = a1;
    v16 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180058410, &pftDueTime, v7);
    if ( !byte_1800583F8 )
    {
      v8 = pti;
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
            (v8 = pti) != 0) )
      {
        pftDueTime = (_FILETIME)-3000000000LL;
        SetThreadpoolTimer(v8, &pftDueTime, 0, 0x124F8u);
        byte_1800583F8 = 1;
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  v11 = (unsigned int)a5[1];
  if ( (_DWORD)v11 )
  {
    v12 = (unsigned int)a5[2];
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
  if ( !a5[4] && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_180058408 )
    {
      v13 = (_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,void (*)(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),&void wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),wistd::integral_constant<unsigned __int64,0>,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,0,std::nullptr_t>>>::operator&(&qword_180058408);
      v14 = (void (__fastcall *)(_QWORD *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v14 = (void (__fastcall *)(_QWORD *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v14(v13, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18000f8f0  mov     [rsp+arg_10], rbx
0x18000f8f5  mov     [rsp+arg_18], rsi
0x18000f8fa  push    rdi
0x18000f8fb  sub     rsp, 50h
0x18000f8ff  mov     rax, cs:__security_cookie
0x18000f906  xor     rax, rsp
0x18000f909  mov     [rsp+58h+var_18], rax
0x18000f90e  mov     rbx, r9
0x18000f911  mov     esi, ecx
0x18000f913  mov     rdi, [rsp+58h+arg_20]
0x18000f91b  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000f922  test    rax, rax
0x18000f925  jz      short loc_18000F941
0x18000f927  test    edx, edx
0x18000f929  jz      short loc_18000F933
0x18000f92b  lea     ecx, [rdx-64h]
0x18000f92e  cmp     ecx, 31h ; '1'
0x18000f931  ja      short loc_18000F941
0x18000f933  mov     r8d, 1
0x18000f939  mov     ecx, esi
0x18000f93b  call    cs:__guard_dispatch_icall_fptr
0x18000f941  cmp     dword ptr [rdi], 0
0x18000f944  jz      loc_18000FA34
0x18000f94a  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000f951  jz      loc_18000FA34
0x18000f957  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000f95e  jnz     loc_18000FA34
0x18000f964  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f96b  test    rax, rax
0x18000f96e  jz      short loc_18000F97E
0x18000f970  call    cs:__guard_dispatch_icall_fptr
0x18000f976  test    al, al
0x18000f978  jnz     loc_18000FA34
0x18000f97e  lea     rcx, SRWLock; SRWLock
0x18000f985  call    cs:__imp_AcquireSRWLockExclusive
0x18000f98b  mov     [rsp+58h+pftDueTime.dwLowDateTime], esi
0x18000f98f  mov     [rsp+58h+var_20], rbx
0x18000f994  lea     rdx, [rsp+58h+pftDueTime]; void *
0x18000f999  lea     rcx, qword_180058410; this
0x18000f9a0  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000f9a5  cmp     cs:byte_1800583F8, 0
0x18000f9ac  jnz     short loc_18000FA26
0x18000f9ae  mov     rcx, cs:pti
0x18000f9b5  test    rcx, rcx
0x18000f9b8  jnz     short loc_18000F9FC
0x18000f9ba  call    cs:__imp_GetLastError
0x18000f9c0  mov     ebx, eax
0x18000f9c2  xor     r8d, r8d; pcbe
0x18000f9c5  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000f9cc  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000f9d3  call    cs:__imp_CreateThreadpoolTimer
0x18000f9d9  mov     rdx, rax
0x18000f9dc  lea     rcx, pti
0x18000f9e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000f9e8  mov     ecx, ebx; dwErrCode
0x18000f9ea  call    cs:__imp_SetLastError
0x18000f9f0  mov     rcx, cs:pti; pti
0x18000f9f7  test    rcx, rcx
0x18000f9fa  jz      short loc_18000FA26
0x18000f9fc  mov     rax, 0FFFFFFFF4D2FA200h
0x18000fa06  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000fa0b  mov     r9d, 124F8h; msWindowLength
0x18000fa11  xor     r8d, r8d; msPeriod
0x18000fa14  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000fa19  call    cs:__imp_SetThreadpoolTimer
0x18000fa1f  mov     cs:byte_1800583F8, 1
0x18000fa26  lea     rcx, SRWLock; SRWLock
0x18000fa2d  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fa33  nop
0x18000fa34  mov     r8d, [rdi+4]
0x18000fa38  test    r8d, r8d
0x18000fa3b  jz      short loc_18000FA75
0x18000fa3d  mov     edx, [rdi+8]
0x18000fa40  cmp     cs:g_wil_details_internalRecordFeatureUsage, 0
0x18000fa48  jz      short loc_18000FA56
0x18000fa4a  lfence
0x18000fa4d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000fa54  jmp     short loc_18000FA6A
0x18000fa56  cmp     cs:g_wil_details_apiRecordFeatureUsage, 0
0x18000fa5e  jz      short loc_18000FA75
0x18000fa60  lfence
0x18000fa63  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000fa6a  xor     r9d, r9d
0x18000fa6d  mov     ecx, esi
0x18000fa6f  call    cs:__guard_dispatch_icall_fptr
0x18000fa75  cmp     dword ptr [rdi+10h], 0
0x18000fa79  jnz     short loc_18000FAEC
0x18000fa7b  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000fa82  jz      short loc_18000FAEC
0x18000fa84  lea     rcx, SRWLock; SRWLock
0x18000fa8b  call    cs:__imp_AcquireSRWLockExclusive
0x18000fa91  cmp     cs:qword_180058408, 0
0x18000fa99  jnz     short loc_18000FADE
0x18000fa9b  lea     rcx, qword_180058408
0x18000faa2  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAU1@@Z$1?WilApi_UnsubscribeFeatureStateChangeNotification@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,void (*)(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),&wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),wistd::integral_constant<unsigned __int64,0>,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,0,std::nullptr_t>>>::operator&(void)
0x18000faa7  mov     r9, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000faae  test    r9, r9
0x18000fab1  jz      short loc_18000FACF
0x18000fab3  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000faba  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000fac1  mov     rcx, rax
0x18000fac4  mov     rax, r9
0x18000fac7  call    cs:__guard_dispatch_icall_fptr
0x18000facd  jmp     short loc_18000FADE
0x18000facf  mov     r9, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000fad6  test    r9, r9
0x18000fad9  jnz     short loc_18000FAB3
0x18000fadb  mov     [rax], r9
0x18000fade  lea     rcx, SRWLock; SRWLock
0x18000fae5  call    cs:__imp_ReleaseSRWLockExclusive
0x18000faeb  nop
0x18000faec  mov     rcx, [rsp+58h+var_18]
0x18000faf1  xor     rcx, rsp; StackCookie
0x18000faf4  call    __security_check_cookie
0x18000faf9  mov     rbx, [rsp+58h+arg_10]
0x18000fafe  mov     rsi, [rsp+58h+arg_18]
0x18000fb03  add     rsp, 50h
0x18000fb07  pop     rdi
0x18000fb08  retn
```
