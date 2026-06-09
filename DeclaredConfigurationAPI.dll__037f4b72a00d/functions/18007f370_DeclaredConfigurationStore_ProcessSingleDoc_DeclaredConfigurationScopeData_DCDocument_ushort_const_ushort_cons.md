# DeclaredConfigurationStore_ProcessSingleDoc(DeclaredConfigurationScopeData *,DCDocument *,ushort const *,ushort const *,bool,long *)

- ea: `0x18007f370`
- end: `0x180080e7f`
- name: `?DeclaredConfigurationStore_ProcessSingleDoc@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@PEBG2_NPEAJ@Z`
- size: `6927`
- prototype: `int(struct DeclaredConfigurationScopeData *, struct DCDocument *, const unsigned __int16 *, const unsigned __int16 *, bool, int *)`
- caller_count: `8`
- callee_count: `47`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18011f0d0`
- `0x18011f9e0`
- `0x180120650`
- `0x180120cf0`
- `0x180121bfc`
- `0x180123d20`
- `0x1801257b0`
- `0x180126110`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x18000bf4c`
- `0x18000c8f4`
- `0x18000e310`
- `0x18000e32c`
- `0x1800117dc`
- `0x180012dc4`
- `0x18001438c`
- `0x1800143c8`
- `0x180018ac0`
- `0x180018b30`
- `0x180018cc4`
- `0x18001924c`
- `0x18001ce5c`
- `0x18001d03c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18004d158`
- `0x18004d1ac`
- `0x18005860c`
- `0x18005ebf0`
- `0x18005ef7c`
- `0x18005f8cc`
- `0x18005fa30`
- `0x18005fcf8`
- `0x18005fde0`
- `0x18006037c`
- `0x18006510c`
- `0x18007f370`
- `0x180086c10`
- `0x18008ec20`
- `0x18008fc10`
- `0x180098e10`
- `0x1800a0174`
- `0x1800a04fc`
- `0x1800a1308`
- `0x1800a21f0`
- `0x1800aab60`
- `0x1800f5c8c`
- `0x1800f83d0`
- `0x1800f9d70`
- `0x1800f9e64`
- `0x1801007e8`
- `0x180100ad8`
- `0x18010136c`
- `0x180102a34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007f59b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007f63c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007f59b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007f63c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007fc01`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007fca8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007fe4f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008022e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800802c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180080473`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007fc01`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007fca8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007fe4f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008022e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800802c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180080473`
- `OLEAUT32!__imp_SysAllocString` at `0x18007fce4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800802fb`
- `OLEAUT32!__imp_SysAllocString` at `0x18007fce4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800802fb`
- `OLEAUT32!__imp_VariantInit` at `0x18007fa25`
- `OLEAUT32!__imp_VariantInit` at `0x18007fa25`
- `OLEAUT32!__imp_VariantClear` at `0x18007ff1f`
- `OLEAUT32!__imp_VariantClear` at `0x180080038`
- `OLEAUT32!__imp_VariantClear` at `0x180080530`
- `OLEAUT32!__imp_VariantClear` at `0x1800805e1`
- `OLEAUT32!__imp_VariantClear` at `0x180080677`
- `OLEAUT32!__imp_VariantClear` at `0x18008070e`
- `OLEAUT32!__imp_VariantClear` at `0x1800807f6`
- `OLEAUT32!__imp_VariantClear` at `0x180080990`
- `OLEAUT32!__imp_VariantClear` at `0x180080ab0`
- `OLEAUT32!__imp_VariantClear` at `0x180080bba`
- `OLEAUT32!__imp_VariantClear` at `0x180080d1a`
- `OLEAUT32!__imp_VariantClear` at `0x18007ff1f`
- `OLEAUT32!__imp_VariantClear` at `0x180080038`
- `OLEAUT32!__imp_VariantClear` at `0x180080530`
- `OLEAUT32!__imp_VariantClear` at `0x1800805e1`
- `OLEAUT32!__imp_VariantClear` at `0x180080677`
- `OLEAUT32!__imp_VariantClear` at `0x18008070e`
- `OLEAUT32!__imp_VariantClear` at `0x1800807f6`
- `OLEAUT32!__imp_VariantClear` at `0x180080990`
- `OLEAUT32!__imp_VariantClear` at `0x180080ab0`
- `OLEAUT32!__imp_VariantClear` at `0x180080bba`
- `OLEAUT32!__imp_VariantClear` at `0x180080d1a`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18007f5ba`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18007f5ba`

## string_xrefs

- `0x18007f463`: `Global\DeclaredConfigurationMutex`
- `0x18007f52f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18007f7ea`: `GetEnrollmentIdSidStateKey`
- `0x1800805c6`: `DeclaredConfigurationStore_WriteResultData`
- `0x1800806f3`: `DeclaredConfigurationStore_WriteResultData`
- `0x18007f445`: `DeclaredConfigurationStore_GetRefreshFlag`
- `0x1800807db`: `DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext`
- `0x180080975`: `DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext`
- `0x180080b9f`: `DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext`
- `0x180080cac`: `DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext`
- `0x18007f494`: `DeclaredConfigurationStore_ProcessSingleDoc`
- `0x18007f4c3`: `DeclaredConfigurationStore_ProcessSingleDoc`
- `0x180080e40`: `DeclaredConfigurationStore_ProcessSingleDoc`
- `0x18007f48d`: `DeclaredConfigurationGlobalMutex.create`
- `0x18007f4da`: `CreateGlobalDeclaredConfigurationMutex`
- `0x18007f5d6`: `DmGetActiveUserSid`
- `0x18007f8aa`: `DCCDNUtil_GetRegistryString:Reading MostRecentVersion`
- `0x18007ff04`: `DeclaredConfigurationStore_ReadResultData:Read doc State`
- `0x180080ca5`: `Refresh on ConfigCompletedSuccess, ConfigCompletedError, ProcessOrchestrationInformationFailure, or ProcessOrchestrationInformationSuccess`
- `0x180080ccb`: `DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext:Refresh on ConfigCompletedSuccess, ConfigCompletedError, ProcessOrchestrationInformationFailure, or ProcessOrchestrationInformationSuccess`
- `0x1800804e5`: `Read reboot state`
- `0x1800804ec`: `DeclaredConfigurationStore_ReadResultData`
- `0x18008050b`: `DeclaredConfigurationStore_ReadResultData: read reboot state`
- `0x1800805bf`: `Update doc reboot state`
- `0x1800806ec`: `Update doc state`
- `0x1800807d4`: `From state: CDNDownloadedCookConfigurationSuccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=27 #try_helpers=1
__int64 __fastcall DeclaredConfigurationStore_ProcessSingleDoc(
        struct DeclaredConfigurationScopeData *a1,
        struct DCDocument *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        bool a5,
        int *a6)
{
  struct DCDocument *v8; // rsi
  const unsigned __int16 *v10; // rdx
  int RefreshFlag; // ebx
  CDeclaredConfigurationLogger *Logger; // rax
  const unsigned __int16 *v13; // r9
  const unsigned __int16 *v14; // r8
  __int64 v15; // rcx
  int v16; // ebx
  CDeclaredConfigurationLogger *v17; // rax
  int v19; // eax
  __int64 v20; // rcx
  unsigned int v21; // ebx
  int ActiveUserSid; // ebx
  CDeclaredConfigurationLogger *v23; // rax
  __int64 v24; // rcx
  int v25; // eax
  const unsigned __int16 *v26; // rbx
  CDeclaredConfigurationLogger *v27; // rax
  __int64 v28; // rcx
  CDeclaredConfigurationLogger *v29; // rax
  int EnrollmentIdSidStateKey; // ebx
  CDeclaredConfigurationLogger *v31; // rax
  __int64 v32; // rcx
  const unsigned __int16 *v33; // rdx
  CDeclaredConfigurationLogger *v34; // rax
  __int64 v35; // r15
  __int64 v36; // rdi
  __int64 v37; // rbx
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  const unsigned __int16 *v42; // rdx
  signed int RegistryMultiString; // edi
  signed int v44; // ebx
  HKEY v45; // r15
  OLECHAR *v46; // r13
  LSTATUS v47; // eax
  unsigned __int64 v48; // rdi
  unsigned __int64 v49; // rax
  BYTE *v50; // rax
  BYTE *v51; // rbx
  LSTATUS v52; // eax
  unsigned __int16 v53; // dx
  LSTATUS Value; // eax
  LONG v55; // eax
  __int64 v56; // rdx
  CDeclaredConfigurationLogger *v57; // rax
  __int64 v58; // rcx
  unsigned int Lo; // edi
  __int64 StateString; // rax
  __int64 v61; // rcx
  bool v62; // zf
  char *v63; // r8
  const unsigned __int16 *v64; // rdx
  int v65; // eax
  int v66; // eax
  int v67; // eax
  HKEY v68; // r13
  BYTE *v69; // r15
  LSTATUS v70; // eax
  unsigned __int64 v71; // rbx
  unsigned __int64 v72; // rax
  BYTE *v73; // rax
  LSTATUS v74; // eax
  OLECHAR *v75; // rcx
  int v76; // eax
  int v77; // eax
  unsigned __int16 v78; // dx
  LSTATUS v79; // eax
  LONG v80; // eax
  CDeclaredConfigurationLogger *v81; // rax
  int v82; // ecx
  LONG lVal; // ebx
  const unsigned __int16 *v84; // r8
  const unsigned __int16 *v85; // rdx
  struct DeclaredConfigurationScopeData *v86; // rdi
  CDeclaredConfigurationLogger *v87; // rax
  CDeclaredConfigurationLogger *v88; // rax
  CDeclaredConfigurationLogger *v89; // rax
  const unsigned __int16 *v90; // rdx
  int v91; // eax
  char v92; // bl
  CDeclaredConfigurationLogger *v93; // rax
  unsigned int v94; // edi
  unsigned int v95; // edi
  unsigned int v96; // edi
  unsigned int v97; // edi
  unsigned int v98; // edi
  unsigned int v99; // edi
  unsigned int v100; // edi
  unsigned int v101; // edi
  unsigned int v102; // edi
  unsigned int v103; // edi
  __int64 v104; // rcx
  CDeclaredConfigurationLogger *v105; // rax
  __int64 v106; // rdx
  int v107; // eax
  CDeclaredConfigurationLogger *v108; // rax
  int v109; // ecx
  const unsigned __int16 *v110; // rdx
  __int64 v111; // rcx
  int lpData; // [rsp+20h] [rbp-1E8h]
  bool v113; // [rsp+40h] [rbp-1C8h]
  DWORD cbData; // [rsp+44h] [rbp-1C4h] BYREF
  DWORD Type[2]; // [rsp+48h] [rbp-1C0h] BYREF
  HKEY v116; // [rsp+50h] [rbp-1B8h] BYREF
  DWORD lpcbData[2]; // [rsp+58h] [rbp-1B0h] BYREF
  void *Block; // [rsp+60h] [rbp-1A8h] BYREF
  unsigned __int16 *v119; // [rsp+68h] [rbp-1A0h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-198h] BYREF
  HKEY v121; // [rsp+78h] [rbp-190h] BYREF
  __int64 v122; // [rsp+80h] [rbp-188h] BYREF
  OLECHAR *strIn; // [rsp+88h] [rbp-180h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-178h] BYREF
  char v125[8]; // [rsp+A8h] [rbp-160h] BYREF
  struct DeclaredConfigurationScopeData *v126; // [rsp+B0h] [rbp-158h]
  char v127; // [rsp+B9h] [rbp-14Fh]
  HKEY v128; // [rsp+C0h] [rbp-148h] BYREF
  unsigned __int16 *v129; // [rsp+C8h] [rbp-140h]
  void **p_Block; // [rsp+D0h] [rbp-138h]
  char v131; // [rsp+D8h] [rbp-130h]
  unsigned __int16 *v132[3]; // [rsp+E0h] [rbp-128h] BYREF
  unsigned __int64 v133; // [rsp+F8h] [rbp-110h]
  HKEY *p_hKey; // [rsp+100h] [rbp-108h] BYREF
  __int64 v135; // [rsp+108h] [rbp-100h] BYREF
  char v136; // [rsp+110h] [rbp-F8h]
  _BYTE v137[32]; // [rsp+120h] [rbp-E8h] BYREF
  _BYTE v138[32]; // [rsp+140h] [rbp-C8h] BYREF
  _BYTE v139[32]; // [rsp+160h] [rbp-A8h] BYREF
  _BYTE v140[32]; // [rsp+180h] [rbp-88h] BYREF
  _BYTE v141[32]; // [rsp+1A0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  v129 = a3;
  v8 = a2;
  v126 = a1;
  strIn = (OLECHAR *)a6;
  v119 = 0;
  if ( !a1 || !a2 || !a3 || !a4 )
  {
    Logger = CDeclaredConfigurationLogger::GetLogger();
    RefreshFlag = -2147024809;
    v13 = &word_180142E98;
    v14 = L"One of the input parameter is NULL";
LABEL_276:
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      Logger,
      L"DeclaredConfigurationStore_ProcessSingleDoc",
      v14,
      v13,
      RefreshFlag);
LABEL_277:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v119);
    return (unsigned int)RefreshFlag;
  }
  Type[0] = 0;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::GetImpl'::`2'::impl,
    a2);
  if ( *((_QWORD *)v8 + 3) <= 7u )
    v10 = (const unsigned __int16 *)v8;
  else
    v10 = *(const unsigned __int16 **)v8;
  RefreshFlag = DeclaredConfigurationStore_GetRefreshFlag(*(OLECHAR **)a1, v10, Type);
  if ( (int)(RefreshFlag + 0x80000000) >= 0 && RefreshFlag != -2147024894 )
  {
    Logger = CDeclaredConfigurationLogger::GetLogger();
    if ( *((_QWORD *)v8 + 3) > 7u )
      v8 = *(struct DCDocument **)v8;
    v13 = (const unsigned __int16 *)v8;
    v14 = L"DeclaredConfigurationStore_GetRefreshFlag";
    goto LABEL_276;
  }
  v113 = Type[0] != 0;
  v122 = 0;
  v16 = _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
          &v122,
          L"Global\\DeclaredConfigurationMutex");
  if ( v16 < 0 )
  {
    v17 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v17,
      L"DeclaredConfigurationStore_ProcessSingleDoc",
      L"DeclaredConfigurationGlobalMutex.create",
      &word_180142E98,
      v16);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v122);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v119);
    return (unsigned int)v16;
  }
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
    McTemplateU0zz_EventWriteTransfer(
      v15,
      OrchestratorGenericSuccess,
      L"DeclaredConfigurationStore_ProcessSingleDoc",
      L"CreateGlobalDeclaredConfigurationMutex");
  Type[0] = 0;
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v122,
    v125,
    Type,
    180000);
  v19 = DCCheckAcquireStatus(Type[0]);
  v21 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F07,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)v19,
      lpData);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v125);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v122);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v119);
    return v21;
  }
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
    McTemplateU0zz_EventWriteTransfer(
      v20,
      OrchestratorGenericSuccess,
      L"DeclaredConfigurationStore_ProcessSingleDoc",
      L"Acquire lock on global mutex");
  v127 = 1;
  if ( !(unsigned int)_o__wcsicmp(a4, L"user") )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v119,
      0);
    ActiveUserSid = DmGetActiveUserSid(&v119);
    if ( ActiveUserSid < 0 )
    {
      v23 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v23,
        L"DeclaredConfigurationStore_ProcessSingleDoc",
        L"DmGetActiveUserSid",
        &word_180142E98,
        ActiveUserSid);
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
        McTemplateU0zz_EventWriteTransfer(
          v24,
          OrchestratorGenericSuccess,
          L"DeclaredConfigurationStore_ProcessSingleDoc",
          L"On exit, unlock mutex");
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v125);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v122);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v119);
      return (unsigned int)ActiveUserSid;
    }
  }
  v25 = _o__wcsicmp(a4, L"device");
  v26 = v119;
  if ( !v25 )
    v26 = a4;
  Type[0] = 0;
  cbData = 63;
  if ( (int)DCIsValidEnrollment(a3, (int *)Type, (enum EnrollmentStateTag *)&cbData) >= 0
    && (!Type[0] || cbData == 4 && *((_DWORD *)v8 + 68) != 2) )
  {
    v27 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogEnrollmentInvalidOrUnenrolling(v27, a3, -2100297726);
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) == 0 )
    {
LABEL_34:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v125);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v122);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v119);
      return 2194669570LL;
    }
