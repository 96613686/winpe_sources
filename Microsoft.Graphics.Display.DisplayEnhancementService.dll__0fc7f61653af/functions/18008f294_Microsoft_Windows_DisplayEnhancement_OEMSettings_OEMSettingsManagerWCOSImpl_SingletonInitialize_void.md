# Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerWCOSImpl::SingletonInitialize(void)

- ea: `0x18008f294`
- end: `0x1800914a5`
- name: `?SingletonInitialize@OEMSettingsManagerWCOSImpl@OEMSettings@DisplayEnhancement@Windows@Microsoft@@QEAAXXZ`
- size: `8721`
- prototype: `void __fastcall(Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerWCOSImpl *__hidden this)`
- caller_count: `1`
- callee_count: `50`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1800849a8`

## callees

- `0x180005860`
- `0x1800058bc`
- `0x180009050`
- `0x180009984`
- `0x180009f68`
- `0x18000f778`
- `0x18000fb14`
- `0x180012358`
- `0x18001f9d8`
- `0x18005635c`
- `0x1800857ec`
- `0x1800858b0`
- `0x180085a08`
- `0x18008c51c`
- `0x18008c5ac`
- `0x18008c638`
- `0x18008c6dc`
- `0x18008c774`
- `0x18008c818`
- `0x18008c8bc`
- `0x18008c960`
- `0x18008ca04`
- `0x18008ca70`
- `0x18008cbbc`
- `0x18008d134`
- `0x18008d180`
- `0x18008d1dc`
- `0x18008d2bc`
- `0x18008d304`
- `0x18008d350`
- `0x18008d3b4`
- `0x18008d458`
- `0x18008d4ac`
- `0x18008d63c`
- `0x18008d6a0`
- `0x18008d704`
- `0x18008dab0`
- `0x18008dba0`
- `0x18008de70`
- `0x18008dea0`
- `0x18008df00`
- `0x18008df30`
- `0x18008e0e0`
- `0x18008e110`
- `0x18008e140`
- `0x18008e170`
- `0x18008e404`
- `0x18008e500`
- `0x18008f294`
- `0x1800914ac`

## string_xrefs

- `0x18008f65c`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\DisplayEnhancementService\OEMSettings\V1`
- `0x18008f776`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\DisplayEnhancementService\OEMSettings\V1`
- `0x18008fc28`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\DisplayEnhancementService\OEMSettings\V1`
- `0x1800907b6`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\DisplayEnhancementService\OEMSettings\V1`
- `0x18009087a`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\DisplayEnhancementService\OEMSettings\V1`
- `0x180090e2e`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\DisplayEnhancementService\OEMSettings\V1`
- `0x18009056a`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\DisplayEnhancementService\OEMSettings\V1\Internal`
- `0x18009062e`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\DisplayEnhancementService\OEMSettings\V1\Internal`
- `0x1800906f2`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\DisplayEnhancementService\OEMSettings\V1\Internal`
- `0x18009093e`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\DisplayEnhancementService\OEMSettings\V1\Internal`
- `0x180090b51`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\DisplayEnhancementService\OEMSettings\V1\Internal`
- `0x180090c15`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\DisplayEnhancementService\OEMSettings\V1\Internal`
- `0x180090cd9`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\DisplayEnhancementService\OEMSettings\V1\Internal`
- `0x180090eed`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\DisplayEnhancementService\OEMSettings\V1\Internal`
- `0x180090fa5`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\DisplayEnhancementService\OEMSettings\V1\Internal`
- `0x18009105d`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\DisplayEnhancementService\OEMSettings\V1\Internal`
- `0x18009111c`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\DisplayEnhancementService\OEMSettings\V1\Internal`
- `0x18008fcd9`: `ShouldStopTransitionDuringHandsOnDisplay`

## pseudocode

