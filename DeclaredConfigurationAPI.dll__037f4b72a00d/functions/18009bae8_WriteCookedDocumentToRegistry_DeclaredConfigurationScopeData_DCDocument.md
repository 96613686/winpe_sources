# WriteCookedDocumentToRegistry(DeclaredConfigurationScopeData *,DCDocument *)

- ea: `0x18009bae8`
- end: `0x18009c3dc`
- name: `?WriteCookedDocumentToRegistry@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@@Z`
- size: `2292`
- prototype: `__int64 __fastcall(struct DeclaredConfigurationScopeData *, struct DCDocument *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009468c`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180011fe0`
- `0x18001440c`
- `0x180018744`
- `0x18001ce5c`
- `0x18001d0b0`
- `0x18004b870`
- `0x1800590c8`
- `0x18005ee00`
- `0x18005eeb8`
- `0x180086c10`
- `0x180098fb4`
- `0x18009b2e4`
- `0x18009bae8`
- `0x18009ff30`
- `0x1800c7da4`
- `0x180100e3c`
- `0x18010136c`
- `0x18012d59c`
- `0x180139010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009c1bd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009c1bd`
- `OLEAUT32!__imp_VariantInit` at `0x18009c0c7`
- `OLEAUT32!__imp_VariantInit` at `0x18009c0c7`
- `OLEAUT32!__imp_VariantClear` at `0x18009c20f`
- `OLEAUT32!__imp_VariantClear` at `0x18009c292`
- `OLEAUT32!__imp_VariantClear` at `0x18009c315`
- `OLEAUT32!__imp_VariantClear` at `0x18009c35c`
- `OLEAUT32!__imp_VariantClear` at `0x18009c3ba`
- `OLEAUT32!__imp_VariantClear` at `0x18009c20f`
- `OLEAUT32!__imp_VariantClear` at `0x18009c292`
- `OLEAUT32!__imp_VariantClear` at `0x18009c315`
- `OLEAUT32!__imp_VariantClear` at `0x18009c35c`
- `OLEAUT32!__imp_VariantClear` at `0x18009c3ba`

## string_xrefs

- `0x18009bf42`: `osconfigscenario`
- `0x18009bf9a`: `osconfigscenarioschema`
- `0x18009bfef`: `osconfigscenariosVersion`
- `0x18009bb84`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009bbf7`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009c1eb`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009c26e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009c2f1`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WriteCookedDocumentToRegistry(struct DeclaredConfigurationScopeData *a1, struct DCDocument *a2)
{
  struct DCDocument *v2; // rdi
  char *v4; // r12
  const unsigned __int16 *v5; // r8
  int CookedSettingsDSCNativeProvider; // ebx
  const unsigned __int16 *v8; // rdx
  __int64 v9; // rdx
  unsigned __int64 v10; // r9
  int v11; // r14d
  _QWORD *v12; // rsi
  _QWORD *v13; // r15
  int v14; // eax
  const unsigned __int16 ***v15; // rax
  int v16; // r8d
  const unsigned __int16 *v17; // r9
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  const unsigned __int16 *v24; // r9
  int v25; // eax
  const unsigned __int16 *v26; // r9
  int v27; // eax
  const unsigned __int16 *v28; // r9
  int v29; // eax
  const unsigned __int16 *v30; // r9
  const unsigned __int16 *v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // r9
  int v34; // eax
  int v35; // eax
  int v36; // eax
  __int64 v37; // rdx
  const unsigned __int16 *v38; // r9
  int v39; // eax
  const unsigned __int16 *v40; // rdx
  LSTATUS v41; // eax
  int v42; // esi
  __int64 v43; // rbx
  int v44; // eax
  unsigned int v45; // edi
  const unsigned __int16 *v46; // r9
  int v47; // eax
  unsigned int v48; // ebx
  int dwOptions; // [rsp+20h] [rbp-F8h]
  int dwOptionsa; // [rsp+20h] [rbp-F8h]
  HKEY hKey; // [rsp+50h] [rbp-C8h] BYREF
  HKEY v52; // [rsp+58h] [rbp-C0h] BYREF
  unsigned int v53[2]; // [rsp+60h] [rbp-B8h] BYREF
  HKEY v54; // [rsp+68h] [rbp-B0h] BYREF
  HKEY *p_hKey; // [rsp+70h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-A0h] BYREF
  char v57; // [rsp+80h] [rbp-98h]
  VARIANTARG pvarg; // [rsp+88h] [rbp-90h] BYREF
  unsigned __int16 v59[16]; // [rsp+A0h] [rbp-78h] BYREF
  unsigned __int16 v60[16]; // [rsp+C0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v2 = a2;
  hKey = 0;
  p_hKey = &hKey;
  phkResult = 0;
  v57 = 1;
  v4 = (char *)a2 + 96;
  if ( *((_QWORD *)a2 + 15) <= 7u )
    v5 = (const unsigned __int16 *)((char *)a2 + 96);
  else
    v5 = *(const unsigned __int16 **)v4;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(struct DCDocument **)a2;
  CookedSettingsDSCNativeProvider = DCGetEnrollmentIdSidStateDocIdVersionKey(
                                      a1,
                                      (const unsigned __int16 *)a2,
                                      v5,
                                      &phkResult,
                                      1);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( CookedSettingsDSCNativeProvider < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D43,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)CookedSettingsDSCNativeProvider,
      dwOptions);