LABEL_33:
    McTemplateU0zz_EventWriteTransfer(
      v28,
      OrchestratorGenericSuccess,
      L"DeclaredConfigurationStore_ProcessSingleDoc",
      L"On exit, unlock mutex");
    goto LABEL_34;
  }
  v121 = 0;
  Type[0] = 0;
  cbData = 63;
  if ( (int)DCIsValidEnrollment(a3, (int *)Type, (enum EnrollmentStateTag *)&cbData) >= 0
    && (!Type[0] || cbData == 4 && *((_DWORD *)v8 + 68) != 2) )
  {
    v29 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogEnrollmentInvalidOrUnenrolling(v29, a3, -2100297726);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v121);
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) == 0 )
      goto LABEL_34;
    goto LABEL_33;
  }
  *(_QWORD *)&pvarg.vt = &v121;
  pvarg.llVal = 0;
  *((_BYTE *)&pvarg.decVal + 16) = 1;
  EnrollmentIdSidStateKey = GetEnrollmentIdSidStateKey(a3, v26, (HKEY *)&pvarg.llVal);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&pvarg);
  if ( EnrollmentIdSidStateKey < 0 )
  {
    v31 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v31,
      L"DeclaredConfigurationStore_ProcessSingleDoc",
      L"GetEnrollmentIdSidStateKey",
      &word_180142E98,
      EnrollmentIdSidStateKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v121);
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
      goto LABEL_257;
    goto LABEL_258;
  }
  Block = 0;
  p_Block = &Block;
  v131 = 1;
  if ( *((_QWORD *)v8 + 3) <= 7u )
    v33 = (const unsigned __int16 *)v8;
  else
    v33 = *(const unsigned __int16 **)v8;
  EnrollmentIdSidStateKey = DCCDNUtil_GetRegistryString(v121, v33, L"MostRecentVersion", (unsigned __int16 **)&Block);
  if ( EnrollmentIdSidStateKey < 0 )
  {
    v34 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v34,
      L"DeclaredConfigurationStore_ProcessSingleDoc",
      L"DCCDNUtil_GetRegistryString:Reading MostRecentVersion",
      &word_180142E98,
      EnrollmentIdSidStateKey);
    operator delete(Block);
    Block = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v121);
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
      goto LABEL_257;
    goto LABEL_258;
  }
  v35 = std::wstring::wstring((__int64)v141, (__int64)L"\\raw");
  v36 = std::wstring::wstring((__int64)v140, (__int64)Block);
  v37 = std::wstring::wstring((__int64)v139, (__int64)L"\\");
  if ( *((_QWORD *)v8 + 3) <= 7u )
    v38 = (__int64)v8;
  else
    v38 = *(_QWORD *)v8;
  v39 = std::wstring::wstring((__int64)v138, v38);
  v40 = std::operator+<unsigned short>(&p_hKey, v39, v37);
  v41 = std::operator+<unsigned short>(v137, v40, v36);
  std::operator+<unsigned short>(v132, v41, v35);
  std::wstring::_Tidy_deallocate(v137);
  std::wstring::_Tidy_deallocate(&p_hKey);
  std::wstring::_Tidy_deallocate(v138);
  std::wstring::_Tidy_deallocate(v139);
  std::wstring::_Tidy_deallocate(v140);
  std::wstring::_Tidy_deallocate(v141);
  std::wstring::wstring((__int64)v137);
  VariantInit(&pvarg);
  pvarg.vt = 3;
  if ( *((_QWORD *)v8 + 3) <= 7u )
    v42 = (const unsigned __int16 *)v8;
  else
    v42 = *(const unsigned __int16 **)v8;
  hKey = 0;
  if ( v42 && Block )
  {
    p_hKey = &hKey;
    v135 = 0;
    v136 = 1;
    GetResultsEnrollmentIdSidStateDocIdVersionKey((_DWORD)a1, (_DWORD)v42, (_DWORD)Block, (unsigned int)&v135, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    v116 = 0;
    if ( pvarg.vt != 3 )
    {
      if ( pvarg.vt == 5 )
        goto LABEL_93;
      if ( pvarg.vt != 8 )
      {
        if ( pvarg.vt != 20 )
        {
          if ( pvarg.vt != 8200 )
          {
            if ( pvarg.vt == 8209 )
            {
              *(_QWORD *)lpcbData = 0;
              Type[0] = 0;
              RegistryMultiString = DCGetRegistryBinary(hKey, 0, L"state", lpcbData, Type);
              if ( RegistryMultiString >= 0 )
              {
                RegistryMultiString = DCInlineSetBinaryToVariant(*(void **)lpcbData, Type[0]);
                if ( RegistryMultiString >= 0 )
                {
                  std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(lpcbData);
LABEL_111:
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v116);
                  RegistryMultiString = 0;
                  LOBYTE(v44) = 87;
                  goto LABEL_115;
                }
              }
              std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(lpcbData);
              goto LABEL_66;
            }
LABEL_99:
            std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v116);
            RegistryMultiString = -2147418113;
            goto LABEL_67;
          }
          goto LABEL_96;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
        {
          *(_QWORD *)lpcbData = 0;
          RegistryMultiString = DCGetRegistryQWORD(hKey, v116, L"state", lpcbData);
          if ( RegistryMultiString >= 0 )
          {
            pvarg.vt = 20;
            pvarg.llVal = *(_QWORD *)lpcbData;
            goto LABEL_111;
          }
          goto LABEL_66;
        }
LABEL_93:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
        {
          *(_QWORD *)lpcbData = 0;
          RegistryMultiString = DCGetRegistryQWORD(hKey, v116, L"state", lpcbData);
          if ( RegistryMultiString >= 0 )
          {
            pvarg.vt = 5;
            pvarg.llVal = *(_QWORD *)lpcbData;
            goto LABEL_111;
          }
          goto LABEL_66;
        }
LABEL_96:
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
          goto LABEL_99;
        *(_QWORD *)Type = 0;
        RegistryMultiString = DCCDNUtil_GetRegistryMultiString(
                                hKey,
                                (const unsigned __int16 *)v116,
                                L"state",
                                (unsigned __int16 **)Type,
                                lpcbData);
        if ( RegistryMultiString >= 0 )
        {
          pvarg.vt = 8200;
          MultiStringToSafeArray(*(OLECHAR **)Type, v53, &pvarg.parray);
          operator delete(*(void **)Type);
          goto LABEL_111;
        }
LABEL_66:
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v116);
LABEL_67:
        LOBYTE(v44) = 87;
        goto LABEL_115;
      }
      v45 = hKey;
      Type[0] = 1;
      cbData = 0;
      if ( !hKey )
      {
        LOBYTE(v44) = 87;
        RegistryMultiString = -2147024809;
        goto LABEL_113;
      }
      v46 = 0;
      v47 = RegQueryValueExW(hKey, L"state", 0, Type, 0, &cbData);
      RegistryMultiString = v47;
      if ( v47 )
      {
        if ( v47 > 0 )
          RegistryMultiString = (unsigned __int16)v47 | 0x80070000;
      }
      else
      {
        if ( Type[0] != 1 )
        {
          RegistryMultiString = -2147418113;
          LOBYTE(v44) = 87;
LABEL_113:
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v116);
          goto LABEL_115;
        }
        v48 = ((unsigned __int64)cbData >> 1) + 1;
        v49 = 2 * v48;
        if ( !is_mul_ok(v48, 2u) )
          v49 = -1;
        v50 = (BYTE *)operator new[](v49, (const struct std::nothrow_t *)std::nothrow);
        v51 = v50;
        if ( !v50 )
        {
          RegistryMultiString = -2147024882;
LABEL_83:
          LOBYTE(v44) = 87;
          goto LABEL_113;
        }
        memset_0(v50, 0, v48);
        v52 = RegQueryValueExW(v45, L"state", 0, Type, v51, &cbData);
        RegistryMultiString = v52;
        if ( !v52 )
        {
          v46 = (OLECHAR *)v51;
          goto LABEL_91;
        }
        if ( v52 > 0 )
          RegistryMultiString = (unsigned __int16)v52 | 0x80070000;
        operator delete(v51);
      }
      if ( RegistryMultiString < 0 )
        goto LABEL_83;
