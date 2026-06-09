# wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)

- ea: `0x180006b20`
- end: `0x180006d39`
- name: `?RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180005ce0`
- `0x180006d40`
- `0x180010230`
- `0x1800103e0`
- `0x180010590`
- `0x180010740`
- `0x180011610`
- `0x18001db40`
- `0x18002e220`
- `0x180036c70`
- `0x180036e20`

## callees

- `0x1800067c0`
- `0x180006b20`
- `0x180006ff0`
- `0x180007260`
- `0x18004c070`
- `0x18005e260`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180006c1a`
- `KERNEL32!SetLastError` at `0x180006c1a`
- `KERNEL32!GetLastError` at `0x180006bea`
- `KERNEL32!GetLastError` at `0x180006bea`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006c5d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006d15`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006c5d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006d15`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006bb5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006cbb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006bb5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006cbb`
- `KERNEL32!SetThreadpoolTimer` at `0x180006c49`
- `KERNEL32!SetThreadpoolTimer` at `0x180006c49`
- `KERNEL32!CreateThreadpoolTimer` at `0x180006c03`
- `KERNEL32!CreateThreadpoolTimer` at `0x180006c03`

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
  void (__fastcall *v14)(_QWORD *, void (*)(), __int64); // r9
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
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180085350, &pftDueTime, v7);
    if ( !byte_180085338 )
    {
      v8 = pti;
      if ( pti
        || (LastError = GetLastError(),
            ThreadpoolTimer = CreateThreadpoolTimer(
                                (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
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
        byte_180085338 = 1;
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
    if ( !qword_180085348 )
    {
      v13 = (_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,void (*)(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),&void wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),wistd::integral_constant<unsigned __int64,0>,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,0,std::nullptr_t>>>::operator&(&qword_180085348);
      v14 = (void (__fastcall *)(_QWORD *, void (*)(), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v14 = (void (__fastcall *)(_QWORD *, void (*)(), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
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
0x180006b20  mov     [rsp+arg_10], rbx
0x180006b25  mov     [rsp+arg_18], rsi
0x180006b2a  push    rdi
0x180006b2b  sub     rsp, 50h
0x180006b2f  mov     rax, cs:__security_cookie
0x180006b36  xor     rax, rsp
0x180006b39  mov     [rsp+58h+var_18], rax
0x180006b3e  mov     rbx, r9
0x180006b41  mov     esi, ecx
0x180006b43  mov     rdi, [rsp+58h+arg_20]
0x180006b4b  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180006b52  test    rax, rax
0x180006b55  jz      short loc_180006B71
0x180006b57  test    edx, edx
0x180006b59  jz      short loc_180006B63
0x180006b5b  lea     ecx, [rdx-64h]
0x180006b5e  cmp     ecx, 31h ; '1'
0x180006b61  ja      short loc_180006B71
0x180006b63  mov     r8d, 1
0x180006b69  mov     ecx, esi
0x180006b6b  call    cs:__guard_dispatch_icall_fptr
0x180006b71  cmp     dword ptr [rdi], 0
0x180006b74  jz      loc_180006C64
0x180006b7a  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180006b81  jz      loc_180006C64
0x180006b87  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006b8e  jnz     loc_180006C64
0x180006b94  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006b9b  test    rax, rax
0x180006b9e  jz      short loc_180006BAE
0x180006ba0  call    cs:__guard_dispatch_icall_fptr
0x180006ba6  test    al, al
0x180006ba8  jnz     loc_180006C64
0x180006bae  lea     rcx, SRWLock; SRWLock
0x180006bb5  call    cs:__imp_AcquireSRWLockExclusive
0x180006bbb  mov     [rsp+58h+pftDueTime.dwLowDateTime], esi
0x180006bbf  mov     [rsp+58h+var_20], rbx
0x180006bc4  lea     rdx, [rsp+58h+pftDueTime]; void *
0x180006bc9  lea     rcx, qword_180085350; this
0x180006bd0  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180006bd5  cmp     cs:byte_180085338, 0
0x180006bdc  jnz     short loc_180006C56
0x180006bde  mov     rcx, cs:pti
0x180006be5  test    rcx, rcx
0x180006be8  jnz     short loc_180006C2C
0x180006bea  call    cs:__imp_GetLastError
0x180006bf0  mov     ebx, eax
0x180006bf2  xor     r8d, r8d; pcbe
0x180006bf5  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180006bfc  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006c03  call    cs:__imp_CreateThreadpoolTimer
0x180006c09  mov     rdx, rax
0x180006c0c  lea     rcx, pti
0x180006c13  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180006c18  mov     ecx, ebx; dwErrCode
0x180006c1a  call    cs:__imp_SetLastError
0x180006c20  mov     rcx, cs:pti; pti
0x180006c27  test    rcx, rcx
0x180006c2a  jz      short loc_180006C56
0x180006c2c  mov     rax, 0FFFFFFFF4D2FA200h
0x180006c36  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180006c3b  mov     r9d, 124F8h; msWindowLength
0x180006c41  xor     r8d, r8d; msPeriod
0x180006c44  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180006c49  call    cs:__imp_SetThreadpoolTimer
0x180006c4f  mov     cs:byte_180085338, 1
0x180006c56  lea     rcx, SRWLock; SRWLock
0x180006c5d  call    cs:__imp_ReleaseSRWLockExclusive
0x180006c63  nop
0x180006c64  mov     r8d, [rdi+4]
0x180006c68  test    r8d, r8d
0x180006c6b  jz      short loc_180006CA5
0x180006c6d  mov     edx, [rdi+8]
0x180006c70  cmp     cs:g_wil_details_internalRecordFeatureUsage, 0
0x180006c78  jz      short loc_180006C86
0x180006c7a  lfence
0x180006c7d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180006c84  jmp     short loc_180006C9A
0x180006c86  cmp     cs:g_wil_details_apiRecordFeatureUsage, 0
0x180006c8e  jz      short loc_180006CA5
0x180006c90  lfence
0x180006c93  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180006c9a  xor     r9d, r9d
0x180006c9d  mov     ecx, esi
0x180006c9f  call    cs:__guard_dispatch_icall_fptr
0x180006ca5  cmp     dword ptr [rdi+10h], 0
0x180006ca9  jnz     short loc_180006D1C
0x180006cab  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180006cb2  jz      short loc_180006D1C
0x180006cb4  lea     rcx, SRWLock; SRWLock
0x180006cbb  call    cs:__imp_AcquireSRWLockExclusive
0x180006cc1  cmp     cs:qword_180085348, 0
0x180006cc9  jnz     short loc_180006D0E
0x180006ccb  lea     rcx, qword_180085348
0x180006cd2  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAU1@@Z$1?WilApi_UnsubscribeFeatureStateChangeNotification@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,void (*)(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),&wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),wistd::integral_constant<unsigned __int64,0>,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,0,std::nullptr_t>>>::operator&(void)
0x180006cd7  mov     r9, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180006cde  test    r9, r9
0x180006ce1  jz      short loc_180006CFF
0x180006ce3  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180006cea  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?BB@??RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z@SA@PEAX@Z; `wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)'::`17'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x180006cf1  mov     rcx, rax
0x180006cf4  mov     rax, r9
0x180006cf7  call    cs:__guard_dispatch_icall_fptr
0x180006cfd  jmp     short loc_180006D0E
0x180006cff  mov     r9, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180006d06  test    r9, r9
0x180006d09  jnz     short loc_180006CE3
0x180006d0b  mov     [rax], r9
0x180006d0e  lea     rcx, SRWLock; SRWLock
0x180006d15  call    cs:__imp_ReleaseSRWLockExclusive
0x180006d1b  nop
0x180006d1c  mov     rcx, [rsp+58h+var_18]
0x180006d21  xor     rcx, rsp; StackCookie
0x180006d24  call    __security_check_cookie
0x180006d29  mov     rbx, [rsp+58h+arg_10]
0x180006d2e  mov     rsi, [rsp+58h+arg_18]
0x180006d33  add     rsp, 50h
0x180006d37  pop     rdi
0x180006d38  retn
```
