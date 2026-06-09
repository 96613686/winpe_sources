# DeclaredConfigurationStore_ConstructURIStorage(DeclaredConfigurationScopeData *,DCDocument *,bool)

- ea: `0x180067160`
- end: `0x180068af9`
- name: `?DeclaredConfigurationStore_ConstructURIStorage@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@_N@Z`
- size: `6553`
- prototype: `__int64 __fastcall(struct DeclaredConfigurationScopeData *, struct DCDocument *, bool)`
- caller_count: `2`
- callee_count: `65`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180084570`
- `0x1801223f0`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x18000c8f4`
- `0x18000e310`
- `0x18000e32c`
- `0x1800117bc`
- `0x1800117dc`
- `0x180011fe0`
- `0x180012dc4`
- `0x18001438c`
- `0x1800143c8`
- `0x180018744`
- `0x180018a20`
- `0x180018ac0`
- `0x180018b30`
- `0x180018c6c`
- `0x180018cc4`
- `0x1800192f8`
- `0x180019d38`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d020`
- `0x18001d03c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18001dea8`
- `0x18004b870`
- `0x18004d158`
- `0x18004d1ac`
- `0x18004dc70`
- `0x180057354`
- `0x180058148`
- `0x180059990`
- `0x18005e76c`
- `0x18005e7dc`
- `0x18005ef7c`
- `0x1800601c0`
- `0x180067160`
- `0x1800725e0`
- `0x1800726a4`
- `0x180086c10`
- `0x18008ea9c`
- `0x180098fb4`
- `0x180099040`
- `0x18009a2e4`
- `0x18009aaf0`
- `0x1800a0138`
- `0x1800a04fc`
- `0x1800a0de4`
- `0x1800a1004`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800687a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800687a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067381`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006820a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180068476`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006820a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180068476`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006779f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006779f`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180067a3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180067a3b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180067a59`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180067a59`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800673c2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800673c2`
- `DeclaredConfiguration!DMOrchestratorConfig` at `0x18006897e`
- `DeclaredConfiguration!DMOrchestratorConfig` at `0x18006897e`
- `OLEAUT32!__imp_VariantInit` at `0x180067f80`
- `OLEAUT32!__imp_VariantInit` at `0x1800680be`
- `OLEAUT32!__imp_VariantInit` at `0x1800685fb`
- `OLEAUT32!__imp_VariantInit` at `0x180067f80`
- `OLEAUT32!__imp_VariantInit` at `0x1800680be`
- `OLEAUT32!__imp_VariantInit` at `0x1800685fb`
- `OLEAUT32!__imp_VariantClear` at `0x180067ff2`
- `OLEAUT32!__imp_VariantClear` at `0x180068020`
- `OLEAUT32!__imp_VariantClear` at `0x180068133`
- `OLEAUT32!__imp_VariantClear` at `0x180068162`
- `OLEAUT32!__imp_VariantClear` at `0x180068672`
- `OLEAUT32!__imp_VariantClear` at `0x180068847`
- `OLEAUT32!__imp_VariantClear` at `0x180067ff2`
- `OLEAUT32!__imp_VariantClear` at `0x180068020`
- `OLEAUT32!__imp_VariantClear` at `0x180068133`
- `OLEAUT32!__imp_VariantClear` at `0x180068162`
- `OLEAUT32!__imp_VariantClear` at `0x180068672`
- `OLEAUT32!__imp_VariantClear` at `0x180068847`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180067c9c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180067c9c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180067262`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180067ccd`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180067262`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180067ccd`
- `dmiso8601utils!FileTimeToISO8601String` at `0x180067aa3`
- `dmiso8601utils!FileTimeToISO8601String` at `0x180067aa3`

## string_xrefs

