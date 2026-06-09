# SystemSettings::BatteryUsageHandlers::OptionComboboxItem::~OptionComboboxItem(void)

- ea: `0x180033dc0`
- end: `0x180033e47`
- name: `??1OptionComboboxItem@BatteryUsageHandlers@SystemSettings@@UEAA@XZ`
- size: `135`
- prototype: `void __fastcall(SystemSettings::BatteryUsageHandlers::OptionComboboxItem *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033e50`

## callees

- `0x18000dda4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033e11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033e29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033e11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033e29`

## pseudocode

```c
void __fastcall SystemSettings::BatteryUsageHandlers::OptionComboboxItem::~OptionComboboxItem(
        SystemSettings::BatteryUsageHandlers::OptionComboboxItem *this)
{
  *(_QWORD *)this = &SystemSettings::BatteryUsageHandlers::OptionComboboxItem::`vftable'{for `SystemSettings::DataModel::ISettingItem'};
  *((_QWORD *)this + 1) = &SystemSettings::BatteryUsageHandlers::AppList2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CListSetting>::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'};
  *((_QWORD *)this + 3) = &SystemSettings::BatteryUsageHandlers::EnergyUsageGraphDayView::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &SystemSettings::BatteryUsageHandlers::DisplayTimeBase2::`vftable'{for `SystemSettings::DataModel::ISettingItem2'};
  *((_QWORD *)this + 5) = &SystemSettings::BatteryUsageHandlers::AppSearchFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  WindowsDeleteString(*((HSTRING *)this + 30));
  *((_QWORD *)this + 30) = 0;
  WindowsDeleteString(*((HSTRING *)this + 29));
  *((_QWORD *)this + 29) = 0;
  SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::~CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>(this);
}

```

## disassembly

```asm
0x180033dc0  push    rbx
0x180033dc2  sub     rsp, 20h
0x180033dc6  lea     rax, ??_7OptionComboboxItem@BatteryUsageHandlers@SystemSettings@@6BISettingItem@DataModel@2@@; const SystemSettings::BatteryUsageHandlers::OptionComboboxItem::`vftable'{for `SystemSettings::DataModel::ISettingItem'}
0x180033dcd  mov     rbx, rcx
0x180033dd0  mov     [rcx], rax
0x180033dd3  lea     rax, ??_7AppList2@BatteryUsageHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UISettingItemTelemetry@DataModel@SystemSettings@@UISettingsAppNotification@67@UISettingItem2@67@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::BatteryUsageHandlers::AppList2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x180033dda  mov     [rcx+8], rax
0x180033dde  lea     rax, ??_7?$CGenericAsyncHelper@VCListSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@6BISettingItemTelemetry@12@@; const SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CListSetting>::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'}
0x180033de5  mov     [rcx+10h], rax
0x180033de9  lea     rax, ??_7EnergyUsageGraphDayView@BatteryUsageHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISettingsAppNotification@DataModel@SystemSettings@@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::BatteryUsageHandlers::EnergyUsageGraphDayView::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x180033df0  mov     [rcx+18h], rax
0x180033df4  lea     rax, ??_7DisplayTimeBase2@BatteryUsageHandlers@SystemSettings@@6BISettingItem2@DataModel@2@@; const SystemSettings::BatteryUsageHandlers::DisplayTimeBase2::`vftable'{for `SystemSettings::DataModel::ISettingItem2'}
0x180033dfb  mov     [rcx+20h], rax
0x180033dff  lea     rax, ??_7AppSearchFilter@BatteryUsageHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const SystemSettings::BatteryUsageHandlers::AppSearchFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180033e06  mov     [rcx+28h], rax
0x180033e0a  mov     rcx, [rcx+0F0h]; string
0x180033e11  call    cs:__imp_WindowsDeleteString
0x180033e17  mov     qword ptr [rbx+0F0h], 0
0x180033e22  mov     rcx, [rbx+0E8h]; string
0x180033e29  call    cs:__imp_WindowsDeleteString
0x180033e2f  mov     rcx, rbx; this
0x180033e32  mov     qword ptr [rbx+0E8h], 0
0x180033e3d  add     rsp, 20h
0x180033e41  pop     rbx
0x180033e42  jmp     ??1?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::~CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>(void)
```
