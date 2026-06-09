# Windows::Internal::Spelling::RoamingDictionaryManager::~RoamingDictionaryManager(void)

- ea: `0x18007cdcc`
- end: `0x18007ce83`
- name: `??1RoamingDictionaryManager@Spelling@Internal@Windows@@UEAA@XZ`
- size: `183`
- prototype: `void __fastcall(Windows::Internal::Spelling::RoamingDictionaryManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007dbd0`

## callees

- `0x180040cc4`
- `0x180041938`
- `0x180042f6c`
- `0x180043c50`
- `0x180044c0c`
- `0x180054c38`
- `0x18007ca08`
- `0x18007cdcc`
- `0x180082b24`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007ce2b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007ce2b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007ce1d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007ce1d`

## pseudocode

```c
void __fastcall Windows::Internal::Spelling::RoamingDictionaryManager::~RoamingDictionaryManager(
        Windows::Internal::Spelling::RoamingDictionaryManager *this)
{
  PTP_TIMER *v2; // rdi
  std::_Ref_count_base *v3; // rcx

  *(_QWORD *)this = &Windows::Internal::Spelling::RoamingDictionaryManager::`vftable';
  *((_QWORD *)this + 1) = &Windows::Internal::Spelling::RoamingDictionaryManager::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::Internal::Spelling::RoamingDictionaryManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v2 = (PTP_TIMER *)((char *)this + 96);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager>::GetImpl'::`2'::impl)
    && *v2 )
  {
    SetThreadpoolTimer(*v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*v2, 1);
  }
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 20);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  std::unique_ptr<wil::details::cloud_store_watcher_t<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs> const,std::default_delete<wil::details::cloud_store_watcher_t<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs> const>>::~unique_ptr<wil::details::cloud_store_watcher_t<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs> const,std::default_delete<wil::details::cloud_store_watcher_t<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs> const>>((char *)this + 144);
  wil::cloud_store::~cloud_store((Windows::Internal::Spelling::RoamingDictionaryManager *)((char *)this + 104));
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>((char *)this + 96);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 88);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>((char *)this + 72);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Spelling::IRoamingDictionaryManager,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Spelling::IRoamingDictionaryManager,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18007cdcc  mov     [rsp+arg_0], rbx
0x18007cdd1  push    rdi
0x18007cdd2  sub     rsp, 20h
0x18007cdd6  mov     rbx, rcx
0x18007cdd9  lea     rax, ??_7RoamingDictionaryManager@Spelling@Internal@Windows@@6B@; const Windows::Internal::Spelling::RoamingDictionaryManager::`vftable'
0x18007cde0  mov     [rcx], rax
0x18007cde3  lea     rax, ??_7RoamingDictionaryManager@Spelling@Internal@Windows@@6BIWeakReferenceSource@@@; const Windows::Internal::Spelling::RoamingDictionaryManager::`vftable'{for `IWeakReferenceSource'}
0x18007cdea  mov     [rcx+8], rax
0x18007cdee  lea     rax, ??_7RoamingDictionaryManager@Spelling@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Internal::Spelling::RoamingDictionaryManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18007cdf5  mov     [rcx+10h], rax
0x18007cdf9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager> `wil::Feature<__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager>::GetImpl(void)'::`2'::impl
0x18007ce00  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager>::__private_IsEnabled(void)
0x18007ce05  lea     rdi, [rbx+60h]
0x18007ce09  test    al, al
0x18007ce0b  jz      short loc_18007CE31
0x18007ce0d  mov     rcx, [rdi]; pti
0x18007ce10  test    rcx, rcx
0x18007ce13  jz      short loc_18007CE31
0x18007ce15  xor     r9d, r9d; msWindowLength
0x18007ce18  xor     r8d, r8d; msPeriod
0x18007ce1b  xor     edx, edx; pftDueTime
0x18007ce1d  call    cs:__imp_SetThreadpoolTimer
0x18007ce23  mov     edx, 1; fCancelPendingCallbacks
0x18007ce28  mov     rcx, [rdi]; pti
0x18007ce2b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18007ce31  mov     rcx, [rbx+0A0h]; this
0x18007ce38  test    rcx, rcx
0x18007ce3b  jz      short loc_18007CE42
0x18007ce3d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007ce42  lea     rcx, [rbx+90h]
0x18007ce49  call    ??1?$unique_ptr@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@U?$default_delete@$$CBV?$cloud_store_watcher_t@UICloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@VCloudStoreDataWatcher@2345@VCloudStoreDataChangedEventArgs@2345@@details@wil@@@std@@@std@@QEAA@XZ; std::unique_ptr<wil::details::cloud_store_watcher_t<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs> const,std::default_delete<wil::details::cloud_store_watcher_t<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs> const>>::~unique_ptr<wil::details::cloud_store_watcher_t<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs> const,std::default_delete<wil::details::cloud_store_watcher_t<Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataWatcher,Windows::Internal::Storage::Cloud::CloudStoreDataChangedEventArgs> const>>(void)
0x18007ce4e  lea     rcx, [rbx+68h]; this
0x18007ce52  call    ??1cloud_store@wil@@QEAA@XZ; wil::cloud_store::~cloud_store(void)
0x18007ce57  mov     rcx, rdi
0x18007ce5a  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x18007ce5f  lea     rcx, [rbx+58h]
0x18007ce63  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007ce68  lea     rcx, [rbx+48h]
0x18007ce6c  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18007ce71  mov     rcx, rbx
0x18007ce74  mov     rbx, [rsp+28h+arg_0]
0x18007ce79  add     rsp, 20h
0x18007ce7d  pop     rdi
0x18007ce7e  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRoamingDictionaryManager@Spelling@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Spelling::IRoamingDictionaryManager,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Spelling::IRoamingDictionaryManager,Microsoft::WRL::FtmBase>(void)
```
