# `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)'::`8'::_lambda_1_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180008310`
- end: `0x180008391`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `129`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180008310`
- `0x180008f98`
- `0x180009604`
- `0x180009e90`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000833b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000833b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008329`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008329`

## pseudocode

```c

```
