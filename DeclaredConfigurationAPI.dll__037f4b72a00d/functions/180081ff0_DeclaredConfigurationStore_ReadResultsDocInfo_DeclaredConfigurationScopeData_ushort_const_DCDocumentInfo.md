# DeclaredConfigurationStore_ReadResultsDocInfo(DeclaredConfigurationScopeData *,ushort const *,DCDocumentInfo *)

- ea: `0x180081ff0`
- end: `0x180082929`
- name: `?DeclaredConfigurationStore_ReadResultsDocInfo@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAVDCDocumentInfo@@@Z`
- size: `2361`
- prototype: `__int64 __fastcall(struct DeclaredConfigurationScopeData *, const unsigned __int16 *, struct DCDocumentInfo *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007c840`

## callees

- `0x18000b9e0`
- `0x18000e310`
- `0x18000e32c`
- `0x1800117dc`
- `0x180012dc4`
- `0x18001438c`
- `0x1800143c8`
- `0x180018ac0`
- `0x180018b30`
- `0x1800192b4`
- `0x180019d38`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d0b0`
- `0x18001dea8`
- `0x18001def8`
- `0x18005ebf0`
- `0x1800725e0`
- `0x180081a94`
- `0x180081ff0`
- `0x1800a04fc`
- `0x180100ad8`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800821d5`
- `OLEAUT32!__imp_VariantInit` at `0x180082379`
- `OLEAUT32!__imp_VariantInit` at `0x1800821d5`
- `OLEAUT32!__imp_VariantInit` at `0x180082379`
- `OLEAUT32!__imp_VariantClear` at `0x180082241`
- `OLEAUT32!__imp_VariantClear` at `0x1800825b8`
- `OLEAUT32!__imp_VariantClear` at `0x1800825e0`
- `OLEAUT32!__imp_VariantClear` at `0x180082815`
- `OLEAUT32!__imp_VariantClear` at `0x18008283d`
- `OLEAUT32!__imp_VariantClear` at `0x18008289d`
- `OLEAUT32!__imp_VariantClear` at `0x1800828c5`
- `OLEAUT32!__imp_VariantClear` at `0x180082241`
- `OLEAUT32!__imp_VariantClear` at `0x1800825b8`
- `OLEAUT32!__imp_VariantClear` at `0x1800825e0`
- `OLEAUT32!__imp_VariantClear` at `0x180082815`
- `OLEAUT32!__imp_VariantClear` at `0x18008283d`
- `OLEAUT32!__imp_VariantClear` at `0x18008289d`
- `OLEAUT32!__imp_VariantClear` at `0x1800828c5`

## string_xrefs

- `0x180082044`: `Global\DeclaredConfigurationMutex`
- `0x180082535`: `osconfigscenario`
- `0x1800826fe`: `osconfigscenarioschema`
- `0x180082658`: `osconfigscenariosVersion`
- `0x180082069`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800820bc`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180082133`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800821af`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18008222f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18008233a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180082577`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180082690`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180082736`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall DeclaredConfigurationStore_ReadResultsDocInfo(
        struct DeclaredConfigurationScopeData *a1,
        const unsigned __int16 *a2,
        char **a3)
{
  int v6; // eax
  signed int EnrollmentIdSidStateDocIdKey; // ebx
  int v8; // eax
  int ResultData; // eax
  __int64 v10; // rdx
  LONG lVal; // r15d
  LONG v12; // r12d
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdi
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  const unsigned __int16 *v21; // rdx
  HKEY v22; // rcx
  int RegistryString; // ebx
  int v24; // esi
  const unsigned __int16 *v25; // rdx
  int v26; // ebx
  const unsigned __int16 *v27; // rdx
  int v28; // ebx
  __int64 v29; // r8
  __int64 v30; // r8
  int v32; // [rsp+20h] [rbp-198h]
  int v33; // [rsp+20h] [rbp-198h]
  int v34; // [rsp+20h] [rbp-198h]
  int v35; // [rsp+20h] [rbp-198h]
  int v36[2]; // [rsp+40h] [rbp-178h] BYREF
  HKEY v37; // [rsp+48h] [rbp-170h] BYREF
  _BYTE v38[8]; // [rsp+50h] [rbp-168h] BYREF
  unsigned int v39; // [rsp+58h] [rbp-160h] BYREF
  _WORD *v40; // [rsp+60h] [rbp-158h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-150h] BYREF
  _WORD *v42; // [rsp+80h] [rbp-138h] BYREF
  _WORD *v43; // [rsp+88h] [rbp-130h] BYREF
  __int64 v44; // [rsp+90h] [rbp-128h] BYREF
  VARIANTARG v45; // [rsp+98h] [rbp-120h] BYREF
  _WORD **v46; // [rsp+B0h] [rbp-108h] BYREF
  HKEY v47; // [rsp+B8h] [rbp-100h] BYREF
  char v48; // [rsp+C0h] [rbp-F8h]
  unsigned __int16 *v49[3]; // [rsp+D0h] [rbp-E8h] BYREF
  unsigned __int64 v50; // [rsp+E8h] [rbp-D0h]
  char *v51[4]; // [rsp+F0h] [rbp-C8h] BYREF
  _BYTE v52[32]; // [rsp+110h] [rbp-A8h] BYREF
  _BYTE v53[32]; // [rsp+130h] [rbp-88h] BYREF
  _BYTE v54[32]; // [rsp+150h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  if ( a1 && a2 && a3 )
  {
    v44 = 0;
    v6 = _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
           &v44,
           L"Global\\DeclaredConfigurationMutex");
    EnrollmentIdSidStateDocIdKey = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D42,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v6,
        v32);
