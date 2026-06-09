# DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc(DeclaredConfigurationScopeData *,DCDocument *,ushort const *,ushort const *,bool)

- ea: `0x1800ac970`
- end: `0x1800ad2ac`
- name: `?DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@PEBG2_N@Z`
- size: `2364`
- prototype: `__int64 __fastcall(struct DeclaredConfigurationScopeData *, struct DCDocument *, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180126bc0`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x18000e310`
- `0x18000e32c`
- `0x1800117dc`
- `0x180012dc4`
- `0x18001438c`
- `0x1800143c8`
- `0x180018ac0`
- `0x180018cc4`
- `0x18001924c`
- `0x18001ce5c`
- `0x18001d0b0`
- `0x18004d1ac`
- `0x18005ebf0`
- `0x18005fde0`
- `0x18006037c`
- `0x18008ec20`
- `0x1800a04fc`
- `0x1800a1308`
- `0x1800a21f0`
- `0x1800ac174`
- `0x1800ac47c`
- `0x1800ac970`
- `0x1800ad2b4`
- `0x1800f5c8c`
- `0x1800f83d0`
- `0x1800f9d70`
- `0x1800f9e64`
- `0x180100ad8`
- `0x18010136c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800acab0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800acab0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad1b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad1b5`
- `OLEAUT32!__imp_VariantInit` at `0x1800acd90`
- `OLEAUT32!__imp_VariantInit` at `0x1800acd90`
- `OLEAUT32!__imp_VariantClear` at `0x1800ace09`
- `OLEAUT32!__imp_VariantClear` at `0x1800acec7`
- `OLEAUT32!__imp_VariantClear` at `0x1800acff0`
- `OLEAUT32!__imp_VariantClear` at `0x1800ad0ce`
- `OLEAUT32!__imp_VariantClear` at `0x1800ad200`
- `OLEAUT32!__imp_VariantClear` at `0x1800ace09`
- `OLEAUT32!__imp_VariantClear` at `0x1800acec7`
- `OLEAUT32!__imp_VariantClear` at `0x1800acff0`
- `OLEAUT32!__imp_VariantClear` at `0x1800ad0ce`
- `OLEAUT32!__imp_VariantClear` at `0x1800ad200`

## string_xrefs

- `0x1800acbb1`: `GetEnrollmentIdSidStateKey`
- `0x1800acf8a`: `DeclaredConfigurationStore_ProcessSingleDoc`
- `0x1800ac9f3`: `DeclaredConfigurationGlobalMutex.create`
- `0x1800aca24`: `CreateGlobalDeclaredConfigurationMutex`
- `0x1800acc3e`: `DCCDNUtil_GetRegistryString:Reading MostRecentVersion`
- `0x1800acdea`: `DeclaredConfigurationStore_ReadResultData:Read doc State`
- `0x1800acfca`: `From state: CDNDownloadedCookConfigurationSuccess`
- `0x1800acf5c`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext`
- `0x1800acfd1`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext`
- `0x1800ad0af`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext`
- `0x1800ac9fa`: `DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc`
- `0x1800aca2b`: `DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc`
- `0x1800acad6`: `DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc`
- `0x1800acbb8`: `DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc`
- `0x1800acc45`: `DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc`
- `0x1800acdf1`: `DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc`
- `0x1800ace7c`: `DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc`
- `0x1800acf63`: `DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc`
- `0x1800acfd8`: `DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc`
- `0x1800ad0b6`: `DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc`
- `0x1800ad278`: `DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc`
- `0x1800aca78`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\processmsftsecuredcorestateinventorydoc.cpp`
- `0x1800acf55`: `Refresh on ConfigCompletedSuccess or ConfigCompletedError`
- `0x1800acf83`: `DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext:Refresh on ConfigCompletedSuccess or ConfigCompletedError`
- `0x1800ac9cc`: `Global\DeclaredConfigurationMutex`

## pseudocode

```c
// Hidden C++ exception states: #wind=19 #try_helpers=1
__int64 __fastcall DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc(
        struct DeclaredConfigurationScopeData *a1,
        struct DCDocument *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        bool a5)
{
  struct DCDocument *v7; // rbx
  __int64 v9; // rcx
  int v10; // esi
  CDeclaredConfigurationLogger *Logger; // rax
  int v13; // eax
  unsigned int v14; // esi
  CDeclaredConfigurationLogger *v15; // rax
  CDeclaredConfigurationLogger *v16; // rax
  int EnrollmentIdSidStateKey; // esi
  CDeclaredConfigurationLogger *v18; // rax
  const unsigned __int16 *v19; // rdx
  int RegistryString; // esi
  CDeclaredConfigurationLogger *v21; // rax
  __int64 v22; // r15
  __int64 v23; // r14
  __int64 v24; // rsi
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  int v29; // r9d
  const unsigned __int16 *v30; // rdx
  int ResultData_0; // esi
  bool v32; // r8
  CDeclaredConfigurationLogger *v33; // rax
  LONG lVal; // esi
  __int64 StateString; // rax
  __int64 v36; // rcx
  int v37; // eax
  char v38; // bl
  CDeclaredConfigurationLogger *v39; // rax
  int v40; // ecx
  int v41; // ebx
  CDeclaredConfigurationLogger *v42; // rax
  const unsigned __int16 *v43; // rdx
  int InventoryBasedOnDocumentAndContext; // ebx
  CDeclaredConfigurationLogger *v45; // rax
  const unsigned __int16 *v46; // rdx
  int v47; // ebx
  HKEY v48; // rcx
  CDeclaredConfigurationLogger *v49; // rax
  bool v50[4]; // [rsp+20h] [rbp-1A8h]
  HKEY v51; // [rsp+28h] [rbp-1A0h]
  __int64 v52; // [rsp+30h] [rbp-198h]
  void *Block; // [rsp+40h] [rbp-188h] BYREF
  HKEY v54; // [rsp+48h] [rbp-180h] BYREF
  __int64 v55; // [rsp+50h] [rbp-178h] BYREF
  unsigned int v56; // [rsp+58h] [rbp-170h] BYREF
  _BYTE v57[8]; // [rsp+60h] [rbp-168h] BYREF
  HKEY p_Block; // [rsp+68h] [rbp-160h] BYREF
  HKEY v59; // [rsp+70h] [rbp-158h] BYREF
  char v60; // [rsp+78h] [rbp-150h]
  HKEY v61; // [rsp+80h] [rbp-148h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-140h] BYREF
  unsigned __int16 *v63[3]; // [rsp+A0h] [rbp-128h] BYREF
  unsigned __int64 v64; // [rsp+B8h] [rbp-110h]
  _BYTE v65[32]; // [rsp+C0h] [rbp-108h] BYREF
  HKEY *v66; // [rsp+E0h] [rbp-E8h] BYREF
  HKEY v67; // [rsp+E8h] [rbp-E0h]
  char v68; // [rsp+F0h] [rbp-D8h]
  _BYTE v69[32]; // [rsp+100h] [rbp-C8h] BYREF
  _BYTE v70[32]; // [rsp+120h] [rbp-A8h] BYREF
  _BYTE v71[32]; // [rsp+140h] [rbp-88h] BYREF
  _BYTE v72[32]; // [rsp+160h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  v7 = a2;
  if ( a1 && a2 && a3 && a4 )
  {
    v55 = 0;
    v10 = _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            &v55,
            L"Global\\DeclaredConfigurationMutex");
    if ( v10 < 0 )
    {
      Logger = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        Logger,
        L"DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc",
        L"DeclaredConfigurationGlobalMutex.create",
        &word_180142E98,
        v10);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v55);
      return (unsigned int)v10;
    }
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(
        v9,
        OrchestratorGenericSuccess,
        L"DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc",
        L"CreateGlobalDeclaredConfigurationMutex");
    v56 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v55,
      v57,
      &v56,
      180000);
    v13 = DCCheckAcquireStatus(v56);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\processmsftsecuredcore"
                      "stateinventorydoc.cpp",
        (const char *)(unsigned int)v13,
        *(int *)v50);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v57);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v55);
      return v14;
    }
    if ( !(unsigned int)_o__wcsicmp(a4, L"user") )
    {
      v15 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v15,
        L"DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc",
        L"Only supports device context.",
        &word_180142E98,
        -2147024809);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v57);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v55);
      return 2147942487LL;
    }
    v56 = 0;
    LODWORD(p_Block) = 63;
    if ( (int)DCIsValidEnrollment(a3, (int *)&v56, (enum EnrollmentStateTag *)&p_Block) >= 0
      && (!v56 || (_DWORD)p_Block == 4) )
    {
      v16 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogEnrollmentInvalidOrUnenrolling(v16, a3, -2100297726);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v57);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v55);
      return 2194669570LL;
    }
    v54 = 0;
    p_Block = (HKEY)&v54;
    v59 = 0;
    v60 = 1;
    EnrollmentIdSidStateKey = GetEnrollmentIdSidStateKey(a3, a4, &v59);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_Block);
    if ( EnrollmentIdSidStateKey < 0 )
    {
      v18 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v18,
        L"DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc",
        L"GetEnrollmentIdSidStateKey",
        &word_180142E98,
        EnrollmentIdSidStateKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v54);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v57);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v55);
      return (unsigned int)EnrollmentIdSidStateKey;
    }
    Block = 0;
    p_Block = (HKEY)&Block;
    LOBYTE(v59) = 1;
    if ( *((_QWORD *)v7 + 3) <= 7u )
      v19 = (const unsigned __int16 *)v7;
    else
      v19 = *(const unsigned __int16 **)v7;
    RegistryString = DCCDNUtil_GetRegistryString(v54, v19, L"MostRecentVersion", (unsigned __int16 **)&Block);
    if ( RegistryString < 0 )
    {
      v21 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v21,
        L"DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc",
        L"DCCDNUtil_GetRegistryString:Reading MostRecentVersion",
        &word_180142E98,
        RegistryString);
      operator delete(Block);
      Block = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v54);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v57);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v55);
      return (unsigned int)RegistryString;
    }
    v22 = std::wstring::wstring((__int64)v72, (__int64)L"\\raw");
    v23 = std::wstring::wstring((__int64)v71, (__int64)Block);
    v24 = std::wstring::wstring((__int64)v70, (__int64)L"\\");
    if ( *((_QWORD *)v7 + 3) <= 7u )
      v25 = (__int64)v7;
    else
      v25 = *(_QWORD *)v7;
    v26 = std::wstring::wstring((__int64)v69, v25);
    v27 = std::operator+<unsigned short>(&v66, v26, v24);
    v28 = std::operator+<unsigned short>(v65, v27, v23);
    std::operator+<unsigned short>(v63, v28, v22);
    std::wstring::_Tidy_deallocate(v65);
    std::wstring::_Tidy_deallocate(&v66);
    std::wstring::_Tidy_deallocate(v69);
    std::wstring::_Tidy_deallocate(v70);
    std::wstring::_Tidy_deallocate(v71);
    std::wstring::_Tidy_deallocate(v72);
    std::wstring::wstring((__int64)v65);
    VariantInit(&pvarg);
    pvarg.vt = 3;
    if ( *((_QWORD *)v7 + 3) <= 7u )
      LODWORD(v30) = (_DWORD)v7;
    else
      v30 = *(const unsigned __int16 **)v7;
    ResultData_0 = DeclaredConfigurationStore_ReadResultData_0(
                     (int)a1,
                     (int)v30,
                     (int)Block,
                     v29,
                     *(DWORD *)v50,
                     v51,
                     v52,
                     (DWORD)&pvarg);
    if ( ResultData_0 < 0 )
    {
      v33 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v33,
        L"DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc",
        L"DeclaredConfigurationStore_ReadResultData:Read doc State",
        &word_180142E98,
        ResultData_0);
      VariantClear(&pvarg);
      std::wstring::_Tidy_deallocate(v65);
      std::wstring::_Tidy_deallocate(v63);
      operator delete(Block);
      Block = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v54);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v57);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v55);
      return (unsigned int)ResultData_0;
    }
    lVal = pvarg.lVal;
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      StateString = getStateString(pvarg.cyVal.Lo);
      McTemplateU0zz_EventWriteTransfer(
        v36,
        OrchestratorDocState,
        L"DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc",
        StateString);
    }
    if ( lVal == 10 || lVal == 11 || lVal == 20 )
    {
      if ( a5 )
        goto LABEL_62;
      if ( *((_QWORD *)v7 + 3) > 7u )
        v7 = *(struct DCDocument **)v7;
      InventoryBasedOnDocumentAndContext = DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext(
                                             a1,
                                             (const unsigned __int16 *)v7,
                                             v32);
      if ( InventoryBasedOnDocumentAndContext < 0 )
      {
        v45 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v45,
          L"DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc",
          L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext",
          &word_180142E98,
          InventoryBasedOnDocumentAndContext);
        VariantClear(&pvarg);
        std::wstring::_Tidy_deallocate(v65);
        std::wstring::_Tidy_deallocate(v63);
        operator delete(Block);
        Block = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v54);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v57);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v55);
        return (unsigned int)InventoryBasedOnDocumentAndContext;
      }
      if ( lVal == 10 )
        goto LABEL_62;
    }
    else
    {
      if ( lVal == 35 )
      {
        if ( *((_QWORD *)v7 + 3) > 7u )
          v7 = *(struct DCDocument **)v7;
        v41 = DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext(a1, (const unsigned __int16 *)v7, v32);
        if ( v41 < 0 )
        {
          v42 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
            v42,
            L"DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc",
            L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext",
            L"From state: CDNDownloadedCookConfigurationSuccess",
            v41);
          VariantClear(&pvarg);
          std::wstring::_Tidy_deallocate(v65);
          std::wstring::_Tidy_deallocate(v63);
          operator delete(Block);
          Block = 0;
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v54);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v57);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v55);
          return (unsigned int)v41;
        }
        v43 = (const unsigned __int16 *)v63;
        if ( v64 > 7 )
          v43 = v63[0];
        DCWriteLastRunTimeStamp(v54, v43);
        goto LABEL_63;
      }
      if ( (unsigned int)(lVal - 80) >= 2 )
      {
        VariantClear(&pvarg);
        std::wstring::_Tidy_deallocate(v65);
        std::wstring::_Tidy_deallocate(v63);
        operator delete(Block);
        Block = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v54);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v57);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v55);
        return 2147549183LL;
      }
      if ( !a5 )
      {
LABEL_62:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &v54,
          0);