- `0x180068734`: `BulkTemplateVersion`
- `0x1800678c0`: `osconfigscenario`
- `0x180067910`: `osconfigscenarioschema`
- `0x18006795c`: `osconfigscenariosVersion`
- `0x180067291`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180067a6b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800688b8`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180067326`: `DeclaredConfigurationStore_ConstructURIStorage:PerOrchestratorRequestMutex`
- `0x1800673aa`: `DeclaredConfigurationStore_ConstructURIStorage`
- `0x1800673fa`: `DeclaredConfigurationStore_ConstructURIStorage`
- `0x180067600`: `DeclaredConfigurationStore_ConstructURIStorage`
- `0x180067709`: `DeclaredConfigurationStore_ConstructURIStorage`
- `0x180068784`: `DeclaredConfigurationStore_ConstructURIStorage`
- `0x1800675f9`: `Same doc id with different operation/configuration request already exists`
- `0x180067702`: `Same doc id with different type already exists`
- `0x180068779`: `DCCDNUtil_GetRegistryString`
- `0x180068759`: `Failed to set the Bulk Template version of the doc`
- `0x180068760`: `DCCDNUtil_SetRegistryString`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall DeclaredConfigurationStore_ConstructURIStorage(
        struct DeclaredConfigurationScopeData *a1,
        struct DCDocument *a2,
        char a3)
{
  struct DeclaredConfigurationScopeData *v4; // r13
  __int64 v5; // rdx
  OrchestratorDBManager *v6; // rcx
  const unsigned __int16 *v7; // r9
  const unsigned __int16 *v8; // r8
  int v9; // eax
  int EnrollmentIdSidStateDocIdKey; // ebx
  __int64 v11; // rdx
  int mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v13; // ecx
  int i; // r14d
  signed int LastError; // eax
  int v16; // ecx
  signed int v17; // ebx
  int v18; // ecx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 *v21; // r12
  __int64 v22; // rax
  const unsigned __int16 *v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  int v26; // ecx
  __int64 v27; // rdx
  __int64 v28; // rdx
  int v29; // ecx
  const unsigned __int16 *v30; // rdx
  signed int FilePathForOriginalDocStorage; // ebx
  __int64 v32; // r8
  __int64 v33; // rdx
  const unsigned __int16 *v34; // r9
  const unsigned __int16 *v35; // r9
  const unsigned __int16 *v36; // r9
  struct DCDocument *v37; // rax
  const unsigned __int16 *v38; // r9
  const unsigned __int16 *v39; // r9
  const unsigned __int16 *v40; // r9
  const char *v41; // r9
  __int64 v42; // rdx
  __int64 v43; // rdx
  int RegistryString; // ebx
  __int64 v45; // r8
  const unsigned __int16 *v46; // r9
  __int64 ****v47; // rcx
  __int64 **v48; // r12
  __int64 **v49; // r13
  const unsigned __int16 *v50; // r8
  const unsigned __int16 *v51; // r9
  __int64 v52; // rcx
  __int64 v53; // r8
  __int64 last_of; // rbx
  __int64 v55; // rax
  __int64 v56; // rax
  wil *v57; // rax
  const unsigned __int16 *v58; // rdx
  const unsigned __int16 *v59; // rax
  const unsigned __int16 *v60; // r9
  const unsigned __int16 *v61; // rax
  const unsigned __int16 *v62; // rax
  const unsigned __int16 *v63; // r8
  const unsigned __int16 *v64; // rax
  const unsigned __int16 *v65; // r8
  unsigned int v66; // r12d
  _QWORD *v67; // r14
  _QWORD *v68; // r13
  int v69; // ebx
  struct DCCSP *v70; // rax
  int v71; // eax
  __int64 v72; // rax
  struct DCCSP *v73; // rax
  _QWORD *v74; // rcx
  struct DCNativeProviderOrchestration *v75; // r14
  void *v76; // rcx
  const unsigned __int16 *v77; // rax
  struct DeclaredConfigurationScopeData *v78; // r12
  unsigned int v79; // r14d
  const unsigned __int16 *v80; // rax
  const unsigned __int16 *v81; // r8
  const unsigned __int16 *v82; // rax
  const unsigned __int16 *v83; // rax
  CDeclaredConfigurationLogger *Logger; // rax
  const unsigned __int16 *v85; // r9
  const unsigned __int16 *v86; // r8
  const unsigned __int16 *v87; // rax
  __int64 v88; // rax
  unsigned int StateMachineTypeFromDefinedScenario; // r14d
  const char *v90; // rax
  __int64 v91; // rdx
  const unsigned __int16 *v92; // rax
  const unsigned __int16 *v93; // r9
  __int64 v94; // rax
  int v95; // eax
  OLECHAR *v96; // r8
  unsigned __int16 *v97; // rdx
  unsigned __int16 *v98; // r9
  __int64 v100; // rcx
  __int64 v101; // r8
  int dwOptions; // [rsp+20h] [rbp-5D8h]
  int dwOptionsa; // [rsp+20h] [rbp-5D8h]
  int dwOptionsb; // [rsp+20h] [rbp-5D8h]
  const char *samDesired; // [rsp+28h] [rbp-5D0h]
  void *Block; // [rsp+50h] [rbp-5A8h] BYREF
  unsigned __int16 *v107; // [rsp+58h] [rbp-5A0h] BYREF
  _BYTE v108[8]; // [rsp+60h] [rbp-598h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-590h] BYREF
  unsigned int v110; // [rsp+70h] [rbp-588h] BYREF
  char v111; // [rsp+74h] [rbp-584h]
  unsigned __int16 *v112; // [rsp+78h] [rbp-580h] BYREF
  HKEY v113; // [rsp+80h] [rbp-578h] BYREF
  HKEY v114; // [rsp+88h] [rbp-570h] BYREF
  VARIANTARG v115; // [rsp+90h] [rbp-568h] BYREF
  HKEY v116; // [rsp+A8h] [rbp-550h] BYREF
  unsigned int v117; // [rsp+B0h] [rbp-548h] BYREF
  struct DeclaredConfigurationScopeData *v118; // [rsp+B8h] [rbp-540h]
  VARIANTARG v119; // [rsp+C0h] [rbp-538h] BYREF
  void *v120; // [rsp+D8h] [rbp-520h] BYREF
  HKEY phkResult; // [rsp+E0h] [rbp-518h] BYREF
  char v122; // [rsp+E8h] [rbp-510h]
  struct _FILETIME FileTime; // [rsp+F0h] [rbp-508h] BYREF
  VARIANTARG pvarg; // [rsp+F8h] [rbp-500h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+110h] [rbp-4E8h] BYREF
  char v126; // [rsp+120h] [rbp-4D8h]
  WCHAR v127[16]; // [rsp+128h] [rbp-4D0h] BYREF
  _BYTE v128[32]; // [rsp+148h] [rbp-4B0h] BYREF
  _BYTE v129[32]; // [rsp+168h] [rbp-490h] BYREF
  GUID pguid; // [rsp+188h] [rbp-470h] BYREF
  WCHAR SubKey[16]; // [rsp+198h] [rbp-460h] BYREF
  GUID rguid; // [rsp+1B8h] [rbp-440h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+1C8h] [rbp-430h] BYREF
  _BYTE v134[32]; // [rsp+1D8h] [rbp-420h] BYREF
  _BYTE v135[32]; // [rsp+1F8h] [rbp-400h] BYREF
  _BYTE v136[32]; // [rsp+218h] [rbp-3E0h] BYREF
  _BYTE v137[32]; // [rsp+238h] [rbp-3C0h] BYREF
  struct _GUID v138; // [rsp+258h] [rbp-3A0h] BYREF
  unsigned __int16 v139[40]; // [rsp+270h] [rbp-388h] BYREF
  OLECHAR v140[40]; // [rsp+2C0h] [rbp-338h] BYREF
  OLECHAR sz[40]; // [rsp+310h] [rbp-2E8h] BYREF
  unsigned __int16 v142[40]; // [rsp+360h] [rbp-298h] BYREF
  unsigned __int16 v143[264]; // [rsp+3B0h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5F8h] [rbp+0h]

  v111 = a3;
  v4 = a1;
  v118 = a1;
  v113 = 0;
  hKey = 0;
  std::wstring::wstring((__int64)v137);
  std::wstring::wstring((__int64)v136);
  std::wstring::wstring((__int64)v135);
  Block = 0;
  std::wstring::wstring((__int64)v134);
  v117 = 0;
  if ( !v4 || !v5 )
  {
    EnrollmentIdSidStateDocIdKey = -2147024809;
    goto LABEL_231;
  }
  rguid = 0;
  if ( *(_QWORD *)(v5 + 24) <= 7u )
    v7 = (const unsigned __int16 *)a2;
  else
    v7 = *(const unsigned __int16 **)v5;
  if ( *(_QWORD *)(v5 + 56) <= 7u )
    v8 = (const unsigned __int16 *)(v5 + 32);
  else
    v8 = *(const unsigned __int16 **)(v5 + 32);
  if ( (int)OrchestratorDBManager::FindRequest(v6, *(const unsigned __int16 **)v4, v8, v7, &rguid) >= 0 )
  {
    if ( StringFromGUID2(&rguid, sz, 39) != 39 )
    {
LABEL_136:
      EnrollmentIdSidStateDocIdKey = -2147418113;
      goto LABEL_231;
    }
    v9 = DCTrimGuidBracket(sz, v142);
    EnrollmentIdSidStateDocIdKey = v9;
    if ( v9 < 0 )
    {
      v11 = 6799;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v9,
        dwOptionsb);
      goto LABEL_231;
    }
    memset_0(v143, 0, 0x104u);
    v9 = StringCchPrintfW(v143, 0x104u, L"Global\\%s", v142);
    EnrollmentIdSidStateDocIdKey = v9;
    if ( v9 < 0 )
    {
      v11 = 6805;
      goto LABEL_13;
    }
    lpFileName[0] = 0;
    mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(lpFileName, v143);
    EnrollmentIdSidStateDocIdKey = mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      if ( byte_180189FC1 < 0 )
        McTemplateU0zzd_EventWriteTransfer(
          v13,
          (unsigned int)OrchestratorGenericFailure,
          (unsigned int)L"DeclaredConfigurationStore_ConstructURIStorage:PerOrchestratorRequestMutex",
          (unsigned int)L"Creation failed",
          mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(lpFileName);
      goto LABEL_231;
    }
    v110 = 0;
    for ( i = 0; i < 3; ++i )
    {
      _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
        lpFileName,
        &v116,
        &v110,
        30000);
      if ( !v110 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v116);
        goto LABEL_31;
      }
      LastError = GetLastError();
      v17 = LastError;
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      if ( byte_180189FC1 < 0 )
        McTemplateU0zzd_EventWriteTransfer(
          v16,
          (unsigned int)OrchestratorGenericFailure,
          (unsigned int)L"DeclaredConfigurationStore_ConstructURIStorage",
          (unsigned int)L"Acquire PerRequest mutex failed, sleep for 10 seconds",
          v17);
      Sleep(0x2710u);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v116);
    }
    if ( v17 < 0 && byte_180189FC1 < 0 )
      McTemplateU0zzd_EventWriteTransfer(
        v18,
        (unsigned int)OrchestratorGenericFailure,
        (unsigned int)L"DeclaredConfigurationStore_ConstructURIStorage",
        (unsigned int)L"exiting after three retries to acquire the mutex",
        v17);