```c
// Hidden C++ exception states: #wind=88
void __fastcall Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerWCOSImpl::SingletonInitialize(
        std::_Ref_count_base **this)
{
  void **v2; // rdi
  void **v3; // rdi
  void **v4; // rdi
  void **v5; // rdi
  void **v6; // rdi
  __int64 ValueFromPolicy; // rax
  std::_Ref_count_base *v8; // rcx
  void **v9; // rdi
  __int64 v10; // r8
  __int64 *v11; // rax
  void **v12; // rdi
  char v13; // di
  __int64 v14; // r8
  __int64 *v15; // rax
  __int64 *v16; // rax
  __int64 v17; // r8
  __int64 *v18; // rax
  char v19; // di
  __int64 v20; // r8
  __int64 *v21; // rax
  __int64 *v22; // rax
  __int64 v23; // r8
  __int64 *v24; // rax
  __int64 v25; // r8
  __int64 *v26; // rax
  __int64 v27; // r8
  __int64 *v28; // rax
  __int64 v29; // r8
  __int64 *v30; // rax
  __int64 v31; // r8
  __int64 *v32; // rax
  __int64 v33; // r8
  __int64 *v34; // rax
  __int64 v35; // r8
  __int64 *v36; // rax
  __int64 v37; // r8
  __int64 *v38; // rax
  void **v39; // rdi
  void **v40; // rdi
  void **v41; // rdi
  void **v42; // rdi
  void **v43; // rdi
  void **v44; // rdi
  void **v45; // rdi
  std::_Ref_count_base *v46; // rcx
  char v47; // di
  __int64 v48; // r8
  const unsigned __int8 *v49; // rax
  __int64 *v50; // rax
  __int64 v51; // r8
  __int64 *v52; // rax
  void **v53; // rdi
  std::_Ref_count_base *v54; // rcx
  void **v55; // rdi
  __int64 *v56; // rax
  __int64 *v57; // rax
  __int64 v58; // r8
  __int64 *v59; // rax
  __int64 v60; // r8
  __int64 *v61; // rax
  __int64 v62; // r8
  __int64 *v63; // rax
  __int64 v64; // r8
  __int64 *v65; // rax
  void **v66; // rdi
  void **v67; // rdi
  void **v68; // rdi
  void **v69; // rdi
  void **v70; // rdi
  void **v71; // rdi
  void **v72; // rdi
  __int64 v73; // r8
  __int64 *v74; // rax
  __int64 v75; // r8
  __int64 *v76; // rax
  __int64 v77; // r8
  __int64 *v78; // rax
  __int64 v79; // r8
  __int64 *v80; // rax
  void **v81; // rdi
  void **v82; // rdi
  void **v83; // rdi
  __int64 v84; // r8
  __int64 *v85; // rax
  __int64 v86; // r8
  __int64 *v87; // rax
  void **v88; // rdi
  void **v89; // rdi
  void **v90; // rdi
  void **v91; // rdi
  void **v92; // rdi
  __int64 v93; // r8
  __int64 *v94; // rax
  int v95; // edx
  int v96; // r8d
  __int64 *v97; // rax
  __int64 v98; // r8
  __int64 v99; // r9
  __int64 *v100; // rax
  __int64 v101; // r8
  __int64 *v102; // rax
  __int64 v103; // r8
  __int64 *v104; // rax
  int v105; // xmm6_4
  int v106; // r13d
  char v107; // r12
  char v108; // r15
  _QWORD *AutobrightnessLuxToNitsCurve; // rax
  __int64 Value; // r14
  unsigned int v111; // esi
  unsigned int v112; // ebx
  __int64 IsAutobrightnessEnabledByDefault; // rax
  __int64 v114; // rcx
  int v115; // [rsp+28h] [rbp-E0h]
  int v116; // [rsp+30h] [rbp-D8h]
  void **v117; // [rsp+68h] [rbp-A0h] BYREF
  std::_Ref_count_base *v118; // [rsp+70h] [rbp-98h]
  void **v119; // [rsp+78h] [rbp-90h] BYREF
  void **v120; // [rsp+80h] [rbp-88h]
  _QWORD v121[2]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v122[2]; // [rsp+98h] [rbp-70h] BYREF
  char v123; // [rsp+A8h] [rbp-60h]
  char v124; // [rsp+A9h] [rbp-5Fh]
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerWCOSImpl *v125; // [rsp+B0h] [rbp-58h]
  _BYTE v126[8]; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD v127[2]; // [rsp+C0h] [rbp-48h] BYREF
  _QWORD v128[2]; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v129[16]; // [rsp+E0h] [rbp-28h] BYREF
  _QWORD v130[2]; // [rsp+F0h] [rbp-18h] BYREF
  _QWORD v131[2]; // [rsp+100h] [rbp-8h] BYREF
  _QWORD v132[2]; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v133[32]; // [rsp+120h] [rbp+18h] BYREF
  _BYTE v134[32]; // [rsp+140h] [rbp+38h] BYREF
  _BYTE v135[32]; // [rsp+160h] [rbp+58h] BYREF

  v125 = (Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerWCOSImpl *)this;
  Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::GetServiceRegistryStateKey(v126);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>::`vftable';
  v2 = (void **)operator new(0x20u);
  v119 = v2;
  *(_OWORD *)v2 = 0;
  *((_DWORD *)v2 + 2) = 1;
  *((_DWORD *)v2 + 3) = 1;
  *v2 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable';
  std::wstring::wstring(v133, L"IsAutobrightnessOnByDefault");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>::OEMSettingFromPolicy<bool>(
    (_DWORD)v2 + 16,
    (unsigned int)v133,
    (unsigned int)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerWCOSImpl::c_isAutobrightnessOnByDefaultDefaultValue,
    (unsigned int)v121,
    (__int64)(this + 128));
  std::wstring::_Tidy_deallocate(v133);
  v117 = v2 + 2;
  v118 = (std::_Ref_count_base *)v2;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 2,
    (__int64 *)&v117);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v117 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::BoundsOEMSettingValidator<unsigned long>::`vftable';
  v118 = (std::_Ref_count_base *)0x6400000000LL;
  v3 = (void **)operator new(0x20u);
  v119 = v3;
  *(_OWORD *)v3 = 0;
  *((_DWORD *)v3 + 2) = 1;
  *((_DWORD *)v3 + 3) = 1;
  *v3 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable';
  std::wstring::wstring(v133, L"DefaultBrightnessSliderPercentage");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<unsigned long>::OEMSettingFromPolicy<unsigned long>(
    (_DWORD)v3 + 16,
    (unsigned int)v133,
    (unsigned int)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerWCOSImpl::c_defaultBrightnessSliderPercentageDefaultValue,
    (unsigned int)&v117,
    (__int64)(this + 128));
  std::wstring::_Tidy_deallocate(v133);
  v119 = v3 + 2;
  v120 = v3;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 4,
    (__int64 *)&v119);
  if ( v120 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v120);
  v117 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::BoundsOEMSettingValidator<unsigned long>::`vftable';
  v118 = (std::_Ref_count_base *)0x6400000000LL;
  v4 = (void **)operator new(0x20u);
  v119 = v4;
  *(_OWORD *)v4 = 0;
  *((_DWORD *)v4 + 2) = 1;
  *((_DWORD *)v4 + 3) = 1;
  *v4 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable';
  std::wstring::wstring(v133, L"DefaultDimBrightnessMultiplier");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<unsigned long>::OEMSettingFromPolicy<unsigned long>(
    (_DWORD)v4 + 16,
    (unsigned int)v133,
    (unsigned int)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerWCOSImpl::c_defaultDimBrightnessMultiplierDefaultValue,
    (unsigned int)&v117,
    (__int64)(this + 128));
  std::wstring::_Tidy_deallocate(v133);
  v119 = v4 + 2;
  v120 = v4;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 6,
    (__int64 *)&v119);
  if ( v120 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v120);
  v117 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::BoundsOEMSettingValidator<unsigned long>::`vftable';
  v118 = (std::_Ref_count_base *)0x6400000000LL;
  v5 = (void **)operator new(0x20u);
  v119 = v5;
  *(_OWORD *)v5 = 0;
  *((_DWORD *)v5 + 2) = 1;
  *((_DWORD *)v5 + 3) = 1;
  *v5 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable';
  std::wstring::wstring(v133, L"DefaultBatterySaverBrightnessMultiplier");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<unsigned long>::OEMSettingFromPolicy<unsigned long>(
    (_DWORD)v5 + 16,
    (unsigned int)v133,
    (unsigned int)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerWCOSImpl::c_defaultBatterySaverBrightnessMultiplierDefaultValue,
    (unsigned int)&v117,
    (__int64)(this + 128));
  std::wstring::_Tidy_deallocate(v133);
  v119 = v5 + 2;
  v120 = v5;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 8,
    (__int64 *)&v119);
  if ( v120 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v120);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::CurveOEMSettingValidator::`vftable';
  v6 = (void **)operator new(0x38u);
  v119 = v6;
  *(_OWORD *)v6 = 0;
  *((_DWORD *)v6 + 2) = 1;
  *((_DWORD *)v6 + 3) = 1;
  *v6 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<unsigned int,unsigned int>>>>::`vftable';
  std::wstring::wstring(v133, L"AutobrightnessLuxToNitsCurve");
  ValueFromPolicy = Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsCurve>::QueryValueFromPolicy((Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsCurve *)v134);
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsCurve>::OEMSetting<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsCurve>(
    v6 + 2,
    ValueFromPolicy,
    v121);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>(v134);
  v6[2] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::ChromaticityXY>>::`vftable';
  std::wstring::_Tidy_deallocate(v133);
  this[10] = (std::_Ref_count_base *)(v6 + 2);
  v8 = this[11];
  this[11] = (std::_Ref_count_base *)v6;
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::BucketMappingOEMSettingValidator::`vftable';
  v9 = (void **)operator new(0x38u);
  v119 = v9;
  *(_OWORD *)v9 = 0;
  *((_DWORD *)v9 + 2) = 1;
  *((_DWORD *)v9 + 3) = 1;
  *v9 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<Microsoft::Windows::DisplayEnhancement::Foundation::BucketedMilliLuxToPercentageCurve>>::`vftable';
  std::wstring::wstring(v134, L"AutobrightnessBucketMapping");
  std::wstring::wstring(
    v133,
    L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\DisplayEnhancementService\\OEMSettings\\V1");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<Microsoft::Windows::DisplayEnhancement::Foundation::BucketedMilliLuxToPercentageCurve>::OEMSettingFromRegistry<Microsoft::Windows::DisplayEnhancement::Foundation::BucketedMilliLuxToPercentageCurve>(
    (_DWORD)v9 + 16,
    -2147483646,
    (unsigned int)v133,
    (unsigned int)v134,
    (__int64)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_autobrightnessBucketMapping,
    (__int64)v121);
  std::wstring::_Tidy_deallocate(v133);
  std::wstring::_Tidy_deallocate(v134);
  v117 = v9 + 2;
  v118 = (std::_Ref_count_base *)v9;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 12,
    (__int64 *)&v117);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<unsigned int,unsigned int>>>::`vftable';
  v122[0] = -2147483646;
  v11 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<unsigned int,unsigned int>>>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[46],std::vector<std::tuple<unsigned int,unsigned int>> const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<unsigned int,unsigned int>>>>(
          &v117,
          v122,
          v10,
          (__int64)L"UpperBrightnessHysteresisLut",
          (__int64)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultUpperBrightness2HysteresisLut,
          (__int64)v121);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 14,
    v11);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>::`vftable';
  v12 = (void **)operator new(0x20u);
  v119 = v12;
  *(_OWORD *)v12 = 0;
  *((_DWORD *)v12 + 2) = 1;
  *((_DWORD *)v12 + 3) = 1;
  *v12 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable';
  std::wstring::wstring(v134, L"EnableLuxHysteresisAndPersistenceFilter");
  std::wstring::wstring(
    v133,
    L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\DisplayEnhancementService\\OEMSettings\\V1");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>::OEMSettingFromRegistry<bool>(
    (_DWORD)v12 + 16,
    -2147483646,
    (unsigned int)v133,
    (unsigned int)v134,
    (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_isLuxHysteresisAndPersistenceFilterEnabled,
    (__int64)v121);
  std::wstring::_Tidy_deallocate(v133);
  std::wstring::_Tidy_deallocate(v134);
  v117 = v12 + 2;
  v118 = (std::_Ref_count_base *)v12;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 40,
    (__int64 *)&v117);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v13 = *(_BYTE *)(*(_QWORD *)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerDesktopImpl::GetIsLuxHysteresisAndPersistenceFilterEnabled(
                                this,
                                &v117)
                 + 8LL);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v122[0] = -2147483646;
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<unsigned int,unsigned int>>>::`vftable';
  v15 = Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultLowerBrightness2HysteresisLutForLuxHysteresisFilter;
  if ( !v13 )
    v15 = Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultLowerBrightness2HysteresisLut;
  v16 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<unsigned int,unsigned int>>>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[46],std::vector<std::tuple<unsigned int,unsigned int>> const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<unsigned int,unsigned int>>>>(
          &v117,
          v122,
          v14,
          (__int64)L"LowerBrightnessHysteresisLut",
          (__int64)v15,
          (__int64)v121);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 16,
    v16);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<unsigned int,unsigned int>>>::`vftable';
  v122[0] = -2147483646;
  v18 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<unsigned int,unsigned int>>>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[46],std::vector<std::tuple<unsigned int,unsigned int>> const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<unsigned int,unsigned int>>>>(
          &v117,
          v122,
          v17,
          (__int64)L"UpperBrightnessHysteresisLut",
          (__int64)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultUpperBrightness3HysteresisLut,
          (__int64)v121);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 18,
    v18);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v19 = *(_BYTE *)(*(_QWORD *)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerDesktopImpl::GetIsLuxHysteresisAndPersistenceFilterEnabled(
                                this,
                                &v117)
                 + 8LL);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v122[0] = -2147483646;
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<unsigned int,unsigned int>>>::`vftable';
  v21 = Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultLowerBrightness3HysteresisLutForLuxHysteresisFilter;
  if ( !v19 )
    v21 = Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultLowerBrightness3HysteresisLut;
  v22 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<unsigned int,unsigned int>>>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[46],std::vector<std::tuple<unsigned int,unsigned int>> const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<unsigned int,unsigned int>>>>(
          &v117,
          v122,
          v20,
          (__int64)L"LowerBrightnessHysteresisLut",
          (__int64)v21,
          (__int64)v121);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 20,
    v22);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<unsigned int,unsigned int>>>::`vftable';
  v122[0] = -2147483646;
  v24 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<unsigned int,unsigned int>>>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[46],std::vector<std::tuple<unsigned int,unsigned int>> const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<unsigned int,unsigned int>>>>(
          &v117,
          v122,
          v23,
          (__int64)L"FirstStageAbsoluteMilliLuxLowerHysteresisLut",
          (__int64)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultFirstStageAbsoluteMilliLuxLowerHysteresisLut,
          (__int64)v121);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 22,
    v24);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<unsigned int,unsigned int>>>::`vftable';
  v122[0] = -2147483646;
  v26 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<unsigned int,unsigned int>>>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[46],std::vector<std::tuple<unsigned int,unsigned int>> const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<unsigned int,unsigned int>>>>(
          &v117,
          v122,
          v25,
          (__int64)L"FirstStageAbsoluteMilliLuxUpperHysteresisLut",
          (__int64)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultFirstStageAbsoluteMilliLuxUpperHysteresisLut,
          (__int64)v121);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 24,
    v26);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<unsigned int,unsigned int>>>::`vftable';
  v122[0] = -2147483646;
  v28 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<unsigned int,unsigned int>>>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[46],std::vector<std::tuple<unsigned int,unsigned int>> const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<unsigned int,unsigned int>>>>(
          &v117,
          v122,
          v27,
          (__int64)L"SecondStageAbsoluteMilliLuxLowerHysteresisLut",
          (__int64)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultSecondStageAbsoluteMilliLuxLowerHysteresisLut,
          (__int64)v121);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 26,
    v28);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<unsigned int,unsigned int>>>::`vftable';
  v122[0] = -2147483646;
  v30 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<unsigned int,unsigned int>>>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[46],std::vector<std::tuple<unsigned int,unsigned int>> const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<unsigned int,unsigned int>>>>(
          &v117,
          v122,
          v29,
          (__int64)L"SecondStageAbsoluteMilliLuxUpperHysteresisLut",
          (__int64)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultSecondStageAbsoluteMilliLuxUpperHysteresisLut,
          (__int64)v121);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 28,
    v30);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>::`vftable';
  v122[0] = -2147483646;
  v32 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<unsigned char>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[41],unsigned char const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>>(
          &v117,
          v122,
          v31,
          (__int64)L"FirstStageUpperRelativeMilliLuxHysteresisThreshold",
          (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultFirstStageUpperRelativeMilliLuxHysteresisThreshold,
          (__int64)v121);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 30,
    v32);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>::`vftable';
  v122[0] = -2147483646;
  v34 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<unsigned char>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[41],unsigned char const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>>(
          &v117,
          v122,
          v33,
          (__int64)L"FirstStageLowerRelativeMilliLuxHysteresisThreshold",
          (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultFirstStageLowerRelativeMilliLuxHysteresisThreshold,
          (__int64)v121);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 32,
    v34);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>::`vftable';
  v122[0] = -2147483646;
  v36 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<unsigned char>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[41],unsigned char const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>>(
          &v117,
          v122,
          v35,
          (__int64)L"SecondStageUpperRelativeMilliLuxHysteresisThreshold",
          (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultSecondStageUpperRelativeMilliLuxHysteresisThreshold,
          (__int64)v121);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 34,
    v36);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>::`vftable';
  v122[0] = -2147483646;
  v38 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<unsigned char>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[41],unsigned char const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>>(
          &v117,
          v122,
          v37,
          (__int64)L"SecondStageLowerRelativeMilliLuxHysteresisThreshold",
          (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultSecondStageLowerRelativeMilliLuxHysteresisThreshold,
          (__int64)v121);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 36,
    v38);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::chrono::duration<__int64,std::ratio<1,1000>>>::`vftable';
  v39 = (void **)operator new(0x28u);
  v119 = v39;
  *(_OWORD *)v39 = 0;
  *((_DWORD *)v39 + 2) = 1;
  *((_DWORD *)v39 + 3) = 1;
  *v39 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::chrono::duration<__int64,std::ratio<1,1000>>>>::`vftable';
  std::wstring::wstring(v134, L"PersistenceFilterDuration");
  std::wstring::wstring(
    v133,
    L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\DisplayEnhancementService\\OEMSettings\\V1");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::chrono::duration<__int64,std::ratio<1,1000>>>::OEMSettingFromRegistry<std::chrono::duration<__int64,std::ratio<1,1000>>>(
    (_DWORD)v39 + 16,
    -2147483646,
    (unsigned int)v133,
    (unsigned int)v134,
    (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultPersistenceFilterDuration,
    (__int64)v121);
  std::wstring::_Tidy_deallocate(v133);
  std::wstring::_Tidy_deallocate(v134);
  v117 = v39 + 2;
  v118 = (std::_Ref_count_base *)v39;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 38,
    (__int64 *)&v117);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>::`vftable';
  v40 = (void **)operator new(0x20u);
  v119 = v40;
  *(_OWORD *)v40 = 0;
  *((_DWORD *)v40 + 2) = 1;
  *((_DWORD *)v40 + 3) = 1;
  *v40 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable';
  std::wstring::wstring(v133, L"ShouldStopTransitionDuringHandsOnDisplay");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>::OEMSettingFromPolicy<bool>(
    (_DWORD)v40 + 16,
    (unsigned int)v133,
    (unsigned int)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_shouldStopTransitionDuringHandsOnDisplayDefaultValue,
    (unsigned int)v121,
    (__int64)(this + 128));
  std::wstring::_Tidy_deallocate(v133);
  v117 = v40 + 2;
  v118 = (std::_Ref_count_base *)v40;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 42,
    (__int64 *)&v117);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>::`vftable';
  v41 = (void **)operator new(0x20u);
  v119 = v41;
  *(_OWORD *)v41 = 0;
  *((_DWORD *)v41 + 2) = 1;
  *((_DWORD *)v41 + 3) = 1;
  *v41 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable';
  std::wstring::wstring(v133, L"AllowAdaptiveColorCapable");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>::OEMSettingFromPolicy<bool>(
    (_DWORD)v41 + 16,
    (unsigned int)v133,
    (unsigned int)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_allowAdaptiveColorCapableDefaultValue,
    (unsigned int)v121,
    (__int64)(this + 128));
  std::wstring::_Tidy_deallocate(v133);
  v117 = v41 + 2;
  v118 = (std::_Ref_count_base *)v41;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 44,
    (__int64 *)&v117);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>::`vftable';
  v42 = (void **)operator new(0x20u);
  v119 = v42;
  *(_OWORD *)v42 = 0;
  *((_DWORD *)v42 + 2) = 1;
  *((_DWORD *)v42 + 3) = 1;
  *v42 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable';
  std::wstring::wstring(v133, L"IsAdaptiveColorOnByDefault");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>::OEMSettingFromPolicy<bool>(
    (_DWORD)v42 + 16,
    (unsigned int)v133,
    (unsigned int)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_isAdaptiveColorOnByDefaultDefaultValue,
    (unsigned int)v121,
    (__int64)(this + 128));
  std::wstring::_Tidy_deallocate(v133);
  v117 = v42 + 2;
  v118 = (std::_Ref_count_base *)v42;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 48,
    (__int64 *)&v117);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v117 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::BoundsOEMSettingValidator<unsigned long>::`vftable';
  v118 = (std::_Ref_count_base *)0x6400000000LL;
  v43 = (void **)operator new(0x20u);
  v119 = v43;
  *(_OWORD *)v43 = 0;
  *((_DWORD *)v43 + 2) = 1;
  *((_DWORD *)v43 + 3) = 1;
  *v43 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable';
  std::wstring::wstring(v133, L"DefaultAdaptiveColorAdaptationStrength");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<unsigned long>::OEMSettingFromPolicy<unsigned long>(
    (_DWORD)v43 + 16,
    (unsigned int)v133,
    (unsigned int)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultAdaptiveColorAdaptationStrengthDefaultValue,
    (unsigned int)&v117,
    (__int64)(this + 128));
  std::wstring::_Tidy_deallocate(v133);
  v119 = v43 + 2;
  v120 = v43;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 50,
    (__int64 *)&v119);
  if ( v120 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v120);
  v117 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::BoundsOEMSettingValidator<unsigned long>::`vftable';
  v118 = (std::_Ref_count_base *)0x6400000000LL;
  v44 = (void **)operator new(0x20u);
  v119 = v44;
  *(_OWORD *)v44 = 0;
  *((_DWORD *)v44 + 2) = 1;
  *((_DWORD *)v44 + 3) = 1;
  *v44 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable';
  std::wstring::wstring(v133, L"AdaptiveColorMultiplierForExternalMonitorPresence");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<unsigned long>::OEMSettingFromPolicy<unsigned long>(
    (_DWORD)v44 + 16,
    (unsigned int)v133,
    (unsigned int)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_adaptiveColorMultiplierForExternalMonitorPresenceDefaultValue,
    (unsigned int)&v117,
    (__int64)(this + 128));
  std::wstring::_Tidy_deallocate(v133);
  v119 = v44 + 2;
  v120 = v44;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 52,
    (__int64 *)&v119);
  if ( v120 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v120);
  v117 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::BoundsOEMSettingValidator<float>::`vftable';
  v118 = (std::_Ref_count_base *)0x3F80000000000000LL;
  v45 = (void **)operator new(0x20u);
  v119 = v45;
  *(_OWORD *)v45 = 0;
  *((_DWORD *)v45 + 2) = 1;
  *((_DWORD *)v45 + 3) = 1;
  *v45 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable';
  std::wstring::wstring(v133, L"ColorSensorChromaticityThreshold");
  LODWORD(v122[0]) = Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<float>::QueryValueFromPolicy(
                       this + 128,
                       v133,
                       &Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_colorSensorChromaticityThresholdDefaultValue);
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<float>::OEMSetting<float>(v45 + 2, v122, &v117);
  v45[2] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<unsigned long>::`vftable';
  std::wstring::_Tidy_deallocate(v133);
  this[54] = (std::_Ref_count_base *)(v45 + 2);
  v46 = this[55];
  this[55] = (std::_Ref_count_base *)v45;
  if ( v46 )
    std::_Ref_count_base::_Decref(v46);
  v47 = *(_BYTE *)(*(_QWORD *)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerDesktopImpl::GetIsLuxHysteresisAndPersistenceFilterEnabled(
                                this,
                                &v117)
                 + 8LL);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v122[0] = -2147483646;
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>::`vftable';
  v49 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_maxRelativeBrightnessHysteresisThresholdForLuxHysteresisFilter;
  if ( !v47 )
    v49 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_maxRelativeBrightnessHysteresisThreshold;
  v50 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<unsigned char>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[41],unsigned char const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>>(
          &v117,
          v122,
          v48,
          (__int64)L"MaxRelativeBrightnessHysteresisThreshold",
          (__int64)v49,
          (__int64)v121);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 56,
    v50);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v121[0] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>::`vftable';
  v122[0] = -2147483646;
  v52 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<unsigned char>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[41],unsigned char const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>>(
          &v117,
          v122,
          v51,
          (__int64)L"MinRelativeBrightnessHysteresisThreshold",
          (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_minRelativeBrightnessHysteresisThreshold,
          (__int64)v121);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 58,
    v52);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned int>::`vftable';
  v53 = (void **)operator new(0x20u);
  v117 = v53;
  *(_OWORD *)v53 = 0;
  *((_DWORD *)v53 + 2) = 1;
  *((_DWORD *)v53 + 3) = 1;
  *v53 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable';
  std::wstring::wstring(v133, L"MinBrightnessTransitionNitDelta");
  LODWORD(v122[0]) = 880;
  LODWORD(v121[0]) = Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<unsigned long>::QueryValueFromPolicy(
                       this + 128,
                       v133,
                       v122);
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned int>::OEMSetting<unsigned int>(
    v53 + 2,
    v121,
    &v119);
  v53[2] = &Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<unsigned long>::`vftable';
  std::wstring::_Tidy_deallocate(v133);
  this[60] = (std::_Ref_count_base *)(v53 + 2);
  v54 = this[61];
  this[61] = (std::_Ref_count_base *)v53;
  if ( v54 )
    std::_Ref_count_base::_Decref(v54);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::chrono::duration<__int64,std::ratio<1,1000>>>::`vftable';
  v55 = (void **)operator new(0x28u);
  v117 = v55;
  *(_OWORD *)v55 = 0;
  *((_DWORD *)v55 + 2) = 1;
  *((_DWORD *)v55 + 3) = 1;
  *v55 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::chrono::duration<__int64,std::ratio<1,1000>>>>::`vftable';
  std::wstring::wstring(v133, L"DefaultBrightnessTransitionInterval");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<std::chrono::duration<__int64,std::ratio<1,1000>>>::OEMSettingFromPolicy<std::chrono::duration<__int64,std::ratio<1,1000>>>(
    (_DWORD)v55 + 16,
    (unsigned int)v133,
    (unsigned int)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultBrightnessTransitionInterval,
    (unsigned int)&v119,
    (__int64)(this + 128));
  std::wstring::_Tidy_deallocate(v133);
  v117 = v55 + 2;
  v118 = (std::_Ref_count_base *)v55;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 62,
    (__int64 *)&v117);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::chrono::duration<__int64,std::ratio<1,1000>>>::`vftable';
  v56 = (__int64 *)std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<std::chrono::duration<__int64,std::ratio<1,1000>>>,unsigned short const (&)[32],std::chrono::duration<__int64,std::ratio<1,1000>> const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::chrono::duration<__int64,std::ratio<1,1000>>>,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::PolicyAdapter> &>(
                     (unsigned int)&v117,
                     (unsigned int)L"MinBrightnessTransitionInterval",
                     (unsigned int)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_minBrightnessTransitionInterval,
                     (unsigned int)&v119,
                     (__int64)(this + 128));
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 64,
    v56);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::chrono::duration<__int64,std::ratio<1,1000>>>::`vftable';
  v57 = (__int64 *)std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<std::chrono::duration<__int64,std::ratio<1,1000>>>,unsigned short const (&)[32],std::chrono::duration<__int64,std::ratio<1,1000>> const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::chrono::duration<__int64,std::ratio<1,1000>>>,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::PolicyAdapter> &>(
                     (unsigned int)&v117,
                     (unsigned int)L"MaxBrightnessTransitionInterval",
                     (unsigned int)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_maxBrightnessTransitionInterval,
                     (unsigned int)&v119,
                     (__int64)(this + 128));
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 66,
    v57);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry>>::`vftable';
  v121[0] = -2147483646;
  v59 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionTimeTableEntry>>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[38],std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionTimeTableEntry> const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionTimeTableEntry>>>(
          &v117,
          v121,
          v58,
          (__int64)L"IncreaseBrightnessTransitionTimeTable",
          (__int64)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_increaseBrightnessTransitionTimeTable,
          (__int64)&v119);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 68,
    v59);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry>>::`vftable';
  v121[0] = -2147483646;
  v61 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionTimeTableEntry>>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[38],std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionTimeTableEntry> const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionTimeTableEntry>>>(
          &v117,
          v121,
          v60,
          (__int64)L"DecreaseBrightnessTransitionTimeTable",
          (__int64)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_decreaseBrightnessTransitionTimeTable,
          (__int64)&v119);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 70,
    v61);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry>>::`vftable';
  v121[0] = -2147483646;
  v63 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry>>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[36],std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry> const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry>>>(
          &v117,
          v121,
          v62,
          (__int64)L"IncreaseBrightnessAccelerationTable",
          (__int64)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_increaseBrightnessAccelerationTable,
          (__int64)&v119);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 72,
    v63);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry>>::`vftable';
  v121[0] = -2147483646;
  v65 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry>>,HKEY__ *,unsigned short const (&)[94],unsigned short const (&)[36],std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry> const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<Microsoft::Windows::DisplayEnhancement::Transition::TransitionAccelerationTableEntry>>>(
          &v117,
          v121,
          v64,
          (__int64)L"DecreaseBrightnessAccelerationTable",
          (__int64)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_decreaseBrightnessAccelerationTable,
          (__int64)&v119);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 74,
    v65);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>::`vftable';
  v66 = (void **)operator new(0x20u);
  v117 = v66;
  *(_OWORD *)v66 = 0;
  *((_DWORD *)v66 + 2) = 1;
  *((_DWORD *)v66 + 3) = 1;
  *v66 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable';
  std::wstring::wstring(v133, L"EnableAdaptiveColorStrengthSlider");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>::OEMSettingFromPolicy<bool>(
    (_DWORD)v66 + 16,
    (unsigned int)v133,
    (unsigned int)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_isAdaptiveColorStrengthSliderEnabled,
    (unsigned int)&v119,
    (__int64)(this + 128));
  std::wstring::_Tidy_deallocate(v133);
  v117 = v66 + 2;
  v118 = (std::_Ref_count_base *)v66;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 76,
    (__int64 *)&v117);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<Microsoft::Windows::DisplayEnhancement::Foundation::ChromaticityXY>::`vftable';
  v67 = (void **)operator new(0x28u);
  v117 = v67;
  *(_OWORD *)v67 = 0;
  *((_DWORD *)v67 + 2) = 1;
  *((_DWORD *)v67 + 3) = 1;
  *v67 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::chrono::duration<__int64,std::ratio<1,1000>>>>::`vftable';
  std::wstring::wstring(v134, L"WhitePointMappingLowLightWhitePoint");
  std::wstring::wstring(
    v133,
    L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\DisplayEnhancementService\\OEMSettings\\V1\\Internal");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<Microsoft::Windows::DisplayEnhancement::Foundation::ChromaticityXY>::OEMSettingFromRegistry<Microsoft::Windows::DisplayEnhancement::Foundation::ChromaticityXY>(
    (_DWORD)v67 + 16,
    -2147483646,
    (unsigned int)v133,
    (unsigned int)v134,
    (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_whitePointMappingLowLightWhitePoint,
    (__int64)&v119);
  std::wstring::_Tidy_deallocate(v133);
  std::wstring::_Tidy_deallocate(v134);
  v117 = v67 + 2;
  v118 = (std::_Ref_count_base *)v67;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 78,
    (__int64 *)&v117);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned int>::`vftable';
  v68 = (void **)operator new(0x20u);
  v117 = v68;
  *(_OWORD *)v68 = 0;
  *((_DWORD *)v68 + 2) = 1;
  *((_DWORD *)v68 + 3) = 1;
  *v68 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable';
  std::wstring::wstring(v134, L"WhitePointMappingLowLightLuxLevel");
  std::wstring::wstring(
    v133,
    L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\DisplayEnhancementService\\OEMSettings\\V1\\Internal");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<unsigned int>::OEMSettingFromRegistry<unsigned int>(
    (_DWORD)v68 + 16,
    -2147483646,
    (unsigned int)v133,
    (unsigned int)v134,
    (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_whitePointMappingLowLightLuxLevel,
    (__int64)&v119);
  std::wstring::_Tidy_deallocate(v133);
  std::wstring::_Tidy_deallocate(v134);
  v117 = v68 + 2;
  v118 = (std::_Ref_count_base *)v68;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 80,
    (__int64 *)&v117);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::ChromaticityXY>>::`vftable';
  v69 = (void **)operator new(0x38u);
  v117 = v69;
  *(_OWORD *)v69 = 0;
  *((_DWORD *)v69 + 2) = 1;
  *((_DWORD *)v69 + 3) = 1;
  *v69 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<unsigned int,unsigned int>>>>::`vftable';
  std::wstring::wstring(v134, L"WhitePointMappingGamut");
  std::wstring::wstring(
    v133,
    L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\DisplayEnhancementService\\OEMSettings\\V1\\Internal");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::ChromaticityXY>>::OEMSettingFromRegistry<std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::ChromaticityXY>>(
    (_DWORD)v69 + 16,
    -2147483646,
    (unsigned int)v133,
    (unsigned int)v134,
    (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_whitePointMappingGamut,
    (__int64)&v119);
  std::wstring::_Tidy_deallocate(v133);
  std::wstring::_Tidy_deallocate(v134);
  v117 = v69 + 2;
  v118 = (std::_Ref_count_base *)v69;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 82,
    (__int64 *)&v117);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<float,float>>>::`vftable';
  v70 = (void **)operator new(0x38u);
  v117 = v70;
  *(_OWORD *)v70 = 0;
  *((_DWORD *)v70 + 2) = 1;
  *((_DWORD *)v70 + 3) = 1;
  *v70 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<unsigned int,unsigned int>>>>::`vftable';
  std::wstring::wstring(v134, L"HueShiftLut");
  std::wstring::wstring(
    v133,
    L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\DisplayEnhancementService\\OEMSettings\\V1");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<float,float>>>::OEMSettingFromRegistry<std::vector<std::tuple<float,float>>>(
    (_DWORD)v70 + 16,
    -2147483646,
    (unsigned int)v133,
    (unsigned int)v134,
    (__int64)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_hueShiftLut,
    (__int64)&v119);
  std::wstring::_Tidy_deallocate(v133);
  std::wstring::_Tidy_deallocate(v134);
  v117 = v70 + 2;
  v118 = (std::_Ref_count_base *)v70;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 84,
    (__int64 *)&v117);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<float,float>>>::`vftable';
  v71 = (void **)operator new(0x38u);
  v117 = v71;
  *(_OWORD *)v71 = 0;
  *((_DWORD *)v71 + 2) = 1;
  *((_DWORD *)v71 + 3) = 1;
  *v71 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<unsigned int,unsigned int>>>>::`vftable';
  std::wstring::wstring(v134, L"ChromaShiftLut");
  std::wstring::wstring(
    v133,
    L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\DisplayEnhancementService\\OEMSettings\\V1");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<float,float>>>::OEMSettingFromRegistry<std::vector<std::tuple<float,float>>>(
    (_DWORD)v71 + 16,
    -2147483646,
    (unsigned int)v133,
    (unsigned int)v134,
    (__int64)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_chromaShiftLut,
    (__int64)&v119);
  std::wstring::_Tidy_deallocate(v133);
  std::wstring::_Tidy_deallocate(v134);
  v117 = v71 + 2;
  v118 = (std::_Ref_count_base *)v71;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 86,
    (__int64 *)&v117);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<unsigned int,float>>>::`vftable';
  v72 = (void **)operator new(0x38u);
  v117 = v72;
  *(_OWORD *)v72 = 0;
  *((_DWORD *)v72 + 2) = 1;
  *((_DWORD *)v72 + 3) = 1;
  *v72 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<unsigned int,unsigned int>>>>::`vftable';
  std::wstring::wstring(v134, L"LuxBasedStrengthAdaptationLut");
  std::wstring::wstring(
    v133,
    L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\DisplayEnhancementService\\OEMSettings\\V1\\Internal");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<unsigned int,float>>>::OEMSettingFromRegistry<std::vector<std::tuple<unsigned int,float>>>(
    (_DWORD)v72 + 16,
    -2147483646,
    (unsigned int)v133,
    (unsigned int)v134,
    (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_luxBasedStrengthAdaptationLut,
    (__int64)&v119);
  std::wstring::_Tidy_deallocate(v133);
  std::wstring::_Tidy_deallocate(v134);
  v117 = v72 + 2;
  v118 = (std::_Ref_count_base *)v72;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 88,
    (__int64 *)&v117);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>::`vftable';
  v121[0] = -2147483646;
  v74 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<float>,HKEY__ *,unsigned short const (&)[103],unsigned short const (&)[30],float const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>>(
          &v117,
          v121,
          v73,
          (__int64)L"ColorTransitionAccelerationFactor",
          (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_colorTransitionAccelerationFactor,
          (__int64)&v119);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 90,
    v74);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>::`vftable';
  v121[0] = -2147483646;
  v76 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<float>,HKEY__ *,unsigned short const (&)[103],unsigned short const (&)[30],float const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>>(
          &v117,
          v121,
          v75,
          (__int64)L"ColorTransitionDecelerationFactor",
          (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_colorTransitionDecelerationFactor,
          (__int64)&v119);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 92,
    v76);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>::`vftable';
  v121[0] = -2147483646;
  v78 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<float>,HKEY__ *,unsigned short const (&)[103],unsigned short const (&)[30],float const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>>(
          &v117,
          v121,
          v77,
          (__int64)L"ColorTransitionMaxColorChange",
          (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_colorTransitionMaxColorChange,
          (__int64)&v119);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 94,
    v78);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>::`vftable';
  v121[0] = -2147483646;
  v80 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<float>,HKEY__ *,unsigned short const (&)[103],unsigned short const (&)[30],float const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>>(
          &v117,
          v121,
          v79,
          (__int64)L"ColorTransitionMinColorChange",
          (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_colorTransitionMinColorChange,
          (__int64)&v119);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 96,
    v80);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<float,float>>>::`vftable';
  v81 = (void **)operator new(0x38u);
  v117 = v81;
  *(_OWORD *)v81 = 0;
  *((_DWORD *)v81 + 2) = 1;
  *((_DWORD *)v81 + 3) = 1;
  *v81 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<unsigned int,unsigned int>>>>::`vftable';
  std::wstring::wstring(v134, L"ColorTransitionNormalizedChromaTimeLut");
  std::wstring::wstring(
    v133,
    L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\DisplayEnhancementService\\OEMSettings\\V1\\Internal");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<float,float>>>::OEMSettingFromRegistry<std::vector<std::tuple<float,float>>>(
    (_DWORD)v81 + 16,
    -2147483646,
    (unsigned int)v133,
    (unsigned int)v134,
    (__int64)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_colorTransitionNormalizedChromaTimeLut,
    (__int64)&v119);
  std::wstring::_Tidy_deallocate(v133);
  std::wstring::_Tidy_deallocate(v134);
  v117 = v81 + 2;
  v118 = (std::_Ref_count_base *)v81;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 98,
    (__int64 *)&v117);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::chrono::duration<__int64,std::ratio<1,1000>>>::`vftable';
  v82 = (void **)operator new(0x28u);
  v117 = v82;
  *(_OWORD *)v82 = 0;
  *((_DWORD *)v82 + 2) = 1;
  *((_DWORD *)v82 + 3) = 1;
  *v82 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::chrono::duration<__int64,std::ratio<1,1000>>>>::`vftable';
  std::wstring::wstring(v134, L"ColorTransitionMinTransitionTime");
  std::wstring::wstring(
    v133,
    L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\DisplayEnhancementService\\OEMSettings\\V1\\Internal");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::chrono::duration<__int64,std::ratio<1,1000>>>::OEMSettingFromRegistry<std::chrono::duration<__int64,std::ratio<1,1000>>>(
    (_DWORD)v82 + 16,
    -2147483646,
    (unsigned int)v133,
    (unsigned int)v134,
    (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_colorTransitionMinTransitionTime,
    (__int64)&v119);
  std::wstring::_Tidy_deallocate(v133);
  std::wstring::_Tidy_deallocate(v134);
  v117 = v82 + 2;
  v118 = (std::_Ref_count_base *)v82;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 100,
    (__int64 *)&v117);
  if ( v118 )
    std::_Ref_count_base::_Decref(v118);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::chrono::duration<__int64,std::ratio<1,1000>>>::`vftable';
  v83 = (void **)operator new(0x28u);
  v117 = v83;
  *(_OWORD *)v83 = 0;
  *((_DWORD *)v83 + 2) = 1;
  *((_DWORD *)v83 + 3) = 1;
  *v83 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::chrono::duration<__int64,std::ratio<1,1000>>>>::`vftable';
  std::wstring::wstring(v135, L"ColorTransitionBaseTransitionTime");
  std::wstring::wstring(
    v133,
    L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\DisplayEnhancementService\\OEMSettings\\V1\\Internal");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::chrono::duration<__int64,std::ratio<1,1000>>>::OEMSettingFromRegistry<std::chrono::duration<__int64,std::ratio<1,1000>>>(
    (_DWORD)v83 + 16,
    -2147483646,
    (unsigned int)v133,
    (unsigned int)v135,
    (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_colorTransitionBaseTransitionTime,
    (__int64)&v119);
  std::wstring::_Tidy_deallocate(v133);
  std::wstring::_Tidy_deallocate(v135);
  v117 = v83 + 2;
  v118 = (std::_Ref_count_base *)v83;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 102,
    (__int64 *)&v117);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(&v117);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>::`vftable';
  v121[0] = -2147483646;
  v85 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<float>,HKEY__ *,unsigned short const (&)[103],unsigned short const (&)[30],float const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>>(
          v122,
          v121,
          v84,
          (__int64)L"ColorTransitionChromaDeltaThresholdX",
          (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_colorTransitionChromaDeltaThresholdX,
          (__int64)&v119);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 104,
    v85);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v122);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>::`vftable';
  v121[0] = -2147483646;
  v87 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<float>,HKEY__ *,unsigned short const (&)[103],unsigned short const (&)[30],float const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>>(
          v127,
          v121,
          v86,
          (__int64)L"ColorTransitionChromaDeltaThresholdY",
          (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_colorTransitionChromaDeltaThresholdY,
          (__int64)&v119);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 106,
    v87);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v127);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>::`vftable';
  v88 = (void **)operator new(0x20u);
  v117 = v88;
  *(_OWORD *)v88 = 0;
  *((_DWORD *)v88 + 2) = 1;
  *((_DWORD *)v88 + 3) = 1;
  *v88 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable';
  std::wstring::wstring(v135, L"ColorTransitionChromaDeltaThresholdDeltaEab");
  std::wstring::wstring(
    v133,
    L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\DisplayEnhancementService\\OEMSettings\\V1");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<float>::OEMSettingFromRegistry<float>(
    (_DWORD)v88 + 16,
    -2147483646,
    (unsigned int)v133,
    (unsigned int)v135,
    (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_colorTransitionChromaDeltaThresholdDeltaEab,
    (__int64)&v119);
  std::wstring::_Tidy_deallocate(v133);
  std::wstring::_Tidy_deallocate(v135);
  v117 = v88 + 2;
  v118 = (std::_Ref_count_base *)v88;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 108,
    (__int64 *)&v117);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(&v117);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<float,float>>>::`vftable';
  v89 = (void **)operator new(0x38u);
  v117 = v89;
  *(_OWORD *)v89 = 0;
  *((_DWORD *)v89 + 2) = 1;
  *((_DWORD *)v89 + 3) = 1;
  *v89 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<unsigned int,unsigned int>>>>::`vftable';
  std::wstring::wstring(v135, L"ColorFusionCctCafReductionLut");
  std::wstring::wstring(
    v133,
    L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\DisplayEnhancementService\\OEMSettings\\V1\\Internal");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<float,float>>>::OEMSettingFromRegistry<std::vector<std::tuple<float,float>>>(
    (_DWORD)v89 + 16,
    -2147483646,
    (unsigned int)v133,
    (unsigned int)v135,
    (__int64)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_colorFusionCctCafReductionLut,
    (__int64)&v119);
  std::wstring::_Tidy_deallocate(v133);
  std::wstring::_Tidy_deallocate(v135);
  v117 = v89 + 2;
  v118 = (std::_Ref_count_base *)v89;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 110,
    (__int64 *)&v117);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(&v117);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>::`vftable';
  v90 = (void **)operator new(0x20u);
  v117 = v90;
  *(_OWORD *)v90 = 0;
  *((_DWORD *)v90 + 2) = 1;
  *((_DWORD *)v90 + 3) = 1;
  *v90 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable';
  std::wstring::wstring(v135, L"ColorFusionMinCaf");
  std::wstring::wstring(
    v133,
    L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\DisplayEnhancementService\\OEMSettings\\V1\\Internal");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<float>::OEMSettingFromRegistry<float>(
    (_DWORD)v90 + 16,
    -2147483646,
    (unsigned int)v133,
    (unsigned int)v135,
    (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_colorFusionMinCaf,
    (__int64)&v119);
  std::wstring::_Tidy_deallocate(v133);
  std::wstring::_Tidy_deallocate(v135);
  v117 = v90 + 2;
  v118 = (std::_Ref_count_base *)v90;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 112,
    (__int64 *)&v117);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(&v117);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>::`vftable';
  v91 = (void **)operator new(0x20u);
  v117 = v91;
  *(_OWORD *)v91 = 0;
  *((_DWORD *)v91 + 2) = 1;
  *((_DWORD *)v91 + 3) = 1;
  *v91 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable';
  std::wstring::wstring(v135, L"ColorFusionTintAccuracyThreshold");
  std::wstring::wstring(
    v133,
    L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\DisplayEnhancementService\\OEMSettings\\V1\\Internal");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<float>::OEMSettingFromRegistry<float>(
    (_DWORD)v91 + 16,
    -2147483646,
    (unsigned int)v133,
    (unsigned int)v135,
    (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_colorFusionTintAccuracyThreshold,
    (__int64)&v119);
  std::wstring::_Tidy_deallocate(v133);
  std::wstring::_Tidy_deallocate(v135);
  v117 = v91 + 2;
  v118 = (std::_Ref_count_base *)v91;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 114,
    (__int64 *)&v117);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(&v117);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::chrono::duration<__int64,std::ratio<1,1000>>>::`vftable';
  v92 = (void **)operator new(0x28u);
  v117 = v92;
  *(_OWORD *)v92 = 0;
  *((_DWORD *)v92 + 2) = 1;
  *((_DWORD *)v92 + 3) = 1;
  *v92 = &std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::chrono::duration<__int64,std::ratio<1,1000>>>>::`vftable';
  std::wstring::wstring(v135, L"ColorSensorFilterAverageTime");
  std::wstring::wstring(
    v133,
    L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\DisplayEnhancementService\\OEMSettings\\V1\\Internal");
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::chrono::duration<__int64,std::ratio<1,1000>>>::OEMSettingFromRegistry<std::chrono::duration<__int64,std::ratio<1,1000>>>(
    (_DWORD)v92 + 16,
    -2147483646,
    (unsigned int)v133,
    (unsigned int)v135,
    (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_colorSensorFilterAverageTimerPeriod,
    (__int64)&v119);
  std::wstring::_Tidy_deallocate(v133);
  std::wstring::_Tidy_deallocate(v135);
  v117 = v92 + 2;
  v118 = (std::_Ref_count_base *)v92;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 116,
    (__int64 *)&v117);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(&v117);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>::`vftable';
  v121[0] = -2147483646;
  v94 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<float>,HKEY__ *,unsigned short const (&)[103],unsigned short const (&)[30],float const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>>(
          v128,
          v121,
          v93,
          (__int64)L"ColorSensorFilterWeightFactor",
          (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_colorSensorFilterWeightFactor,
          (__int64)&v119);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 118,
    v94);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v128);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned char>::`vftable';
  v97 = (__int64 *)std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>,unsigned short const (&)[23],bool const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::BoolSettingValidator,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::PolicyAdapter> &>(
                     (unsigned int)v129,
                     v95,
                     v96,
                     (unsigned int)&v119,
                     (__int64)(this + 128));
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 120,
    v97);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v129);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned int>::`vftable';
  v121[0] = -2147483646;
  v100 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<unsigned int>,HKEY__ *,unsigned short const (&)[103],unsigned short const (&)[47],unsigned int const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<unsigned int>>(
           v130,
           v121,
           v98,
           v99,
           v115,
           (__int64)&v119);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 122,
    v100);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v130);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>::`vftable';
  v121[0] = -2147483646;
  v102 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<float>,HKEY__ *,unsigned short const (&)[103],unsigned short const (&)[30],float const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>>(
           v131,
           v121,
           v101,
           (__int64)L"TelemetryColorTransitionChromaDeltaThresholdX",
           (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_telemetryColorTransitionChromaDeltaThresholdX,
           (__int64)&v119);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 124,
    v102);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v131);
  v119 = &Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>::`vftable';
  v121[0] = -2147483646;
  v104 = std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<float>,HKEY__ *,unsigned short const (&)[103],unsigned short const (&)[30],float const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<float>>(
           v132,
           v121,
           v103,
           (__int64)L"TelemetryColorTransitionChromaDeltaThresholdY",
           (__int64)&Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_telemetryColorTransitionChromaDeltaThresholdY,
           (__int64)&v119);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 126,
    v104);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v132);
  v123 = *(_BYTE *)(*(_QWORD *)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerDesktopImpl::GetIsLuxHysteresisAndPersistenceFilterEnabled(
                                 this,
                                 v134)
                  + 8LL);
  v105 = *(_DWORD *)(*(_QWORD *)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerDesktopImpl::GetMaxRelativeBrightnessHysteresisThreshold(
                                  this,
                                  v135)
                   + 8LL);
  v124 = *(_BYTE *)(*(_QWORD *)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerDesktopImpl::GetWhitePointMappingLowLightWhitePoint(
                                 this,
                                 v122)
                  + 8LL);
  v106 = *(_DWORD *)(*(_QWORD *)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerWCOSImpl::GetDefaultAdaptiveColorAdaptationStrength(
                                  this,
                                  v121)
                   + 8LL);
  v107 = *(_BYTE *)(*(_QWORD *)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerWCOSImpl::GetIsAdaptiveOnByDefault(
                                 this,
                                 &v119)
                  + 8LL);
  v108 = *(_BYTE *)(*(_QWORD *)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerDesktopImpl::GetShouldStopTransitionsDuringHandsOnDisplay(
                                 this,
                                 v127)
                  + 8LL);
  AutobrightnessLuxToNitsCurve = (_QWORD *)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerDesktopImpl::GetAutobrightnessLuxToNitsCurve(
                                             this,
                                             v128);
  Value = Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsCurve>::GetValue(
            *AutobrightnessLuxToNitsCurve,
            v133);
  v111 = *(_DWORD *)(*(_QWORD *)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerDesktopImpl::GetDefaultBatterySaverBrightnessMultiplier(
                                  this,
                                  v129)
                   + 8LL);
  LODWORD(v92) = *(_DWORD *)(*(_QWORD *)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerWCOSImpl::GetDefaultDimBrightnessMultiplier(
                                          v125,
                                          v130)
                           + 8LL);
  v112 = *(_DWORD *)(*(_QWORD *)Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerWCOSImpl::GetDefaultSliderPosition(
                                  v125,
                                  v131)
                   + 8LL);
  IsAutobrightnessEnabledByDefault = Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerDesktopImpl::GetIsAutobrightnessEnabledByDefault(
                                       v125,
                                       v132);
  v114 = *(_QWORD *)IsAutobrightnessEnabledByDefault;
  LOBYTE(v116) = v108;
  LOBYTE(v114) = *(_BYTE *)(*(_QWORD *)IsAutobrightnessEnabledByDefault + 8LL);
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetryProvider::WriteOEMSettingsEvent(
    v114,
    v112,
    (unsigned int)v92,
    v111,
    Value,
    v116,
    v107,
    v106,
    v124,
    v105,
    v123);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v132);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v131);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v130);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v129);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v128);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v127);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(&v119);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v121);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v122);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v135);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v134);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v126);
}