LABEL_69:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v44);
      return (unsigned int)EnrollmentIdSidStateDocIdKey;
    }
    v39 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v44,
      v38,
      &v39,
      180000);
    v8 = DCCheckAcquireStatus(v39);
    EnrollmentIdSidStateDocIdKey = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D46,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v8,
        v32);
LABEL_8:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v38);
      goto LABEL_69;
    }
    v37 = 0;
    v46 = (_WORD **)&v37;
    v47 = 0;
    v48 = 1;
    EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(a1, a2, &v47, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v46);
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D4D,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)EnrollmentIdSidStateDocIdKey,
        v32);
LABEL_11:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v37);
      goto LABEL_8;
    }
    *(_QWORD *)v36 = 0;
    v46 = (_WORD **)v36;
    v47 = 0;
    v48 = 1;
    EnrollmentIdSidStateDocIdKey = DCCDNUtil_GetRegistryString(v37, 0, L"MostRecentVersion", (unsigned __int16 **)&v47);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v46);
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D54,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)EnrollmentIdSidStateDocIdKey,
        v32);
LABEL_14:
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(v36);
      goto LABEL_11;
    }
    VariantInit(&pvarg);
    pvarg.vt = 3;
    ResultData = DeclaredConfigurationStore_ReadResultData((int)a1, (int)a2, v36[0], 0, 0, 0, L"state", (DWORD)&pvarg);
    EnrollmentIdSidStateDocIdKey = ResultData;
    if ( ResultData < 0 )
    {
      v10 = 19809;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)ResultData,
        v33);