LABEL_31:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(lpFileName);
  }
  v116 = 0;
  *(_QWORD *)&v115.vt = &v116;
  v115.llVal = 0;
  *((_BYTE *)&v115.decVal + 16) = 1;
  EnrollmentIdSidStateDocIdKey = DCGetEnrollmentsRootKey(&v115.decVal.Lo32, 1);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v115);
  if ( EnrollmentIdSidStateDocIdKey < 0
    || (EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryString(
                                         v116,
                                         0,
                                         L"_Container_EnrollmentId",
                                         *(const unsigned __int16 **)v4,
                                         0),
        EnrollmentIdSidStateDocIdKey < 0) )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v116);
    goto LABEL_231;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v116);
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v19, EnterpriseDiagnosticsDeclaredConfigurationDCConstructURIStorageLock, v20, 1);
  try
  {
    v108[1] = 1;
    v21 = (__int64 *)((char *)a2 + 96);
    v22 = std::operator+<unsigned short>(v128, (char *)a2 + 96, L"\\raw");
    std::wstring::operator=(v134, v22);
    std::wstring::_Tidy_deallocate(v128);
    *(_QWORD *)&v115.vt = &v113;
    v115.llVal = 0;
    *((_BYTE *)&v115.decVal + 16) = 1;
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v23 = (const unsigned __int16 *)a2;
    else
      v23 = *(const unsigned __int16 **)a2;
    EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                                     v4,
                                     v23,
                                     (HKEY *)&v115.llVal,
                                     1);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v115);
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AD4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x8007000ELL,
      dwOptionsa);
    goto LABEL_227;
  }
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_48;
  *(_QWORD *)&v138.Data1 = &Block;
  v138.Data4[0] = 1;
  if ( DCCDNUtil_GetRegistryString(v113, 0, L"MostRecentVersion", (unsigned __int16 **)&Block) >= 0 )
  {
    v110 = 0;
    EnrollmentIdSidStateDocIdKey = DCCDNUtil_GetRegistryDWORD(v113, 0, L"operation", &v110);
    if ( EnrollmentIdSidStateDocIdKey < 0 )
      goto LABEL_47;
    if ( *((_DWORD *)a2 + 68) != v110 )
    {
      EnrollmentIdSidStateDocIdKey = -2147024809;
      if ( byte_180189FC1 < 0 )
        McTemplateU0zzd_EventWriteTransfer(
          v26,
          (unsigned int)OrchestratorGenericFailure,
          (unsigned int)L"DeclaredConfigurationStore_ConstructURIStorage",
          (unsigned int)L"Same doc id with different operation/configuration request already exists",
          87);
      goto LABEL_47;
    }
    *(_QWORD *)&v115.vt = &hKey;
    v115.llVal = 0;
    *((_BYTE *)&v115.decVal + 16) = 1;
    if ( *((_QWORD *)a2 + 3) <= 7u )
      LODWORD(v27) = (_DWORD)a2;
    else
      v27 = *(_QWORD *)a2;
    EnrollmentIdSidStateDocIdKey = GetEnrollmentIdSidStateDocIdVersionRawKey(
                                     (_DWORD)v4,
                                     v27,
                                     (_DWORD)Block,
                                     (unsigned int)&v115.cyVal.Lo,
                                     1);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v115);
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
LABEL_47:
      operator delete(Block);
      Block = 0;
LABEL_48:
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
        McGenEventWrite_EventWriteTransfer(
          v24,
          EnterpriseDiagnosticsDeclaredConfigurationDCConstructURIStorageUnlock,
          v25,
          1);
      goto LABEL_231;
    }
    v110 = 0;
    if ( DCCDNUtil_GetRegistryDWORD(hKey, 0, L"behavior", &v110) >= 0 )
    {
      v29 = *((_DWORD *)a2 + 169);
      if ( (((unsigned __int8)v110 ^ *((_BYTE *)a2 + 676)) & 1) != 0 || (v29 ^= v110, (v29 & 0x10) != 0) )
      {
        EnrollmentIdSidStateDocIdKey = -2147024809;
        if ( byte_180189FC1 < 0 )
          McTemplateU0zzd_EventWriteTransfer(
            v29,
            (unsigned int)OrchestratorGenericFailure,
            (unsigned int)L"DeclaredConfigurationStore_ConstructURIStorage",
            (unsigned int)L"Same doc id with different type already exists",
            87);
        LOBYTE(v28) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationGetConfigurationDocument>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationGetConfigurationDocument>::GetImpl'::`2'::impl,
          v28);
        if ( *((_QWORD *)a2 + 58) )
        {
          lpFileName[0] = 0;
          *(_QWORD *)&v115.vt = lpFileName;
          v115.llVal = 0;
          *((_BYTE *)&v115.decVal + 16) = 1;
          v30 = (const unsigned __int16 *)((char *)a2 + 448);
          if ( *((_QWORD *)a2 + 59) > 7u )
            v30 = *(const unsigned __int16 **)v30;
          FilePathForOriginalDocStorage = DeclaredConfigurationStore_GetFilePathForOriginalDocStorage(
                                            v4,
                                            v30,
                                            a2,
                                            &v115.bstrVal);
          wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v115);
          if ( FilePathForOriginalDocStorage >= 0 )
            DeleteFileW(lpFileName[0]);
          EnrollmentIdSidStateDocIdKey = 0;
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(lpFileName);
        }
        goto LABEL_47;
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  if ( v111 == 1 )
    SetFlagThatEnrollmentWillNeedSessionInitiated(v4);
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryDWORD(v113, 0, L"operation", *((_DWORD *)a2 + 68));
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_47;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v113,
    0);
  *(_QWORD *)&v115.vt = &hKey;
  v115.llVal = 0;
  *((_BYTE *)&v115.decVal + 16) = 1;
  if ( (unsigned __int64)v21[3] <= 7 )
    LODWORD(v32) = (_DWORD)v21;
  else
    v32 = *v21;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    LODWORD(v33) = (_DWORD)a2;
  else
    v33 = *(_QWORD *)a2;
  EnrollmentIdSidStateDocIdKey = GetEnrollmentIdSidStateDocIdVersionRawKey(
                                   (_DWORD)v4,
                                   v33,
                                   v32,
                                   (unsigned int)&v115.cyVal.Lo,
                                   1);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v115);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_47;
  v34 = *((_QWORD *)a2 + 67) <= 7u
      ? (const unsigned __int16 *)((char *)a2 + 512)
      : (const unsigned __int16 *)*((_QWORD *)a2 + 64);
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryString(hKey, 0, L"osdefinedscenario", v34, 0);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_47;
  v35 = (const unsigned __int16 *)((char *)a2 + 544);
  if ( *((_QWORD *)a2 + 71) > 7u )
    v35 = *(const unsigned __int16 **)v35;
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryString(hKey, 0, L"osconfigscenario", v35, 0);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_47;
  v36 = (const unsigned __int16 *)((char *)a2 + 576);
  v37 = *((_QWORD *)a2 + 75) <= 7u ? (struct DCDocument *)((char *)a2 + 576) : *(struct DCDocument **)v36;
  if ( v37 && *((_QWORD *)a2 + 74) )
  {
    if ( *((_QWORD *)a2 + 75) > 7u )
      v36 = *(const unsigned __int16 **)v36;
    EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryString(hKey, 0, L"osconfigscenarioschema", v36, 0);
    if ( EnrollmentIdSidStateDocIdKey < 0 )
      goto LABEL_47;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::GetImpl'::`2'::impl)
    && *((_QWORD *)a2 + 88) )
  {
    v38 = (const unsigned __int16 *)((char *)a2 + 688);
    if ( *((_QWORD *)a2 + 89) > 7u )
      v38 = *(const unsigned __int16 **)v38;
    EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryString(hKey, 0, L"osconfigscenariosVersion", v38, 0);
    if ( EnrollmentIdSidStateDocIdKey < 0 )
      goto LABEL_47;
  }
  v39 = (const unsigned __int16 *)((char *)a2 + 128);
  if ( *((_QWORD *)a2 + 19) > 7u )
    v39 = *(const unsigned __int16 **)v39;
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryString(hKey, 0, L"schema", v39, 0);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_47;
  v40 = *((_QWORD *)a2 + 7) <= 7u
      ? (const unsigned __int16 *)((char *)a2 + 32)
      : (const unsigned __int16 *)*((_QWORD *)a2 + 4);
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryString(hKey, 0, L"context", v40, 0);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_47;
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"behavior", *((_DWORD *)a2 + 169));
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_47;
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"downloadRequest", *((unsigned __int8 *)a2 + 672));
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_47;
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  FileTime = 0;
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    EnrollmentIdSidStateDocIdKey = wil::details::in1diag3::Return_GetLastError(
                                     retaddr,
                                     (void *)0x1B9A,
                                     (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel"
                                                   "\\lib\\declaredconfigurationapi.cpp",
                                     v41);
    goto LABEL_47;
  }
  v107 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v107,
    0);
  FileTimeToISO8601String(&FileTime, 0, &v107);
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryString(hKey, 0, L"requestTimeStamp", v107, 0);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_107;
  LOBYTE(v42) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationParseJSONToDCDoc>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationParseJSONToDCDoc>::GetImpl'::`2'::impl,
    v42);
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"model", *((_DWORD *)a2 + 69));
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_107;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::GetImpl'::`2'::impl) )
  {
    lpFileName[0] = 0;
    *(_QWORD *)&v115.vt = lpFileName;
    v115.llVal = 0;
    *((_BYTE *)&v115.decVal + 16) = 1;
    RegistryString = DCCDNUtil_GetRegistryString(hKey, 0, L"originalDocStorageGuid", &v115.bstrVal);
    wil::details::out_param_t<std::unique_ptr<unsigned char [0]>>::~out_param_t<std::unique_ptr<unsigned char [0]>>(&v115);
    if ( RegistryString >= 0 )
    {
      v45 = -1;
      do
        ++v45;
      while ( lpFileName[0][v45] );
      std::wstring::_Assign<unsigned short>((char **)a2 + 90, lpFileName[0], (char *)v45);
    }
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(lpFileName);
  }
  LOBYTE(v43) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationGetConfigurationDocument>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationGetConfigurationDocument>::GetImpl'::`2'::impl,
    v43);
  v46 = (const unsigned __int16 *)((char *)a2 + 448);
  if ( *((_QWORD *)a2 + 59) > 7u )
    v46 = *(const unsigned __int16 **)v46;
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryString(hKey, 0, L"originalDocStorageGuid", v46, 0);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
LABEL_107:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v107);
    goto LABEL_47;
  }
  v47 = (__int64 ****)*((_QWORD *)a2 + 23);
  if ( *((__int64 *****)a2 + 24) != v47 )
  {
    v48 = **v47;
    v49 = (*v47)[1];
    while ( v48 != v49 )
    {
      v50 = (const unsigned __int16 *)*v48;
      if ( *((_DWORD *)*v48 + 16) == 1 )
      {
        v51 = v50 + 16;
        if ( *((_QWORD *)v50 + 7) > 7u )
          v51 = *(const unsigned __int16 **)v51;
        if ( *((_QWORD *)v50 + 3) > 7u )
          v50 = *(const unsigned __int16 **)v50;
        EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryString(hKey, L"ReflectedProperties", v50, v51, 0);
        if ( EnrollmentIdSidStateDocIdKey < 0 )
          goto LABEL_107;
      }
      v48 += 2;
    }
    v4 = v118;
  }
  if ( !*((_BYTE *)a2 + 672) || !*((_QWORD *)a2 + 38) )
  {
    VariantInit(&v115);
    v115.vt = 3;
    v115.lVal = *((_DWORD *)a2 + 70);
    std::wstring::c_str((char *)a2 + 96);
    v64 = (const unsigned __int16 *)std::wstring::c_str(a2);
    EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_WriteResultData(v4, v64, v65, 0, 0, 0, L"state", &v115);
    if ( EnrollmentIdSidStateDocIdKey < 0
      || (EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"state", *((_DWORD *)a2 + 70)),
          EnrollmentIdSidStateDocIdKey < 0) )
    {
      VariantClear(&v115);
      goto LABEL_140;
    }
    VariantClear(&v115);
    goto LABEL_157;
  }
  v112 = 0;
  pguid = 0;
  v139[0] = 0;
  v140[0] = 0;
  EnrollmentIdSidStateDocIdKey = CoCreateGuid(&pguid);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
