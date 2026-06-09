# `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,void *)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)

- ea: `0x180002390`
- end: `0x1800023ab`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@5@PEAX@Z@SA@1@Z`
- size: `27`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180002390`
- `0x180005ea4`

## pseudocode

```c
void __fastcall `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock'::`5'::_lambda_1_::_lambda_invoker_cdecl_(
        __int64 a1)
{
  if ( *(_BYTE *)a1 )
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)(a1 + 72), (PSRWLOCK)(a1 + 32));
}

```

## disassembly

```asm
0x180002390  sub     rsp, 28h
0x180002394  cmp     byte ptr [rcx], 0
0x180002397  jz      short loc_1800023A6
0x180002399  lea     rdx, [rcx+20h]; SRWLock
0x18000239d  add     rcx, 48h ; 'H'; lpCriticalSection
0x1800023a1  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1800023a6  add     rsp, 28h
0x1800023aa  retn
```