LABEL_63:
        v61 = 0;
        v66 = &v61;
        v68 = 1;
        p_Block = 0;
        v67 = 0;
        v47 = DCGetHKey_0(qword_18018A5A0);
        v48 = p_Block;
        if ( v47 >= 0 )
        {
          v67 = p_Block;
          v48 = 0;
        }
        if ( v48 )
          RegCloseKey(v48);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v66);
        if ( v47 >= 0 )
          DCCDNUtil_SetRegistryString(v61, 0, L"WinDCActiveEnrollmentId", a3, 0);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v61);
        VariantClear(&pvarg);
        std::wstring::_Tidy_deallocate(v65);
        std::wstring::_Tidy_deallocate(v63);
        operator delete(Block);
        Block = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v54);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v57);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v55);
        return (unsigned int)v47;
      }
      if ( *((_QWORD *)v7 + 3) > 7u )
        v7 = *(struct DCDocument **)v7;
      v37 = DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext(a1, (const unsigned __int16 *)v7, v32);
      v38 = v37;
      if ( v37 < 0 )
      {
        v39 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(
          v39,
          L"DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc",
          L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext",
          L"Refresh on ConfigCompletedSuccess or ConfigCompletedError");
        if ( byte_180189FC1 < 0 )
          McTemplateU0zzd_EventWriteTransfer(
            v40,
            (unsigned int)OrchestratorGenericWarning,
            (unsigned int)L"DeclaredConfigurationStore_ProcessSingleDoc",
            (unsigned int)L"DeclaredConfigurationStore_GetInventoryBasedOnDocumentAndContext:Refresh on ConfigCompletedSuc"
                           "cess or ConfigCompletedError",
            v38);
      }
    }
    v46 = (const unsigned __int16 *)v63;
    if ( v64 > 7 )
      v46 = v63[0];
    DCWriteLastRunTimeStamp(v54, v46);
    goto LABEL_62;
  }
  v49 = CDeclaredConfigurationLogger::GetLogger();
  v47 = -2147024809;
  CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
    v49,
    L"DeclaredConfigurationStore_ProcessMsftSecuredCoreStateInventoryDoc",
    L"One of the input parameter is NULL",
    &word_180142E98,
    -2147024809);
  return (unsigned int)v47;
}