LABEL_132:
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v112);
    goto LABEL_107;
  }
  if ( StringFromGUID2(&pguid, v140, 39) != 39 )
  {
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v112);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v107);
    operator delete(Block);
    Block = 0;
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(
        v52,
        EnterpriseDiagnosticsDeclaredConfigurationDCConstructURIStorageUnlock,
        v53,
        1);
    goto LABEL_136;
  }
  EnrollmentIdSidStateDocIdKey = DCTrimGuidBracket(v140, v139);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_132;
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryString(hKey, 0, L"downloadGUID", v139, 0);
  if ( EnrollmentIdSidStateDocIdKey < 0
    || (*(_QWORD *)&v115.vt = &v112,
        v115.llVal = 0,
        *((_BYTE *)&v115.decVal + 16) = 1,
        EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetFilePathForOriginalDocStorage(
                                         v4,
                                         v139,
                                         a2,
                                         &v115.bstrVal),
        wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v115),
        EnrollmentIdSidStateDocIdKey < 0) )
  {
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v112);
    goto LABEL_140;
  }
  std::wstring::wstring((__int64)v129, (__int64)v112);
  last_of = std::wstring::find_last_of(v129, L"\\");
  std::wstring::wstring((__int64)v128);
  std::wstring::wstring((__int64)v127);
  try
  {
    v55 = std::wstring::substr(v129, SubKey, 0, last_of);
    std::wstring::operator=(v128, v55);
    std::wstring::_Tidy_deallocate(SubKey);
    v56 = std::wstring::substr(v129, SubKey, last_of + 1, -1);
    std::wstring::operator=(v127, v56);
    std::wstring::_Tidy_deallocate(SubKey);
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C0C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x8007000ELL,
      dwOptions);
    std::wstring::_Tidy_deallocate(v127);
    std::wstring::_Tidy_deallocate(v128);
    std::wstring::_Tidy_deallocate(v129);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v112);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v107);
    operator delete(Block);
    Block = 0;
LABEL_227:
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(
        v100,
        EnterpriseDiagnosticsDeclaredConfigurationDCConstructURIStorageUnlock,
        v101,
        1);
    EnrollmentIdSidStateDocIdKey = -2147024882;
    goto LABEL_231;
  }
  v57 = (wil *)std::wstring::c_str(v128);
  EnrollmentIdSidStateDocIdKey = wil::CreateDirectoryDeepNoThrow(v57, v58);
  if ( (int)(EnrollmentIdSidStateDocIdKey + 0x80000000) >= 0 && EnrollmentIdSidStateDocIdKey != -2147024713
    || (EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryString(hKey, 0, L"downloadDestination", v112, 0),
        EnrollmentIdSidStateDocIdKey < 0)
    || (v59 = (const unsigned __int16 *)std::wstring::c_str((char *)a2 + 288),
        EnrollmentIdSidStateDocIdKey = CDNDownload_StartDownload(v139, v59, v112, v60, *(const unsigned __int16 **)v4),
        EnrollmentIdSidStateDocIdKey < 0)
    || (v61 = (const unsigned __int16 *)std::wstring::c_str((char *)a2 + 288),
        EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryString(hKey, 0, L"downloadUrl", v61, 0),
        EnrollmentIdSidStateDocIdKey < 0) )
  {
LABEL_145:
    std::wstring::_Tidy_deallocate(v127);
    std::wstring::_Tidy_deallocate(v128);
    std::wstring::_Tidy_deallocate(v129);
    goto LABEL_132;
  }
  VariantInit(&pvarg);
  pvarg.vt = 3;
  pvarg.lVal = 30;
  std::wstring::c_str((char *)a2 + 96);
  v62 = (const unsigned __int16 *)std::wstring::c_str(a2);
  EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_WriteResultData(v4, v62, v63, 0, 0, 0, L"state", &pvarg);
  if ( EnrollmentIdSidStateDocIdKey < 0
    || (EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"state", 0x1Eu),
        EnrollmentIdSidStateDocIdKey < 0) )
  {
    VariantClear(&pvarg);
    goto LABEL_145;
  }
  VariantClear(&pvarg);
  std::wstring::_Tidy_deallocate(v127);
  std::wstring::_Tidy_deallocate(v128);
  std::wstring::_Tidy_deallocate(v129);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v112);
