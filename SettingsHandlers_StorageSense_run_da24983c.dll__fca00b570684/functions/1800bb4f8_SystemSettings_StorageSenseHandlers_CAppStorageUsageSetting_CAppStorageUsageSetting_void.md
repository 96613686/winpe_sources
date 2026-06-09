# SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::~CAppStorageUsageSetting(void)

- ea: `0x1800bb4f8`
- end: `0x1800bb5d9`
- name: `??1CAppStorageUsageSetting@StorageSenseHandlers@SystemSettings@@UEAA@XZ`
- size: `225`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800bb6f0`

## callees

- `0x180017d04`
- `0x1800343ec`
- `0x1800bb400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800bb57e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800bb57e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb58b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb5a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb5bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb58b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb5a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb5bb`

## pseudocode

```c
void __fastcall SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::~CAppStorageUsageSetting(
        SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting *this)
{
  *(_QWORD *)this = &SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::`vftable'{for `SystemSettings::DataModel::ISettingItem'};
  *((_QWORD *)this + 1) = &SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'};
  *((_QWORD *)this + 3) = &SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::`vftable'{for `SystemSettings::DataModel::ISettingItem2'};
  *((_QWORD *)this + 5) = &SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 27) = &SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::`vftable';
  SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::RecommendationNotificationBase> const &>::Unregister(
    &SystemSettings::StorageSenseHandlers::g_appRefreshSingleton,
    ((unsigned __int64)this + 216) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>((char *)this + 360);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 8);
  WindowsDeleteString(*((HSTRING *)this + 33));
  *((_QWORD *)this + 33) = 0;
  WindowsDeleteString(*((HSTRING *)this + 32));
  *((_QWORD *)this + 32) = 0;
  WindowsDeleteString(*((HSTRING *)this + 31));
  *((_QWORD *)this + 31) = 0;
  SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::~CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>(this);
}

```

## disassembly

```asm
0x1800bb4f8  push    rbx
0x1800bb4fa  sub     rsp, 20h
0x1800bb4fe  mov     rbx, rcx
0x1800bb501  lea     rax, ??_7CAppStorageUsageSetting@StorageSenseHandlers@SystemSettings@@6BISettingItem@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::`vftable'{for `SystemSettings::DataModel::ISettingItem'}
0x1800bb508  mov     [rcx], rax
0x1800bb50b  lea     rax, ??_7CAppStorageUsageSetting@StorageSenseHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UISettingItemTelemetry@DataModel@SystemSettings@@UISettingsAppNotification@67@UISettingItem2@67@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x1800bb512  mov     [rcx+8], rax
0x1800bb516  lea     rax, ??_7CAppStorageUsageSetting@StorageSenseHandlers@SystemSettings@@6BISettingItemTelemetry@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'}
0x1800bb51d  mov     [rcx+10h], rax
0x1800bb521  lea     rax, ??_7CAppStorageUsageSetting@StorageSenseHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISettingsAppNotification@DataModel@SystemSettings@@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x1800bb528  mov     [rcx+18h], rax
0x1800bb52c  lea     rax, ??_7CAppStorageUsageSetting@StorageSenseHandlers@SystemSettings@@6BISettingItem2@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::`vftable'{for `SystemSettings::DataModel::ISettingItem2'}
0x1800bb533  mov     [rcx+20h], rax
0x1800bb537  lea     rax, ??_7CAppStorageUsageSetting@StorageSenseHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800bb53e  mov     [rcx+28h], rax
0x1800bb542  lea     r8, [rcx+0D8h]
0x1800bb549  lea     rax, ??_7CAppStorageUsageSetting@StorageSenseHandlers@SystemSettings@@6B@; const SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::`vftable'
0x1800bb550  mov     [r8], rax
0x1800bb553  mov     rax, rcx
0x1800bb556  neg     rax
0x1800bb559  sbb     rdx, rdx
0x1800bb55c  and     rdx, r8
0x1800bb55f  lea     rcx, ?g_appRefreshSingleton@StorageSenseHandlers@SystemSettings@@3VCAppSizeRefreshSingleton@12@A; SystemSettings::StorageSenseHandlers::CAppSizeRefreshSingleton SystemSettings::StorageSenseHandlers::g_appRefreshSingleton
0x1800bb566  call    ?Unregister@?$CSingletonHelper@AEBV?$shared_ptr@URecommendationNotificationBase@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z; SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::RecommendationNotificationBase> const &>::Unregister(SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::RecommendationNotificationBase> const &>::CCallback *)
0x1800bb56b  lea     rcx, [rbx+168h]
0x1800bb572  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x1800bb577  lea     rcx, [rbx+140h]; lpCriticalSection
0x1800bb57e  call    cs:__imp_DeleteCriticalSection
0x1800bb584  mov     rcx, [rbx+108h]; string
0x1800bb58b  call    cs:__imp_WindowsDeleteString
0x1800bb591  mov     qword ptr [rbx+108h], 0
0x1800bb59c  mov     rcx, [rbx+100h]; string
0x1800bb5a3  call    cs:__imp_WindowsDeleteString
0x1800bb5a9  mov     qword ptr [rbx+100h], 0
0x1800bb5b4  mov     rcx, [rbx+0F8h]; string
0x1800bb5bb  call    cs:__imp_WindowsDeleteString
0x1800bb5c1  mov     qword ptr [rbx+0F8h], 0
0x1800bb5cc  mov     rcx, rbx; this
0x1800bb5cf  add     rsp, 20h
0x1800bb5d3  pop     rbx
0x1800bb5d4  jmp     ??1?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAUIUser@System@Windows@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::~CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>(void)
```