LABEL_8:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return (unsigned int)CookedSettingsDSCNativeProvider;
  }
  v52 = 0;
  p_hKey = &v52;
  phkResult = 0;
  v57 = 1;
  if ( *((_QWORD *)v2 + 3) <= 7u )
    v8 = (const unsigned __int16 *)v2;
  else
    v8 = *(const unsigned __int16 **)v2;
  CookedSettingsDSCNativeProvider = DCGetEnrollmentIdSidStateDocIdKey(a1, v8, &phkResult);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( CookedSettingsDSCNativeProvider < 0 )
  {
    v9 = 11598;
LABEL_14:
    v10 = (unsigned int)CookedSettingsDSCNativeProvider;
    goto LABEL_15;
  }
  v60[0] = 0;
  v11 = 0;
  v12 = (_QWORD *)*((_QWORD *)v2 + 20);
  v13 = (_QWORD *)*((_QWORD *)v2 + 21);
  while ( v12 != v13 )
  {
    CookedSettingsDSCNativeProvider = StringCchPrintfW(v60, 0xFu, L"CSP%d", (unsigned int)++v11);
    if ( CookedSettingsDSCNativeProvider < 0 )
    {
      v9 = 11609;
      goto LABEL_14;
    }
    v14 = (**(__int64 (__fastcall ***)(_QWORD))*v12)(*v12);
    if ( v14 == 1 )
    {
      v15 = (const unsigned __int16 ***)_RTDynamicCast_0(
                                          *v12,
                                          0,
                                          &DCProvider `RTTI Type Descriptor',
                                          &DCCSP `RTTI Type Descriptor',
                                          0);
      if ( !v15 )
        goto LABEL_34;
      CookedSettingsDSCNativeProvider = WriteCookedCspProviderToRegistry(
                                          a1,
                                          v2,
                                          *(const unsigned __int16 **)a1,
                                          v15,
                                          v60,
                                          hKey);
      if ( CookedSettingsDSCNativeProvider < 0 )
        goto LABEL_16;
    }
    else
    {
      if ( v14 != 2
        || !_RTDynamicCast_0(*v12, 0, &DCProvider `RTTI Type Descriptor', &DCDSCNative `RTTI Type Descriptor', 0) )
      {
LABEL_34:
        CookedSettingsDSCNativeProvider = -2147418113;
        goto LABEL_16;
      }
      std::vector<ConfigDoc>::vector<ConfigDoc>(v59);
      CookedSettingsDSCNativeProvider = CreateCookedSettingsDSCNativeProvider(
                                          (int)a1,
                                          (int)v2,
                                          v16,
                                          (int)v60,
                                          v11,
                                          hKey,
                                          (__int64)v59);
      if ( CookedSettingsDSCNativeProvider < 0 )
      {
        std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(v59);
        goto LABEL_16;
      }
      std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(v59);
    }
    v12 += 2;
  }
  v17 = (const unsigned __int16 *)((char *)v2 + 32);
  if ( *((_QWORD *)v2 + 7) > 7u )
    v17 = *(const unsigned __int16 **)v17;
  v18 = DCCDNUtil_SetRegistryString(hKey, L"cooked", L"context", v17, 0);
  CookedSettingsDSCNativeProvider = v18;
  if ( v18 < 0 )
  {
    v10 = (unsigned int)v18;
    v9 = 11663;
    goto LABEL_15;
  }
  v19 = DCCDNUtil_SetRegistryDWORD(hKey, L"cooked", L"behavior", *((_DWORD *)v2 + 169));
  CookedSettingsDSCNativeProvider = v19;
  if ( v19 < 0 )
  {
    v10 = (unsigned int)v19;
    v9 = 11669;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)v10,
      dwOptions);
LABEL_16:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v52);
    goto LABEL_8;
  }
  v20 = DCCDNUtil_SetRegistryDWORD(hKey, L"cooked", L"downloadRequest", *((unsigned __int8 *)v2 + 672));
  CookedSettingsDSCNativeProvider = v20;
  if ( v20 < 0 )
  {
    v10 = (unsigned int)v20;
    v9 = 11675;
    goto LABEL_15;
  }
  v21 = DCCDNUtil_SetRegistryDWORD(hKey, L"cooked", L"state", *((_DWORD *)v2 + 70));
  CookedSettingsDSCNativeProvider = v21;
  if ( v21 < 0 )
  {
    v10 = (unsigned int)v21;
    v9 = 11681;
    goto LABEL_15;
  }
  v22 = DCCDNUtil_SetRegistryDWORD(hKey, L"cooked", L"operation", *((_DWORD *)v2 + 68));
  CookedSettingsDSCNativeProvider = v22;
  if ( v22 < 0 )
  {
    v10 = (unsigned int)v22;
    v9 = 11687;
    goto LABEL_15;
  }
  v23 = DCCDNUtil_SetRegistryDWORD(v52, 0, L"operation", *((_DWORD *)v2 + 68));
  CookedSettingsDSCNativeProvider = v23;
  if ( v23 < 0 )
  {
    v10 = (unsigned int)v23;
    v9 = 11694;
    goto LABEL_15;
  }
  v24 = (const unsigned __int16 *)((char *)v2 + 128);
  if ( *((_QWORD *)v2 + 19) > 7u )
    v24 = *(const unsigned __int16 **)v24;
  v25 = DCCDNUtil_SetRegistryString(hKey, L"cooked", L"schema", v24, 0);
  CookedSettingsDSCNativeProvider = v25;
  if ( v25 < 0 )
  {
    v10 = (unsigned int)v25;
    v9 = 11700;
    goto LABEL_15;
  }
  v26 = (const unsigned __int16 *)((char *)v2 + 512);
  if ( *((_QWORD *)v2 + 67) > 7u )
    v26 = *(const unsigned __int16 **)v26;
  v27 = DCCDNUtil_SetRegistryString(hKey, L"cooked", L"osdefinedscenario", v26, 0);
  CookedSettingsDSCNativeProvider = v27;
  if ( v27 < 0 )
  {
    v10 = (unsigned int)v27;
    v9 = 11706;
    goto LABEL_15;
  }
  v28 = (const unsigned __int16 *)((char *)v2 + 544);
  if ( *((_QWORD *)v2 + 71) > 7u )
    v28 = *(const unsigned __int16 **)v28;
  v29 = DCCDNUtil_SetRegistryString(hKey, L"cooked", L"osconfigscenario", v28, 0);
  CookedSettingsDSCNativeProvider = v29;
  if ( v29 < 0 )
  {
    v10 = (unsigned int)v29;
    v9 = 11712;
    goto LABEL_15;
  }
  v30 = (const unsigned __int16 *)((char *)v2 + 576);
  if ( *((_QWORD *)v2 + 75) <= 7u )
    v31 = (const unsigned __int16 *)((char *)v2 + 576);
  else
    v31 = *(const unsigned __int16 **)v30;
  if ( v31 && *((_QWORD *)v2 + 74) )
  {
    if ( *((_QWORD *)v2 + 75) > 7u )
      v30 = *(const unsigned __int16 **)v30;
    v32 = DCCDNUtil_SetRegistryString(hKey, L"cooked", L"osconfigscenarioschema", v30, 0);
    CookedSettingsDSCNativeProvider = v32;
    if ( v32 < 0 )
    {
      v10 = (unsigned int)v32;
      v9 = 11720;
      goto LABEL_15;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::GetImpl'::`2'::impl)
    && *((_QWORD *)v2 + 88) )
  {
    v33 = (const unsigned __int16 *)((char *)v2 + 688);
    if ( *((_QWORD *)v2 + 89) > 7u )
      v33 = *(const unsigned __int16 **)v33;
    v34 = DCCDNUtil_SetRegistryString(hKey, L"cooked", L"osconfigscenariosVersion", v33, 0);
    CookedSettingsDSCNativeProvider = v34;
    if ( v34 < 0 )
    {
      v10 = (unsigned int)v34;
      v9 = 11740;
      goto LABEL_15;
    }
  }
  v35 = DCCDNUtil_SetRegistryDWORD(hKey, L"cooked", L"model", *((_DWORD *)v2 + 69));
  CookedSettingsDSCNativeProvider = v35;
  if ( v35 < 0 )
  {
    v10 = (unsigned int)v35;
    v9 = 11748;
    goto LABEL_15;
  }
  v36 = DCCDNUtil_SetRegistryDWORD(
          hKey,
          L"cooked",
          L"CspCount",
          (__int64)(*((_QWORD *)v2 + 21) - *((_QWORD *)v2 + 20)) >> 4);
  CookedSettingsDSCNativeProvider = v36;
  if ( v36 < 0 )
  {
    v10 = (unsigned int)v36;
    v9 = 11754;
    goto LABEL_15;
  }
  LOBYTE(v37) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationGetConfigurationDocument>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationGetConfigurationDocument>::GetImpl'::`2'::impl,
    v37);
  v38 = (const unsigned __int16 *)((char *)v2 + 448);
  if ( *((_QWORD *)v2 + 59) > 7u )
    v38 = *(const unsigned __int16 **)v38;
  v39 = DCCDNUtil_SetRegistryString(hKey, L"cooked", L"originalDocStorageGuid", v38, 0);
  if ( v39 < 0 )
  {
    CookedSettingsDSCNativeProvider = v39;
    goto LABEL_16;
  }
  VariantInit(&pvarg);
  v53[0] = 0;
  CookedSettingsDSCNativeProvider = ULongLongToULong((__int64)(*((_QWORD *)v2 + 21) - *((_QWORD *)v2 + 20)) >> 4, v53);
  if ( CookedSettingsDSCNativeProvider < 0 )
    goto LABEL_93;
  pvarg.vt = 3;
  pvarg.lVal = v53[0];
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(char **)v4;
  v40 = *((_QWORD *)v2 + 3) <= 7u ? (const unsigned __int16 *)v2 : *(const unsigned __int16 **)v2;
  CookedSettingsDSCNativeProvider = DeclaredConfigurationStore_WriteResultData(
                                      a1,
                                      v40,
                                      (const unsigned __int16 *)v4,
                                      0,
                                      0,
                                      0,
                                      L"CspCount",
                                      &pvarg);
  if ( CookedSettingsDSCNativeProvider < 0 )
  {
LABEL_93:
    VariantClear(&pvarg);
    goto LABEL_16;
  }
  if ( *((_QWORD *)v2 + 33) )
  {
    v54 = 0;
    p_hKey = &v54;
    phkResult = 0;
    v57 = 1;
    v41 = RegCreateKeyExW(hKey, L"cooked", 0, 0, 0, 0x20106u, 0, &phkResult, 0);
    CookedSettingsDSCNativeProvider = v41;
    if ( v41 > 0 )
      CookedSettingsDSCNativeProvider = (unsigned __int16)v41 | 0x80070000;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( CookedSettingsDSCNativeProvider < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E1C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)CookedSettingsDSCNativeProvider,
        dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v54);
      goto LABEL_93;
    }
    v59[0] = 0;
    v42 = 0;
    v43 = **((_QWORD **)v2 + 32);
    *(_QWORD *)v53 = v43;
    while ( !*(_BYTE *)(v43 + 25) )
    {
      v44 = StringCchPrintfW(v59, 0xFu, L"Data%d", (unsigned int)++v42);
      v45 = v44;
      if ( v44 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2E27,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)v44,
          dwOptionsa);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v54);
        VariantClear(&pvarg);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v52);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v45;
      }
      v46 = (const unsigned __int16 *)(v43 + 32);
      if ( *(_QWORD *)(v43 + 56) > 7u )
        v46 = *(const unsigned __int16 **)v46;
      v47 = DCCDNUtil_SetRegistryString(v54, L"instanceDataList", v59, v46, 0);
      v48 = v47;
      if ( v47 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2E2A,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)v47,
          dwOptionsa);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v54);
        VariantClear(&pvarg);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v52);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v48;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::tuple<std::wstring,std::wstring,unsigned long,std::wstring,ATL::CComVariant>>>>,std::_Iterator_base0>::operator++(v53);
      v43 = *(_QWORD *)v53;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v54);
  }
  VariantClear(&pvarg);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v52);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x18009bae8  mov     [rsp+arg_10], rbx
