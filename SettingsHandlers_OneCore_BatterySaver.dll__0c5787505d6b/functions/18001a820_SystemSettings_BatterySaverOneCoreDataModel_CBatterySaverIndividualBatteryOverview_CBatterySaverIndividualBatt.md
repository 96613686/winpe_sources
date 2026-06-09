# SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverIndividualBatteryOverview::~CBatterySaverIndividualBatteryOverview(void)

- ea: `0x18001a820`
- end: `0x18001a8db`
- name: `??1CBatterySaverIndividualBatteryOverview@BatterySaverOneCoreDataModel@SystemSettings@@UEAA@XZ`
- size: `187`
- prototype: `void __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverIndividualBatteryOverview *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b970`

## callees

- `0x180019e94`
- `0x18001a820`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a8b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a8b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverIndividualBatteryOverview::~CBatterySaverIndividualBatteryOverview(
        SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverIndividualBatteryOverview *this)
{
  volatile signed __int32 *v2; // rdi

  *(_QWORD *)this = &SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverIndividualBatteryOverview::`vftable'{for `SystemSettings::DataModel::ISettingItem'};
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
0x18001a820  mov     [rsp+arg_0], rbx
0x18001a825  push    rdi
0x18001a826  sub     rsp, 20h
0x18001a82a  lea     rax, ??_7CBatterySaverIndividualBatteryOverview@BatterySaverOneCoreDataModel@SystemSettings@@6BISettingItem@DataModel@2@@; const SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverIndividualBatteryOverview::`vftable'{for `SystemSettings::DataModel::ISettingItem'}
0x18001a831  mov     rbx, rcx
0x18001a834  mov     [rcx], rax
0x18001a837  lea     rax, ??_7CBatterySaverSettingsThresholdValue@BatterySaverOneCoreDataModel@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UISettingItemTelemetry@DataModel@SystemSettings@@UISettingsAppNotification@67@UISettingItem2@67@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x18001a83e  mov     [rcx+8], rax
0x18001a842  lea     rax, ??_7?$CGenericAsyncHelper@VCListSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@6BISettingItemTelemetry@12@@; const SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CListSetting>::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'}
0x18001a849  mov     [rcx+10h], rax
0x18001a84d  lea     rax, ??_7CBatterySaverIndividualBatteryCapacity@BatterySaverOneCoreDataModel@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISettingsAppNotification@DataModel@SystemSettings@@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverIndividualBatteryCapacity::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x18001a854  mov     [rcx+18h], rax
0x18001a858  lea     rax, ??_7CBatterySaverSettingsThresholdValue@BatterySaverOneCoreDataModel@SystemSettings@@6BISettingItem2@DataModel@2@@; const SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::`vftable'{for `SystemSettings::DataModel::ISettingItem2'}
0x18001a85f  mov     [rcx+20h], rax
0x18001a863  lea     rax, ??_7CDisplayStringSetting@DataModel@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const SystemSettings::DataModel::CDisplayStringSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001a86a  mov     [rcx+28h], rax
0x18001a86e  mov     rdi, [rcx+0F8h]
0x18001a875  test    rdi, rdi
0x18001a878  jz      short loc_18001A8B1
0x18001a87a  or      eax, 0FFFFFFFFh
0x18001a87d  lock xadd [rdi+8], eax
0x18001a882  cmp     eax, 1
0x18001a885  jnz     short loc_18001A8B1
0x18001a887  mov     rax, [rdi]
0x18001a88a  mov     rcx, rdi
0x18001a88d  mov     rax, [rax]
0x18001a890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a895  or      eax, 0FFFFFFFFh
0x18001a898  lock xadd [rdi+0Ch], eax
0x18001a89d  cmp     eax, 1
0x18001a8a0  jnz     short loc_18001A8B1
0x18001a8a2  mov     rax, [rdi]
0x18001a8a5  mov     rcx, rdi
0x18001a8a8  mov     rax, [rax+8]
0x18001a8ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8b1  mov     rcx, [rbx+0E8h]; string
0x18001a8b8  call    cs:__imp_WindowsDeleteString
0x18001a8be  mov     rcx, rbx; this
0x18001a8c1  mov     qword ptr [rbx+0E8h], 0
0x18001a8cc  mov     rbx, [rsp+28h+arg_0]
0x18001a8d1  add     rsp, 20h
0x18001a8d5  pop     rdi
0x18001a8d6  jmp     ??1?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::~CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>(void)
```
