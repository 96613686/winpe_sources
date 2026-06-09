# `wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)'::`17'::_lambda_1_::_lambda_invoker_cdecl_(void *)

- ea: `0x140009470`
- end: `0x1400094ba`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?BB@??RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z@SA@PEAX@Z`
- size: `74`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x140006208`
- `0x140009470`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009485`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009485`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400094af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400094af`

## pseudocode

```c
void `wil::details::RecordFeatureUsageCallback'::`17'::_lambda_1_::_lambda_invoker_cdecl_()
{
  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( wil::details::g_enabledStateManager )
    {
      wil::details::EnabledStateManager::RecordCachedUsageUnderLock(&wil::details::g_enabledStateManager);
      byte_140011698 = 0;
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x140009470  sub     rsp, 28h
0x140009474  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000947a  test    eax, eax
0x14000947c  jz      short loc_1400094B5
0x14000947e  lea     rcx, SRWLock; SRWLock
0x140009485  call    cs:__imp_AcquireSRWLockExclusive
0x14000948b  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140009491  test    eax, eax
0x140009493  jz      short loc_1400094A8
0x140009495  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000949c  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1400094a1  mov     cs:byte_140011698, 0
0x1400094a8  lea     rcx, SRWLock; SRWLock
0x1400094af  call    cs:__imp_ReleaseSRWLockExclusive
0x1400094b5  add     rsp, 28h
0x1400094b9  retn
```