LABEL_91:
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)SysAllocString(v46);
      operator delete(v46);
      goto LABEL_111;
    }
    cbData = 0;
    Type[0] = 4;
    lpcbData[0] = 4;
    if ( !hKey )
    {
      LOBYTE(v44) = 87;
      RegistryMultiString = -2147024809;
      goto LABEL_113;
    }
    Value = RegQueryValueExW(hKey, L"state", 0, Type, (LPBYTE)&cbData, lpcbData);
    RegistryMultiString = Value;
    if ( Value )
    {
      if ( Value > 0 )
        RegistryMultiString = (unsigned __int16)Value | 0x80070000;
      v55 = 0;
      if ( RegistryMultiString < 0 )
        goto LABEL_108;
    }
    else
    {
      if ( Type[0] != 4 )
      {
        RegistryMultiString = -2147418113;
LABEL_108:
        LOBYTE(v44) = 87;
        goto LABEL_113;
      }
      v55 = cbData;
    }
    pvarg.vt = 3;
    pvarg.lVal = v55;
    goto LABEL_111;
  }
  LOBYTE(v44) = 87;
  RegistryMultiString = -2147024809;
LABEL_115:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  if ( RegistryMultiString < 0 )
  {
    v57 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v57,
      L"DeclaredConfigurationStore_ProcessSingleDoc",
      L"DeclaredConfigurationStore_ReadResultData:Read doc State",
      &word_180142E98,
      RegistryMultiString);
    VariantClear(&pvarg);
    std::wstring::_Tidy_deallocate(v137);
    std::wstring::_Tidy_deallocate(v132);
    operator delete(Block);
    Block = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v121);
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(
        v58,
        OrchestratorGenericSuccess,
        L"DeclaredConfigurationStore_ProcessSingleDoc",
        L"On exit, unlock mutex");
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v125);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v122);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v119);
    return (unsigned int)RegistryMultiString;
  }
  Lo = pvarg.cyVal.Lo;
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
  {
    StateString = getStateString(pvarg.cyVal.Lo);
    McTemplateU0zz_EventWriteTransfer(
      v61,
      OrchestratorDocState,
      L"DeclaredConfigurationStore_ProcessSingleDoc",
      StateString);
  }
  if ( Lo > 0x3E )
  {
    if ( Lo <= 0x5F )
    {
      if ( Lo == 95 )
        goto LABEL_270;
      v94 = Lo - 63;
      if ( !v94 )
        goto LABEL_270;
      v95 = v94 - 27;
      if ( !v95 )
        goto LABEL_270;
      v96 = v95 - 1;
      if ( !v96 )
        goto LABEL_270;
      v97 = v96 - 1;
      if ( !v97 )
        goto LABEL_270;
      v98 = v97 - 1;
      if ( !v98 )
        goto LABEL_270;
      v62 = v98 == 1;
      goto LABEL_240;
    }
    v99 = Lo - 96;
    if ( !v99 )
      goto LABEL_270;
    v100 = v99 - 1;
    if ( !v100 )
      goto LABEL_270;
    v101 = v100 - 2;
    if ( !v101 )
      goto LABEL_270;
    v102 = v101 - 3;
    if ( !v102 )
      goto LABEL_270;
    v103 = v102 - 8;
    if ( v103 )
    {
      if ( v103 != 1 )
        goto LABEL_248;
    }
    else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support>::GetImpl'::`2'::impl) )
    {
      if ( !v113 )
      {
        if ( *((_QWORD *)v8 + 3) > 7u )
          v8 = *(struct DCDocument **)v8;
        EnrollmentIdSidStateKey = DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext(
                                    v126,
                                    (const unsigned __int16 *)v8,
                                    0,
                                    (int *)strIn);
        if ( EnrollmentIdSidStateKey < 0 )
        {
          v105 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
            v105,
            L"DeclaredConfigurationStore_ProcessSingleDoc",
            L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
            &word_180142E98,
            EnrollmentIdSidStateKey);
          VariantClear(&pvarg);
          std::wstring::_Tidy_deallocate(v137);
          std::wstring::_Tidy_deallocate(v132);
          operator delete(Block);
          Block = 0;
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v121);
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
LABEL_257:
            McTemplateU0zz_EventWriteTransfer(
              v32,
              OrchestratorGenericSuccess,
              L"DeclaredConfigurationStore_ProcessSingleDoc",
              L"On exit, unlock mutex");
LABEL_258:
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v125);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v122);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v119);
          return (unsigned int)EnrollmentIdSidStateKey;
        }
        goto LABEL_266;
      }
      goto LABEL_269;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support>::GetImpl'::`2'::impl) )
      goto LABEL_270;
    if ( v113 )
    {
      LOBYTE(v106) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::GetImpl'::`2'::impl,
        v106);
      if ( *((_QWORD *)v8 + 3) > 7u )
        v8 = *(struct DCDocument **)v8;
      v107 = DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext(
               v126,
               (const unsigned __int16 *)v8,
               1,
               (int *)strIn);
      v92 = v107;
      if ( v107 >= 0 )
        goto LABEL_266;
