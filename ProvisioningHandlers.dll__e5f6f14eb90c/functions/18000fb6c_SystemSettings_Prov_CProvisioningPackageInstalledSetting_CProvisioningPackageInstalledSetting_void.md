# SystemSettings::Prov::CProvisioningPackageInstalledSetting::CProvisioningPackageInstalledSetting(void)

- ea: `0x18000fb6c`
- end: `0x18000fca6`
- name: `??0CProvisioningPackageInstalledSetting@Prov@SystemSettings@@QEAA@XZ`
- size: `314`
- prototype: `__int64 __fastcall(SystemSettings::Prov::CProvisioningPackageInstalledSetting *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000cc28`

## callees

- `0x1800045d8`
- `0x18000eb98`
- `0x18000f6c0`
- `0x18000fb6c`
- `0x180010988`
- `0x1800114a0`
- `0x18001a800`
- `0x18001b0d4`
- `0x180021c3c`
- `0x180028860`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
SystemSettings::Prov::CProvisioningPackageInstalledSetting *__fastcall SystemSettings::Prov::CProvisioningPackageInstalledSetting::CProvisioningPackageInstalledSetting(
        SystemSettings::Prov::CProvisioningPackageInstalledSetting *this)
{
  SystemSettings::Prov::CProvisioningPackageInstalledSetting *v1; // rdi
  __int64 v2; // rcx
  char IsStateSeparationEnabled; // al
  int v4; // edx
  int v5; // r9d
  const wchar_t *v6; // r8
  __int64 registry_watcher; // rax
  wil *v8; // rcx
  int v10; // eax
  int v11; // [rsp+20h] [rbp-A8h]
  _BYTE v12[8]; // [rsp+30h] [rbp-98h] BYREF
  SystemSettings::Prov::CProvisioningPackageInstalledSetting *v13; // [rsp+38h] [rbp-90h]
  _BYTE v14[8]; // [rsp+40h] [rbp-88h] BYREF
  _QWORD v15[14]; // [rsp+48h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v1 = this;
  v13 = this;
  SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>();
  SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback::CCallback((char *)v1 + 232);
  *(_QWORD *)v1 = &SystemSettings::Prov::CProvisioningPackageInstalledSetting::`vftable'{for `SystemSettings::DataModel::ISettingItem'};
  *((_QWORD *)v1 + 1) = &SystemSettings::Prov::CProvisioningDisplayStringSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)v1 + 2) = &SystemSettings::Prov::CProvisioningProviderSetting::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'};
  *((_QWORD *)v1 + 3) = &SystemSettings::Prov::CProvisioningPackageInstalledSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)v1 + 4) = &SystemSettings::Prov::CProvisioningPackageInstalledSetting::`vftable'{for `SystemSettings::DataModel::ISettingItem2'};
  *((_QWORD *)v1 + 5) = &SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CListSetting>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)v1 + 29) = &SystemSettings::Prov::CProvisioningPackageInstalledSetting::`vftable';
  *((_QWORD *)v1 + 33) = 0;
  SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::Register(v2, (__int64)v1 + 232);
  v15[0] = off_18002F1B8;
  v15[13] = v15;
  IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
  v6 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Results";
  if ( !IsStateSeparationEnabled )
    v6 = L"SOFTWARE\\Microsoft\\Provisioning\\Results";
  try
  {
    registry_watcher = wil::make_registry_watcher((unsigned int)v12, v4, (_DWORD)v6, v5, (__int64)v14);
    wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>>::operator=(
      (char *)v1 + 264,
      registry_watcher);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(v12);
    wistd::function<void (enum wil::RegistryChangeKind)>::~function<void (enum wil::RegistryChangeKind)>(v14);
  }
  catch ( ... )
  {
    v10 = wil::ResultFromCaughtException(v8);
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x548,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)v10,
        v11);
    return v13;
  }
  return v1;
}

```

## disassembly

