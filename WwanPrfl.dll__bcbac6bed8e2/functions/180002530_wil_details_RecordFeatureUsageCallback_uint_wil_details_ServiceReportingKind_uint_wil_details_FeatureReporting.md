# `wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)'::`17'::_lambda_1_::_lambda_invoker_cdecl_(void *)

- ea: `0x180002530`
- end: `0x18000257a`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?BB@??RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z@SA@PEAX@Z`
- size: `74`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180002530`
- `0x180006614`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000256f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000256f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002545`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002545`

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
      byte_18001F418 = 0;
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x180002530  sub     rsp, 28h
0x180002534  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000253a  test    eax, eax
0x18000253c  jz      short loc_180002575
0x18000253e  lea     rcx, SRWLock; SRWLock
0x180002545  call    cs:__imp_AcquireSRWLockExclusive
0x18000254b  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180002551  test    eax, eax
0x180002553  jz      short loc_180002568
0x180002555  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000255c  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180002561  mov     cs:byte_18001F418, 0
0x180002568  lea     rcx, SRWLock; SRWLock
0x18000256f  call    cs:__imp_ReleaseSRWLockExclusive
0x180002575  add     rsp, 28h
0x180002579  retn
```