LABEL_18:
      VariantClear(&pvarg);
      goto LABEL_14;
    }
    lVal = pvarg.lVal;
    ResultData = DeclaredConfigurationStore_ReadResultData(
                   (int)a1,
                   (int)a2,
                   v36[0],
                   0,
                   0,
                   0,
                   L"operation",
                   (DWORD)&pvarg);
    EnrollmentIdSidStateDocIdKey = ResultData;
    if ( ResultData < 0 )
    {
      v10 = 19820;
      goto LABEL_17;
    }
    v12 = pvarg.lVal;
    pvarg.vt = 8;
    ResultData = DeclaredConfigurationStore_ReadResultData((int)a1, (int)a2, v36[0], 0, 0, 0, L"context", (DWORD)&pvarg);
    EnrollmentIdSidStateDocIdKey = ResultData;
    if ( ResultData < 0 )
    {
      v10 = 19832;
      goto LABEL_17;
    }
    std::wstring::wstring((__int64)v52, pvarg.llVal);
    v13 = DeclaredConfigurationStore_ReadResultData((int)a1, (int)a2, v36[0], 0, 0, 0, L"resultchecksum", (DWORD)&pvarg);
    EnrollmentIdSidStateDocIdKey = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D83,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v13,
        v34);
      std::wstring::_Tidy_deallocate(v52);
      goto LABEL_18;
    }
    std::wstring::wstring((__int64)v53, pvarg.llVal);
    VariantInit(&v45);
    v45.vt = 8;
    std::wstring::wstring((__int64)v51, (__int64)&word_180142E98);
    v14 = DeclaredConfigurationStore_ReadResultData((int)a1, (int)a2, v36[0], 0, 0, 0, L"resultTimeStamp", (DWORD)&v45);
    v15 = -1;
    if ( v14 >= 0 )
    {
      v16 = -1;
      do
        ++v16;
      while ( *(_WORD *)(v45.llVal + 2 * v16) );
      std::wstring::_Assign<unsigned short>(v51, v45.bstrVal, (char *)v16);
    }
    v17 = -1;
    do
      ++v17;
    while ( a2[v17] );
    std::wstring::_Assign<unsigned short>(a3, a2, (char *)v17);
    std::wstring::operator=(a3 + 4, v52);
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)(*(_QWORD *)v36 + 2 * v18) );
    std::wstring::_Assign<unsigned short>(a3 + 8, *(const void **)v36, (char *)v18);
    std::wstring::operator=(a3 + 12, v53);
    *((_DWORD *)a3 + 40) = v12;
    *((_DWORD *)a3 + 41) = lVal;
    std::wstring::operator=(a3 + 16, v51);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
    {
      std::wstring::wstring((__int64)v49);
      try
      {
        v19 = std::wstring::wstring((__int64)v54, *(__int64 *)v36);
        v20 = std::operator+<unsigned short>(&v46, v19, L"\\raw");
        std::wstring::operator=(v49, v20);
        std::wstring::_Tidy_deallocate(&v46);
        std::wstring::_Tidy_deallocate(v54);
        v40 = 0;
        v46 = &v40;
        v47 = 0;
        v48 = 1;
        v21 = (const unsigned __int16 *)v49;
        if ( v50 > 7 )
          v21 = v49[0];
        v22 = v37;
      }
      catch ( ... )
      {
        v39 = wil::details::in1diag3::Return_CaughtException(
                retaddr,
                (void *)0x4DA4,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
                (const char *)&v47);
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::_Tidy_deallocate(v51);
        VariantClear(&v45);
        std::wstring::_Tidy_deallocate(v53);
        std::wstring::_Tidy_deallocate(v52);
        VariantClear(&pvarg);
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(v36);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v37);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v38);
        EnrollmentIdSidStateDocIdKey = v39;
        goto LABEL_69;
      }
      RegistryString = DCCDNUtil_GetRegistryString(v22, v21, L"osconfigscenario", (unsigned __int16 **)&v47);
      wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v46);
      v24 = 0;
      if ( RegistryString != -2147024894 )
        v24 = RegistryString;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4DB1,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)v24,
          v35);
LABEL_42:
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v40);
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::_Tidy_deallocate(v51);
        VariantClear(&v45);
        std::wstring::_Tidy_deallocate(v53);
        std::wstring::_Tidy_deallocate(v52);
        VariantClear(&pvarg);
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(v36);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v37);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v38);
        EnrollmentIdSidStateDocIdKey = v24;
        goto LABEL_69;
      }
      v42 = 0;
      v46 = &v42;
      v47 = 0;
      v48 = 1;
      v25 = (const unsigned __int16 *)v49;
      if ( v50 > 7 )
        v25 = v49[0];
      v26 = DCCDNUtil_GetRegistryString(v37, v25, L"osconfigscenariosVersion", (unsigned __int16 **)&v47);
      wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v46);
      v24 = 0;
      if ( v26 != -2147024894 )
        v24 = v26;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4DBD,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)v24,
          v35);