```

## disassembly

```asm
0x18008f294  mov     rax, rsp
0x18008f297  push    rbp
0x18008f298  push    rbx
0x18008f299  push    rsi
0x18008f29a  push    rdi
0x18008f29b  push    r12
0x18008f29d  push    r13
0x18008f29f  push    r14
0x18008f2a1  push    r15
0x18008f2a3  lea     rbp, [rax-0D8h]
0x18008f2aa  sub     rsp, 198h
0x18008f2b1  movaps  xmmword ptr [rax-58h], xmm6
0x18008f2b5  mov     rax, cs:__security_cookie
0x18008f2bc  xor     rax, rsp
0x18008f2bf  mov     qword ptr [rbp+0D0h+var_58], rax
0x18008f2c3  mov     rsi, rcx
0x18008f2c6  mov     [rbp+0D0h+var_128], rcx
0x18008f2ca  xor     r15d, r15d
0x18008f2cd  lea     rcx, [rbp+0D0h+var_120]
0x18008f2d1  call    ?GetServiceRegistryStateKey@?$ServiceHostService@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4SERVICE_REGISTRY_STATE_TYPE@@K@Z; Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::GetServiceRegistryStateKey(SERVICE_REGISTRY_STATE_TYPE,ulong)
0x18008f2d6  nop
0x18008f2d7  lea     rax, ??_7?$NoOpSettingValidator@E@OEMSettings@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<uchar>::`vftable'
0x18008f2de  mov     [rbp+0D0h+var_150], rax
0x18008f2e2  lea     r13d, [r15+20h]
0x18008f2e6  mov     ecx, r13d; Size
0x18008f2e9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008f2ee  mov     rdi, rax
0x18008f2f1  mov     [rsp+1D0h+var_160], rax
0x18008f2f6  lea     r14, [rsi+400h]
0x18008f2fd  xorps   xmm0, xmm0
0x18008f300  movups  xmmword ptr [rax], xmm0
0x18008f303  lea     r12d, [r15+1]
0x18008f307  mov     [rax+8], r12d
0x18008f30b  mov     [rax+0Ch], r12d
0x18008f30f  lea     rax, ??_7?$_Ref_count_obj2@V?$OEMSettingFromPolicy@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable'
0x18008f316  mov     [rdi], rax
0x18008f319  lea     rbx, [rdi+10h]
0x18008f31d  lea     rdx, aIsautobrightne_0; "IsAutobrightnessOnByDefault"
0x18008f324  lea     rcx, [rbp+0D0h+var_B8]
0x18008f328  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008f32d  nop
0x18008f32e  mov     [rsp+1D0h+var_1B0], r14
0x18008f333  lea     r9, [rbp+0D0h+var_150]
0x18008f337  lea     r8, ?c_isAutobrightnessOnByDefaultDefaultValue@OEMSettingsManagerWCOSImpl@OEMSettings@DisplayEnhancement@Windows@Microsoft@@2_NB; bool const Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerWCOSImpl::c_isAutobrightnessOnByDefaultDefaultValue
0x18008f33e  lea     rdx, [rbp+0D0h+var_B8]
0x18008f342  mov     rcx, rbx
0x18008f345  call    ??0?$OEMSettingFromPolicy@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEB_NAEBU?$OEMSettingValidator@_N@1234@AEBV?$shared_ptr@VPolicyAdapter@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@6@@Z; Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>::OEMSettingFromPolicy<bool>(std::wstring const &,bool const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingValidator<bool> const &,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::PolicyAdapter> const &)
0x18008f34a  nop
0x18008f34b  lea     rcx, [rbp+0D0h+var_B8]
0x18008f34f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008f354  nop
0x18008f355  mov     [rsp+1D0h+var_170], rbx
0x18008f35a  mov     [rsp+1D0h+var_168], rdi
0x18008f35f  lea     rcx, [rsi+10h]
0x18008f363  lea     rdx, [rsp+1D0h+var_170]
0x18008f368  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x18008f36d  mov     rcx, [rsp+1D0h+var_168]; this
0x18008f372  test    rcx, rcx
0x18008f375  jz      short loc_18008F37C
0x18008f377  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f37c  lea     rax, ??_7?$BoundsOEMSettingValidator@K@OEMSettings@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::OEMSettings::BoundsOEMSettingValidator<ulong>::`vftable'
0x18008f383  mov     [rsp+1D0h+var_170], rax
0x18008f388  mov     dword ptr [rsp+1D0h+var_168], r15d
0x18008f38d  mov     dword ptr [rsp+1D0h+var_168+4], 64h ; 'd'
0x18008f395  mov     rcx, r13; Size
0x18008f398  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008f39d  mov     rdi, rax
0x18008f3a0  mov     [rsp+1D0h+var_160], rax
0x18008f3a5  xorps   xmm0, xmm0
0x18008f3a8  movups  xmmword ptr [rax], xmm0
0x18008f3ab  mov     [rax+8], r12d
0x18008f3af  mov     [rax+0Ch], r12d
0x18008f3b3  lea     rax, ??_7?$_Ref_count_obj2@V?$OEMSettingFromPolicy@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable'
0x18008f3ba  mov     [rdi], rax
0x18008f3bd  lea     rbx, [rdi+10h]
0x18008f3c1  lea     rdx, aDefaultbrightn; "DefaultBrightnessSliderPercentage"
0x18008f3c8  lea     rcx, [rbp+0D0h+var_B8]
0x18008f3cc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008f3d1  nop
0x18008f3d2  mov     [rsp+1D0h+var_1B0], r14
0x18008f3d7  lea     r9, [rsp+1D0h+var_170]
0x18008f3dc  lea     r8, ?c_defaultBrightnessSliderPercentageDefaultValue@OEMSettingsManagerWCOSImpl@OEMSettings@DisplayEnhancement@Windows@Microsoft@@2KB; ulong const Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerWCOSImpl::c_defaultBrightnessSliderPercentageDefaultValue
0x18008f3e3  lea     rdx, [rbp+0D0h+var_B8]
0x18008f3e7  mov     rcx, rbx
0x18008f3ea  call    ??0?$OEMSettingFromPolicy@K@OEMSettings@DisplayEnhancement@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBKAEBU?$OEMSettingValidator@K@1234@AEBV?$shared_ptr@VPolicyAdapter@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@6@@Z; Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<ulong>::OEMSettingFromPolicy<ulong>(std::wstring const &,ulong const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingValidator<ulong> const &,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::PolicyAdapter> const &)
0x18008f3ef  nop
0x18008f3f0  lea     rcx, [rbp+0D0h+var_B8]
0x18008f3f4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008f3f9  nop
0x18008f3fa  mov     [rsp+1D0h+var_160], rbx
0x18008f3ff  mov     [rsp+1D0h+var_158], rdi
0x18008f404  lea     rcx, [rsi+20h]
0x18008f408  lea     rdx, [rsp+1D0h+var_160]
0x18008f40d  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x18008f412  mov     rcx, [rsp+1D0h+var_158]; this
0x18008f417  test    rcx, rcx
0x18008f41a  jz      short loc_18008F421
0x18008f41c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f421  lea     rax, ??_7?$BoundsOEMSettingValidator@K@OEMSettings@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::OEMSettings::BoundsOEMSettingValidator<ulong>::`vftable'
0x18008f428  mov     [rsp+1D0h+var_170], rax
0x18008f42d  mov     dword ptr [rsp+1D0h+var_168], r15d
0x18008f432  mov     dword ptr [rsp+1D0h+var_168+4], 64h ; 'd'
0x18008f43a  mov     rcx, r13; Size
0x18008f43d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008f442  mov     rdi, rax
0x18008f445  mov     [rsp+1D0h+var_160], rax
0x18008f44a  xorps   xmm0, xmm0
0x18008f44d  movups  xmmword ptr [rax], xmm0
0x18008f450  mov     [rax+8], r12d
0x18008f454  mov     [rax+0Ch], r12d
0x18008f458  lea     rax, ??_7?$_Ref_count_obj2@V?$OEMSettingFromPolicy@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable'
0x18008f45f  mov     [rdi], rax
0x18008f462  lea     rbx, [rdi+10h]
0x18008f466  lea     rdx, aDefaultdimbrig; "DefaultDimBrightnessMultiplier"
0x18008f46d  lea     rcx, [rbp+0D0h+var_B8]
0x18008f471  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008f476  nop
0x18008f477  mov     [rsp+1D0h+var_1B0], r14
0x18008f47c  lea     r9, [rsp+1D0h+var_170]
0x18008f481  lea     r8, ?c_defaultDimBrightnessMultiplierDefaultValue@OEMSettingsManagerWCOSImpl@OEMSettings@DisplayEnhancement@Windows@Microsoft@@2KB; ulong const Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerWCOSImpl::c_defaultDimBrightnessMultiplierDefaultValue
0x18008f488  lea     rdx, [rbp+0D0h+var_B8]
0x18008f48c  mov     rcx, rbx
0x18008f48f  call    ??0?$OEMSettingFromPolicy@K@OEMSettings@DisplayEnhancement@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBKAEBU?$OEMSettingValidator@K@1234@AEBV?$shared_ptr@VPolicyAdapter@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@6@@Z; Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<ulong>::OEMSettingFromPolicy<ulong>(std::wstring const &,ulong const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingValidator<ulong> const &,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::PolicyAdapter> const &)
0x18008f494  nop
0x18008f495  lea     rcx, [rbp+0D0h+var_B8]
0x18008f499  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008f49e  nop
0x18008f49f  mov     [rsp+1D0h+var_160], rbx
0x18008f4a4  mov     [rsp+1D0h+var_158], rdi
0x18008f4a9  lea     rcx, [rsi+30h]
0x18008f4ad  lea     rdx, [rsp+1D0h+var_160]
0x18008f4b2  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x18008f4b7  mov     rcx, [rsp+1D0h+var_158]; this
0x18008f4bc  test    rcx, rcx
0x18008f4bf  jz      short loc_18008F4C6
0x18008f4c1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f4c6  lea     rax, ??_7?$BoundsOEMSettingValidator@K@OEMSettings@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::OEMSettings::BoundsOEMSettingValidator<ulong>::`vftable'
0x18008f4cd  mov     [rsp+1D0h+var_170], rax
0x18008f4d2  mov     dword ptr [rsp+1D0h+var_168], r15d
0x18008f4d7  mov     dword ptr [rsp+1D0h+var_168+4], 64h ; 'd'
0x18008f4df  mov     rcx, r13; Size
0x18008f4e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008f4e7  mov     rdi, rax
0x18008f4ea  mov     [rsp+1D0h+var_160], rax
0x18008f4ef  xorps   xmm0, xmm0
0x18008f4f2  movups  xmmword ptr [rax], xmm0
0x18008f4f5  mov     [rax+8], r12d
0x18008f4f9  mov     [rax+0Ch], r12d
0x18008f4fd  lea     rax, ??_7?$_Ref_count_obj2@V?$OEMSettingFromPolicy@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable'
0x18008f504  mov     [rdi], rax
0x18008f507  lea     rbx, [rdi+10h]
0x18008f50b  lea     rdx, aDefaultbattery; "DefaultBatterySaverBrightnessMultiplier"
0x18008f512  lea     rcx, [rbp+0D0h+var_B8]
0x18008f516  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008f51b  nop
0x18008f51c  mov     [rsp+1D0h+var_1B0], r14
0x18008f521  lea     r9, [rsp+1D0h+var_170]
0x18008f526  lea     r8, ?c_defaultBatterySaverBrightnessMultiplierDefaultValue@OEMSettingsManagerWCOSImpl@OEMSettings@DisplayEnhancement@Windows@Microsoft@@2KB; ulong const Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerWCOSImpl::c_defaultBatterySaverBrightnessMultiplierDefaultValue
0x18008f52d  lea     rdx, [rbp+0D0h+var_B8]
0x18008f531  mov     rcx, rbx
0x18008f534  call    ??0?$OEMSettingFromPolicy@K@OEMSettings@DisplayEnhancement@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBKAEBU?$OEMSettingValidator@K@1234@AEBV?$shared_ptr@VPolicyAdapter@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@6@@Z; Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<ulong>::OEMSettingFromPolicy<ulong>(std::wstring const &,ulong const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingValidator<ulong> const &,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::PolicyAdapter> const &)
0x18008f539  nop
0x18008f53a  lea     rcx, [rbp+0D0h+var_B8]
0x18008f53e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008f543  nop
0x18008f544  mov     [rsp+1D0h+var_160], rbx
0x18008f549  mov     [rsp+1D0h+var_158], rdi
0x18008f54e  lea     rcx, [rsi+40h]
0x18008f552  lea     rdx, [rsp+1D0h+var_160]
0x18008f557  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x18008f55c  mov     rcx, [rsp+1D0h+var_158]; this
0x18008f561  test    rcx, rcx
0x18008f564  jz      short loc_18008F56B
0x18008f566  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f56b  lea     rax, ??_7CurveOEMSettingValidator@OEMSettings@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::OEMSettings::CurveOEMSettingValidator::`vftable'
0x18008f572  mov     [rbp+0D0h+var_150], rax
0x18008f576  mov     r13d, 38h ; '8'
0x18008f57c  mov     ecx, r13d; Size
0x18008f57f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008f584  mov     rdi, rax
0x18008f587  mov     [rsp+1D0h+var_160], rax
0x18008f58c  xorps   xmm0, xmm0
0x18008f58f  movups  xmmword ptr [rax], xmm0
0x18008f592  mov     [rax+8], r12d
0x18008f596  mov     [rax+0Ch], r12d
0x18008f59a  lea     rax, ??_7?$_Ref_count_obj2@V?$OEMSettingFromRegistry@V?$vector@V?$tuple@II@std@@V?$allocator@V?$tuple@II@std@@@2@@std@@@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<uint,uint>>>>::`vftable'
0x18008f5a1  mov     [rdi], rax
0x18008f5a4  lea     rbx, [rdi+10h]
0x18008f5a8  lea     rdx, aAutobrightness_1; "AutobrightnessLuxToNitsCurve"
0x18008f5af  lea     rcx, [rbp+0D0h+var_B8]
0x18008f5b3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008f5b8  nop
0x18008f5b9  lea     r9, ?c_autobrightnessLuxToNitsCurveDefaultValue@OEMSettingsManager@OEMSettings@DisplayEnhancement@Windows@Microsoft@@2UMilliLuxToMilliNitsCurve@Foundation@345@B; Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsCurve const Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_autobrightnessLuxToNitsCurveDefaultValue
0x18008f5c0  lea     r8, [rbp+0D0h+var_B8]
0x18008f5c4  mov     rdx, r14
0x18008f5c7  lea     rcx, [rbp+0D0h+var_98]; this
0x18008f5cb  call    ?QueryValueFromPolicy@?$OEMSettingFromPolicy@UMilliLuxToMilliNitsCurve@Foundation@DisplayEnhancement@Windows@Microsoft@@@OEMSettings@DisplayEnhancement@Windows@Microsoft@@SA?AUMilliLuxToMilliNitsCurve@Foundation@345@AEBV?$shared_ptr@VPolicyAdapter@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@9@AEBU67345@@Z; Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsCurve>::QueryValueFromPolicy(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::PolicyAdapter> const &,std::wstring const &,Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsCurve const &)
0x18008f5d0  nop
0x18008f5d1  lea     r8, [rbp+0D0h+var_150]
0x18008f5d5  mov     rdx, rax
0x18008f5d8  mov     rcx, rbx
0x18008f5db  call    ??0?$OEMSetting@UMilliLuxToMilliNitsCurve@Foundation@DisplayEnhancement@Windows@Microsoft@@@OEMSettings@DisplayEnhancement@Windows@Microsoft@@QEAA@AEBUMilliLuxToMilliNitsCurve@Foundation@234@AEBU?$OEMSettingValidator@UMilliLuxToMilliNitsCurve@Foundation@DisplayEnhancement@Windows@Microsoft@@@1234@@Z; Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsCurve>::OEMSetting<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsCurve>(Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsCurve const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingValidator<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsCurve> const &)
0x18008f5e0  nop
0x18008f5e1  lea     rcx, [rbp+0D0h+var_98]
0x18008f5e5  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@VClientContextHandle@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>(void)
0x18008f5ea  lea     rax, ??_7?$OEMSettingFromRegistry@V?$vector@UChromaticityXY@Foundation@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UChromaticityXY@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@@OEMSettings@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::ChromaticityXY>>::`vftable'
0x18008f5f1  mov     [rbx], rax
0x18008f5f4  lea     rcx, [rbp+0D0h+var_B8]
0x18008f5f8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008f5fd  nop
0x18008f5fe  mov     [rsi+50h], rbx
0x18008f602  mov     rcx, [rsi+58h]; this
0x18008f606  mov     [rsi+58h], rdi
0x18008f60a  test    rcx, rcx
0x18008f60d  jz      short loc_18008F614
0x18008f60f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f614  lea     rax, ??_7BucketMappingOEMSettingValidator@OEMSettings@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::OEMSettings::BucketMappingOEMSettingValidator::`vftable'
0x18008f61b  mov     [rbp+0D0h+var_150], rax
0x18008f61f  mov     rcx, r13; Size
0x18008f622  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008f627  mov     rdi, rax
0x18008f62a  mov     [rsp+1D0h+var_160], rax
0x18008f62f  xorps   xmm0, xmm0
0x18008f632  movups  xmmword ptr [rax], xmm0
0x18008f635  mov     [rax+8], r12d
0x18008f639  mov     [rax+0Ch], r12d
0x18008f63d  lea     rax, ??_7?$_Ref_count_obj2@V?$OEMSettingFromRegistry@UBucketedMilliLuxToPercentageCurve@Foundation@DisplayEnhancement@Windows@Microsoft@@@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<Microsoft::Windows::DisplayEnhancement::Foundation::BucketedMilliLuxToPercentageCurve>>::`vftable'
0x18008f644  mov     [rdi], rax
0x18008f647  lea     rbx, [rdi+10h]
0x18008f64b  lea     rdx, aAutobrightness_5; "AutobrightnessBucketMapping"
0x18008f652  lea     rcx, [rbp+0D0h+var_98]
0x18008f656  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008f65b  nop
0x18008f65c  lea     rdx, ?c_rootKeyPath@OEMSettingsManagerWCOSImpl@OEMSettings@DisplayEnhancement@Windows@Microsoft@@0QBGB; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x18008f663  lea     rcx, [rbp+0D0h+var_B8]
0x18008f667  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008f66c  nop
0x18008f66d  lea     rax, [rbp+0D0h+var_150]
0x18008f671  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x18008f676  lea     rax, ?c_autobrightnessBucketMapping@OEMSettingsManager@OEMSettings@DisplayEnhancement@Windows@Microsoft@@2UBucketedMilliLuxToPercentageCurve@Foundation@345@B; Microsoft::Windows::DisplayEnhancement::Foundation::BucketedMilliLuxToPercentageCurve const Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_autobrightnessBucketMapping
0x18008f67d  mov     [rsp+1D0h+var_1B0], rax
0x18008f682  lea     r9, [rbp+0D0h+var_98]
0x18008f686  lea     r8, [rbp+0D0h+var_B8]
0x18008f68a  mov     r13, 0FFFFFFFF80000002h
0x18008f691  mov     rdx, r13
0x18008f694  mov     rcx, rbx
0x18008f697  call    ??0?$OEMSettingFromRegistry@UBucketedMilliLuxToPercentageCurve@Foundation@DisplayEnhancement@Windows@Microsoft@@@OEMSettings@DisplayEnhancement@Windows@Microsoft@@QEAA@QEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEBUBucketedMilliLuxToPercentageCurve@Foundation@234@AEBU?$OEMSettingValidator@UBucketedMilliLuxToPercentageCurve@Foundation@DisplayEnhancement@Windows@Microsoft@@@1234@@Z; Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<Microsoft::Windows::DisplayEnhancement::Foundation::BucketedMilliLuxToPercentageCurve>::OEMSettingFromRegistry<Microsoft::Windows::DisplayEnhancement::Foundation::BucketedMilliLuxToPercentageCurve>(HKEY__ * const,std::wstring const &,std::wstring const &,Microsoft::Windows::DisplayEnhancement::Foundation::BucketedMilliLuxToPercentageCurve const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingValidator<Microsoft::Windows::DisplayEnhancement::Foundation::BucketedMilliLuxToPercentageCurve> const &)
0x18008f69c  nop
0x18008f69d  lea     rcx, [rbp+0D0h+var_B8]
0x18008f6a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008f6a6  nop
0x18008f6a7  lea     rcx, [rbp+0D0h+var_98]
0x18008f6ab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008f6b0  nop
0x18008f6b1  mov     [rsp+1D0h+var_170], rbx
0x18008f6b6  mov     [rsp+1D0h+var_168], rdi
0x18008f6bb  lea     rcx, [rsi+60h]
0x18008f6bf  lea     rdx, [rsp+1D0h+var_170]
0x18008f6c4  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x18008f6c9  mov     rcx, [rsp+1D0h+var_168]; this
0x18008f6ce  test    rcx, rcx
0x18008f6d1  jz      short loc_18008F6D8
0x18008f6d3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f6d8  lea     rax, ??_7?$NoOpSettingValidator@V?$vector@V?$tuple@II@std@@V?$allocator@V?$tuple@II@std@@@2@@std@@@OEMSettings@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<uint,uint>>>::`vftable'
0x18008f6df  mov     [rbp+0D0h+var_150], rax
0x18008f6e3  mov     [rbp+0D0h+var_140], r13
0x18008f6e7  lea     rax, [rbp+0D0h+var_150]
0x18008f6eb  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x18008f6f0  lea     rax, ?c_defaultUpperBrightness2HysteresisLut@OEMSettingsManager@OEMSettings@DisplayEnhancement@Windows@Microsoft@@2V?$vector@V?$tuple@II@std@@V?$allocator@V?$tuple@II@std@@@2@@std@@B; std::vector<std::tuple<uint,uint>> const Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::c_defaultUpperBrightness2HysteresisLut
0x18008f6f7  mov     [rsp+1D0h+var_1B0], rax
0x18008f6fc  lea     r9, aUpperbrightnes; "UpperBrightnessHysteresisLut"
0x18008f703  lea     rdx, [rbp+0D0h+var_140]
0x18008f707  lea     rcx, [rsp+1D0h+var_170]
0x18008f70c  call    ??$make_shared@V?$OEMSettingFromRegistry@V?$vector@V?$tuple@II@std@@V?$allocator@V?$tuple@II@std@@@2@@std@@@OEMSettings@DisplayEnhancement@Windows@Microsoft@@PEAUHKEY__@@AEAY0FO@$$CBGAEAY0CO@$$CBGAEBV?$vector@V?$tuple@II@std@@V?$allocator@V?$tuple@II@std@@@2@@std@@U?$NoOpSettingValidator@V?$vector@V?$tuple@II@std@@V?$allocator@V?$tuple@II@std@@@2@@std@@@2345@@std@@YA?AV?$shared_ptr@V?$OEMSettingFromRegistry@V?$vector@V?$tuple@II@std@@V?$allocator@V?$tuple@II@std@@@2@@std@@@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@0@$$QEAPEAUHKEY__@@AEAY0FO@$$CBGAEAY0CO@$$CBGAEBV?$vector@V?$tuple@II@std@@V?$allocator@V?$tuple@II@std@@@2@@0@$$QEAU?$NoOpSettingValidator@V?$vector@V?$tuple@II@std@@V?$allocator@V?$tuple@II@std@@@2@@std@@@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@Z; std::make_shared<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<std::vector<std::tuple<uint,uint>>>,HKEY__ *,ushort const (&)[94],ushort const (&)[46],std::vector<std::tuple<uint,uint>> const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<uint,uint>>>>(HKEY__ * &&,ushort const (&)[94],ushort const (&)[46],std::vector<std::tuple<uint,uint>> const &,Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<std::vector<std::tuple<uint,uint>>> &&)
0x18008f711  lea     rcx, [rsi+70h]
0x18008f715  mov     rdx, rax
0x18008f718  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x18008f71d  mov     rcx, [rsp+1D0h+var_168]; this
0x18008f722  test    rcx, rcx
0x18008f725  jz      short loc_18008F72C
0x18008f727  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f72c  lea     rax, ??_7?$NoOpSettingValidator@E@OEMSettings@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::OEMSettings::NoOpSettingValidator<uchar>::`vftable'
0x18008f733  mov     [rbp+0D0h+var_150], rax
0x18008f737  mov     ecx, 20h ; ' '; Size
0x18008f73c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008f741  mov     rdi, rax
0x18008f744  mov     [rsp+1D0h+var_160], rax
0x18008f749  xorps   xmm0, xmm0
0x18008f74c  movups  xmmword ptr [rax], xmm0
0x18008f74f  mov     [rax+8], r12d
0x18008f753  mov     [rax+0Ch], r12d
0x18008f757  lea     rax, ??_7?$_Ref_count_obj2@V?$OEMSettingFromPolicy@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromPolicy<bool>>::`vftable'
0x18008f75e  mov     [rdi], rax
0x18008f761  lea     rbx, [rdi+10h]
0x18008f765  lea     rdx, aEnableluxhyste; "EnableLuxHysteresisAndPersistenceFilter"
0x18008f76c  lea     rcx, [rbp+0D0h+var_98]
0x18008f770  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008f775  nop
0x18008f776  lea     rdx, ?c_rootKeyPath@OEMSettingsManagerWCOSImpl@OEMSettings@DisplayEnhancement@Windows@Microsoft@@0QBGB; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x18008f77d  lea     rcx, [rbp+0D0h+var_B8]
  ... truncated ...
```
