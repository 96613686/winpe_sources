# SystemSettings::StorageSenseHandlers::CAppSizesFilter::~CAppSizesFilter(void)

- ea: `0x18003b850`
- end: `0x18003b95c`
- name: `??1CAppSizesFilter@StorageSenseHandlers@SystemSettings@@UEAA@XZ`
- size: `268`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::CAppSizesFilter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003cc30`

## callees

- `0x180017d04`
- `0x1800465f8`
- `0x1800467c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b905`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b91b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b93d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b905`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b91b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b93d`

## pseudocode

```c
void __fastcall SystemSettings::StorageSenseHandlers::CAppSizesFilter::~CAppSizesFilter(
        SystemSettings::StorageSenseHandlers::CAppSizesFilter *this)
{
  unsigned __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `SystemSettings::DataModel::ISettingItem'};
  *((_QWORD *)this + 1) = &SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'};
  *((_QWORD *)this + 3) = &SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `SystemSettings::DataModel::ISettingItem2'};
  *((_QWORD *)this + 5) = &SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 26) = &SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::CNoCallback'};
  *((_QWORD *)this + 30) = &SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `SystemSettings::StorageSenseHandlers::CAppEnumerationMode'};
  v2 = (unsigned __int64)this + 264;
  *(_QWORD *)v2 = &SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::IsUpdatingNotification *>::CCallback'};
  *((_QWORD *)this + 37) = &SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::TotalVisibleAppNotification *>::CCallback'};
  SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::IsUpdatingNotification *>::Unregister(
    v2,
    v2 & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
  SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::TotalVisibleAppNotification *>::Unregister(
    v3,
    ((unsigned __int64)this + 296) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
  WindowsDeleteString(*((HSTRING *)this + 42));
  *((_QWORD *)this + 42) = 0;
  WindowsDeleteString(*((HSTRING *)this + 41));
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 30) = &SystemSettings::StorageSenseHandlers::CAppEnumerationMode::`vftable';
  WindowsDeleteString(*((HSTRING *)this + 31));
  *((_QWORD *)this + 31) = 0;
  SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::~CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>(this);
}

```

## disassembly

```asm
0x18003b850  mov     [rsp+arg_0], rbx
0x18003b855  push    rdi
0x18003b856  sub     rsp, 20h
0x18003b85a  mov     rdi, rcx
0x18003b85d  lea     rax, ??_7CAppSizesFilter@StorageSenseHandlers@SystemSettings@@6BISettingItem@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `SystemSettings::DataModel::ISettingItem'}
0x18003b864  mov     [rcx], rax
0x18003b867  lea     rax, ??_7CAppSizesFilter@StorageSenseHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UISettingItemTelemetry@DataModel@SystemSettings@@UISettingsAppNotification@67@UISettingItem2@67@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x18003b86e  mov     [rcx+8], rax
0x18003b872  lea     rax, ??_7CAppSizesFilter@StorageSenseHandlers@SystemSettings@@6BISettingItemTelemetry@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'}
0x18003b879  mov     [rcx+10h], rax
0x18003b87d  lea     rax, ??_7CAppSizesFilter@StorageSenseHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISettingsAppNotification@DataModel@SystemSettings@@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x18003b884  mov     [rcx+18h], rax
0x18003b888  lea     rax, ??_7CAppSizesFilter@StorageSenseHandlers@SystemSettings@@6BISettingItem2@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `SystemSettings::DataModel::ISettingItem2'}
0x18003b88f  mov     [rcx+20h], rax
0x18003b893  lea     rax, ??_7CAppSizesFilter@StorageSenseHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003b89a  mov     [rcx+28h], rax
0x18003b89e  lea     rax, ??_7CAppSizesFilter@StorageSenseHandlers@SystemSettings@@6BCNoCallback@?$CSingletonHelper@PEAUAppListChangeNotification@StorageSenseHandlers@SystemSettings@@@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::CNoCallback'}
0x18003b8a5  mov     [rcx+0D0h], rax
0x18003b8ac  lea     rax, ??_7CAppSizesFilter@StorageSenseHandlers@SystemSettings@@6BCAppEnumerationMode@12@@; const SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `SystemSettings::StorageSenseHandlers::CAppEnumerationMode'}
0x18003b8b3  mov     [rcx+0F0h], rax
0x18003b8ba  add     rcx, 108h
0x18003b8c1  lea     rax, ??_7CAppSizesFilter@StorageSenseHandlers@SystemSettings@@6BCCallback@?$CSingletonHelper@PEAUIsUpdatingNotification@StorageSenseHandlers@SystemSettings@@@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::IsUpdatingNotification *>::CCallback'}
0x18003b8c8  mov     [rcx], rax
0x18003b8cb  lea     rbx, [rdi+128h]
0x18003b8d2  lea     rax, ??_7CAppSizesFilter@StorageSenseHandlers@SystemSettings@@6BCCallback@?$CSingletonHelper@PEAUTotalVisibleAppNotification@StorageSenseHandlers@SystemSettings@@@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppSizesFilter::`vftable'{for `SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::TotalVisibleAppNotification *>::CCallback'}
0x18003b8d9  mov     [rbx], rax
0x18003b8dc  mov     rax, rdi
0x18003b8df  neg     rax
0x18003b8e2  sbb     rdx, rdx
0x18003b8e5  and     rdx, rcx
0x18003b8e8  call    ?Unregister@?$CSingletonHelper@PEAUIsUpdatingNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::IsUpdatingNotification *>::Unregister(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::IsUpdatingNotification *>::CCallback *)
0x18003b8ed  mov     rax, rdi
0x18003b8f0  neg     rax
0x18003b8f3  sbb     rdx, rdx
0x18003b8f6  and     rdx, rbx
0x18003b8f9  call    ?Unregister@?$CSingletonHelper@PEAUTotalVisibleAppNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::TotalVisibleAppNotification *>::Unregister(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::TotalVisibleAppNotification *>::CCallback *)
0x18003b8fe  mov     rcx, [rdi+150h]; string
0x18003b905  call    cs:__imp_WindowsDeleteString
0x18003b90b  xor     ebx, ebx
0x18003b90d  mov     [rdi+150h], rbx
0x18003b914  mov     rcx, [rdi+148h]; string
0x18003b91b  call    cs:__imp_WindowsDeleteString
0x18003b921  mov     [rdi+148h], rbx
0x18003b928  lea     rax, ??_7CAppEnumerationMode@StorageSenseHandlers@SystemSettings@@6B@; const SystemSettings::StorageSenseHandlers::CAppEnumerationMode::`vftable'
0x18003b92f  mov     [rdi+0F0h], rax
0x18003b936  mov     rcx, [rdi+0F8h]; string
0x18003b93d  call    cs:__imp_WindowsDeleteString
0x18003b943  mov     [rdi+0F8h], rbx
0x18003b94a  mov     rcx, rdi; this
0x18003b94d  mov     rbx, [rsp+28h+arg_0]
0x18003b952  add     rsp, 20h
0x18003b956  pop     rdi
0x18003b957  jmp     ??1?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAUIUser@System@Windows@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::~CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>(void)
```