LABEL_264:
      v108 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(
        v108,
        L"DeclaredConfigurationStore_ProcessSingleDoc",
        L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
        L"Refresh on ConfigCompletedSuccess, ConfigCompletedError, ProcessOrchestrationInformationFailure, or ProcessOrche"
         "strationInformationSuccess");
      if ( byte_180189FC1 < 0 )
        McTemplateU0zzd_EventWriteTransfer(
          v109,
          (unsigned int)OrchestratorGenericWarning,
          (unsigned int)L"DeclaredConfigurationStore_ProcessSingleDoc",
          (unsigned int)L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext:Refresh on ConfigCompletedSuccess,"
                         " ConfigCompletedError, ProcessOrchestrationInformationFailure, or ProcessOrchestrationInformationSuccess",
          v92);
LABEL_266:
      v110 = (const unsigned __int16 *)v132;
      if ( v133 > 7 )
        v110 = v132[0];
      DCWriteLastRunTimeStamp(v121, v110);
    }
LABEL_269:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v121,
      0);
    goto LABEL_270;
  }
  if ( Lo == 62 )
    goto LABEL_270;
  if ( Lo <= 0x23 )
  {
    if ( Lo == 35 )
    {
      if ( *((_QWORD *)v8 + 3) > 7u )
        v8 = *(struct DCDocument **)v8;
      EnrollmentIdSidStateKey = DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext(
                                  v126,
                                  (const unsigned __int16 *)v8,
                                  0,
                                  (int *)strIn);
      if ( EnrollmentIdSidStateKey < 0 )
      {
        v89 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v89,
          L"DeclaredConfigurationStore_ProcessSingleDoc",
          L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
          L"From state: CDNDownloadedCookConfigurationSuccess",
          EnrollmentIdSidStateKey);
        VariantClear(&pvarg);
        std::wstring::_Tidy_deallocate(v137);
        std::wstring::_Tidy_deallocate(v132);
        operator delete(Block);
        Block = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v121);
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
          goto LABEL_257;
        goto LABEL_258;
      }
      v90 = (const unsigned __int16 *)v132;
      if ( v133 > 7 )
        v90 = v132[0];
      DCWriteLastRunTimeStamp(v121, v90);
      goto LABEL_270;
    }
    if ( Lo == 1 || Lo == 2 )
      goto LABEL_224;
    if ( Lo != 3 )
    {
      if ( Lo != 10 && Lo != 11 && Lo != 20 )
      {
        v62 = Lo == 34;
LABEL_240:
        if ( !v62 )
          goto LABEL_248;
LABEL_270:
        VariantClear(&pvarg);
        std::wstring::_Tidy_deallocate(v137);
        std::wstring::_Tidy_deallocate(v132);
        operator delete(Block);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v121);
        v128 = 0;
        p_hKey = &v128;
        v135 = 0;
        v136 = 1;
        RefreshFlag = DCGetEnrollmentsRootKey(&v135, 0);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
        if ( RefreshFlag >= 0 )
          DCCDNUtil_SetRegistryString(v128, 0, L"WinDCActiveEnrollmentId", v129, 0);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v128);
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
          McTemplateU0zz_EventWriteTransfer(
            v111,
            OrchestratorGenericSuccess,
            L"DeclaredConfigurationStore_ProcessSingleDoc",
            L"On exit, unlock mutex");
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v125);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v122);
        goto LABEL_277;
      }
