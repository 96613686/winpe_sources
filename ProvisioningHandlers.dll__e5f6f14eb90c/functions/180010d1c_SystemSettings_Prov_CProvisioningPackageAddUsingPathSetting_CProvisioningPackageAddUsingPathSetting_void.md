# SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting::~CProvisioningPackageAddUsingPathSetting(void)

- ea: `0x180010d1c`
- end: `0x180010d91`
- name: `??1CProvisioningPackageAddUsingPathSetting@Prov@SystemSettings@@UEAA@XZ`
- size: `117`
- prototype: `void __fastcall(SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011cf0`

## callees

- `0x18001032c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010d6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010d6d`

## pseudocode

```c
void __fastcall SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting::~CProvisioningPackageAddUsingPathSetting(
        SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting *this)
{
  *(_QWORD *)this = &SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting::`vftable'{for `SystemSettings::DataModel::ISettingItem'};
  *((_QWORD *)this + 1) = &SystemSettings::Prov::CProvisioningDisplayStringSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'};
  *((_QWORD *)this + 3) = &SystemSettings::Prov::CProvisioningPackageAddSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &SystemSettings::Prov::CProvisioningPackageAddSetting::`vftable'{for `SystemSettings::DataModel::ISettingItem2'};
  *((_QWORD *)this + 5) = &SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CListSetting>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  WindowsDeleteString(*((HSTRING *)this + 27));
  *((_QWORD *)this + 27) = 0;
  SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::~CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>(this);
}

```

## disassembly

```asm
0x180010d1c  push    rbx
0x180010d1e  sub     rsp, 20h
0x180010d22  lea     rax, ??_7CProvisioningPackageAddUsingPathSetting@Prov@SystemSettings@@6BISettingItem@DataModel@2@@; const SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting::`vftable'{for `SystemSettings::DataModel::ISettingItem'}
0x180010d29  mov     rbx, rcx
0x180010d2c  mov     [rcx], rax
0x180010d2f  lea     rax, ??_7CProvisioningDisplayStringSetting@Prov@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UISettingItemTelemetry@DataModel@SystemSettings@@UISettingsAppNotification@67@UISettingItem2@67@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::Prov::CProvisioningDisplayStringSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x180010d36  mov     [rcx+8], rax
0x180010d3a  lea     rax, ??_7CProvisioningPackageAddUsingPathSetting@Prov@SystemSettings@@6BISettingItemTelemetry@DataModel@2@@; const SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'}
0x180010d41  mov     [rcx+10h], rax
0x180010d45  lea     rax, ??_7CProvisioningPackageAddSetting@Prov@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISettingsAppNotification@DataModel@SystemSettings@@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::Prov::CProvisioningPackageAddSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x180010d4c  mov     [rcx+18h], rax
0x180010d50  lea     rax, ??_7CProvisioningPackageAddSetting@Prov@SystemSettings@@6BISettingItem2@DataModel@2@@; const SystemSettings::Prov::CProvisioningPackageAddSetting::`vftable'{for `SystemSettings::DataModel::ISettingItem2'}
0x180010d57  mov     [rcx+20h], rax
0x180010d5b  lea     rax, ??_7?$CGetValueAsyncHelper@VCListSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CListSetting>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180010d62  mov     [rcx+28h], rax
0x180010d66  mov     rcx, [rcx+0D8h]; string
0x180010d6d  call    cs:__imp_WindowsDeleteString
0x180010d74  nop     dword ptr [rax+rax+00h]
0x180010d79  mov     rcx, rbx; this
0x180010d7c  mov     qword ptr [rbx+0D8h], 0
0x180010d87  add     rsp, 20h
0x180010d8b  pop     rbx
0x180010d8c  jmp     ??1?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::~CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>(void)
```