LABEL_49:
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v42);
        goto LABEL_42;
      }
      v43 = 0;
      v46 = &v43;
      v47 = 0;
      v48 = 1;
      v27 = (const unsigned __int16 *)v49;
      if ( v50 > 7 )
        v27 = v49[0];
      v28 = DCCDNUtil_GetRegistryString(v37, v27, L"osconfigscenarioschema", (unsigned __int16 **)&v47);
      wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v46);
      v24 = 0;
      if ( v28 != -2147024894 )
        v24 = v28;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4DC9,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)v24,
          v35);
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v43);
        goto LABEL_49;
      }
      if ( v40 )
      {
        v29 = -1;
        do
          ++v29;
        while ( v40[v29] );
        std::wstring::_Assign<unsigned short>(a3 + 21, v40, (char *)v29);
      }
      if ( v42 )
      {
        v30 = -1;
        do
          ++v30;
        while ( v42[v30] );
        std::wstring::_Assign<unsigned short>(a3 + 29, v42, (char *)v30);
      }
      if ( v43 )
      {
        do
          ++v15;
        while ( v43[v15] );
        std::wstring::_Assign<unsigned short>(a3 + 25, v43, (char *)v15);
      }
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v43);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v42);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v40);
      std::wstring::_Tidy_deallocate(v49);
    }
    std::wstring::_Tidy_deallocate(v51);
    VariantClear(&v45);
    std::wstring::_Tidy_deallocate(v53);
    std::wstring::_Tidy_deallocate(v52);
    VariantClear(&pvarg);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(v36);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v37);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v38);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v44);
    return 0;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180081ff0  push    rbx