LABEL_157:
  v66 = 1;
  v67 = (_QWORD *)*((_QWORD *)a2 + 20);
  v68 = (_QWORD *)*((_QWORD *)a2 + 21);
  while ( 1 )
  {
    if ( v67 == v68 )
    {
      v110 = 0;
      EnrollmentIdSidStateDocIdKey = ULongLongToULong(
                                       (__int64)(*((_QWORD *)a2 + 21) - *((_QWORD *)a2 + 20)) >> 4,
                                       &v110);
      if ( EnrollmentIdSidStateDocIdKey < 0 )
        goto LABEL_140;
      v74 = (_QWORD *)*((_QWORD *)a2 + 26);
      if ( !((__int64)(*((_QWORD *)a2 + 27) - (_QWORD)v74) >> 4) )
        goto LABEL_188;
      v75 = (struct DCNativeProviderOrchestration *)_RTDynamicCast_0(
                                                      *v74,
                                                      0,
                                                      &DCProviderOrchestration `RTTI Type Descriptor',
                                                      &DCNativeProviderOrchestration `RTTI Type Descriptor',
                                                      0);
      if ( v75 )
      {
        lpFileName[0] = 0;
        wcscpy(v127, L"Orchesration1");
        v120 = lpFileName;
        phkResult = 0;
        v122 = 1;
        EnrollmentIdSidStateDocIdKey = RegCreateKeyExW(hKey, v127, 0, 0, 0, 0x2011Fu, 0, &phkResult, 0);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v120);
        if ( EnrollmentIdSidStateDocIdKey )
        {
          if ( EnrollmentIdSidStateDocIdKey > 0 )
            EnrollmentIdSidStateDocIdKey = (unsigned __int16)EnrollmentIdSidStateDocIdKey | 0x80070000;
          v76 = lpFileName;
          goto LABEL_185;
        }
        EnrollmentIdSidStateDocIdKey = ConstructDSCNativeOrchestrator(v75, (HKEY)lpFileName[0]);
        v76 = lpFileName;
        if ( EnrollmentIdSidStateDocIdKey < 0 )
          goto LABEL_185;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(lpFileName);
LABEL_188:
        if ( (__int64)(*((_QWORD *)a2 + 30) - *((_QWORD *)a2 + 29)) >> 4 )
        {
          EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"PrecheckCount", 1u);
          if ( EnrollmentIdSidStateDocIdKey < 0 )
            goto LABEL_190;
          EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(_QWORD, HKEY, __int64))(***((_QWORD ***)a2 + 29)
                                                                                          + 16LL))(
                                           **((_QWORD **)a2 + 29),
                                           hKey,
                                           1);
          if ( EnrollmentIdSidStateDocIdKey < 0 )
            goto LABEL_190;
        }
        v120 = &v113;
        phkResult = 0;
        v122 = 1;
        v77 = (const unsigned __int16 *)std::wstring::c_str(a2);
        v78 = v118;
        EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                                         v118,
                                         v77,
                                         &phkResult,
                                         0);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v120);
        if ( EnrollmentIdSidStateDocIdKey < 0 )
          goto LABEL_190;
        VariantInit(&v119);
        v119.vt = 3;
        v79 = v110;
        v119.lVal = v110;
        std::wstring::c_str((char *)a2 + 96);
        v80 = (const unsigned __int16 *)std::wstring::c_str(a2);
        EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_WriteResultData(
                                         v78,
                                         v80,
                                         v81,
                                         0,
                                         0,
                                         0,
                                         L"CspCount",
                                         &v119);
        if ( EnrollmentIdSidStateDocIdKey < 0
          || (v82 = (const unsigned __int16 *)std::wstring::c_str(v134),
              EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryDWORD(v113, v82, L"CspCount", v79),
              EnrollmentIdSidStateDocIdKey < 0) )
        {
LABEL_194:
          VariantClear(&v119);
LABEL_190:
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v107);
          operator delete(Block);
          Block = 0;
          wil::details::ScopeExitFn__lambda_6d489affffef7b2723a2e4eac64c34f1___::operator()(v108);
          goto LABEL_231;
        }
        DCCDNUtil_GetRegistryDWORD(HKEY_LOCAL_MACHINE, c_szDCRegistry, L"InProcTest", &v117);
        EnrollmentIdSidStateDocIdKey = DCCDNUtil_GetRegistryString(
                                         v113,
                                         0,
                                         L"PreviousVersion",
                                         (unsigned __int16 **)&Block);
        if ( EnrollmentIdSidStateDocIdKey < 0 || !Block )
        {
          EnrollmentIdSidStateDocIdKey = DCCDNUtil_GetRegistryString(
                                           v113,
                                           0,
                                           L"MostRecentVersion",
                                           (unsigned __int16 **)&Block);
          if ( EnrollmentIdSidStateDocIdKey == -2147024894 )
          {
            EnrollmentIdSidStateDocIdKey = 0;
          }
          else if ( EnrollmentIdSidStateDocIdKey < 0 )
          {
            Logger = CDeclaredConfigurationLogger::GetLogger();
            v85 = L"Failed to find the most recent version of the doc";
            v86 = L"DCCDNUtil_GetRegistryString";
            goto LABEL_206;
          }
        }
        v83 = (const unsigned __int16 *)std::wstring::c_str((char *)a2 + 96);
        if ( (*((_BYTE *)a2 + 676) & 0x20) != 0 )
        {
          EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryString(v113, 0, L"BulkTemplateVersion", v83, 0);
          if ( EnrollmentIdSidStateDocIdKey < 0 )
          {
            Logger = CDeclaredConfigurationLogger::GetLogger();
            v85 = L"Failed to set the Bulk Template version of the doc";
LABEL_203:
            v86 = L"DCCDNUtil_SetRegistryString";
LABEL_206:
            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
              Logger,
              L"DeclaredConfigurationStore_ConstructURIStorage",
              v86,
              v85,
              EnrollmentIdSidStateDocIdKey);
            goto LABEL_194;
          }
        }
        else if ( (unsigned int)_o__wcsicmp(v83, Block) )
        {
          v87 = (const unsigned __int16 *)std::wstring::c_str((char *)a2 + 96);
          EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryString(v113, 0, L"MostRecentVersion", v87, 0);
          if ( EnrollmentIdSidStateDocIdKey < 0 )
          {
            Logger = CDeclaredConfigurationLogger::GetLogger();
            v85 = L"Failed to set the most recent version of the doc";
            goto LABEL_203;
          }
          if ( Block )
          {
            EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryString(
                                             v113,
                                             0,
                                             L"PreviousVersion",
                                             (const unsigned __int16 *)Block,
                                             0);
            if ( EnrollmentIdSidStateDocIdKey < 0 )
            {
              Logger = CDeclaredConfigurationLogger::GetLogger();
              v85 = L"Failed to set the previous version of the doc";
              goto LABEL_203;
            }
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &v113,
          0);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hKey,
          0);
        VariantClear(&v119);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v107);
        operator delete(Block);
        Block = 0;
        wil::details::ScopeExitFn__lambda_6d489affffef7b2723a2e4eac64c34f1___::operator()(v108);
        if ( v111 != 1 || (*((_BYTE *)a2 + 676) & 0x20) != 0 )
          goto LABEL_231;
        v88 = std::wstring::c_str((char *)a2 + 512);
        StateMachineTypeFromDefinedScenario = getStateMachineTypeFromDefinedScenario(v88);
        if ( StateMachineTypeFromDefinedScenario == 63 )
        {
          v90 = "state machine type is invalid";
          EnrollmentIdSidStateDocIdKey = -2147024809;
          v91 = 7576;
LABEL_217:
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)v91,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)(unsigned int)EnrollmentIdSidStateDocIdKey,
            (int)v90,
            samDesired);
          goto LABEL_231;
        }
        if ( v117 )
        {
          if ( v117 != 1 )
            goto LABEL_231;
          *(_OWORD *)lpFileName = 0;
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl'::`2'::impl)
            && !*(_QWORD *)&qword_18018A6C8 )
          {
            InitOrchestratorEngine();
            if ( !*(_QWORD *)&qword_18018A6C8 )
            {
              v90 = "could not get DC OrchestratorEngine";
              EnrollmentIdSidStateDocIdKey = -2147467259;
              v91 = 7616;
              goto LABEL_217;
            }
          }
          std::wstring::c_str((char *)a2 + 96);
          std::wstring::c_str(a2);
          v96 = (OLECHAR *)std::wstring::c_str((char *)a2 + 32);
          v95 = OrchestratorConfig(
                  0,
                  *(OLECHAR **)v78,
                  v96,
                  v98,
                  v97,
                  (char *)L"Host",
                  StateMachineTypeFromDefinedScenario,
                  Block != 0,
                  (struct _GUID *)lpFileName);
        }
        else
        {
          pguid = 0;
          v138 = 0;
          std::wstring::c_str(a2);
          v92 = (const unsigned __int16 *)std::wstring::c_str((char *)a2 + 32);
          OrchestratorDBManager::FindRequest(
            (OrchestratorDBManager *)&v138,
            *(const unsigned __int16 **)v78,
            v92,
            v93,
            &v138);
          std::wstring::c_str((char *)a2 + 96);
          std::wstring::c_str(a2);
          v94 = std::wstring::c_str((char *)a2 + 32);
          v95 = DMOrchestratorConfig(*(_QWORD *)v78, v94);
        }
        EnrollmentIdSidStateDocIdKey = v95;
        goto LABEL_231;
      }
