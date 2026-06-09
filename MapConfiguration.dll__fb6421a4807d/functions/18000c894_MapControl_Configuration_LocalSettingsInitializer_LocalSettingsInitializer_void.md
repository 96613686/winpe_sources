# MapControl::Configuration::LocalSettingsInitializer::LocalSettingsInitializer(void)

- ea: `0x18000c894`
- end: `0x18000ca5b`
- name: `??0LocalSettingsInitializer@Configuration@MapControl@@QEAA@XZ`
- size: `455`
- prototype: `MapControl::Configuration::LocalSettingsInitializer *__fastcall(MapControl::Configuration::LocalSettingsInitializer *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000c410`

## callees

- `0x1800094a0`
- `0x18000c2f8`
- `0x18000c354`
- `0x18000c850`
- `0x18001518c`
- `0x1800151a4`
- `0x180025efc`
- `0x180025fd0`

## string_xrefs

- `0x18000c8c8`: `System\Maps\Configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
MapControl::Configuration::LocalSettingsInitializer *__fastcall MapControl::Configuration::LocalSettingsInitializer::LocalSettingsInitializer(
        MapControl::Configuration::LocalSettingsInitializer *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  _BYTE v8[32]; // [rsp+20h] [rbp-19h] BYREF
  _BYTE v9[32]; // [rsp+40h] [rbp+7h] BYREF
  _BYTE v10[32]; // [rsp+60h] [rbp+27h] BYREF

  std::wstring::wstring((__int64)v10, (__int64)L"System\\Maps");
  std::wstring::wstring((__int64)v9, (__int64)L"System\\Maps\\Configuration");
  RegUtils::GetPersistedRegistryLocation(v2, v10);
  RegUtils::GetVolatileRegistryLocation(v3, v9);
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9);
  std::wstring::wstring((__int64)v8, v4);
  Pal::LocalSettingsSourceIdToProviderIdMapping::add(
    &Pal::LocalSettingsSingleton<Pal::PlatformAbstractionLocalSettings>::sId,
    v8);
  std::wstring::_Tidy_deallocate(v8);
  v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9);
  std::wstring::wstring((__int64)v8, v5);
  Pal::LocalSettingsSourceIdToProviderIdMapping::add(
    &Pal::LocalSettingsSingleton<MapControl::ConfigurationLocalSettings>::sId,
    v8);
  std::wstring::_Tidy_deallocate(v8);
  v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v10);
  std::wstring::wstring((__int64)v8, v6);
  Pal::LocalSettingsSourceIdToProviderIdMapping::add(
    &Pal::LocalSettingsSingleton<MapControl::LegacyConfigurationLocalSettings>::sId,
    v8);
  std::wstring::_Tidy_deallocate(v8);
  std::wstring::wstring((__int64)v8, (__int64)L"DisableOfflineDetection");
  Pal::LocalSettingIdToRegistryValueMapping::add(&Pal::PlatformAbstractionLocalSettings::sDisableOfflineDetection, v8);
  std::wstring::_Tidy_deallocate(v8);
  std::wstring::wstring((__int64)v8, (__int64)L"UseIntData");
  Pal::LocalSettingIdToRegistryValueMapping::add(&MapControl::ConfigurationLocalSettings::sUseIntData, v8);
  std::wstring::_Tidy_deallocate(v8);
  std::wstring::wstring((__int64)v8, (__int64)L"OEMChinaVariantWin10");
  Pal::LocalSettingIdToRegistryValueMapping::add(
    &MapControl::LegacyConfigurationLocalSettings::sOEMChinaVariantWin10,
    v8);
  std::wstring::_Tidy_deallocate(v8);
  std::wstring::wstring((__int64)v8, (__int64)L"ChinaVariant");
  Pal::LocalSettingIdToRegistryValueMapping::add(&MapControl::LegacyConfigurationLocalSettings::sUseChinaVariant, v8);
  std::wstring::_Tidy_deallocate(v8);
  std::wstring::_Tidy_deallocate(v9);
  std::wstring::_Tidy_deallocate(v10);
  return this;
}

```

## disassembly