0x18009baed  mov     [rsp+arg_18], rsi
0x18009baf2  push    rdi
0x18009baf3  push    r12
0x18009baf5  push    r13
0x18009baf7  push    r14
0x18009baf9  push    r15
0x18009bafb  sub     rsp, 0F0h
0x18009bb02  mov     rax, cs:__security_cookie
0x18009bb09  xor     rax, rsp
0x18009bb0c  mov     [rsp+118h+var_38], rax
0x18009bb14  mov     rdi, rdx
0x18009bb17  mov     r13, rcx
0x18009bb1a  xor     esi, esi
0x18009bb1c  mov     [rsp+118h+hKey], rsi
0x18009bb21  lea     rax, [rsp+118h+hKey]
0x18009bb26  mov     [rsp+118h+var_A8], rax
0x18009bb2b  mov     [rsp+118h+var_A0], rsi
0x18009bb30  mov     [rsp+118h+var_98], 1
0x18009bb38  lea     r12, [rdx+60h]
0x18009bb3c  cmp     qword ptr [r12+18h], 7
0x18009bb42  jbe     short loc_18009BB4A
0x18009bb44  mov     r8, [r12]
0x18009bb48  jmp     short loc_18009BB4D
0x18009bb4a  mov     r8, r12; unsigned __int16 *
0x18009bb4d  cmp     qword ptr [rdx+18h], 7
0x18009bb52  jbe     short loc_18009BB57
0x18009bb54  mov     rdx, [rdx]; unsigned __int16 *
0x18009bb57  mov     [rsp+118h+dwOptions], 1; int
0x18009bb5f  lea     r9, [rsp+118h+var_A0]; HKEY *
0x18009bb64  call    ?DCGetEnrollmentIdSidStateDocIdVersionKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBG1PEAPEAUHKEY__@@H@Z; DCGetEnrollmentIdSidStateDocIdVersionKey(DeclaredConfigurationScopeData *,ushort const *,ushort const *,HKEY__ * *,int)
0x18009bb69  mov     ebx, eax
0x18009bb6b  lea     rcx, [rsp+118h+var_A8]
0x18009bb70  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18009bb75  test    ebx, ebx
0x18009bb77  jns     short loc_18009BBA7
0x18009bb79  mov     rcx, [rsp+118h]; this
0x18009bb81  mov     r9d, ebx; char *
0x18009bb84  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18009bb8b  mov     edx, 2D43h; void *
0x18009bb90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009bb95  nop
0x18009bb96  lea     rcx, [rsp+118h+hKey]
0x18009bb9b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009bba0  mov     eax, ebx
0x18009bba2  jmp     loc_18009C37A
0x18009bba7  mov     [rsp+118h+var_C0], rsi
0x18009bbac  lea     rax, [rsp+118h+var_C0]
0x18009bbb1  mov     [rsp+118h+var_A8], rax
0x18009bbb6  mov     [rsp+118h+var_A0], rsi
0x18009bbbb  mov     [rsp+118h+var_98], 1
0x18009bbc3  cmp     qword ptr [rdi+18h], 7
0x18009bbc8  jbe     short loc_18009BBCF
0x18009bbca  mov     rdx, [rdi]
0x18009bbcd  jmp     short loc_18009BBD2
0x18009bbcf  mov     rdx, rdi; unsigned __int16 *
0x18009bbd2  lea     r8, [rsp+118h+var_A0]; HKEY *
0x18009bbd7  mov     rcx, r13; struct DeclaredConfigurationScopeData *
0x18009bbda  call    ?DCGetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@@Z; DCGetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *)
0x18009bbdf  mov     ebx, eax
0x18009bbe1  lea     rcx, [rsp+118h+var_A8]
0x18009bbe6  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18009bbeb  test    ebx, ebx
0x18009bbed  jns     short loc_18009BC1B
0x18009bbef  mov     edx, 2D4Eh; void *
0x18009bbf4  mov     r9d, ebx; char *
0x18009bbf7  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18009bbfe  mov     rcx, [rsp+118h]; this
0x18009bc06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009bc0b  nop
0x18009bc0c  lea     rcx, [rsp+118h+var_C0]
0x18009bc11  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009bc16  jmp     loc_18009BB96
0x18009bc1b  mov     [rsp+118h+var_58], si
0x18009bc23  mov     r14d, esi
0x18009bc26  mov     rsi, [rdi+0A0h]
0x18009bc2d  mov     r15, [rdi+0A8h]
0x18009bc34  jmp     loc_18009BD5F
0x18009bc39  inc     r14d
0x18009bc3c  mov     r9d, r14d
0x18009bc3f  lea     r8, aCspD; "CSP%d"
0x18009bc46  mov     edx, 0Fh; unsigned __int64
0x18009bc4b  lea     rcx, [rsp+118h+var_58]; unsigned __int16 *
0x18009bc53  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009bc58  mov     ebx, eax
0x18009bc5a  test    eax, eax
0x18009bc5c  js      loc_18009BDC5
0x18009bc62  mov     rcx, [rsi]
0x18009bc65  mov     rax, [rcx]
0x18009bc68  mov     rax, [rax]
0x18009bc6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bc70  cmp     eax, 1
0x18009bc73  jnz     short loc_18009BCD6
0x18009bc75  mov     [rsp+118h+dwOptions], 0
0x18009bc7d  lea     r9, ??_R0?AVDCCSP@@@8; DCCSP `RTTI Type Descriptor'
0x18009bc84  lea     r8, ??_R0?AVDCProvider@@@8; DCProvider `RTTI Type Descriptor'
0x18009bc8b  xor     edx, edx
0x18009bc8d  mov     rcx, [rsi]
0x18009bc90  call    __RTDynamicCast_0
0x18009bc95  test    rax, rax
0x18009bc98  jz      loc_18009BDBB
0x18009bc9e  mov     rcx, [rsp+118h+hKey]
0x18009bca3  mov     qword ptr [rsp+118h+samDesired], rcx; HKEY
0x18009bca8  lea     rcx, [rsp+118h+var_58]
0x18009bcb0  mov     qword ptr [rsp+118h+dwOptions], rcx; unsigned __int16 *
0x18009bcb5  mov     r9, rax; struct DCCSP *
0x18009bcb8  mov     r8, [r13+0]; unsigned __int16 *
0x18009bcbc  mov     rdx, rdi; struct DCDocument *
0x18009bcbf  mov     rcx, r13; struct DeclaredConfigurationScopeData *
0x18009bcc2  call    ?WriteCookedCspProviderToRegistry@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@PEBGPEAVDCCSP@@2PEAUHKEY__@@@Z; WriteCookedCspProviderToRegistry(DeclaredConfigurationScopeData *,DCDocument *,ushort const *,DCCSP *,ushort const *,HKEY__ *)
0x18009bcc7  mov     ebx, eax
0x18009bcc9  test    eax, eax
0x18009bccb  js      loc_18009BC0C
0x18009bcd1  jmp     loc_18009BD5B
0x18009bcd6  cmp     eax, 2
0x18009bcd9  jnz     loc_18009BDBB
0x18009bcdf  mov     [rsp+118h+dwOptions], 0
0x18009bce7  lea     r9, ??_R0?AVDCDSCNative@@@8; DCDSCNative `RTTI Type Descriptor'
0x18009bcee  lea     r8, ??_R0?AVDCProvider@@@8; DCProvider `RTTI Type Descriptor'
0x18009bcf5  xor     edx, edx
0x18009bcf7  mov     rcx, [rsi]
0x18009bcfa  call    __RTDynamicCast_0
0x18009bcff  mov     r8, rax
0x18009bd02  test    rax, rax
0x18009bd05  jz      loc_18009BDBB
0x18009bd0b  lea     rcx, [rsp+118h+var_78]
0x18009bd13  call    ??0?$vector@VConfigDoc@@V?$allocator@VConfigDoc@@@std@@@std@@QEAA@XZ; std::vector<ConfigDoc>::vector<ConfigDoc>(void)
0x18009bd18  nop
0x18009bd19  lea     rax, [rsp+118h+var_78]
0x18009bd21  mov     [rsp+118h+lpSecurityAttributes], rax; __int64
0x18009bd26  mov     rcx, [rsp+118h+hKey]
0x18009bd2b  mov     qword ptr [rsp+118h+samDesired], rcx; hKey
0x18009bd30  mov     [rsp+118h+dwOptions], r14d; int
0x18009bd35  lea     r9, [rsp+118h+var_58]; int
0x18009bd3d  mov     rdx, rdi; int
0x18009bd40  mov     rcx, r13; int
0x18009bd43  call    ?CreateCookedSettingsDSCNativeProvider@@YAJPEAUDeclaredConfigurationScopeData@@AEAVDCDocument@@PEAVDCDSCNative@@PEBGHPEAUHKEY__@@PEAV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; CreateCookedSettingsDSCNativeProvider(DeclaredConfigurationScopeData *,DCDocument &,DCDSCNative *,ushort const *,int,HKEY__ *,std::vector<std::pair<std::wstring,std::wstring>> *)
0x18009bd48  mov     ebx, eax
0x18009bd4a  lea     rcx, [rsp+118h+var_78]
0x18009bd52  test    eax, eax
0x18009bd54  js      short loc_18009BDB1
0x18009bd56  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(void)
0x18009bd5b  add     rsi, 10h
0x18009bd5f  cmp     rsi, r15
0x18009bd62  jnz     loc_18009BC39
0x18009bd68  lea     r9, [rdi+20h]
0x18009bd6c  mov     r15d, 7
0x18009bd72  cmp     [r9+18h], r15
0x18009bd76  jbe     short loc_18009BD7B
0x18009bd78  mov     r9, [r9]; unsigned __int16 *
0x18009bd7b  xor     r14d, r14d
0x18009bd7e  mov     byte ptr [rsp+118h+dwOptions], r14b; bool
0x18009bd83  lea     r8, aContext_1; "context"
0x18009bd8a  lea     rsi, aCooked; "cooked"
0x18009bd91  mov     rdx, rsi; unsigned __int16 *
0x18009bd94  mov     rcx, [rsp+118h+hKey]; HKEY
0x18009bd99  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x18009bd9e  mov     ebx, eax
0x18009bda0  test    eax, eax
0x18009bda2  jns     short loc_18009BDCF
0x18009bda4  mov     r9d, eax
0x18009bda7  mov     edx, 2D8Fh
0x18009bdac  jmp     loc_18009BBF7
0x18009bdb1  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(void)
0x18009bdb6  jmp     loc_18009BC0C
0x18009bdbb  mov     ebx, 8000FFFFh
0x18009bdc0  jmp     loc_18009BC0C
0x18009bdc5  mov     edx, 2D59h
0x18009bdca  jmp     loc_18009BBF4
0x18009bdcf  mov     r9d, [rdi+2A4h]; unsigned int
0x18009bdd6  lea     r8, aBehavior_0; "behavior"
0x18009bddd  mov     rdx, rsi; unsigned __int16 *
0x18009bde0  mov     rcx, [rsp+118h+hKey]; HKEY
0x18009bde5  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18009bdea  mov     ebx, eax
0x18009bdec  test    eax, eax
0x18009bdee  jns     short loc_18009BDFD
0x18009bdf0  mov     r9d, eax
0x18009bdf3  mov     edx, 2D95h
0x18009bdf8  jmp     loc_18009BBF7
0x18009bdfd  movzx   r9d, byte ptr [rdi+2A0h]; unsigned int
0x18009be05  lea     r8, aDownloadreques; "downloadRequest"
0x18009be0c  mov     rdx, rsi; unsigned __int16 *
0x18009be0f  mov     rcx, [rsp+118h+hKey]; HKEY
0x18009be14  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18009be19  mov     ebx, eax
0x18009be1b  test    eax, eax
0x18009be1d  jns     short loc_18009BE2C
0x18009be1f  mov     r9d, eax
0x18009be22  mov     edx, 2D9Bh
0x18009be27  jmp     loc_18009BBF7
0x18009be2c  mov     r9d, [rdi+118h]; unsigned int
0x18009be33  lea     r8, ValueName; "state"
0x18009be3a  mov     rdx, rsi; unsigned __int16 *
0x18009be3d  mov     rcx, [rsp+118h+hKey]; HKEY
0x18009be42  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18009be47  mov     ebx, eax
0x18009be49  test    eax, eax
0x18009be4b  jns     short loc_18009BE5A
0x18009be4d  mov     r9d, eax
0x18009be50  mov     edx, 2DA1h
0x18009be55  jmp     loc_18009BBF7
0x18009be5a  mov     r9d, [rdi+110h]; unsigned int
0x18009be61  lea     r8, aOperation; "operation"
0x18009be68  mov     rdx, rsi; unsigned __int16 *
0x18009be6b  mov     rcx, [rsp+118h+hKey]; HKEY
0x18009be70  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18009be75  mov     ebx, eax
0x18009be77  test    eax, eax
0x18009be79  jns     short loc_18009BE88
0x18009be7b  mov     r9d, eax
0x18009be7e  mov     edx, 2DA7h
0x18009be83  jmp     loc_18009BBF7
0x18009be88  mov     r9d, [rdi+110h]; unsigned int
0x18009be8f  lea     r8, aOperation; "operation"
0x18009be96  xor     edx, edx; unsigned __int16 *
0x18009be98  mov     rcx, [rsp+118h+var_C0]; HKEY
0x18009be9d  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18009bea2  mov     ebx, eax
0x18009bea4  test    eax, eax
0x18009bea6  jns     short loc_18009BEB5
0x18009bea8  mov     r9d, eax
0x18009beab  mov     edx, 2DAEh
0x18009beb0  jmp     loc_18009BBF7
0x18009beb5  lea     r9, [rdi+80h]
0x18009bebc  cmp     [r9+18h], r15
0x18009bec0  jbe     short loc_18009BEC5
0x18009bec2  mov     r9, [r9]; unsigned __int16 *
0x18009bec5  mov     byte ptr [rsp+118h+dwOptions], r14b; bool
0x18009beca  lea     r8, aSchema; "schema"
0x18009bed1  mov     rdx, rsi; unsigned __int16 *
0x18009bed4  mov     rcx, [rsp+118h+hKey]; HKEY
0x18009bed9  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x18009bede  mov     ebx, eax
0x18009bee0  test    eax, eax
0x18009bee2  jns     short loc_18009BEF1
0x18009bee4  mov     r9d, eax
0x18009bee7  mov     edx, 2DB4h
0x18009beec  jmp     loc_18009BBF7
0x18009bef1  lea     r9, [rdi+200h]
0x18009bef8  cmp     [r9+18h], r15
0x18009befc  jbe     short loc_18009BF01
0x18009befe  mov     r9, [r9]; unsigned __int16 *
0x18009bf01  mov     byte ptr [rsp+118h+dwOptions], r14b; bool
0x18009bf06  lea     r8, aOsdefinedscena; "osdefinedscenario"
0x18009bf0d  mov     rdx, rsi; unsigned __int16 *
0x18009bf10  mov     rcx, [rsp+118h+hKey]; HKEY
0x18009bf15  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x18009bf1a  mov     ebx, eax
0x18009bf1c  test    eax, eax
0x18009bf1e  jns     short loc_18009BF2D
0x18009bf20  mov     r9d, eax
0x18009bf23  mov     edx, 2DBAh
0x18009bf28  jmp     loc_18009BBF7
0x18009bf2d  lea     r9, [rdi+220h]
0x18009bf34  cmp     [r9+18h], r15
0x18009bf38  jbe     short loc_18009BF3D
0x18009bf3a  mov     r9, [r9]; unsigned __int16 *
0x18009bf3d  mov     byte ptr [rsp+118h+dwOptions], r14b; bool
0x18009bf42  lea     r8, aOsconfigscenar_1; "osconfigscenario"
0x18009bf49  mov     rdx, rsi; unsigned __int16 *
0x18009bf4c  mov     rcx, [rsp+118h+hKey]; HKEY
0x18009bf51  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x18009bf56  mov     ebx, eax
0x18009bf58  test    eax, eax
0x18009bf5a  jns     short loc_18009BF69
0x18009bf5c  mov     r9d, eax
0x18009bf5f  mov     edx, 2DC0h
0x18009bf64  jmp     loc_18009BBF7
0x18009bf69  lea     r9, [rdi+240h]
0x18009bf70  cmp     [r9+18h], r15
0x18009bf74  jbe     short loc_18009BF7B
0x18009bf76  mov     rax, [r9]
0x18009bf79  jmp     short loc_18009BF7E
0x18009bf7b  mov     rax, r9
0x18009bf7e  test    rax, rax
0x18009bf81  jz      short loc_18009BFC1
0x18009bf83  cmp     [rdi+250h], r14
0x18009bf8a  jz      short loc_18009BFC1
0x18009bf8c  cmp     [r9+18h], r15
0x18009bf90  jbe     short loc_18009BF95
0x18009bf92  mov     r9, [r9]; unsigned __int16 *
0x18009bf95  mov     byte ptr [rsp+118h+dwOptions], r14b; bool
0x18009bf9a  lea     r8, aOsconfigscenar; "osconfigscenarioschema"
0x18009bfa1  mov     rdx, rsi; unsigned __int16 *
0x18009bfa4  mov     rcx, [rsp+118h+hKey]; HKEY
0x18009bfa9  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x18009bfae  mov     ebx, eax
0x18009bfb0  test    eax, eax
0x18009bfb2  jns     short loc_18009BFC1
0x18009bfb4  mov     r9d, eax
0x18009bfb7  mov     edx, 2DC8h
0x18009bfbc  jmp     loc_18009BBF7
0x18009bfc1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::GetImpl(void)'::`2'::impl
0x18009bfc8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::__private_IsEnabled(void)
0x18009bfcd  test    al, al
0x18009bfcf  jz      short loc_18009C016
0x18009bfd1  cmp     [rdi+2C0h], r14
0x18009bfd8  jz      short loc_18009C016
0x18009bfda  lea     r9, [rdi+2B0h]
  ... truncated ...
```