0x180081ff2  push    rsi
0x180081ff3  push    rdi
0x180081ff4  push    r12
0x180081ff6  push    r13
0x180081ff8  push    r14
0x180081ffa  push    r15
0x180081ffc  sub     rsp, 180h
0x180082003  mov     rax, cs:__security_cookie
0x18008200a  xor     rax, rsp
0x18008200d  mov     [rsp+1B8h+var_48], rax
0x180082015  mov     r14, r8
0x180082018  mov     rsi, rdx
0x18008201b  mov     rdi, rcx
0x18008201e  xor     r13d, r13d
0x180082021  test    rcx, rcx
0x180082024  jz      loc_180082901
0x18008202a  test    rdx, rdx
0x18008202d  jz      loc_180082901
0x180082033  test    r8, r8
0x180082036  jz      loc_180082901
0x18008203c  mov     [rsp+1B8h+var_128], r13
0x180082044  lea     rdx, aGlobalDeclared; "Global\\DeclaredConfigurationMutex"
0x18008204b  lea     rcx, [rsp+1B8h+var_128]
0x180082053  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180082058  mov     ebx, eax
0x18008205a  test    eax, eax
0x18008205c  jns     short loc_18008207F
0x18008205e  mov     rcx, [rsp+1B8h]; this
0x180082066  mov     r9d, eax; char *
0x180082069  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180082070  mov     edx, 4D42h; void *
0x180082075  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008207a  jmp     loc_1800828F0
0x18008207f  mov     [rsp+1B8h+var_160], r13d
0x180082084  mov     r9d, 2BF20h
0x18008208a  lea     r8, [rsp+1B8h+var_160]
0x18008208f  lea     rdx, [rsp+1B8h+var_168]
0x180082094  lea     rcx, [rsp+1B8h+var_128]
0x18008209c  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800820a1  nop
0x1800820a2  mov     ecx, [rsp+1B8h+var_160]; unsigned int
0x1800820a6  call    ?DCCheckAcquireStatus@@YAJK@Z; DCCheckAcquireStatus(ulong)
0x1800820ab  mov     ebx, eax
0x1800820ad  test    eax, eax
0x1800820af  jns     short loc_1800820DD
0x1800820b1  mov     rcx, [rsp+1B8h]; this
0x1800820b9  mov     r9d, eax; char *
0x1800820bc  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800820c3  mov     edx, 4D46h; void *
0x1800820c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800820cd  nop
0x1800820ce  lea     rcx, [rsp+1B8h+var_168]
0x1800820d3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800820d8  jmp     loc_1800828F0
0x1800820dd  mov     [rsp+1B8h+var_170], r13
0x1800820e2  lea     rax, [rsp+1B8h+var_170]
0x1800820e7  mov     [rsp+1B8h+var_108], rax
0x1800820ef  mov     [rsp+1B8h+var_100], r13
0x1800820f7  mov     [rsp+1B8h+var_F8], 1
0x1800820ff  xor     r9d, r9d; int
0x180082102  lea     r8, [rsp+1B8h+var_100]; HKEY *
0x18008210a  mov     rdx, rsi; unsigned __int16 *
0x18008210d  mov     rcx, rdi; struct DeclaredConfigurationScopeData *
0x180082110  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x180082115  mov     ebx, eax
0x180082117  lea     rcx, [rsp+1B8h+var_108]
0x18008211f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180082124  test    ebx, ebx
0x180082126  jns     short loc_180082154
0x180082128  mov     rcx, [rsp+1B8h]; this
0x180082130  mov     r9d, ebx; char *
0x180082133  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18008213a  mov     edx, 4D4Dh; void *
0x18008213f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082144  nop
0x180082145  lea     rcx, [rsp+1B8h+var_170]
0x18008214a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008214f  jmp     loc_1800820CE
0x180082154  mov     qword ptr [rsp+1B8h+var_178], r13
0x180082159  lea     rax, [rsp+1B8h+var_178]
0x18008215e  mov     [rsp+1B8h+var_108], rax
0x180082166  mov     [rsp+1B8h+var_100], r13
0x18008216e  mov     [rsp+1B8h+var_F8], 1
0x180082176  lea     r9, [rsp+1B8h+var_100]; unsigned __int16 **
0x18008217e  lea     r8, aMostrecentvers; "MostRecentVersion"
0x180082185  xor     edx, edx; unsigned __int16 *
0x180082187  mov     rcx, [rsp+1B8h+var_170]; HKEY
0x18008218c  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180082191  mov     ebx, eax
0x180082193  lea     rcx, [rsp+1B8h+var_108]
0x18008219b  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800821a0  test    ebx, ebx
0x1800821a2  jns     short loc_1800821D0
0x1800821a4  mov     rcx, [rsp+1B8h]; this
0x1800821ac  mov     r9d, ebx; char *
0x1800821af  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800821b6  mov     edx, 4D54h; void *
0x1800821bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800821c0  nop
0x1800821c1  lea     rcx, [rsp+1B8h+var_178]
0x1800821c6  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800821cb  jmp     loc_180082145
0x1800821d0  lea     rcx, [rsp+1B8h+pvarg]; pvarg
0x1800821d5  call    cs:__imp_VariantInit
0x1800821db  nop
0x1800821dc  mov     eax, 3
0x1800821e1  mov     word ptr [rsp+1B8h+pvarg], ax
0x1800821e6  lea     rax, [rsp+1B8h+pvarg]
0x1800821eb  mov     qword ptr [rsp+1B8h+cbData], rax; cbData
0x1800821f0  lea     rax, ValueName; "state"
0x1800821f7  mov     [rsp+1B8h+lpValueName], rax; lpValueName
0x1800821fc  mov     [rsp+1B8h+var_190], r13; __int64
0x180082201  mov     [rsp+1B8h+var_198], r13; int
0x180082206  xor     r9d, r9d; int
0x180082209  mov     r8, qword ptr [rsp+1B8h+var_178]; int
0x18008220e  mov     rdx, rsi; int
0x180082211  mov     rcx, rdi; int
0x180082214  call    DeclaredConfigurationStore_ReadResultData
0x180082219  mov     ebx, eax
0x18008221b  test    eax, eax
0x18008221d  jns     short loc_18008224C
0x18008221f  mov     edx, 4D61h; void *
0x180082224  mov     rcx, [rsp+1B8h]; this
0x18008222c  mov     r9d, eax; char *
0x18008222f  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180082236  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008223b  nop
0x18008223c  lea     rcx, [rsp+1B8h+pvarg]; pvarg
0x180082241  call    cs:__imp_VariantClear
0x180082247  jmp     loc_1800821C1
0x18008224c  mov     r15d, dword ptr [rsp+1B8h+pvarg+8]
0x180082251  lea     rax, [rsp+1B8h+pvarg]
0x180082256  mov     qword ptr [rsp+1B8h+cbData], rax; cbData
0x18008225b  lea     rax, aOperation; "operation"
0x180082262  mov     [rsp+1B8h+lpValueName], rax; lpValueName
0x180082267  mov     [rsp+1B8h+var_190], r13; __int64
0x18008226c  mov     [rsp+1B8h+var_198], r13; __int64
0x180082271  xor     r9d, r9d; int
0x180082274  mov     r8, qword ptr [rsp+1B8h+var_178]; int
0x180082279  mov     rdx, rsi; int
0x18008227c  mov     rcx, rdi; int
0x18008227f  call    DeclaredConfigurationStore_ReadResultData
0x180082284  mov     ebx, eax
0x180082286  test    eax, eax
0x180082288  jns     short loc_180082291
0x18008228a  mov     edx, 4D6Ch
0x18008228f  jmp     short loc_180082224
0x180082291  mov     r12d, dword ptr [rsp+1B8h+pvarg+8]
0x180082296  mov     eax, 8
0x18008229b  mov     word ptr [rsp+1B8h+pvarg], ax
0x1800822a0  lea     rax, [rsp+1B8h+pvarg]
0x1800822a5  mov     qword ptr [rsp+1B8h+cbData], rax; cbData
0x1800822aa  lea     rax, aContext_1; "context"
0x1800822b1  mov     [rsp+1B8h+lpValueName], rax; lpValueName
0x1800822b6  mov     [rsp+1B8h+var_190], r13; __int64
0x1800822bb  mov     [rsp+1B8h+var_198], r13; __int64
0x1800822c0  xor     r9d, r9d; int
0x1800822c3  mov     r8, qword ptr [rsp+1B8h+var_178]; int
0x1800822c8  mov     rdx, rsi; int
0x1800822cb  mov     rcx, rdi; int
0x1800822ce  call    DeclaredConfigurationStore_ReadResultData
0x1800822d3  mov     ebx, eax
0x1800822d5  test    eax, eax
0x1800822d7  jns     short loc_1800822E3
0x1800822d9  mov     edx, 4D78h
0x1800822de  jmp     loc_180082224
0x1800822e3  mov     rdx, qword ptr [rsp+1B8h+pvarg+8]
0x1800822e8  lea     rcx, [rsp+1B8h+var_A8]
0x1800822f0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800822f5  nop
0x1800822f6  lea     rax, [rsp+1B8h+pvarg]
0x1800822fb  mov     qword ptr [rsp+1B8h+cbData], rax; cbData
0x180082300  lea     rax, aResultchecksum; "resultchecksum"
0x180082307  mov     [rsp+1B8h+lpValueName], rax; lpValueName
0x18008230c  mov     [rsp+1B8h+var_190], r13; __int64
0x180082311  mov     [rsp+1B8h+var_198], r13; int
0x180082316  xor     r9d, r9d; int
0x180082319  mov     r8, qword ptr [rsp+1B8h+var_178]; int
0x18008231e  mov     rdx, rsi; int
0x180082321  mov     rcx, rdi; int
0x180082324  call    DeclaredConfigurationStore_ReadResultData
0x180082329  mov     ebx, eax
0x18008232b  test    eax, eax
0x18008232d  jns     short loc_18008235E
0x18008232f  mov     rcx, [rsp+1B8h]; this
0x180082337  mov     r9d, eax; char *
0x18008233a  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180082341  mov     edx, 4D83h; void *
0x180082346  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008234b  nop
0x18008234c  lea     rcx, [rsp+1B8h+var_A8]
0x180082354  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180082359  jmp     loc_18008223C
0x18008235e  mov     rdx, qword ptr [rsp+1B8h+pvarg+8]
0x180082363  lea     rcx, [rsp+1B8h+var_88]
0x18008236b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180082370  nop
0x180082371  lea     rcx, [rsp+1B8h+var_120]; pvarg
0x180082379  call    cs:__imp_VariantInit
0x18008237f  nop
0x180082380  mov     eax, 8
0x180082385  mov     word ptr [rsp+1B8h+var_120], ax
0x18008238d  lea     rdx, word_180142E98
0x180082394  lea     rcx, [rsp+1B8h+var_C8]
0x18008239c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800823a1  nop
0x1800823a2  lea     rax, [rsp+1B8h+var_120]
0x1800823aa  mov     qword ptr [rsp+1B8h+cbData], rax; cbData
0x1800823af  lea     rax, aResulttimestam_0; "resultTimeStamp"
0x1800823b6  mov     [rsp+1B8h+lpValueName], rax; lpValueName
0x1800823bb  mov     [rsp+1B8h+var_190], r13; __int64
0x1800823c0  mov     [rsp+1B8h+var_198], r13; int
0x1800823c5  xor     r9d, r9d; int
0x1800823c8  mov     r8, qword ptr [rsp+1B8h+var_178]; int
0x1800823cd  mov     rdx, rsi; int
0x1800823d0  mov     rcx, rdi; int
0x1800823d3  call    DeclaredConfigurationStore_ReadResultData
0x1800823d8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800823dc  test    eax, eax
0x1800823de  js      short loc_180082402
0x1800823e0  mov     rdx, qword ptr [rsp+1B8h+var_120+8]
0x1800823e8  mov     r8, rdi
0x1800823eb  inc     r8
0x1800823ee  cmp     [rdx+r8*2], r13w
0x1800823f3  jnz     short loc_1800823EB
0x1800823f5  lea     rcx, [rsp+1B8h+var_C8]
0x1800823fd  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180082402  mov     r8, rdi
0x180082405  inc     r8
0x180082408  cmp     [rsi+r8*2], r13w
0x18008240d  jnz     short loc_180082405
0x18008240f  mov     rdx, rsi
0x180082412  mov     rcx, r14
0x180082415  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18008241a  lea     rcx, [r14+20h]
0x18008241e  lea     rdx, [rsp+1B8h+var_A8]
0x180082426  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18008242b  mov     rdx, qword ptr [rsp+1B8h+var_178]
0x180082430  mov     r8, rdi
0x180082433  inc     r8
0x180082436  cmp     [rdx+r8*2], r13w
0x18008243b  jnz     short loc_180082433
0x18008243d  lea     rcx, [r14+40h]
0x180082441  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180082446  lea     rcx, [r14+60h]
0x18008244a  lea     rdx, [rsp+1B8h+var_88]
0x180082452  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180082457  mov     [r14+0A0h], r12d
0x18008245e  mov     [r14+0A4h], r15d
0x180082465  lea     rcx, [r14+80h]
0x18008246c  lea     rdx, [rsp+1B8h+var_C8]
0x180082474  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180082479  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x180082480  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x180082485  test    al, al
0x180082487  jz      loc_1800827FF
0x18008248d  lea     rcx, [rsp+1B8h+var_E8]
0x180082495  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008249a  nop
0x18008249b  mov     rdx, qword ptr [rsp+1B8h+var_178]
0x1800824a0  lea     rcx, [rsp+1B8h+var_68]
0x1800824a8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800824ad  nop
0x1800824ae  lea     r8, aRaw_0; "\\raw"
0x1800824b5  mov     rdx, rax
0x1800824b8  lea     rcx, [rsp+1B8h+var_108]
0x1800824c0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800824c5  mov     rdx, rax
0x1800824c8  lea     rcx, [rsp+1B8h+var_E8]
0x1800824d0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800824d5  lea     rcx, [rsp+1B8h+var_108]
0x1800824dd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800824e2  nop
0x1800824e3  lea     rcx, [rsp+1B8h+var_68]
0x1800824eb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800824f0  nop
0x1800824f1  mov     [rsp+1B8h+var_158], r13
0x1800824f6  lea     rax, [rsp+1B8h+var_158]
0x1800824fb  mov     [rsp+1B8h+var_108], rax
0x180082503  mov     [rsp+1B8h+var_100], r13
0x18008250b  mov     [rsp+1B8h+var_F8], 1
0x180082513  lea     rdx, [rsp+1B8h+var_E8]
0x18008251b  cmp     [rsp+1B8h+var_D0], 7
0x180082524  cmova   rdx, [rsp+1B8h+var_E8]; unsigned __int16 *
0x18008252d  lea     r9, [rsp+1B8h+var_100]; unsigned __int16 **
0x180082535  lea     r8, aOsconfigscenar_1; "osconfigscenario"
0x18008253c  mov     rcx, [rsp+1B8h+var_170]; HKEY
0x180082541  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180082546  mov     ebx, eax
0x180082548  lea     rcx, [rsp+1B8h+var_108]
0x180082550  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x180082555  mov     esi, r13d
0x180082558  mov     r15d, 80070002h
0x18008255e  cmp     ebx, r15d
0x180082561  cmovnz  esi, ebx
0x180082564  test    esi, esi
0x180082566  jns     loc_18008260E
0x18008256c  mov     rcx, [rsp+1B8h]; this
0x180082574  mov     r9d, esi; char *
  ... truncated ...
```
