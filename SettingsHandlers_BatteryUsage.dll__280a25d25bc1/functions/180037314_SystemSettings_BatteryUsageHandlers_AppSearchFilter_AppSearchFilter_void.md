# SystemSettings::BatteryUsageHandlers::AppSearchFilter::~AppSearchFilter(void)

- ea: `0x180037314`
- end: `0x1800373ac`
- name: `??1AppSearchFilter@BatteryUsageHandlers@SystemSettings@@UEAA@XZ`
- size: `152`
- prototype: `void __fastcall(SystemSettings::BatteryUsageHandlers::AppSearchFilter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800373c0`

## callees

- `0x180010cdc`
- `0x180021e04`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003738e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003738e`

## pseudocode

```c
void __fastcall SystemSettings::BatteryUsageHandlers::AppSearchFilter::~AppSearchFilter(
        SystemSettings::BatteryUsageHandlers::AppSearchFilter *this)
{
  *(_QWORD *)this = &SystemSettings::BatteryUsageHandlers::AppSearchFilter::`vftable'{for `SystemSettings::DataModel::ISettingItem'};
  *((_QWORD *)this + 1) = &SystemSettings::BatteryUsageHandlers::AppList2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CListSetting>::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'};
  *((_QWORD *)this + 3) = &SystemSettings::BatteryUsageHandlers::EnergyUsageGraphDayView::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &SystemSettings::BatteryUsageHandlers::DisplayTimeBase2::`vftable'{for `SystemSettings::DataModel::ISettingItem2'};
  *((_QWORD *)this + 5) = &SystemSettings::BatteryUsageHandlers::AppSearchFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 29) = &SystemSettings::BatteryUsageHandlers::AppList::`vftable'{for `SystemSettings::DataModel::CSingletonHelper<unsigned long>::CNoCallback'};
  SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::Unregister(
    (__int64)&SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton,
    ((unsigned __int64)this + 232) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64),
    (__int64)this + 232);
  WindowsDeleteString(*((HSTRING *)this + 33));
  *((_QWORD *)this + 33) = 0;
  SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CListSetting>::~CGenericAsyncHelper<SystemSettings::DataModel::CListSetting>(this);
}

```

## disassembly

```asm
0x180037314  push    rbx
0x180037316  sub     rsp, 20h
0x18003731a  mov     rbx, rcx
0x18003731d  lea     rax, ??_7AppSearchFilter@BatteryUsageHandlers@SystemSettings@@6BISettingItem@DataModel@2@@; const SystemSettings::BatteryUsageHandlers::AppSearchFilter::`vftable'{for `SystemSettings::DataModel::ISettingItem'}
0x180037324  mov     [rcx], rax
0x180037327  lea     rax, ??_7AppList2@BatteryUsageHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UISettingItemTelemetry@DataModel@SystemSettings@@UISettingsAppNotification@67@UISettingItem2@67@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::BatteryUsageHandlers::AppList2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x18003732e  mov     [rcx+8], rax
0x180037332  lea     rax, ??_7?$CGenericAsyncHelper@VCListSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@6BISettingItemTelemetry@12@@; const SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CListSetting>::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'}
0x180037339  mov     [rcx+10h], rax
0x18003733d  lea     rax, ??_7EnergyUsageGraphDayView@BatteryUsageHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISettingsAppNotification@DataModel@SystemSettings@@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::BatteryUsageHandlers::EnergyUsageGraphDayView::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x180037344  mov     [rcx+18h], rax
0x180037348  lea     rax, ??_7DisplayTimeBase2@BatteryUsageHandlers@SystemSettings@@6BISettingItem2@DataModel@2@@; const SystemSettings::BatteryUsageHandlers::DisplayTimeBase2::`vftable'{for `SystemSettings::DataModel::ISettingItem2'}
0x18003734f  mov     [rcx+20h], rax
0x180037353  lea     rax, ??_7AppSearchFilter@BatteryUsageHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const SystemSettings::BatteryUsageHandlers::AppSearchFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003735a  mov     [rcx+28h], rax
0x18003735e  lea     r8, [rcx+0E8h]
0x180037365  lea     rax, ??_7AppList@BatteryUsageHandlers@SystemSettings@@6BCNoCallback@?$CSingletonHelper@K@DataModel@2@@; const SystemSettings::BatteryUsageHandlers::AppList::`vftable'{for `SystemSettings::DataModel::CSingletonHelper<ulong>::CNoCallback'}
0x18003736c  mov     [r8], rax
0x18003736f  mov     rax, rcx
0x180037372  neg     rax
0x180037375  sbb     rdx, rdx
0x180037378  and     rdx, r8
0x18003737b  lea     rcx, ?g_UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@3VUsageDataSingleton@12@A; SystemSettings::BatteryUsageHandlers::UsageDataSingleton SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton
0x180037382  call    ?Unregister@?$CSingletonHelper@W4BatteryGraphNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::Unregister(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *)
0x180037387  mov     rcx, [rbx+108h]; string
0x18003738e  call    cs:__imp_WindowsDeleteString
0x180037394  mov     qword ptr [rbx+108h], 0
0x18003739f  mov     rcx, rbx; this
0x1800373a2  add     rsp, 20h
0x1800373a6  pop     rbx
0x1800373a7  jmp     ??1?$CGenericAsyncHelper@VCListSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CListSetting>::~CGenericAsyncHelper<SystemSettings::DataModel::CListSetting>(void)
```