LABEL_181:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v107);
      operator delete(Block);
      Block = 0;
      lambda_6d489affffef7b2723a2e4eac64c34f1_::operator()();
      goto LABEL_136;
    }
    v114 = 0;
    SubKey[0] = 0;
    EnrollmentIdSidStateDocIdKey = StringCchPrintfW(SubKey, 0xFu, L"CSP%d", v66);
    if ( EnrollmentIdSidStateDocIdKey < 0 )
      goto LABEL_184;
    lpFileName[0] = (LPCWSTR)&v114;
    lpFileName[1] = 0;
    v126 = 1;
    EnrollmentIdSidStateDocIdKey = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2011Fu, 0, (PHKEY)&lpFileName[1], 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(lpFileName);
    if ( EnrollmentIdSidStateDocIdKey )
      break;
    ++v66;
    v69 = (**(__int64 (__fastcall ***)(_QWORD))*v67)(*v67);
    if ( v69 == 1 )
    {
      v70 = (struct DCCSP *)_RTDynamicCast_0(
                              *v67,
                              0,
                              &DCProvider `RTTI Type Descriptor',
                              &DCCSP `RTTI Type Descriptor',
                              0);
      if ( !v70 )
        goto LABEL_180;
      v71 = ConstructCSPProvider(v118, a2, v70, v114, SubKey, v66);
    }
    else if ( v69 == 2 )
    {
      v72 = _RTDynamicCast_0(*v67, 0, &DCProvider `RTTI Type Descriptor', &DCDSCNative `RTTI Type Descriptor', 0);
      if ( !v72 )
        goto LABEL_180;
      v71 = ConstructDSCNativeProvider(v118, a2, 1, v72, v114, SubKey, v66, 0);
    }
    else
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
        goto LABEL_180;
      if ( v69 != 3 )
        goto LABEL_171;
      v73 = (struct DCCSP *)_RTDynamicCast_0(
                              *v67,
                              0,
                              &DCProvider `RTTI Type Descriptor',
                              &DCCSP `RTTI Type Descriptor',
                              0);
      if ( !v73 )
      {
LABEL_180:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v114);
        goto LABEL_181;
      }
      v71 = ConstructRegistryProvider(v118, a2, v73, v114, SubKey, v66);
    }
    EnrollmentIdSidStateDocIdKey = v71;
    if ( v71 < 0 )
      goto LABEL_184;
LABEL_171:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v114);
    v67 += 2;
  }
  if ( EnrollmentIdSidStateDocIdKey > 0 )
    EnrollmentIdSidStateDocIdKey = (unsigned __int16)EnrollmentIdSidStateDocIdKey | 0x80070000;
LABEL_184:
  v76 = &v114;
LABEL_185:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v76);
LABEL_140:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v107);
  operator delete(Block);
  Block = 0;
  lambda_6d489affffef7b2723a2e4eac64c34f1_::operator()();
LABEL_231:
  std::wstring::_Tidy_deallocate(v134);
  std::wstring::_Tidy_deallocate(v135);
  std::wstring::_Tidy_deallocate(v136);
  std::wstring::_Tidy_deallocate(v137);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v113);
  return (unsigned int)EnrollmentIdSidStateDocIdKey;
}

