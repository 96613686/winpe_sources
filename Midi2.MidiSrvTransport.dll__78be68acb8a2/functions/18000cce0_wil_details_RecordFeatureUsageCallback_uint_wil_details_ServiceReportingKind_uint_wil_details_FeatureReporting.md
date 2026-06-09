# `wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)'::`17'::_lambda_1_::_lambda_invoker_cdecl_(void *)

- ea: `0x18000cce0`
- end: `0x18000cd2a`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?BB@??RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z@SA@PEAX@Z`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000cce0`
- `0x18000fbb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ccf5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ccf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cd1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cd1f`

## pseudocode

```c
void `wil::details::RecordFeatureUsageCallback'::`17'::_lambda_1_::_lambda_invoker_cdecl_()
{
  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( wil::details::g_enabledStateManager )
    {
      wil::details::EnabledStateManager::RecordCachedUsageUnderLock((__int64)&wil::details::g_enabledStateManager);
      byte_18001E408 = 0;
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x18000cce0  sub     rsp, 28h
0x18000cce4  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ccea  test    eax, eax
0x18000ccec  jz      short loc_18000CD25
0x18000ccee  lea     rcx, SRWLock; SRWLock
0x18000ccf5  call    cs:__imp_AcquireSRWLockExclusive
0x18000ccfb  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000cd01  test    eax, eax
0x18000cd03  jz      short loc_18000CD18
0x18000cd05  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000cd0c  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000cd11  mov     cs:byte_18001E408, 0
0x18000cd18  lea     rcx, SRWLock; SRWLock
0x18000cd1f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cd25  add     rsp, 28h
0x18000cd29  retn
```
