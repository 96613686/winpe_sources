# SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverIndividualBatteryCapacity::~CBatterySaverIndividualBatteryCapacity(void)

- ea: `0x18001a75c`
- end: `0x18001a817`
- name: `??1CBatterySaverIndividualBatteryCapacity@BatterySaverOneCoreDataModel@SystemSettings@@UEAA@XZ`
- size: `187`
- prototype: `void __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverIndividualBatteryCapacity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b930`

## callees

- `0x180019e94`
- `0x18001a75c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a7f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a7f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverIndividualBatteryCapacity::~CBatterySaverIndividualBatteryCapacity(
        SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverIndividualBatteryCapacity *this)
{
  volatile signed __int32 *v2; // rdi

  *(_QWORD *)this = &SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverIndividualBatteryCapacity::`vftable'{for `SystemSettings::DataModel::ISettingItem'};
  *((_QWORD *)this + 1) = &SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CListSetting>::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'};
  *((_QWORD *)this + 3) = &SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverIndividualBatteryCapacity::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::`vftable'{for `SystemSettings::DataModel::ISettingItem2'};
  *((_QWORD *)this + 5) = &SystemSettings::DataModel::CDisplayStringSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 31);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  WindowsDeleteString(*((HSTRING *)this + 29));
  *((_QWORD *)this + 29) = 0;
  SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::~CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>(this);
}

```

## disassembly

```asm
0x18001a75c  mov     [rsp+arg_0], rbx
0x18001a761  push    rdi
0x18001a762  sub     rsp, 20h
0x18001a766  lea     rax, ??_7CBatterySaverIndividualBatteryCapacity@BatterySaverOneCoreDataModel@SystemSettings@@6BISettingItem@DataModel@2@@; const SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverIndividualBatteryCapacity::`vftable'{for `SystemSettings::DataModel::ISettingItem'}
0x18001a76d  mov     rbx, rcx
0x18001a770  mov     [rcx], rax
0x18001a773  lea     rax, ??_7CBatterySaverSettingsThresholdValue@BatterySaverOneCoreDataModel@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UISettingItemTelemetry@DataModel@SystemSettings@@UISettingsAppNotification@67@UISettingItem2@67@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x18001a77a  mov     [rcx+8], rax
0x18001a77e  lea     rax, ??_7?$CGenericAsyncHelper@VCListSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@6BISettingItemTelemetry@12@@; const SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CListSetting>::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'}
0x18001a785  mov     [rcx+10h], rax
0x18001a789  lea     rax, ??_7CBatterySaverIndividualBatteryCapacity@BatterySaverOneCoreDataModel@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISettingsAppNotification@DataModel@SystemSettings@@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverIndividualBatteryCapacity::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x18001a790  mov     [rcx+18h], rax
0x18001a794  lea     rax, ??_7CBatterySaverSettingsThresholdValue@BatterySaverOneCoreDataModel@SystemSettings@@6BISettingItem2@DataModel@2@@; const SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::`vftable'{for `SystemSettings::DataModel::ISettingItem2'}
0x18001a79b  mov     [rcx+20h], rax
0x18001a79f  lea     rax, ??_7CDisplayStringSetting@DataModel@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const SystemSettings::DataModel::CDisplayStringSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001a7a6  mov     [rcx+28h], rax
0x18001a7aa  mov     rdi, [rcx+0F8h]
0x18001a7b1  test    rdi, rdi
0x18001a7b4  jz      short loc_18001A7ED
0x18001a7b6  or      eax, 0FFFFFFFFh
0x18001a7b9  lock xadd [rdi+8], eax
0x18001a7be  cmp     eax, 1
0x18001a7c1  jnz     short loc_18001A7ED
0x18001a7c3  mov     rax, [rdi]
0x18001a7c6  mov     rcx, rdi
0x18001a7c9  mov     rax, [rax]
0x18001a7cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7d1  or      eax, 0FFFFFFFFh
0x18001a7d4  lock xadd [rdi+0Ch], eax
0x18001a7d9  cmp     eax, 1
0x18001a7dc  jnz     short loc_18001A7ED
0x18001a7de  mov     rax, [rdi]
0x18001a7e1  mov     rcx, rdi
0x18001a7e4  mov     rax, [rax+8]
0x18001a7e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7ed  mov     rcx, [rbx+0E8h]; string
0x18001a7f4  call    cs:__imp_WindowsDeleteString
0x18001a7fa  mov     rcx, rbx; this
0x18001a7fd  mov     qword ptr [rbx+0E8h], 0
0x18001a808  mov     rbx, [rsp+28h+arg_0]
0x18001a80d  add     rsp, 20h
0x18001a811  pop     rdi
0x18001a812  jmp     ??1?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::~CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>(void)
```