```

## disassembly

```asm
0x180067160  mov     r11, rsp
0x180067163  mov     [r11+18h], rbx
0x180067167  mov     [r11+20h], rsi
0x18006716b  push    rdi
0x18006716c  push    r12
0x18006716e  push    r13
0x180067170  push    r14
0x180067172  push    r15
0x180067174  sub     rsp, 5D0h
0x18006717b  mov     rax, cs:__security_cookie
0x180067182  xor     rax, rsp
0x180067185  mov     [rsp+5F8h+var_38], rax
0x18006718d  mov     [rsp+5F8h+var_584], r8b
0x180067192  mov     r15, rdx
0x180067195  mov     r13, rcx
0x180067198  mov     [rsp+5F8h+var_540], rcx
0x1800671a0  xor     edi, edi
0x1800671a2  mov     [r11-578h], rdi
0x1800671a9  mov     [rsp+5F8h+hKey], rdi
0x1800671ae  lea     rcx, [r11-3C0h]
0x1800671b5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800671ba  nop
0x1800671bb  lea     rcx, [rsp+5F8h+var_3E0]
0x1800671c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800671c8  nop
0x1800671c9  lea     rcx, [rsp+5F8h+var_400]
0x1800671d1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800671d6  nop
0x1800671d7  mov     [rsp+5F8h+Block], rdi
0x1800671dc  lea     rcx, [rsp+5F8h+var_420]
0x1800671e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800671e9  nop
0x1800671ea  mov     [rsp+5F8h+var_548], edi
0x1800671f1  test    r13, r13
0x1800671f4  jz      loc_180068A75
0x1800671fa  test    rdx, rdx
0x1800671fd  jz      loc_180068A75
0x180067203  xorps   xmm0, xmm0
0x180067206  movups  xmmword ptr [rsp+5F8h+rguid.Data1], xmm0
0x18006720e  cmp     qword ptr [rdx+18h], 7
0x180067213  jbe     short loc_18006721A
0x180067215  mov     r9, [rdx]
0x180067218  jmp     short loc_18006721D
0x18006721a  mov     r9, r15; unsigned __int16 *
0x18006721d  cmp     qword ptr [rdx+38h], 7
0x180067222  jbe     short loc_18006722A
0x180067224  mov     r8, [rdx+20h]
0x180067228  jmp     short loc_18006722E
0x18006722a  lea     r8, [rdx+20h]; unsigned __int16 *
0x18006722e  lea     rax, [rsp+5F8h+rguid]
0x180067236  mov     qword ptr [rsp+5F8h+dwOptions], rax; int
0x18006723b  mov     rdx, [r13+0]; unsigned __int16 *
0x18006723f  call    ?FindRequest@OrchestratorDBManager@@QEAAJPEBG00PEAU_GUID@@@Z; OrchestratorDBManager::FindRequest(ushort const *,ushort const *,ushort const *,_GUID *)
0x180067244  test    eax, eax
0x180067246  js      loc_18006742B
0x18006724c  mov     r8d, 27h ; '''; cchMax
0x180067252  lea     rdx, [rsp+5F8h+sz]; lpsz
0x18006725a  lea     rcx, [rsp+5F8h+rguid]; rguid
0x180067262  call    cs:__imp_StringFromGUID2
0x180067268  cmp     eax, 27h ; '''
0x18006726b  jnz     loc_180067D22
0x180067271  lea     rdx, [rsp+5F8h+var_298]; unsigned __int16 *
0x180067279  lea     rcx, [rsp+5F8h+sz]; unsigned __int16 *
0x180067281  call    ?DCTrimGuidBracket@@YAJPEBGPEAG@Z; DCTrimGuidBracket(ushort const *,ushort *)
0x180067286  mov     ebx, eax
0x180067288  test    eax, eax
0x18006728a  jns     short loc_1800672AD
0x18006728c  mov     edx, 1A8Fh; void *
0x180067291  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180067298  mov     r9d, eax; char *
0x18006729b  mov     rcx, [rsp+5F8h]; this
0x1800672a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800672a8  jmp     loc_180068A7A
0x1800672ad  mov     ebx, 104h
0x1800672b2  mov     r8d, ebx; Size
0x1800672b5  xor     edx, edx; Val
0x1800672b7  lea     rcx, [rsp+5F8h+var_248]; void *
0x1800672bf  call    memset_0
0x1800672c4  lea     r9, [rsp+5F8h+var_298]
0x1800672cc  lea     r8, aGlobalS; "Global\\%s"
0x1800672d3  mov     edx, ebx; unsigned __int64
0x1800672d5  lea     rcx, [rsp+5F8h+var_248]; unsigned __int16 *
0x1800672dd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800672e2  mov     ebx, eax
0x1800672e4  test    eax, eax
0x1800672e6  jns     short loc_1800672EF
0x1800672e8  mov     edx, 1A95h
0x1800672ed  jmp     short loc_180067291
0x1800672ef  mov     [rsp+5F8h+lpFileName], rdi
0x1800672f7  lea     rdx, [rsp+5F8h+var_248]
0x1800672ff  lea     rcx, [rsp+5F8h+lpFileName]
0x180067307  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18006730c  mov     ebx, eax
0x18006730e  test    eax, eax
0x180067310  jns     short loc_18006734B
0x180067312  cmp     cs:byte_180189FC1, dil
0x180067319  jge     short loc_180067339
0x18006731b  mov     [rsp+5F8h+dwOptions], eax
0x18006731f  lea     r9, aCreationFailed; "Creation failed"
0x180067326  lea     r8, aDeclaredconfig_188; "DeclaredConfigurationStore_ConstructURI"...
0x18006732d  lea     rdx, OrchestratorGenericFailure
0x180067334  call    McTemplateU0zzd_EventWriteTransfer
0x180067339  lea     rcx, [rsp+5F8h+lpFileName]
0x180067341  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180067346  jmp     loc_180068A7A
0x18006734b  mov     [rsp+5F8h+var_588], edi
0x18006734f  mov     r14d, edi
0x180067352  mov     esi, 1
0x180067357  mov     r9d, 7530h
0x18006735d  lea     r8, [rsp+5F8h+var_588]
0x180067362  lea     rdx, [rsp+5F8h+var_550]
0x18006736a  lea     rcx, [rsp+5F8h+lpFileName]
0x180067372  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180067377  cmp     [rsp+5F8h+var_588], edi
0x18006737b  jz      loc_18006740F
0x180067381  call    cs:__imp_GetLastError
0x180067387  mov     ebx, eax
0x180067389  test    eax, eax
0x18006738b  jle     short loc_180067396
0x18006738d  movzx   ebx, ax
0x180067390  or      ebx, 80070000h
0x180067396  cmp     cs:byte_180189FC1, dil
0x18006739d  jge     short loc_1800673BD
0x18006739f  mov     [rsp+5F8h+dwOptions], ebx
0x1800673a3  lea     r9, aAcquirePerrequ; "Acquire PerRequest mutex failed, sleep "...
0x1800673aa  lea     r8, aDeclaredconfig_180; "DeclaredConfigurationStore_ConstructURI"...
0x1800673b1  lea     rdx, OrchestratorGenericFailure
0x1800673b8  call    McTemplateU0zzd_EventWriteTransfer
0x1800673bd  mov     ecx, 2710h; dwMilliseconds
0x1800673c2  call    cs:__imp_Sleep
0x1800673c8  lea     rcx, [rsp+5F8h+var_550]
0x1800673d0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800673d5  add     r14d, esi
0x1800673d8  cmp     r14d, 3
0x1800673dc  jl      loc_180067357
0x1800673e2  test    ebx, ebx
0x1800673e4  jns     short loc_18006741C
0x1800673e6  cmp     cs:byte_180189FC1, dil
0x1800673ed  jge     short loc_18006741C
0x1800673ef  mov     [rsp+5F8h+dwOptions], ebx
0x1800673f3  lea     r9, aExitingAfterTh; "exiting after three retries to acquire "...
0x1800673fa  lea     r8, aDeclaredconfig_180; "DeclaredConfigurationStore_ConstructURI"...
0x180067401  lea     rdx, OrchestratorGenericFailure
0x180067408  call    McTemplateU0zzd_EventWriteTransfer
0x18006740d  jmp     short loc_18006741C
0x18006740f  lea     rcx, [rsp+5F8h+var_550]
0x180067417  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006741c  lea     rcx, [rsp+5F8h+lpFileName]
0x180067424  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180067429  jmp     short loc_180067430
0x18006742b  mov     esi, 1
0x180067430  mov     [rsp+5F8h+var_550], rdi
0x180067438  lea     rax, [rsp+5F8h+var_550]
0x180067440  mov     qword ptr [rsp+5F8h+var_568], rax
0x180067448  mov     qword ptr [rsp+5F8h+var_568+8], rdi
0x180067450  mov     byte ptr [rsp+5F8h+var_568+10h], sil
0x180067458  mov     edx, esi
0x18006745a  lea     rcx, [rsp+5F8h+var_568+8]
0x180067462  call    DCGetEnrollmentsRootKey
0x180067467  mov     ebx, eax
0x180067469  lea     rcx, [rsp+5F8h+var_568]
0x180067471  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180067476  test    ebx, ebx
0x180067478  jns     short loc_18006748C
0x18006747a  lea     rcx, [rsp+5F8h+var_550]
0x180067482  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180067487  jmp     loc_180068A7A
0x18006748c  mov     byte ptr [rsp+5F8h+dwOptions], dil; bool
0x180067491  mov     r9, [r13+0]; unsigned __int16 *
0x180067495  lea     r8, aContainerEnrol; "_Container_EnrollmentId"
0x18006749c  xor     edx, edx; unsigned __int16 *
0x18006749e  mov     rcx, [rsp+5F8h+var_550]; HKEY
0x1800674a6  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800674ab  mov     ebx, eax
0x1800674ad  lea     rcx, [rsp+5F8h+var_550]
0x1800674b5  test    eax, eax
0x1800674b7  js      short loc_180067482
0x1800674b9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800674be  mov     r14b, 4
0x1800674c1  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, r14b
0x1800674c8  jz      short loc_1800674E6
0x1800674ca  lea     rax, [rsp+5F8h+var_3A0]
0x1800674d2  mov     qword ptr [rsp+5F8h+dwOptions], rax
0x1800674d7  mov     r9d, esi
0x1800674da  lea     rdx, EnterpriseDiagnosticsDeclaredConfigurationDCConstructURIStorageLock
0x1800674e1  call    McGenEventWrite_EventWriteTransfer
0x1800674e6  mov     [rsp+5F8h+var_597], sil
0x1800674eb  lea     r12, [r15+60h]
0x1800674ef  lea     r8, aRaw_0; "\\raw"
0x1800674f6  mov     rdx, r12
0x1800674f9  lea     rcx, [rsp+5F8h+var_4B0]
0x180067501  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180067506  mov     rdx, rax
0x180067509  lea     rcx, [rsp+5F8h+var_420]
0x180067511  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180067516  lea     rcx, [rsp+5F8h+var_4B0]
0x18006751e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180067523  nop
0x180067524  lea     rax, [rsp+5F8h+var_578]
0x18006752c  mov     qword ptr [rsp+5F8h+var_568], rax
0x180067534  mov     qword ptr [rsp+5F8h+var_568+8], rdi
0x18006753c  mov     byte ptr [rsp+5F8h+var_568+10h], sil
0x180067544  cmp     qword ptr [r15+18h], 7
0x180067549  jbe     short loc_180067550
0x18006754b  mov     rdx, [r15]
0x18006754e  jmp     short loc_180067553
0x180067550  mov     rdx, r15; unsigned __int16 *
0x180067553  mov     r9d, esi; int
0x180067556  lea     r8, [rsp+5F8h+var_568+8]; HKEY *
0x18006755e  mov     rcx, r13; struct DeclaredConfigurationScopeData *
0x180067561  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x180067566  mov     ebx, eax
0x180067568  lea     rcx, [rsp+5F8h+var_568]
0x180067570  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180067575  test    ebx, ebx
0x180067577  js      loc_180067623
0x18006757d  lea     rax, [rsp+5F8h+Block]
0x180067582  mov     qword ptr [rsp+5F8h+var_3A0.Data1], rax
0x18006758a  mov     [rsp+5F8h+var_3A0.Data4], sil
0x180067592  lea     r9, [rsp+5F8h+Block]; unsigned __int16 **
0x180067597  lea     r8, aMostrecentvers; "MostRecentVersion"
0x18006759e  xor     edx, edx; unsigned __int16 *
0x1800675a0  mov     rcx, [rsp+5F8h+var_578]; HKEY
0x1800675a8  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800675ad  test    eax, eax
0x1800675af  js      loc_1800677B9
0x1800675b5  mov     [rsp+5F8h+var_588], edi
0x1800675b9  lea     r9, [rsp+5F8h+var_588]; unsigned int *
0x1800675be  lea     r8, aOperation; "operation"
0x1800675c5  xor     edx, edx; unsigned __int16 *
0x1800675c7  mov     rcx, [rsp+5F8h+var_578]; HKEY
0x1800675cf  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800675d4  mov     ebx, eax
0x1800675d6  test    eax, eax
0x1800675d8  js      short loc_180067614
0x1800675da  mov     eax, [rsp+5F8h+var_588]
0x1800675de  cmp     [r15+110h], eax
0x1800675e5  jz      short loc_180067651
0x1800675e7  mov     ebx, 80070057h
0x1800675ec  cmp     cs:byte_180189FC1, dil
0x1800675f3  jge     short loc_180067614
0x1800675f5  mov     [rsp+5F8h+dwOptions], ebx
0x1800675f9  lea     r9, aSameDocIdWithD_0; "Same doc id with different operation/co"...
0x180067600  lea     r8, aDeclaredconfig_180; "DeclaredConfigurationStore_ConstructURI"...
0x180067607  lea     rdx, OrchestratorGenericFailure
0x18006760e  call    McTemplateU0zzd_EventWriteTransfer
0x180067613  nop
0x180067614  mov     rcx, [rsp+5F8h+Block]; Block
0x180067619  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006761e  mov     [rsp+5F8h+Block], rdi
0x180067623  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, r14b
0x18006762a  jz      loc_180068A7A
0x180067630  lea     rax, [rsp+5F8h+var_3A0]
0x180067638  mov     qword ptr [rsp+5F8h+dwOptions], rax
0x18006763d  mov     r9d, esi
0x180067640  lea     rdx, EnterpriseDiagnosticsDeclaredConfigurationDCConstructURIStorageUnlock
0x180067647  call    McGenEventWrite_EventWriteTransfer
0x18006764c  jmp     loc_180068A7A
0x180067651  lea     rax, [rsp+5F8h+hKey]
0x180067656  mov     qword ptr [rsp+5F8h+var_568], rax
0x18006765e  mov     qword ptr [rsp+5F8h+var_568+8], rdi
0x180067666  mov     byte ptr [rsp+5F8h+var_568+10h], sil
0x18006766e  cmp     qword ptr [r15+18h], 7
0x180067673  jbe     short loc_18006767A
0x180067675  mov     rdx, [r15]
0x180067678  jmp     short loc_18006767D
0x18006767a  mov     rdx, r15
0x18006767d  mov     [rsp+5F8h+dwOptions], esi
0x180067681  lea     r9, [rsp+5F8h+var_568+8]
0x180067689  mov     r8, [rsp+5F8h+Block]
0x18006768e  mov     rcx, r13
0x180067691  call    GetEnrollmentIdSidStateDocIdVersionRawKey
0x180067696  mov     ebx, eax
0x180067698  lea     rcx, [rsp+5F8h+var_568]
0x1800676a0  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800676a5  test    ebx, ebx
0x1800676a7  js      loc_180067614
0x1800676ad  mov     [rsp+5F8h+var_588], edi
0x1800676b1  lea     r9, [rsp+5F8h+var_588]; unsigned int *
0x1800676b6  lea     r8, aBehavior_0; "behavior"
0x1800676bd  xor     edx, edx; unsigned __int16 *
0x1800676bf  mov     rcx, [rsp+5F8h+hKey]; HKEY
0x1800676c4  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800676c9  test    eax, eax
0x1800676cb  js      loc_1800677B9
0x1800676d1  mov     ecx, [r15+2A4h]
0x1800676d8  mov     eax, ecx
0x1800676da  xor     eax, [rsp+5F8h+var_588]
0x1800676de  test    sil, al
0x1800676e1  jnz     short loc_1800676F0
0x1800676e3  xor     ecx, [rsp+5F8h+var_588]
0x1800676e7  test    cl, 10h
0x1800676ea  jz      loc_1800677B9
0x1800676f0  mov     ebx, 80070057h
0x1800676f5  cmp     cs:byte_180189FC1, dil
0x1800676fc  jge     short loc_18006771C
0x1800676fe  mov     [rsp+5F8h+dwOptions], ebx
0x180067702  lea     r9, aSameDocIdWithD; "Same doc id with different type already"...
0x180067709  lea     r8, aDeclaredconfig_180; "DeclaredConfigurationStore_ConstructURI"...
0x180067710  lea     rdx, OrchestratorGenericFailure
  ... truncated ...
```