LABEL_224:
      if ( v113 )
        goto LABEL_269;
      if ( *((_QWORD *)v8 + 3) > 7u )
        v8 = *(struct DCDocument **)v8;
      EnrollmentIdSidStateKey = DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext(
                                  v126,
                                  (const unsigned __int16 *)v8,
                                  0,
                                  (int *)strIn);
      if ( EnrollmentIdSidStateKey < 0 )
      {
        v93 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v93,
          L"DeclaredConfigurationStore_ProcessSingleDoc",
          L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
          &word_180142E98,
          EnrollmentIdSidStateKey);
        VariantClear(&pvarg);
        std::wstring::_Tidy_deallocate(v137);
        std::wstring::_Tidy_deallocate(v132);
        operator delete(Block);
        Block = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v121);
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
          goto LABEL_257;
        goto LABEL_258;
      }
      if ( Lo - 10 <= 1 )
        goto LABEL_269;
      goto LABEL_266;
    }
    VariantClear(&pvarg);
    pvarg.vt = 3;
    if ( *((_QWORD *)v8 + 15) <= 7u )
      v63 = (char *)v8 + 96;
    else
      v63 = (char *)*((_QWORD *)v8 + 12);
    if ( *((_QWORD *)v8 + 3) <= 7u )
      v64 = (const unsigned __int16 *)v8;
    else
      v64 = *(const unsigned __int16 **)v8;
    v116 = 0;
    if ( !v64 || !v63 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v116);
LABEL_190:
      v81 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(
        v81,
        L"DeclaredConfigurationStore_ProcessSingleDoc",
        L"DeclaredConfigurationStore_ReadResultData",
        L"Read reboot state");
      if ( byte_180189FC1 < 0 )
        McTemplateU0zzd_EventWriteTransfer(
          v82,
          (unsigned int)OrchestratorGenericWarning,
          (unsigned int)L"DeclaredConfigurationStore_ProcessSingleDoc",
          (unsigned int)L"DeclaredConfigurationStore_ReadResultData: read reboot state",
          v44);
LABEL_192:
      lVal = pvarg.lVal;
      VariantClear(&pvarg);
      pvarg.vt = 3;
      if ( lVal )
      {
        pvarg.lVal = 0;
        v84 = (const unsigned __int16 *)((char *)v8 + 96);
        if ( *((_QWORD *)v8 + 15) > 7u )
          v84 = *(const unsigned __int16 **)v84;
        if ( *((_QWORD *)v8 + 3) <= 7u )
          v85 = (const unsigned __int16 *)v8;
        else
          v85 = *(const unsigned __int16 **)v8;
        v86 = v126;
        EnrollmentIdSidStateKey = DeclaredConfigurationStore_WriteResultData(
                                    v126,
                                    v85,
                                    v84,
                                    0,
                                    0,
                                    0,
                                    L"rebootstate",
                                    &pvarg);
        if ( EnrollmentIdSidStateKey < 0 )
        {
          v87 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
            v87,
            L"DeclaredConfigurationStore_ProcessSingleDoc",
            L"DeclaredConfigurationStore_WriteResultData",
            L"Update doc reboot state",
            EnrollmentIdSidStateKey);
          VariantClear(&pvarg);
          std::wstring::_Tidy_deallocate(v137);
          std::wstring::_Tidy_deallocate(v132);
          operator delete(Block);
          Block = 0;
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v121);
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
            goto LABEL_257;
          goto LABEL_258;
        }
        VariantClear(&pvarg);
        pvarg.vt = 3;
        pvarg.lVal = 63;
        if ( *((_QWORD *)v8 + 3) > 7u )
          v8 = *(struct DCDocument **)v8;
        EnrollmentIdSidStateKey = DeclaredConfigurationStore_WriteResultData(
                                    v86,
                                    (const unsigned __int16 *)v8,
                                    (const unsigned __int16 *)Block,
                                    0,
                                    0,
                                    0,
                                    L"state",
                                    &pvarg);
        if ( EnrollmentIdSidStateKey < 0 )
        {
          v88 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
            v88,
            L"DeclaredConfigurationStore_ProcessSingleDoc",
            L"DeclaredConfigurationStore_WriteResultData",
            L"Update doc state",
            EnrollmentIdSidStateKey);
          VariantClear(&pvarg);
          std::wstring::_Tidy_deallocate(v137);
          std::wstring::_Tidy_deallocate(v132);
          operator delete(Block);
          Block = 0;
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v121);
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
            goto LABEL_257;
          goto LABEL_258;
        }
      }
      goto LABEL_270;
    }
    p_hKey = &v116;
    v135 = 0;
    v136 = 1;
    GetResultsEnrollmentIdSidStateDocIdVersionKey((_DWORD)v126, (_DWORD)v64, (_DWORD)v63, (unsigned int)&v135, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    hKey = 0;
    if ( pvarg.vt != 3 )
    {
      if ( pvarg.vt == 5 )
        goto LABEL_172;
      if ( pvarg.vt != 8 )
      {
        if ( pvarg.vt != 20 )
        {
          if ( pvarg.vt != 8200 )
          {
            if ( pvarg.vt == 8209 )
            {
              *(_QWORD *)lpcbData = 0;
              Type[0] = 0;
              v65 = DCGetRegistryBinary(v116, 0, L"rebootstate", lpcbData, Type);
              LOBYTE(v44) = v65;
              if ( v65 >= 0 )
              {
                v66 = DCInlineSetBinaryToVariant(*(void **)lpcbData, Type[0]);
                LOBYTE(v44) = v66;
                if ( v66 >= 0 )
                {
                  std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(lpcbData);
LABEL_188:
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&hKey);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v116);
                  goto LABEL_192;
                }
              }
              std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(lpcbData);
              goto LABEL_171;
            }
            goto LABEL_178;
          }
LABEL_175:
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
          {
LABEL_178:
            std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&hKey);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v116);
            LOBYTE(v44) = -1;
            goto LABEL_190;
          }
          strIn = 0;
          v77 = DCCDNUtil_GetRegistryMultiString(v116, (const unsigned __int16 *)hKey, L"rebootstate", &strIn, lpcbData);
          LOBYTE(v44) = v77;
          if ( v77 >= 0 )
          {
            pvarg.vt = 8200;
            MultiStringToSafeArray(strIn, v78, &pvarg.parray);
            v75 = strIn;
            goto LABEL_170;
          }
