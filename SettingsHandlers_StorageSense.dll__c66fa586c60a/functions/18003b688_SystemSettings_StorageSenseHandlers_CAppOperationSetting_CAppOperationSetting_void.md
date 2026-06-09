# SystemSettings::StorageSenseHandlers::CAppOperationSetting::~CAppOperationSetting(void)

- ea: `0x18003b688`
- end: `0x18003b746`
- name: `??1CAppOperationSetting@StorageSenseHandlers@SystemSettings@@UEAA@XZ`
- size: `190`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::CAppOperationSetting *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003cb70`

## callees

- `0x18000c964`
- `0x180028fe0`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b6f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b710`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b728`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b6f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b710`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b728`

## pseudocode

```c
void __fastcall SystemSettings::StorageSenseHandlers::CAppOperationSetting::~CAppOperationSetting(
        SystemSettings::StorageSenseHandlers::CAppOperationSetting *this)
{
  *(_QWORD *)this = &SystemSettings::StorageSenseHandlers::CAppOperationSetting::`vftable'{for `SystemSettings::DataModel::ISettingItem'};
  *((_QWORD *)this + 1) = &SystemSettings::StorageSenseHandlers::CAppOperationSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &SystemSettings::StorageSenseHandlers::CAppOperationSetting::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'};
  *((_QWORD *)this + 3) = &SystemSettings::StorageSenseHandlers::CAppOperationSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &SystemSettings::StorageSenseHandlers::CAppOperationSetting::`vftable'{for `SystemSettings::DataModel::ISettingItem2'};
  *((_QWORD *)this + 5) = &SystemSettings::StorageSenseHandlers::CAppOperationSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 31) + 16LL))(*((_QWORD *)this + 31));
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 280);
  WindowsDeleteString(*((HSTRING *)this + 29));
  *((_QWORD *)this + 29) = 0;
  WindowsDeleteString(*((HSTRING *)this + 28));
  *((_QWORD *)this + 28) = 0;
  WindowsDeleteString(*((HSTRING *)this + 27));
  *((_QWORD *)this + 27) = 0;
  SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::~CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>(this);
}

```

## disassembly

```asm
0x18003b688  push    rbx
0x18003b68a  sub     rsp, 20h
0x18003b68e  mov     rbx, rcx
0x18003b691  lea     rax, ??_7CAppOperationSetting@StorageSenseHandlers@SystemSettings@@6BISettingItem@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppOperationSetting::`vftable'{for `SystemSettings::DataModel::ISettingItem'}
0x18003b698  mov     [rcx], rax
0x18003b69b  lea     rax, ??_7CAppOperationSetting@StorageSenseHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UISettingItemTelemetry@DataModel@SystemSettings@@UISettingsAppNotification@67@UISettingItem2@67@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::StorageSenseHandlers::CAppOperationSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x18003b6a2  mov     [rcx+8], rax
0x18003b6a6  lea     rax, ??_7CAppOperationSetting@StorageSenseHandlers@SystemSettings@@6BISettingItemTelemetry@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppOperationSetting::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'}
0x18003b6ad  mov     [rcx+10h], rax
0x18003b6b1  lea     rax, ??_7CAppOperationSetting@StorageSenseHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISettingsAppNotification@DataModel@SystemSettings@@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::StorageSenseHandlers::CAppOperationSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x18003b6b8  mov     [rcx+18h], rax
0x18003b6bc  lea     rax, ??_7CAppOperationSetting@StorageSenseHandlers@SystemSettings@@6BISettingItem2@DataModel@2@@; const SystemSettings::StorageSenseHandlers::CAppOperationSetting::`vftable'{for `SystemSettings::DataModel::ISettingItem2'}
0x18003b6c3  mov     [rcx+20h], rax
0x18003b6c7  lea     rax, ??_7CAppOperationSetting@StorageSenseHandlers@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const SystemSettings::StorageSenseHandlers::CAppOperationSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003b6ce  mov     [rcx+28h], rax
0x18003b6d2  mov     rcx, [rcx+0F8h]
0x18003b6d9  mov     rax, [rcx]
0x18003b6dc  mov     rax, [rax+10h]
0x18003b6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6e5  lea     rcx, [rbx+118h]
0x18003b6ec  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18003b6f1  mov     rcx, [rbx+0E8h]; string
0x18003b6f8  call    cs:__imp_WindowsDeleteString
0x18003b6fe  mov     qword ptr [rbx+0E8h], 0
0x18003b709  mov     rcx, [rbx+0E0h]; string
0x18003b710  call    cs:__imp_WindowsDeleteString
0x18003b716  mov     qword ptr [rbx+0E0h], 0
0x18003b721  mov     rcx, [rbx+0D8h]; string
0x18003b728  call    cs:__imp_WindowsDeleteString
0x18003b72e  mov     qword ptr [rbx+0D8h], 0
0x18003b739  mov     rcx, rbx; this
0x18003b73c  add     rsp, 20h
0x18003b740  pop     rbx
0x18003b741  jmp     ??1?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::~CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>(void)
```