```asm
0x18000c894  mov     [rsp-8+arg_0], rbx
0x18000c899  push    rbp
0x18000c89a  lea     rbp, [rsp-57h]
0x18000c89f  sub     rsp, 90h
0x18000c8a6  mov     rax, cs:__security_cookie
0x18000c8ad  xor     rax, rsp
0x18000c8b0  mov     [rbp+57h+var_10], rax
0x18000c8b4  mov     rbx, rcx
0x18000c8b7  lea     rdx, aSystemMaps; "System\\Maps"
0x18000c8be  lea     rcx, [rbp+57h+var_30]
0x18000c8c2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c8c7  nop
0x18000c8c8  lea     rdx, aSystemMapsConf; "System\\Maps\\Configuration"
0x18000c8cf  lea     rcx, [rbp+57h+var_50]
0x18000c8d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c8d8  nop
0x18000c8d9  lea     rdx, [rbp+57h+var_30]
0x18000c8dd  call    ?GetPersistedRegistryLocation@RegUtils@@SAJW4MapsRegKeys@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,std::wstring *)
0x18000c8e2  lea     rdx, [rbp+57h+var_50]
0x18000c8e6  call    ?GetVolatileRegistryLocation@RegUtils@@SAJW4MapsRegKeys@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetVolatileRegistryLocation(MapsRegKeys,std::wstring *)
0x18000c8eb  lea     rcx, [rbp+57h+var_50]
0x18000c8ef  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000c8f4  mov     rdx, rax
0x18000c8f7  lea     rcx, [rbp+57h+var_70]
0x18000c8fb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c900  nop
0x18000c901  lea     rdx, [rbp+57h+var_70]
0x18000c905  lea     rcx, ?sId@?$LocalSettingsSingleton@VPlatformAbstractionLocalSettings@Pal@@@Pal@@0VLocalSettingsSourceId@2@B; Pal::LocalSettingsSourceId const Pal::LocalSettingsSingleton<Pal::PlatformAbstractionLocalSettings>::sId
0x18000c90c  call    ?add@LocalSettingsSourceIdToProviderIdMapping@Pal@@SAXAEBVLocalSettingsSourceId@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::LocalSettingsSourceIdToProviderIdMapping::add(Pal::LocalSettingsSourceId const &,std::wstring const &)
0x18000c911  nop
0x18000c912  lea     rcx, [rbp+57h+var_70]
0x18000c916  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c91b  lea     rcx, [rbp+57h+var_50]
0x18000c91f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000c924  mov     rdx, rax
0x18000c927  lea     rcx, [rbp+57h+var_70]
0x18000c92b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c930  nop
0x18000c931  lea     rdx, [rbp+57h+var_70]
0x18000c935  lea     rcx, ?sId@?$LocalSettingsSingleton@VConfigurationLocalSettings@MapControl@@@Pal@@0VLocalSettingsSourceId@2@B; Pal::LocalSettingsSourceId const Pal::LocalSettingsSingleton<MapControl::ConfigurationLocalSettings>::sId
0x18000c93c  call    ?add@LocalSettingsSourceIdToProviderIdMapping@Pal@@SAXAEBVLocalSettingsSourceId@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::LocalSettingsSourceIdToProviderIdMapping::add(Pal::LocalSettingsSourceId const &,std::wstring const &)
0x18000c941  nop
0x18000c942  lea     rcx, [rbp+57h+var_70]
0x18000c946  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c94b  lea     rcx, [rbp+57h+var_30]
0x18000c94f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000c954  mov     rdx, rax
0x18000c957  lea     rcx, [rbp+57h+var_70]
0x18000c95b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c960  nop
0x18000c961  lea     rdx, [rbp+57h+var_70]
0x18000c965  lea     rcx, ?sId@?$LocalSettingsSingleton@VLegacyConfigurationLocalSettings@MapControl@@@Pal@@0VLocalSettingsSourceId@2@B; Pal::LocalSettingsSourceId const Pal::LocalSettingsSingleton<MapControl::LegacyConfigurationLocalSettings>::sId
0x18000c96c  call    ?add@LocalSettingsSourceIdToProviderIdMapping@Pal@@SAXAEBVLocalSettingsSourceId@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::LocalSettingsSourceIdToProviderIdMapping::add(Pal::LocalSettingsSourceId const &,std::wstring const &)
0x18000c971  nop
0x18000c972  lea     rcx, [rbp+57h+var_70]
0x18000c976  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c97b  lea     rdx, aDisableoffline; "DisableOfflineDetection"
0x18000c982  lea     rcx, [rbp+57h+var_70]
0x18000c986  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c98b  nop
0x18000c98c  lea     rdx, [rbp+57h+var_70]
0x18000c990  lea     rcx, ?sDisableOfflineDetection@PlatformAbstractionLocalSettings@Pal@@0VLocalSettingId@2@B; Pal::LocalSettingId const Pal::PlatformAbstractionLocalSettings::sDisableOfflineDetection
0x18000c997  call    ?add@LocalSettingIdToRegistryValueMapping@Pal@@SAXAEBVLocalSettingId@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::LocalSettingIdToRegistryValueMapping::add(Pal::LocalSettingId const &,std::wstring const &)
0x18000c99c  nop
0x18000c99d  lea     rcx, [rbp+57h+var_70]
0x18000c9a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c9a6  lea     rdx, aUseintdata; "UseIntData"
0x18000c9ad  lea     rcx, [rbp+57h+var_70]
0x18000c9b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c9b6  nop
0x18000c9b7  lea     rdx, [rbp+57h+var_70]
0x18000c9bb  lea     rcx, ?sUseIntData@ConfigurationLocalSettings@MapControl@@0VLocalSettingId@Pal@@B; Pal::LocalSettingId const MapControl::ConfigurationLocalSettings::sUseIntData
0x18000c9c2  call    ?add@LocalSettingIdToRegistryValueMapping@Pal@@SAXAEBVLocalSettingId@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::LocalSettingIdToRegistryValueMapping::add(Pal::LocalSettingId const &,std::wstring const &)
0x18000c9c7  nop
0x18000c9c8  lea     rcx, [rbp+57h+var_70]
0x18000c9cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c9d1  lea     rdx, aOemchinavarian; "OEMChinaVariantWin10"
0x18000c9d8  lea     rcx, [rbp+57h+var_70]
0x18000c9dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c9e1  nop
0x18000c9e2  lea     rdx, [rbp+57h+var_70]
0x18000c9e6  lea     rcx, ?sOEMChinaVariantWin10@LegacyConfigurationLocalSettings@MapControl@@0VLocalSettingId@Pal@@B; Pal::LocalSettingId const MapControl::LegacyConfigurationLocalSettings::sOEMChinaVariantWin10
0x18000c9ed  call    ?add@LocalSettingIdToRegistryValueMapping@Pal@@SAXAEBVLocalSettingId@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::LocalSettingIdToRegistryValueMapping::add(Pal::LocalSettingId const &,std::wstring const &)
0x18000c9f2  nop
0x18000c9f3  lea     rcx, [rbp+57h+var_70]
0x18000c9f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c9fc  lea     rdx, aChinavariant; "ChinaVariant"
0x18000ca03  lea     rcx, [rbp+57h+var_70]
0x18000ca07  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000ca0c  nop
0x18000ca0d  lea     rdx, [rbp+57h+var_70]
0x18000ca11  lea     rcx, ?sUseChinaVariant@LegacyConfigurationLocalSettings@MapControl@@0VLocalSettingId@Pal@@B; Pal::LocalSettingId const MapControl::LegacyConfigurationLocalSettings::sUseChinaVariant
0x18000ca18  call    ?add@LocalSettingIdToRegistryValueMapping@Pal@@SAXAEBVLocalSettingId@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::LocalSettingIdToRegistryValueMapping::add(Pal::LocalSettingId const &,std::wstring const &)
0x18000ca1d  nop
0x18000ca1e  lea     rcx, [rbp+57h+var_70]
0x18000ca22  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ca27  nop
0x18000ca28  lea     rcx, [rbp+57h+var_50]
0x18000ca2c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ca31  nop
0x18000ca32  lea     rcx, [rbp+57h+var_30]
0x18000ca36  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ca3b  mov     rax, rbx
0x18000ca3e  mov     rcx, [rbp+57h+var_10]
0x18000ca42  xor     rcx, rsp; StackCookie
0x18000ca45  call    __security_check_cookie
0x18000ca4a  mov     rbx, [rsp+90h+arg_0]
0x18000ca52  add     rsp, 90h
0x18000ca59  pop     rbp
0x18000ca5a  retn
```