LABEL_171:
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&hKey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v116);
          goto LABEL_190;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
        {
          strIn = 0;
          v67 = DCGetRegistryQWORD(v116, hKey, L"rebootstate", &strIn);
          LOBYTE(v44) = v67;
          if ( v67 < 0 )
            goto LABEL_171;
          pvarg.vt = 20;
          goto LABEL_153;
        }
LABEL_172:
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
          goto LABEL_175;
        strIn = 0;
        v76 = DCGetRegistryQWORD(v116, hKey, L"rebootstate", &strIn);
        LOBYTE(v44) = v76;
        if ( v76 < 0 )
          goto LABEL_171;
        pvarg.vt = 5;
LABEL_153:
        pvarg.llVal = (LONGLONG)strIn;
        goto LABEL_188;
      }
      v68 = v116;
      cbData = 1;
      Type[0] = 0;
      if ( !v116 )
        goto LABEL_171;
      v69 = 0;
      strIn = 0;
      v70 = RegQueryValueExW(v116, L"rebootstate", 0, &cbData, 0, Type);
      v44 = v70;
      if ( v70 )
      {
        if ( v70 > 0 )
          v44 = (unsigned __int16)v70 | 0x80070000;
        goto LABEL_168;
      }
      if ( cbData == 1 )
      {
        v71 = ((unsigned __int64)Type[0] >> 1) + 1;
        v72 = 2 * v71;
        if ( !is_mul_ok(v71, 2u) )
          v72 = -1;
        v73 = (BYTE *)operator new[](v72, (const struct std::nothrow_t *)std::nothrow);
        v69 = v73;
        if ( !v73 )
        {
          LOBYTE(v44) = 14;
          goto LABEL_171;
        }
        memset_0(v73, 0, v71);
        v74 = RegQueryValueExW(v68, L"rebootstate", 0, &cbData, v69, Type);
        v44 = v74;
        if ( !v74 )
        {
LABEL_169:
          pvarg.vt = 8;
          pvarg.llVal = (LONGLONG)SysAllocString((const OLECHAR *)v69);
          v75 = (OLECHAR *)v69;
LABEL_170:
          operator delete(v75);
          goto LABEL_188;
        }
        if ( v74 > 0 )
          v44 = (unsigned __int16)v74 | 0x80070000;
        operator delete(v69);
        v69 = (BYTE *)strIn;
LABEL_168:
        if ( v44 < 0 )
          goto LABEL_171;
        goto LABEL_169;
      }
LABEL_159:
      LOBYTE(v44) = -1;
      goto LABEL_171;
    }
    cbData = 0;
    Type[0] = 4;
    lpcbData[0] = 4;
    if ( !v116 )
      goto LABEL_171;
    v79 = RegQueryValueExW(v116, L"rebootstate", 0, Type, (LPBYTE)&cbData, lpcbData);
    v44 = v79;
    if ( v79 )
    {
      if ( v79 > 0 )
        v44 = (unsigned __int16)v79 | 0x80070000;
      v80 = 0;
      if ( v44 < 0 )
        goto LABEL_171;
    }
    else
    {
      if ( Type[0] != 4 )
        goto LABEL_159;
      v80 = cbData;
    }
    pvarg.vt = 3;
    pvarg.lVal = v80;
    goto LABEL_188;
  }
  switch ( Lo )
  {
    case '$':
    case '(':
      goto LABEL_270;
    case ')':
      goto LABEL_219;
    case '+':
      goto LABEL_224;
  }
  if ( Lo - 60 <= 1 )
  {
LABEL_219:
    if ( v113 )
    {
      LOBYTE(v56) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::GetImpl'::`2'::impl,
        v56);
      if ( *((_QWORD *)v8 + 3) > 7u )
        v8 = *(struct DCDocument **)v8;
      v91 = DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext(
              v126,
              (const unsigned __int16 *)v8,
              1,
              (int *)strIn);
      v92 = v91;
      if ( v91 >= 0 )
        goto LABEL_266;
      goto LABEL_264;
    }
    goto LABEL_269;
  }
LABEL_248:
  VariantClear(&pvarg);
  std::wstring::_Tidy_deallocate(v137);
  std::wstring::_Tidy_deallocate(v132);
  operator delete(Block);
  Block = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v121);
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
    McTemplateU0zz_EventWriteTransfer(
      v104,
      OrchestratorGenericSuccess,
      L"DeclaredConfigurationStore_ProcessSingleDoc",
      L"On exit, unlock mutex");
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v125);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v122);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v119);
  return 2147549183LL;
}