```asm
0x18000fb6c  mov     [rsp+arg_8], rbx
0x18000fb71  mov     [rsp+arg_10], rsi
0x18000fb76  push    rdi
0x18000fb77  sub     rsp, 0C0h
0x18000fb7e  mov     rax, cs:__security_cookie
0x18000fb85  xor     rax, rsp
0x18000fb88  mov     [rsp+0C8h+var_10], rax
0x18000fb90  mov     rdi, rcx
0x18000fb93  mov     [rsp+0C8h+var_90], rcx
0x18000fb98  call    ??0?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAA@XZ; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>(void)
0x18000fb9d  nop
0x18000fb9e  lea     rbx, [rdi+0E8h]
0x18000fba5  mov     rcx, rbx
0x18000fba8  call    ??0CCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@QEAA@XZ; SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback::CCallback(void)
0x18000fbad  lea     rax, ??_7CProvisioningPackageInstalledSetting@Prov@SystemSettings@@6BISettingItem@DataModel@2@@; const SystemSettings::Prov::CProvisioningPackageInstalledSetting::`vftable'{for `SystemSettings::DataModel::ISettingItem'}
0x18000fbb4  mov     [rdi], rax
0x18000fbb7  lea     rax, ??_7CProvisioningDisplayStringSetting@Prov@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UISettingItemTelemetry@DataModel@SystemSettings@@UISettingsAppNotification@67@UISettingItem2@67@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::Prov::CProvisioningDisplayStringSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x18000fbbe  mov     [rdi+8], rax
0x18000fbc2  lea     rax, ??_7CProvisioningProviderSetting@Prov@SystemSettings@@6BISettingItemTelemetry@DataModel@2@@; const SystemSettings::Prov::CProvisioningProviderSetting::`vftable'{for `SystemSettings::DataModel::ISettingItemTelemetry'}
0x18000fbc9  mov     [rdi+10h], rax
0x18000fbcd  lea     rax, ??_7CProvisioningPackageInstalledSetting@Prov@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISettingsAppNotification@DataModel@SystemSettings@@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@; const SystemSettings::Prov::CProvisioningPackageInstalledSetting::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>'}
0x18000fbd4  mov     [rdi+18h], rax
0x18000fbd8  lea     rax, ??_7CProvisioningPackageInstalledSetting@Prov@SystemSettings@@6BISettingItem2@DataModel@2@@; const SystemSettings::Prov::CProvisioningPackageInstalledSetting::`vftable'{for `SystemSettings::DataModel::ISettingItem2'}
0x18000fbdf  mov     [rdi+20h], rax
0x18000fbe3  lea     rax, ??_7?$CGetValueAsyncHelper@VCListSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CListSetting>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000fbea  mov     [rdi+28h], rax
0x18000fbee  lea     rax, ??_7CProvisioningPackageInstalledSetting@Prov@SystemSettings@@6B@; const SystemSettings::Prov::CProvisioningPackageInstalledSetting::`vftable'
0x18000fbf5  mov     [rbx], rax
0x18000fbf8  lea     rsi, [rdi+108h]
0x18000fbff  mov     qword ptr [rsi], 0
0x18000fc06  mov     rdx, rbx
0x18000fc09  call    ?Register@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z; SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::Register(SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *)
0x18000fc0e  nop
0x18000fc0f  lea     rax, off_18002F1B8
0x18000fc16  mov     [rsp+0C8h+var_80], rax
0x18000fc1b  lea     rax, [rsp+0C8h+var_80]
0x18000fc20  mov     [rsp+0C8h+var_18], rax
0x18000fc28  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x18000fc2d  lea     rcx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Provisioning\\Resu"...
0x18000fc34  lea     r8, aOsdataSoftware; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x18000fc3b  test    al, al
0x18000fc3d  cmovz   r8, rcx
0x18000fc41  lea     rax, [rsp+0C8h+var_88]
0x18000fc46  mov     [rsp+0C8h+var_A8], rax
0x18000fc4b  lea     rcx, [rsp+0C8h+var_98]
0x18000fc50  call    ?make_registry_watcher@wil@@YA?AV?$unique_any_t@V?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@1@PEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::make_registry_watcher(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18000fc55  mov     rdx, rax
0x18000fc58  mov     rcx, rsi
0x18000fc5b  call    ??4?$unique_any_t@V?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>>::operator=(wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>> &&)
0x18000fc60  lea     rcx, [rsp+0C8h+var_98]
0x18000fc65  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x18000fc6a  nop
0x18000fc6b  lea     rcx, [rsp+0C8h+var_88]
0x18000fc70  call    ??1?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@QEAA@XZ; wistd::function<void (wil::RegistryChangeKind)>::~function<void (wil::RegistryChangeKind)>(void)
0x18000fc75  nop
0x18000fc76  jmp     short loc_18000FC7D
0x18000fc78  mov     rdi, [rsp+0C8h+var_90]
0x18000fc7d  mov     rax, rdi
0x18000fc80  mov     rcx, [rsp+0C8h+var_10]
0x18000fc88  xor     rcx, rsp; StackCookie
0x18000fc8b  call    __security_check_cookie
0x18000fc90  lea     r11, [rsp+0C8h+var_8]
0x18000fc98  mov     rbx, [r11+18h]
0x18000fc9c  mov     rsi, [r11+20h]
0x18000fca0  mov     rsp, r11
0x18000fca3  pop     rdi
0x18000fca4  retn
```
