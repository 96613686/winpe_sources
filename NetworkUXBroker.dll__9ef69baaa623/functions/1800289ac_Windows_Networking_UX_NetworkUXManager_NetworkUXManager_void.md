# Windows::Networking::UX::NetworkUXManager::~NetworkUXManager(void)

- ea: `0x1800289ac`
- end: `0x180028aca`
- name: `??1NetworkUXManager@UX@Networking@Windows@@UEAA@XZ`
- size: `286`
- prototype: `void __fastcall(Windows::Networking::UX::NetworkUXManager *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180029e80`

## callees

- `0x18000955c`
- `0x18000b638`
- `0x180011a44`
- `0x1800249a0`
- `0x180028080`
- `0x1800281b8`
- `0x180028294`
- `0x180028588`
- `0x1800289ac`
- `0x18002d5f0`
- `0x180031278`
- `0x180032c90`
- `0x180033ba8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028a7e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028a7e`

## pseudocode

```c
void __fastcall Windows::Networking::UX::NetworkUXManager::~NetworkUXManager(
        Windows::Networking::UX::NetworkUXManager *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &Windows::Networking::UX::NetworkUXManager::`vftable'{for `Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Networking::UX::INetworkUXManager,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 1) = &Windows::Networking::UX::NetworkUXManager::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::Networking::UX::NetworkUXManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 8) = &Windows::Networking::UX::NetworkUXManager::`vftable'{for `CServiceStatusListener'};
  Windows::Networking::UX::NetworkUXManager::_Cleanup(this);
  std::_Optional_destruct_base<tip2::tip_test<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>>,0>::~_Optional_destruct_base<tip2::tip_test<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>>,0>((char *)this + 1456);
  *((_QWORD *)this + 112) = &CServiceMonitor::`vftable';
  CServiceMonitor::Stop((Windows::Networking::UX::NetworkUXManager *)((char *)this + 896));
  *((_QWORD *)this + 42) = &CServiceMonitor::`vftable';
  CServiceMonitor::Stop((Windows::Networking::UX::NetworkUXManager *)((char *)this + 336));
  Microsoft::WRL::ComPtr<Windows::Networking::UX::RadioManagerNotifySink>::InternalRelease((char *)this + 312);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 304);
  Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::~ComPtr<Microsoft::WRL::Details::EventTargetArray>((__int64 *)this + 35);
  Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::~ComPtr<Microsoft::WRL::Details::EventTargetArray>((__int64 *)this + 32);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 248);
  __1___Hash_V___Umap_traits_W4NetworkMediaType_UX_Networking_Windows__V__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__V___Uhash_compare_W4NetworkMediaType_UX_Networking_Windows__U__hash_W4NetworkMediaType_UX_Networking_Windows___std__U__equal_to_W4NetworkMediaType_UX_Networking_Windows___6__std__V__allocator_U__pair___CBW4NetworkMediaType_UX_Networking_Windows__V__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___std___8__0A__std___std__QEAA_XZ((__int64)this + 176);
  std::vector<enum Windows::Networking::UX::NetworkMediaType>::_Tidy((char *)this + 152);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((char *)this + 144);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v2 = *((_QWORD *)this + 9);
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Windows::Networking::UX::MediaManagerInstance>>>(
      v2,
      *((_QWORD *)this + 10));
    std::_Deallocate<16>(*((void **)this + 9), (*((_QWORD *)this + 11) - *((_QWORD *)this + 9)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 9) = 0;
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 11) = 0;
  }
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IAdapter,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IAdapter,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x1800289ac  mov     [rsp+arg_0], rbx
0x1800289b1  push    rdi
0x1800289b2  sub     rsp, 20h
0x1800289b6  mov     rbx, rcx
0x1800289b9  lea     rax, ??_7NetworkUXManager@UX@Networking@Windows@@6B?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UINetworkUXManager@UX@Networking@Windows@@VFtmBase@23@@WRL@Microsoft@@@; const Windows::Networking::UX::NetworkUXManager::`vftable'{for `Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Networking::UX::INetworkUXManager,Microsoft::WRL::FtmBase>'}
0x1800289c0  mov     [rcx], rax
0x1800289c3  lea     rax, ??_7NetworkUXManager@UX@Networking@Windows@@6BIWeakReferenceSource@@@; const Windows::Networking::UX::NetworkUXManager::`vftable'{for `IWeakReferenceSource'}
0x1800289ca  mov     [rcx+8], rax
0x1800289ce  lea     rax, ??_7NetworkUXManager@UX@Networking@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::NetworkUXManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800289d5  mov     [rcx+10h], rax
0x1800289d9  lea     rax, ??_7NetworkUXManager@UX@Networking@Windows@@6BCServiceStatusListener@@@; const Windows::Networking::UX::NetworkUXManager::`vftable'{for `CServiceStatusListener'}
0x1800289e0  mov     [rcx+40h], rax
0x1800289e4  call    ?_Cleanup@NetworkUXManager@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::NetworkUXManager::_Cleanup(void)
0x1800289e9  lea     rcx, [rbx+5B0h]
0x1800289f0  call    ??1?$_Optional_destruct_base@V?$tip_test@V?$merged_data@U_tip_NetworkUXManagerInitializationTest@@U1@@details@tip2@@@tip2@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<tip2::tip_test<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>>,0>::~_Optional_destruct_base<tip2::tip_test<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>>,0>(void)
0x1800289f5  lea     rcx, [rbx+380h]; this
0x1800289fc  lea     rdi, ??_7CServiceMonitor@@6B@; const CServiceMonitor::`vftable'
0x180028a03  mov     [rcx], rdi
0x180028a06  call    ?Stop@CServiceMonitor@@QEAAJXZ; CServiceMonitor::Stop(void)
0x180028a0b  lea     rcx, [rbx+150h]; this
0x180028a12  mov     [rcx], rdi
0x180028a15  call    ?Stop@CServiceMonitor@@QEAAJXZ; CServiceMonitor::Stop(void)
0x180028a1a  lea     rcx, [rbx+138h]
0x180028a21  call    ?InternalRelease@?$ComPtr@VRadioManagerNotifySink@UX@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::RadioManagerNotifySink>::InternalRelease(void)
0x180028a26  lea     rcx, [rbx+130h]
0x180028a2d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028a32  lea     rcx, [rbx+118h]
0x180028a39  call    ??1?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::~ComPtr<Microsoft::WRL::Details::EventTargetArray>(void)
0x180028a3e  lea     rcx, [rbx+100h]
0x180028a45  call    ??1?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::~ComPtr<Microsoft::WRL::Details::EventTargetArray>(void)
0x180028a4a  lea     rcx, [rbx+0F8h]
0x180028a51  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028a56  lea     rcx, [rbx+0B0h]
0x180028a5d  call    ??1?$_Hash@V?$_Umap_traits@W4NetworkMediaType@UX@Networking@Windows@@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@V?$_Uhash_compare@W4NetworkMediaType@UX@Networking@Windows@@U?$hash@W4NetworkMediaType@UX@Networking@Windows@@@std@@U?$equal_to@W4NetworkMediaType@UX@Networking@Windows@@@6@@std@@V?$allocator@U?$pair@$$CBW4NetworkMediaType@UX@Networking@Windows@@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@@8@$0A@@std@@@std@@QEAA@XZ
0x180028a62  lea     rcx, [rbx+98h]
0x180028a69  call    ?_Tidy@?$vector@W4NetworkMediaType@UX@Networking@Windows@@V?$allocator@W4NetworkMediaType@UX@Networking@Windows@@@std@@@std@@AEAAXXZ; std::vector<Windows::Networking::UX::NetworkMediaType>::_Tidy(void)
0x180028a6e  lea     rcx, [rbx+90h]
0x180028a75  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180028a7a  lea     rcx, [rbx+68h]; lpCriticalSection
0x180028a7e  call    cs:__imp_DeleteCriticalSection
0x180028a84  mov     rcx, [rbx+48h]
0x180028a88  xor     edi, edi
0x180028a8a  test    rcx, rcx
0x180028a8d  jz      short loc_180028AB8
0x180028a8f  mov     rdx, [rbx+50h]
0x180028a93  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@VMediaManagerInstance@UX@Networking@Windows@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@VMediaManagerInstance@UX@Networking@Windows@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@VMediaManagerInstance@UX@Networking@Windows@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Windows::Networking::UX::MediaManagerInstance>>>(Microsoft::WRL::ComPtr<Windows::Networking::UX::MediaManagerInstance> *,Microsoft::WRL::ComPtr<Windows::Networking::UX::MediaManagerInstance> * const,std::allocator<Microsoft::WRL::ComPtr<Windows::Networking::UX::MediaManagerInstance>> &)
0x180028a98  mov     rcx, [rbx+48h]
0x180028a9c  mov     rdx, [rbx+58h]
0x180028aa0  sub     rdx, rcx
0x180028aa3  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180028aa7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180028aac  mov     [rbx+48h], rdi
0x180028ab0  mov     [rbx+50h], rdi
0x180028ab4  mov     [rbx+58h], rdi
0x180028ab8  mov     rcx, rbx
0x180028abb  mov     rbx, [rsp+28h+arg_0]
0x180028ac0  add     rsp, 20h
0x180028ac4  pop     rdi
0x180028ac5  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAdapter@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IAdapter,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IAdapter,Microsoft::WRL::FtmBase>(void)
```