```

## disassembly

```asm
0x1800ac970  push    rbx
0x1800ac972  push    rsi
0x1800ac973  push    r12
0x1800ac975  push    r13
0x1800ac977  push    r14
0x1800ac979  push    r15
0x1800ac97b  sub     rsp, 198h
0x1800ac982  mov     rax, cs:__security_cookie
0x1800ac989  xor     rax, rsp
0x1800ac98c  mov     [rsp+1C8h+var_48], rax
0x1800ac994  mov     r14, r9
0x1800ac997  mov     r13, r8
0x1800ac99a  mov     rbx, rdx
0x1800ac99d  mov     r12, rcx
0x1800ac9a0  xor     r15d, r15d
0x1800ac9a3  test    rcx, rcx
0x1800ac9a6  jz      loc_1800AD25C
0x1800ac9ac  test    rdx, rdx
0x1800ac9af  jz      loc_1800AD25C
0x1800ac9b5  test    r8, r8
0x1800ac9b8  jz      loc_1800AD25C
0x1800ac9be  test    r9, r9
0x1800ac9c1  jz      loc_1800AD25C
0x1800ac9c7  mov     [rsp+1C8h+var_178], r15
0x1800ac9cc  lea     rdx, aGlobalDeclared_0; "Global\\DeclaredConfigurationMutex"
0x1800ac9d3  lea     rcx, [rsp+1C8h+var_178]
0x1800ac9d8  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800ac9dd  mov     esi, eax
0x1800ac9df  test    eax, eax
0x1800ac9e1  jns     short loc_1800ACA1B
0x1800ac9e3  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ac9e8  mov     dword ptr [rsp+1C8h+var_1A8], esi; int
0x1800ac9ec  lea     r9, word_180142E98; unsigned __int16 *
0x1800ac9f3  lea     r8, aDeclaredconfig_192; "DeclaredConfigurationGlobalMutex.create"
0x1800ac9fa  lea     rdx, aDeclaredconfig_129; "DeclaredConfigurationStore_ProcessMsftS"...
0x1800aca01  mov     rcx, rax; this
0x1800aca04  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800aca09  nop
0x1800aca0a  lea     rcx, [rsp+1C8h+var_178]
0x1800aca0f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800aca14  mov     eax, esi
0x1800aca16  jmp     loc_1800AD289
0x1800aca1b  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x1800aca22  jz      short loc_1800ACA3E
0x1800aca24  lea     r9, aCreateglobalde; "CreateGlobalDeclaredConfigurationMutex"
0x1800aca2b  lea     r8, aDeclaredconfig_129; "DeclaredConfigurationStore_ProcessMsftS"...
0x1800aca32  lea     rdx, OrchestratorGenericSuccess
0x1800aca39  call    McTemplateU0zz_EventWriteTransfer
0x1800aca3e  mov     [rsp+1C8h+var_170], r15d
0x1800aca43  mov     r9d, 2BF20h
0x1800aca49  lea     r8, [rsp+1C8h+var_170]
0x1800aca4e  lea     rdx, [rsp+1C8h+var_168]
0x1800aca53  lea     rcx, [rsp+1C8h+var_178]
0x1800aca58  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800aca5d  nop
0x1800aca5e  mov     ecx, [rsp+1C8h+var_170]; unsigned int
0x1800aca62  call    ?DCCheckAcquireStatus@@YAJK@Z; DCCheckAcquireStatus(ulong)
0x1800aca67  mov     esi, eax
0x1800aca69  test    eax, eax
0x1800aca6b  jns     short loc_1800ACAA6
0x1800aca6d  mov     rcx, [rsp+1C8h]; this
0x1800aca75  mov     r9d, eax; char *
0x1800aca78  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800aca7f  mov     edx, 0D5h; void *
0x1800aca84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aca89  nop
0x1800aca8a  lea     rcx, [rsp+1C8h+var_168]
0x1800aca8f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800aca94  nop
0x1800aca95  lea     rcx, [rsp+1C8h+var_178]
0x1800aca9a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800aca9f  mov     eax, esi
0x1800acaa1  jmp     loc_1800AD289
0x1800acaa6  lea     rdx, aUser_0; "user"
0x1800acaad  mov     rcx, r14
0x1800acab0  call    cs:__imp__o__wcsicmp
0x1800acab6  test    eax, eax
0x1800acab8  jnz     short loc_1800ACB02
0x1800acaba  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800acabf  mov     ebx, 80070057h
0x1800acac4  mov     dword ptr [rsp+1C8h+var_1A8], ebx; int
0x1800acac8  lea     r9, word_180142E98; unsigned __int16 *
0x1800acacf  lea     r8, aOnlySupportsDe; "Only supports device context."
0x1800acad6  lea     rdx, aDeclaredconfig_129; "DeclaredConfigurationStore_ProcessMsftS"...
0x1800acadd  mov     rcx, rax; this
0x1800acae0  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800acae5  nop
0x1800acae6  lea     rcx, [rsp+1C8h+var_168]
0x1800acaeb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800acaf0  nop
0x1800acaf1  lea     rcx, [rsp+1C8h+var_178]
0x1800acaf6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800acafb  mov     eax, ebx
0x1800acafd  jmp     loc_1800AD289
0x1800acb02  mov     [rsp+1C8h+var_170], r15d
0x1800acb07  mov     dword ptr [rsp+1C8h+var_160], 3Fh ; '?'
0x1800acb0f  lea     r8, [rsp+1C8h+var_160]; enum EnrollmentStateTag *
0x1800acb14  lea     rdx, [rsp+1C8h+var_170]; int *
0x1800acb19  mov     rcx, r13; StringUuid
0x1800acb1c  call    ?DCIsValidEnrollment@@YAJPEBGPEAHPEAW4EnrollmentStateTag@@@Z; DCIsValidEnrollment(ushort const *,int *,EnrollmentStateTag *)
0x1800acb21  test    eax, eax
0x1800acb23  js      short loc_1800ACB68
0x1800acb25  cmp     [rsp+1C8h+var_170], r15d
0x1800acb2a  jz      short loc_1800ACB33
0x1800acb2c  cmp     dword ptr [rsp+1C8h+var_160], 4
0x1800acb31  jnz     short loc_1800ACB68
0x1800acb33  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800acb38  mov     ebx, 82D00002h
0x1800acb3d  mov     r8d, ebx; int
0x1800acb40  mov     rdx, r13; unsigned __int16 *
0x1800acb43  mov     rcx, rax; this
0x1800acb46  call    ?LogEnrollmentInvalidOrUnenrolling@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogEnrollmentInvalidOrUnenrolling(ushort const *,long)
0x1800acb4b  nop
0x1800acb4c  lea     rcx, [rsp+1C8h+var_168]
0x1800acb51  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800acb56  nop
0x1800acb57  lea     rcx, [rsp+1C8h+var_178]
0x1800acb5c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800acb61  mov     eax, ebx
0x1800acb63  jmp     loc_1800AD289
0x1800acb68  mov     [rsp+1C8h+var_180], r15
0x1800acb6d  lea     rax, [rsp+1C8h+var_180]
0x1800acb72  mov     [rsp+1C8h+var_160], rax
0x1800acb77  mov     [rsp+1C8h+var_158], r15
0x1800acb7c  mov     [rsp+1C8h+var_150], 1
0x1800acb81  lea     r8, [rsp+1C8h+var_158]; HKEY *
0x1800acb86  mov     rdx, r14; unsigned __int16 *
0x1800acb89  mov     rcx, r13; unsigned __int16 *
0x1800acb8c  call    ?GetEnrollmentIdSidStateKey@@YAJPEBG0PEAPEAUHKEY__@@@Z; GetEnrollmentIdSidStateKey(ushort const *,ushort const *,HKEY__ * *)
0x1800acb91  mov     esi, eax
0x1800acb93  lea     rcx, [rsp+1C8h+var_160]
0x1800acb98  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800acb9d  test    esi, esi
0x1800acb9f  jns     short loc_1800ACBEF
0x1800acba1  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800acba6  mov     dword ptr [rsp+1C8h+var_1A8], esi; int
0x1800acbaa  lea     r9, word_180142E98; unsigned __int16 *
0x1800acbb1  lea     r8, aGetenrollmenti_3; "GetEnrollmentIdSidStateKey"
0x1800acbb8  lea     rdx, aDeclaredconfig_129; "DeclaredConfigurationStore_ProcessMsftS"...
0x1800acbbf  mov     rcx, rax; this
0x1800acbc2  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800acbc7  nop
0x1800acbc8  lea     rcx, [rsp+1C8h+var_180]
0x1800acbcd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800acbd2  nop
0x1800acbd3  lea     rcx, [rsp+1C8h+var_168]
0x1800acbd8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800acbdd  nop
0x1800acbde  lea     rcx, [rsp+1C8h+var_178]
0x1800acbe3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800acbe8  mov     eax, esi
0x1800acbea  jmp     loc_1800AD289
0x1800acbef  mov     [rsp+1C8h+Block], r15
0x1800acbf4  lea     rax, [rsp+1C8h+Block]
0x1800acbf9  mov     [rsp+1C8h+var_160], rax
0x1800acbfe  mov     byte ptr [rsp+1C8h+var_158], 1
0x1800acc03  cmp     qword ptr [rbx+18h], 7
0x1800acc08  jbe     short loc_1800ACC0F
0x1800acc0a  mov     rdx, [rbx]
0x1800acc0d  jmp     short loc_1800ACC12
0x1800acc0f  mov     rdx, rbx; unsigned __int16 *
0x1800acc12  lea     r9, [rsp+1C8h+Block]; unsigned __int16 **
0x1800acc17  lea     r8, aMostrecentvers; "MostRecentVersion"
0x1800acc1e  mov     rcx, [rsp+1C8h+var_180]; HKEY
0x1800acc23  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800acc28  mov     esi, eax
0x1800acc2a  test    eax, eax
0x1800acc2c  jns     short loc_1800ACC8B
0x1800acc2e  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800acc33  mov     dword ptr [rsp+1C8h+var_1A8], esi; int
0x1800acc37  lea     r9, word_180142E98; unsigned __int16 *
0x1800acc3e  lea     r8, aDccdnutilGetre_2; "DCCDNUtil_GetRegistryString:Reading Mos"...
0x1800acc45  lea     rdx, aDeclaredconfig_129; "DeclaredConfigurationStore_ProcessMsftS"...
0x1800acc4c  mov     rcx, rax; this
0x1800acc4f  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800acc54  nop
0x1800acc55  mov     rcx, [rsp+1C8h+Block]; Block
0x1800acc5a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800acc5f  mov     [rsp+1C8h+Block], r15
0x1800acc64  lea     rcx, [rsp+1C8h+var_180]
0x1800acc69  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800acc6e  nop
0x1800acc6f  lea     rcx, [rsp+1C8h+var_168]
0x1800acc74  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800acc79  nop
0x1800acc7a  lea     rcx, [rsp+1C8h+var_178]
0x1800acc7f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800acc84  mov     eax, esi
0x1800acc86  jmp     loc_1800AD289
0x1800acc8b  lea     rdx, aRaw_0; "\\raw"
0x1800acc92  lea     rcx, [rsp+1C8h+var_68]
0x1800acc9a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800acc9f  mov     r15, rax
0x1800acca2  mov     rdx, [rsp+1C8h+Block]
0x1800acca7  lea     rcx, [rsp+1C8h+var_88]
0x1800accaf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800accb4  mov     r14, rax
0x1800accb7  lea     rdx, StringValue; "\\"
0x1800accbe  lea     rcx, [rsp+1C8h+var_A8]
0x1800accc6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800acccb  mov     rsi, rax
0x1800accce  cmp     qword ptr [rbx+18h], 7
0x1800accd3  jbe     short loc_1800ACCDA
0x1800accd5  mov     rdx, [rbx]
0x1800accd8  jmp     short loc_1800ACCDD
0x1800accda  mov     rdx, rbx
0x1800accdd  lea     rcx, [rsp+1C8h+var_C8]
0x1800acce5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800accea  nop
0x1800acceb  mov     r8, rsi
0x1800accee  mov     rdx, rax
0x1800accf1  lea     rcx, [rsp+1C8h+var_E8]
0x1800accf9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800accfe  nop
0x1800accff  mov     r8, r14
0x1800acd02  mov     rdx, rax
0x1800acd05  lea     rcx, [rsp+1C8h+var_108]
0x1800acd0d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800acd12  nop
0x1800acd13  mov     r8, r15
0x1800acd16  mov     rdx, rax
0x1800acd19  lea     rcx, [rsp+1C8h+var_128]
0x1800acd21  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800acd26  nop
0x1800acd27  lea     rcx, [rsp+1C8h+var_108]
0x1800acd2f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800acd34  nop
0x1800acd35  lea     rcx, [rsp+1C8h+var_E8]
0x1800acd3d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800acd42  nop
0x1800acd43  lea     rcx, [rsp+1C8h+var_C8]
0x1800acd4b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800acd50  nop
0x1800acd51  lea     rcx, [rsp+1C8h+var_A8]
0x1800acd59  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800acd5e  nop
0x1800acd5f  lea     rcx, [rsp+1C8h+var_88]
0x1800acd67  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800acd6c  nop
0x1800acd6d  lea     rcx, [rsp+1C8h+var_68]
0x1800acd75  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800acd7a  lea     rcx, [rsp+1C8h+var_108]
0x1800acd82  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800acd87  nop
0x1800acd88  lea     rcx, [rsp+1C8h+pvarg]; pvarg
0x1800acd90  call    cs:__imp_VariantInit
0x1800acd96  nop
0x1800acd97  mov     eax, 3
0x1800acd9c  mov     word ptr [rsp+1C8h+pvarg], ax
0x1800acda4  cmp     qword ptr [rbx+18h], 7
0x1800acda9  jbe     short loc_1800ACDB0
0x1800acdab  mov     rdx, [rbx]
0x1800acdae  jmp     short loc_1800ACDB3
0x1800acdb0  mov     rdx, rbx; int
0x1800acdb3  lea     rax, [rsp+1C8h+pvarg]
0x1800acdbb  mov     qword ptr [rsp+1C8h+Type], rax; Type
0x1800acdc0  mov     r8, [rsp+1C8h+Block]; int
0x1800acdc5  mov     rcx, r12; int
0x1800acdc8  call    DeclaredConfigurationStore_ReadResultData_0
0x1800acdcd  mov     esi, eax
0x1800acdcf  xor     r14d, r14d
0x1800acdd2  test    eax, eax
0x1800acdd4  jns     loc_1800ACE62
0x1800acdda  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800acddf  mov     dword ptr [rsp+1C8h+var_1A8], esi; int
0x1800acde3  lea     r9, word_180142E98; unsigned __int16 *
0x1800acdea  lea     r8, aDeclaredconfig_189; "DeclaredConfigurationStore_ReadResultDa"...
0x1800acdf1  lea     rdx, aDeclaredconfig_129; "DeclaredConfigurationStore_ProcessMsftS"...
0x1800acdf8  mov     rcx, rax; this
0x1800acdfb  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800ace00  nop
0x1800ace01  lea     rcx, [rsp+1C8h+pvarg]; pvarg
0x1800ace09  call    cs:__imp_VariantClear
0x1800ace0f  nop
0x1800ace10  lea     rcx, [rsp+1C8h+var_108]
0x1800ace18  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ace1d  nop
0x1800ace1e  lea     rcx, [rsp+1C8h+var_128]
0x1800ace26  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ace2b  nop
0x1800ace2c  mov     rcx, [rsp+1C8h+Block]; Block
0x1800ace31  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ace36  mov     [rsp+1C8h+Block], r14
0x1800ace3b  lea     rcx, [rsp+1C8h+var_180]
0x1800ace40  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ace45  nop
0x1800ace46  lea     rcx, [rsp+1C8h+var_168]
0x1800ace4b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ace50  nop
0x1800ace51  lea     rcx, [rsp+1C8h+var_178]
0x1800ace56  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ace5b  mov     eax, esi
0x1800ace5d  jmp     loc_1800AD289
0x1800ace62  mov     esi, dword ptr [rsp+1C8h+pvarg+8]
0x1800ace69  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x1800ace70  jz      short loc_1800ACE8F
0x1800ace72  mov     ecx, esi
0x1800ace74  call    getStateString
0x1800ace79  mov     r9, rax
0x1800ace7c  lea     r8, aDeclaredconfig_129; "DeclaredConfigurationStore_ProcessMsftS"...
  ... truncated ...
```