```

## disassembly

```asm
0x18007f370  push    rbx
0x18007f372  push    rsi
0x18007f373  push    rdi
0x18007f374  push    r12
0x18007f376  push    r13
0x18007f378  push    r14
0x18007f37a  push    r15
0x18007f37c  sub     rsp, 1D0h
0x18007f383  mov     rax, cs:__security_cookie
0x18007f38a  xor     rax, rsp
0x18007f38d  mov     [rsp+208h+var_48], rax
0x18007f395  mov     rdi, r9
0x18007f398  mov     r13, r8
0x18007f39b  mov     [rsp+208h+var_140], r8
0x18007f3a3  mov     rsi, rdx
0x18007f3a6  mov     r12, rcx
0x18007f3a9  mov     [rsp+208h+var_158], rcx
0x18007f3b1  mov     rax, [rsp+208h+arg_28]
0x18007f3b9  mov     [rsp+208h+strIn], rax
0x18007f3c1  xor     r14d, r14d
0x18007f3c4  mov     [rsp+208h+var_1A0], r14
0x18007f3c9  test    rcx, rcx
0x18007f3cc  jz      loc_180080E24
0x18007f3d2  test    rdx, rdx
0x18007f3d5  jz      loc_180080E24
0x18007f3db  test    r8, r8
0x18007f3de  jz      loc_180080E24
0x18007f3e4  test    r9, r9
0x18007f3e7  jz      loc_180080E24
0x18007f3ed  mov     [rsp+208h+Type], r14d
0x18007f3f2  mov     dl, 1
0x18007f3f4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::GetImpl(void)'::`2'::impl
0x18007f3fb  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18007f400  cmp     qword ptr [rsi+18h], 7
0x18007f405  jbe     short loc_18007F40C
0x18007f407  mov     rdx, [rsi]
0x18007f40a  jmp     short loc_18007F40F
0x18007f40c  mov     rdx, rsi; unsigned __int16 *
0x18007f40f  lea     r8, [rsp+208h+Type]; unsigned int *
0x18007f414  mov     rcx, [r12]; psz
0x18007f418  call    ?DeclaredConfigurationStore_GetRefreshFlag@@YAJPEBG0PEAK@Z; DeclaredConfigurationStore_GetRefreshFlag(ushort const *,ushort const *,ulong *)
0x18007f41d  mov     ebx, eax
0x18007f41f  mov     eax, 80000000h
0x18007f424  lea     ecx, [rbx+rax]
0x18007f427  test    eax, ecx
0x18007f429  jnz     short loc_18007F451
0x18007f42b  cmp     ebx, 80070002h
0x18007f431  jz      short loc_18007F451
0x18007f433  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18007f438  cmp     qword ptr [rsi+18h], 7
0x18007f43d  jbe     short loc_18007F442
0x18007f43f  mov     rsi, [rsi]
0x18007f442  mov     r9, rsi
0x18007f445  lea     r8, aDeclaredconfig_237; "DeclaredConfigurationStore_GetRefreshFl"...
0x18007f44c  jmp     loc_180080E3C
0x18007f451  cmp     [rsp+208h+Type], r14d
0x18007f456  setnz   [rsp+208h+var_1C8]
0x18007f45b  mov     [rsp+208h+var_188], r14
0x18007f463  lea     rdx, aGlobalDeclared; "Global\\DeclaredConfigurationMutex"
0x18007f46a  lea     rcx, [rsp+208h+var_188]
0x18007f472  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18007f477  mov     ebx, eax
0x18007f479  test    eax, eax
0x18007f47b  jns     short loc_18007F4C3
0x18007f47d  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18007f482  mov     dword ptr [rsp+208h+lpData], ebx; int
0x18007f486  lea     r9, word_180142E98; unsigned __int16 *
0x18007f48d  lea     r8, aDeclaredconfig_192; "DeclaredConfigurationGlobalMutex.create"
0x18007f494  lea     rdx, aDeclaredconfig_182; "DeclaredConfigurationStore_ProcessSingl"...
0x18007f49b  mov     rcx, rax; this
0x18007f49e  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x18007f4a3  nop
0x18007f4a4  lea     rcx, [rsp+208h+var_188]
0x18007f4ac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f4b1  nop
0x18007f4b2  lea     rcx, [rsp+208h+var_1A0]
0x18007f4b7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007f4bc  mov     eax, ebx
0x18007f4be  jmp     loc_180080E5C
0x18007f4c3  lea     r14, aDeclaredconfig_182; "DeclaredConfigurationStore_ProcessSingl"...
0x18007f4ca  lea     r15, OrchestratorGenericSuccess
0x18007f4d1  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x18007f4d8  jz      short loc_18007F4EC
0x18007f4da  lea     r9, aCreateglobalde; "CreateGlobalDeclaredConfigurationMutex"
0x18007f4e1  mov     r8, r14
0x18007f4e4  mov     rdx, r15
0x18007f4e7  call    McTemplateU0zz_EventWriteTransfer
0x18007f4ec  mov     [rsp+208h+Type], 0
0x18007f4f4  mov     r9d, 2BF20h
0x18007f4fa  lea     r8, [rsp+208h+Type]
0x18007f4ff  lea     rdx, [rsp+208h+var_160]
0x18007f507  lea     rcx, [rsp+208h+var_188]
0x18007f50f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18007f514  nop
0x18007f515  mov     ecx, [rsp+208h+Type]; unsigned int
0x18007f519  call    ?DCCheckAcquireStatus@@YAJK@Z; DCCheckAcquireStatus(ulong)
0x18007f51e  mov     ebx, eax
0x18007f520  test    eax, eax
0x18007f522  jns     short loc_18007F56E
0x18007f524  mov     rcx, [rsp+208h]; this
0x18007f52c  mov     r9d, eax; char *
0x18007f52f  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18007f536  mov     edx, 3F07h; void *
0x18007f53b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f540  nop
0x18007f541  lea     rcx, [rsp+208h+var_160]
0x18007f549  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f54e  nop
0x18007f54f  lea     rcx, [rsp+208h+var_188]
0x18007f557  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f55c  nop
0x18007f55d  lea     rcx, [rsp+208h+var_1A0]
0x18007f562  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007f567  mov     eax, ebx
0x18007f569  jmp     loc_180080E5C
0x18007f56e  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x18007f575  jz      short loc_18007F589
0x18007f577  lea     r9, aAcquireLockOnG; "Acquire lock on global mutex"
0x18007f57e  mov     r8, r14
0x18007f581  mov     rdx, r15
0x18007f584  call    McTemplateU0zz_EventWriteTransfer
0x18007f589  mov     [rsp+208h+var_14F], 1
0x18007f591  lea     rdx, aUser_0; "user"
0x18007f598  mov     rcx, rdi
0x18007f59b  call    cs:__imp__o__wcsicmp
0x18007f5a1  test    eax, eax
0x18007f5a3  jnz     loc_18007F632
0x18007f5a9  xor     edx, edx
0x18007f5ab  lea     rcx, [rsp+208h+var_1A0]
0x18007f5b0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18007f5b5  lea     rcx, [rsp+208h+var_1A0]
0x18007f5ba  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18007f5c0  mov     ebx, eax
0x18007f5c2  test    eax, eax
0x18007f5c4  jns     short loc_18007F632
0x18007f5c6  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18007f5cb  mov     dword ptr [rsp+208h+lpData], ebx; int
0x18007f5cf  lea     r9, word_180142E98; unsigned __int16 *
0x18007f5d6  lea     r8, aDmgetactiveuse_1; "DmGetActiveUserSid"
0x18007f5dd  mov     rdx, r14; unsigned __int16 *
0x18007f5e0  mov     rcx, rax; this
0x18007f5e3  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x18007f5e8  nop
0x18007f5e9  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x18007f5f0  jz      short loc_18007F605
0x18007f5f2  lea     r9, aOnExitUnlockMu; "On exit, unlock mutex"
0x18007f5f9  mov     r8, r14
0x18007f5fc  mov     rdx, r15
0x18007f5ff  call    McTemplateU0zz_EventWriteTransfer
0x18007f604  nop
0x18007f605  lea     rcx, [rsp+208h+var_160]
0x18007f60d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f612  nop
0x18007f613  lea     rcx, [rsp+208h+var_188]
0x18007f61b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f620  nop
0x18007f621  lea     rcx, [rsp+208h+var_1A0]
0x18007f626  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007f62b  mov     eax, ebx
0x18007f62d  jmp     loc_180080E5C
0x18007f632  lea     rdx, aDevice_4; "device"
0x18007f639  mov     rcx, rdi
0x18007f63c  call    cs:__imp__o__wcsicmp
0x18007f642  mov     rbx, [rsp+208h+var_1A0]
0x18007f647  test    eax, eax
0x18007f649  cmovz   rbx, rdi
0x18007f64d  xor     edi, edi
0x18007f64f  mov     [rsp+208h+Type], edi
0x18007f653  mov     [rsp+208h+cbData], 3Fh ; '?'
0x18007f65b  lea     r8, [rsp+208h+cbData]; enum EnrollmentStateTag *
0x18007f660  lea     rdx, [rsp+208h+Type]; int *
0x18007f665  mov     rcx, r13; StringUuid
0x18007f668  call    ?DCIsValidEnrollment@@YAJPEBGPEAHPEAW4EnrollmentStateTag@@@Z; DCIsValidEnrollment(ushort const *,int *,EnrollmentStateTag *)
0x18007f66d  test    eax, eax
0x18007f66f  js      short loc_18007F6E9
0x18007f671  cmp     [rsp+208h+Type], edi
0x18007f675  jz      short loc_18007F687
0x18007f677  cmp     [rsp+208h+cbData], 4
0x18007f67c  jnz     short loc_18007F6E9
0x18007f67e  cmp     dword ptr [rsi+110h], 2
0x18007f685  jz      short loc_18007F6E9
0x18007f687  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18007f68c  mov     ebx, 82D00002h
0x18007f691  mov     r8d, ebx; int
0x18007f694  mov     rdx, r13; unsigned __int16 *
0x18007f697  mov     rcx, rax; this
0x18007f69a  call    ?LogEnrollmentInvalidOrUnenrolling@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogEnrollmentInvalidOrUnenrolling(ushort const *,long)
0x18007f69f  nop
0x18007f6a0  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x18007f6a7  jz      short loc_18007F6BC
0x18007f6a9  lea     r9, aOnExitUnlockMu; "On exit, unlock mutex"
0x18007f6b0  mov     r8, r14
0x18007f6b3  mov     rdx, r15
0x18007f6b6  call    McTemplateU0zz_EventWriteTransfer
0x18007f6bb  nop
0x18007f6bc  lea     rcx, [rsp+208h+var_160]
0x18007f6c4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f6c9  nop
0x18007f6ca  lea     rcx, [rsp+208h+var_188]
0x18007f6d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f6d7  nop
0x18007f6d8  lea     rcx, [rsp+208h+var_1A0]
0x18007f6dd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007f6e2  mov     eax, ebx
0x18007f6e4  jmp     loc_180080E5C
0x18007f6e9  mov     [rsp+208h+var_190], rdi
0x18007f6ee  mov     [rsp+208h+Type], edi
0x18007f6f2  mov     [rsp+208h+cbData], 3Fh ; '?'
0x18007f6fa  lea     r8, [rsp+208h+cbData]; enum EnrollmentStateTag *
0x18007f6ff  lea     rdx, [rsp+208h+Type]; int *
0x18007f704  mov     rcx, r13; StringUuid
0x18007f707  call    ?DCIsValidEnrollment@@YAJPEBGPEAHPEAW4EnrollmentStateTag@@@Z; DCIsValidEnrollment(ushort const *,int *,EnrollmentStateTag *)
0x18007f70c  test    eax, eax
0x18007f70e  js      loc_18007F797
0x18007f714  cmp     [rsp+208h+Type], edi
0x18007f718  jz      short loc_18007F72A
0x18007f71a  cmp     [rsp+208h+cbData], 4
0x18007f71f  jnz     short loc_18007F797
0x18007f721  cmp     dword ptr [rsi+110h], 2
0x18007f728  jz      short loc_18007F797
0x18007f72a  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18007f72f  mov     ebx, 82D00002h
0x18007f734  mov     r8d, ebx; int
0x18007f737  mov     rdx, r13; unsigned __int16 *
0x18007f73a  mov     rcx, rax; this
0x18007f73d  call    ?LogEnrollmentInvalidOrUnenrolling@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogEnrollmentInvalidOrUnenrolling(ushort const *,long)
0x18007f742  nop
0x18007f743  lea     rcx, [rsp+208h+var_190]
0x18007f748  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007f74d  nop
0x18007f74e  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x18007f755  jz      short loc_18007F76A
0x18007f757  lea     r9, aOnExitUnlockMu; "On exit, unlock mutex"
0x18007f75e  mov     r8, r14
0x18007f761  mov     rdx, r15
0x18007f764  call    McTemplateU0zz_EventWriteTransfer
0x18007f769  nop
0x18007f76a  lea     rcx, [rsp+208h+var_160]
0x18007f772  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f777  nop
0x18007f778  lea     rcx, [rsp+208h+var_188]
0x18007f780  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f785  nop
0x18007f786  lea     rcx, [rsp+208h+var_1A0]
0x18007f78b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007f790  mov     eax, ebx
0x18007f792  jmp     loc_180080E5C
0x18007f797  lea     rax, [rsp+208h+var_190]
0x18007f79c  mov     qword ptr [rsp+208h+pvarg], rax
0x18007f7a4  mov     qword ptr [rsp+208h+pvarg+8], rdi
0x18007f7ac  mov     byte ptr [rsp+208h+pvarg+10h], 1
0x18007f7b4  lea     r8, [rsp+208h+pvarg+8]; HKEY *
0x18007f7bc  mov     rdx, rbx; unsigned __int16 *
0x18007f7bf  mov     rcx, r13; unsigned __int16 *
0x18007f7c2  call    ?GetEnrollmentIdSidStateKey@@YAJPEBG0PEAPEAUHKEY__@@@Z; GetEnrollmentIdSidStateKey(ushort const *,ushort const *,HKEY__ * *)
0x18007f7c7  mov     ebx, eax
0x18007f7c9  lea     rcx, [rsp+208h+pvarg]
0x18007f7d1  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18007f7d6  test    ebx, ebx
0x18007f7d8  jns     short loc_18007F851
0x18007f7da  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18007f7df  mov     dword ptr [rsp+208h+lpData], ebx; int
0x18007f7e3  lea     r9, word_180142E98; unsigned __int16 *
0x18007f7ea  lea     r8, aGetenrollmenti_3; "GetEnrollmentIdSidStateKey"
0x18007f7f1  mov     rdx, r14; unsigned __int16 *
0x18007f7f4  mov     rcx, rax; this
0x18007f7f7  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x18007f7fc  nop
0x18007f7fd  lea     rcx, [rsp+208h+var_190]
0x18007f802  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007f807  nop
0x18007f808  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x18007f80f  jz      short loc_18007F824
0x18007f811  lea     r9, aOnExitUnlockMu; "On exit, unlock mutex"
0x18007f818  mov     r8, r14
0x18007f81b  mov     rdx, r15
0x18007f81e  call    McTemplateU0zz_EventWriteTransfer
0x18007f823  nop
0x18007f824  lea     rcx, [rsp+208h+var_160]
0x18007f82c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f831  nop
0x18007f832  lea     rcx, [rsp+208h+var_188]
0x18007f83a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f83f  nop
0x18007f840  lea     rcx, [rsp+208h+var_1A0]
0x18007f845  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007f84a  mov     eax, ebx
0x18007f84c  jmp     loc_180080E5C
0x18007f851  mov     [rsp+208h+Block], rdi
0x18007f856  lea     rax, [rsp+208h+Block]
0x18007f85b  mov     [rsp+208h+var_138], rax
0x18007f863  mov     [rsp+208h+var_130], 1
0x18007f86b  cmp     qword ptr [rsi+18h], 7
0x18007f870  jbe     short loc_18007F877
0x18007f872  mov     rdx, [rsi]
0x18007f875  jmp     short loc_18007F87A
0x18007f877  mov     rdx, rsi; unsigned __int16 *
0x18007f87a  lea     r9, [rsp+208h+Block]; unsigned __int16 **
0x18007f87f  lea     r8, aMostrecentvers; "MostRecentVersion"
0x18007f886  mov     rcx, [rsp+208h+var_190]; HKEY
  ... truncated ...
```
