# DeclaredConfigurationStore_ReconstructQueueForEnrollment(ushort const *)

- ea: `0x180082930`
- end: `0x180083b24`
- name: `?DeclaredConfigurationStore_ReconstructQueueForEnrollment@@YAJPEBG@Z`
- size: `4596`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180117898`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x18000e310`
- `0x18000e32c`
- `0x180012dc4`
- `0x180013d4c`
- `0x180019d38`
- `0x18001a60c`
- `0x18001c08c`
- `0x18001ce5c`
- `0x18001d0b0`
- `0x180056b5c`
- `0x180056bcc`
- `0x180058b08`
- `0x180058b3c`
- `0x18005990c`
- `0x18005ef7c`
- `0x18005f218`
- `0x18005fde0`
- `0x180082930`
- `0x18008cec8`
- `0x18008ea9c`
- `0x18008ec20`
- `0x18009a2e4`
- `0x1800a04fc`
- `0x1800a1004`
- `0x1800f5c8c`
- `0x1800f83d0`
- `0x1800f9d70`
- `0x1800fa310`
- `0x180100ad8`
- `0x180100e3c`
- `0x1801090b4`
- `0x180109dd8`
- `0x18010aedc`
- `0x18010bab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180083576`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008382d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180083576`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008382d`
- `OLEAUT32!__imp_SysAllocString` at `0x180082fe5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800830bc`
- `OLEAUT32!__imp_SysAllocString` at `0x180082fe5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800830bc`

## string_xrefs

- `0x1800829b7`: `Global\DeclaredConfigurationMutex`
- `0x180083465`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180083329`: `DCCDNUtil_GetRegistryString`
- `0x180082a5a`: `DeclaredConfigurationGlobalMutex.acquire`
- `0x180082a61`: `DeclaredConfigurationStore_ReconstructQueueForEnrollment`
- `0x180082bb3`: `DeclaredConfigurationStore_ReconstructQueueForEnrollment`
- `0x180082c57`: `DeclaredConfigurationStore_ReconstructQueueForEnrollment`
- `0x180082d1c`: `DeclaredConfigurationStore_ReconstructQueueForEnrollment`
- `0x18008320b`: `DeclaredConfigurationStore_ReconstructQueueForEnrollment`
- `0x180083330`: `DeclaredConfigurationStore_ReconstructQueueForEnrollment`
- `0x18008343f`: `DeclaredConfigurationStore_ReconstructQueueForEnrollment`
- `0x18008370d`: `DeclaredConfigurationStore_ReconstructQueueForEnrollment`
- `0x180083887`: `DeclaredConfigurationStore_ReconstructQueueForEnrollment`
- `0x180082c50`: `DCCDNUtil_SetRegistryDWORD:Set _Container_ReprocessDocs`
- `0x180082d15`: `DCGetReadonlyEnrollmentIdKey`
- `0x180083204`: `GetEnrollmentIdSidStateDocIdVersionRawKey`
- `0x180083880`: `OrchestratorIDatabaseManagerSingleton::instance().UpdateRequestDocVersion`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall DeclaredConfigurationStore_ReconstructQueueForEnrollment(unsigned __int16 *a1)
{
  int v2; // ebx
  __int64 v3; // rcx
  __int64 result; // rax
  CDeclaredConfigurationLogger *Logger; // rax
  __int64 v6; // rcx
  int valid; // ebx
  CDeclaredConfigurationLogger *v8; // rax
  __int64 v9; // rcx
  int v10; // ebx
  CDeclaredConfigurationLogger *v11; // rax
  __int64 v12; // rcx
  int v13; // ebx
  CDeclaredConfigurationLogger *v14; // rax
  __int64 v15; // rcx
  int v16; // ebx
  CDeclaredConfigurationLogger *v17; // rax
  __int64 v18; // rcx
  DWORD i; // r15d
  int v20; // ebx
  CDeclaredConfigurationLogger *v21; // rax
  __int64 v22; // rcx
  int EnrollmentIdSidStateKey; // ebx
  DWORD j; // r14d
  __int64 v25; // rcx
  int EnrollmentIdSidStateDocIdVersionRawKey; // ebx
  CDeclaredConfigurationLogger *v27; // rax
  __int64 v28; // rcx
  int RegistryString; // ebx
  CDeclaredConfigurationLogger *v30; // rax
  __int64 v31; // rcx
  unsigned int StateMachineTypeFromDefinedScenario; // ebx
  CDeclaredConfigurationLogger *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // r8
  int v36; // eax
  const OLECHAR *v37; // rdx
  __int64 v38; // r8
  _WORD *v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r8
  OrchestratorDBManager *v42; // rcx
  const unsigned __int16 *v43; // r9
  const unsigned __int16 *v44; // r8
  const unsigned __int16 *v45; // rdx
  struct _GUID v46; // xmm6
  OrchestratorDBManager *v47; // rcx
  int Request; // ebx
  CDeclaredConfigurationLogger *v49; // rax
  __int64 v50; // rcx
  char **v51; // rdx
  _QWORD *v52; // rcx
  OrchestratorDCInfo *v53; // rax
  __int64 v54; // rcx
  int updated; // ebx
  CDeclaredConfigurationLogger *v56; // rax
  OrchestratorDCInfo *v57; // rax
  __int64 v58; // rcx
  int v59; // ebx
  CDeclaredConfigurationLogger *v60; // rax
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  enum DCLifecycleNotificationType *v64; // [rsp+28h] [rbp-350h]
  void *Block; // [rsp+30h] [rbp-348h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-340h] BYREF
  int v67; // [rsp+40h] [rbp-338h] BYREF
  __int64 v68; // [rsp+48h] [rbp-330h] BYREF
  void *v69; // [rsp+50h] [rbp-328h] BYREF
  int v70; // [rsp+60h] [rbp-318h] BYREF
  unsigned __int16 *v71; // [rsp+68h] [rbp-310h] BYREF
  HKEY v72; // [rsp+70h] [rbp-308h] BYREF
  _BYTE v73[8]; // [rsp+78h] [rbp-300h] BYREF
  HKEY v74; // [rsp+80h] [rbp-2F8h] BYREF
  HKEY v75; // [rsp+88h] [rbp-2F0h] BYREF
  void *p_hKey; // [rsp+90h] [rbp-2E8h] BYREF
  HKEY v77; // [rsp+98h] [rbp-2E0h] BYREF
  int v78; // [rsp+A0h] [rbp-2D8h]
  int v79; // [rsp+A4h] [rbp-2D4h]
  int v80; // [rsp+A8h] [rbp-2D0h] BYREF
  DWORD v81; // [rsp+ACh] [rbp-2CCh] BYREF
  DWORD v82; // [rsp+B0h] [rbp-2C8h] BYREF
  __int64 v83; // [rsp+B8h] [rbp-2C0h] BYREF
  __int64 v84; // [rsp+C0h] [rbp-2B8h] BYREF
  _QWORD v85[2]; // [rsp+C8h] [rbp-2B0h] BYREF
  char v86; // [rsp+D8h] [rbp-2A0h]
  _QWORD v87[2]; // [rsp+E0h] [rbp-298h] BYREF
  char v88; // [rsp+F0h] [rbp-288h]
  int v89; // [rsp+F8h] [rbp-280h] BYREF
  struct _GUID v90; // [rsp+100h] [rbp-278h] BYREF
  char v91; // [rsp+110h] [rbp-268h]
  unsigned __int16 **v92; // [rsp+120h] [rbp-258h]
  char v93; // [rsp+128h] [rbp-250h]
  void **p_Block; // [rsp+130h] [rbp-248h]
  char v95; // [rsp+138h] [rbp-240h]
  _BYTE v96[160]; // [rsp+140h] [rbp-238h] BYREF
  unsigned __int16 *v97[4]; // [rsp+1E0h] [rbp-198h] BYREF
  unsigned __int16 *v98[4]; // [rsp+200h] [rbp-178h] BYREF
  unsigned __int16 *v99[4]; // [rsp+220h] [rbp-158h] BYREF
  char *v100[4]; // [rsp+240h] [rbp-138h] BYREF
  char *v101; // [rsp+260h] [rbp-118h] BYREF
  __int128 v102; // [rsp+280h] [rbp-F8h] BYREF
  _BYTE v103[96]; // [rsp+290h] [rbp-E8h] BYREF
  _QWORD v104[8]; // [rsp+2F0h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+0h]

  std::list<std::wstring>::list<std::wstring>(&v69);
  OrchestratorDCInfo::OrchestratorDCInfo((OrchestratorDCInfo *)v97);
  v67 = 63;
  hKey = 0;
  v82 = 0;
  v81 = 0;
  v83 = 0;
  v84 = 0;
  v70 = 0;
  v68 = 0;
  v2 = _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
         &v68,
         L"Global\\DeclaredConfigurationMutex");
  if ( v2 >= 0 )
  {
    v80 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v68,
      v73,
      &v80,
      30000);
    try
    {
      if ( (v80 & 0xFFFFFF7F) != 0 )
      {
        Logger = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          Logger,
          L"DeclaredConfigurationStore_ReconstructQueueForEnrollment",
          L"DeclaredConfigurationGlobalMutex.acquire",
          &word_180142E98,
          -2100297724);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v73);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v68);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v97);
        std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
          v6,
          v69);
        std::_Deallocate<16>(v69, 0x30u);
        result = 2194669572LL;
      }
      else
      {
        BYTE1(v80) = 1;
        valid = DCIsValidEnrollment(a1, &v70, (enum EnrollmentStateTag *)&v67);
        if ( valid < 0 || v70 && v67 != 4 )
        {
          v72 = 0;
          p_hKey = &v72;
          v77 = 0;
          LOBYTE(v78) = 1;
          v10 = DCGetEnrollmentsRootKey(&v77, 0);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
          if ( v10 >= 0 )
          {
            v13 = DCCDNUtil_SetRegistryDWORD(v72, 0, L"_Container_ReprocessDocs", 1);
            if ( v13 >= 0 )
            {
              p_hKey = &hKey;
              v77 = 0;
              LOBYTE(v78) = 1;
              v16 = DCGetReadonlyEnrollmentIdKey(a1, &v77);
              wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
              if ( v16 >= 0 )
              {
                if ( (unsigned int)GetDocIdSubKeys(hKey, &v81, &v83) != -2147024894 )
                {
                  v85[0] = &v83;
                  v85[1] = &v81;
                  v86 = 1;
                  for ( i = 0; i < v81; ++i )
                  {
                    if ( *(_QWORD *)(v83 + 8LL * i) )
                    {
                      v74 = 0;
                      v67 = 0;
                      v70 = 63;
                      v20 = DCIsValidEnrollment(a1, &v67, (enum EnrollmentStateTag *)&v70);
                      if ( v20 >= 0 && (!v67 || v70 == 4) )
                      {
                        v21 = CDeclaredConfigurationLogger::GetLogger();
                        CDeclaredConfigurationLogger::LogEnrollmentInvalidOrUnenrolling(v21, a1, v20);
                        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v74);
                        v86 = 0;
                        lambda_bec8b26cd41394074412db657cb61652_::operator()(v85);
                        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v72);
                        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v73);
                        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v68);
                        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                        OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v97);
                        std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                          v22,
                          v69);
                        std::_Deallocate<16>(v69, 0x30u);
                        result = 2194669570LL;
                        goto LABEL_74;
                      }
                      p_hKey = &v74;
                      v77 = 0;
                      LOBYTE(v78) = 1;
                      EnrollmentIdSidStateKey = GetEnrollmentIdSidStateKey(
                                                  a1,
                                                  *(const unsigned __int16 **)(v83 + 8LL * i),
                                                  &v77);
                      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
                      if ( EnrollmentIdSidStateKey >= 0 && (unsigned int)GetDocIdSubKeys(v74, &v82, &v84) != -2147024894 )
                      {
                        v87[0] = &v84;
                        v87[1] = &v82;
                        v88 = 1;
                        for ( j = 0; j < v82; ++j )
                        {
                          Block = 0;
                          p_Block = &Block;
                          v95 = 1;
                          DCCDNUtil_GetRegistryString(
                            v74,
                            *(const unsigned __int16 **)(v84 + 8LL * j),
                            L"MostRecentVersion",
                            (unsigned __int16 **)&Block);
                          v77 = 0;
                          v78 = 0;
                          v79 = 63;
                          p_hKey = SysAllocString(a1);
                          if ( !p_hKey || (v77 = (HKEY)SysAllocString(*(const OLECHAR **)(v83 + 8LL * i))) == 0 )
                          {
                            DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&p_hKey);
                            operator delete(Block);
                            Block = 0;
                            v88 = 0;
                            lambda_bec8b26cd41394074412db657cb61652_::operator()(v87);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v74);
                            v86 = 0;
                            lambda_bec8b26cd41394074412db657cb61652_::operator()(v85);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v72);
                            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v73);
                            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v68);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                            OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v97);
                            std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                              v25,
                              v69);
                            std::_Deallocate<16>(v69, 0x30u);
                            result = 2147942414LL;
                            goto LABEL_74;
                          }
                          v75 = 0;
                          *(_QWORD *)&v90.Data1 = &v75;
                          *(_QWORD *)v90.Data4 = 0;
                          v91 = 1;
                          EnrollmentIdSidStateDocIdVersionRawKey = GetEnrollmentIdSidStateDocIdVersionRawKey(
                                                                     (unsigned int)&p_hKey,
                                                                     *(_QWORD *)(v84 + 8LL * j),
                                                                     (_DWORD)Block,
                                                                     (unsigned int)v90.Data4,
                                                                     1);
                          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v90);
                          if ( EnrollmentIdSidStateDocIdVersionRawKey < 0 )
                          {
                            v27 = CDeclaredConfigurationLogger::GetLogger();
                            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                              v27,
                              L"DeclaredConfigurationStore_ReconstructQueueForEnrollment",
                              L"GetEnrollmentIdSidStateDocIdVersionRawKey",
                              &word_180142E98,
                              EnrollmentIdSidStateDocIdVersionRawKey);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v75);
                            DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&p_hKey);
                            operator delete(Block);
                            Block = 0;
                            v88 = 0;
                            lambda_bec8b26cd41394074412db657cb61652_::operator()(v87);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v74);
                            v86 = 0;
                            lambda_bec8b26cd41394074412db657cb61652_::operator()(v85);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v72);
                            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v73);
                            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v68);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                            OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v97);
                            std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                              v28,
                              v69);
                            std::_Deallocate<16>(v69, 0x30u);
                            result = (unsigned int)EnrollmentIdSidStateDocIdVersionRawKey;
                            goto LABEL_74;
                          }
                          v71 = 0;
                          v92 = &v71;
                          v93 = 1;
                          RegistryString = DCCDNUtil_GetRegistryString(v75, 0, L"osdefinedscenario", &v71);
                          if ( RegistryString < 0 )
                          {
                            v30 = CDeclaredConfigurationLogger::GetLogger();
                            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                              v30,
                              L"DeclaredConfigurationStore_ReconstructQueueForEnrollment",
                              L"DCCDNUtil_GetRegistryString",
                              L"Get OSDefinedScenario failed",
                              RegistryString);
                            operator delete(v71);
                            v71 = 0;
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v75);
                            DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&p_hKey);
                            operator delete(Block);
                            Block = 0;
                            v88 = 0;
                            lambda_bec8b26cd41394074412db657cb61652_::operator()(v87);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v74);
                            v86 = 0;
                            lambda_bec8b26cd41394074412db657cb61652_::operator()(v85);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v72);
                            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v73);
                            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v68);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                            OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v97);
                            std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                              v31,
                              v69);
                            std::_Deallocate<16>(v69, 0x30u);
                            result = (unsigned int)RegistryString;
                            goto LABEL_74;
                          }
                          StateMachineTypeFromDefinedScenario = getStateMachineTypeFromDefinedScenario(v71);
                          if ( StateMachineTypeFromDefinedScenario == 63 )
                          {
                            v33 = CDeclaredConfigurationLogger::GetLogger();
                            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                              v33,
                              L"DeclaredConfigurationStore_ReconstructQueueForEnrollment",
                              L"getStateMachineTypeFromDefinedScenario",
                              L"state machine type is invalid",
                              -2147024809);
                            wil::details::in1diag3::Return_HrMsg(
                              retaddr,
                              (void *)0x4747,
                              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\"
                                            "declaredconfigurationapi.cpp",
                              (const char *)0x80070057LL,
                              (int)"state machine type is invalid",
                              (const char *)v64);
                            operator delete(v71);
                            v71 = 0;
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v75);
                            DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&p_hKey);
                            operator delete(Block);
                            Block = 0;
                            v88 = 0;
                            lambda_bec8b26cd41394074412db657cb61652_::operator()(v87);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v74);
                            v86 = 0;
                            lambda_bec8b26cd41394074412db657cb61652_::operator()(v85);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v72);
                            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v73);
                            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v68);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                            OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v97);
                            std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                              v34,
                              v69);
                            std::_Deallocate<16>(v69, 0x30u);
                            result = 2147942487LL;
                            goto LABEL_74;
                          }
                          v35 = -1;
                          do
                            ++v35;
                          while ( a1[v35] );
                          std::wstring::_Assign<unsigned short>((char **)v97, a1, (char *)v35);
                          v36 = _o__wcsicmp(*(_QWORD *)(v83 + 8LL * i), L"device");
                          v37 = L"device";
                          if ( v36 )
                            v37 = L"user";
                          v38 = -1;
                          do
                            ++v38;
                          while ( v37[v38] );
                          std::wstring::_Assign<unsigned short>((char **)v98, v37, (char *)v38);
                          v39 = *(_WORD **)(v84 + 8LL * j);
                          v40 = -1;
                          do
                            ++v40;
                          while ( v39[v40] );
                          std::wstring::_Assign<unsigned short>((char **)v99, v39, (char *)v40);
                          v41 = -1;
                          do
                            ++v41;
                          while ( *((_WORD *)Block + v41) );
                          std::wstring::_Assign<unsigned short>(v100, Block, (char *)v41);
                          std::wstring::_Assign<unsigned short>(&v101, L"Host", (char *)4);
                          v102 = 0;
                          v90 = 0;
                          v43 = (const unsigned __int16 *)v99;
                          if ( v99[3] > (unsigned __int16 *)7 )
                            v43 = v99[0];
                          v44 = (const unsigned __int16 *)v98;
                          if ( v98[3] > (unsigned __int16 *)7 )
                            v44 = v98[0];
                          v45 = (const unsigned __int16 *)v97;
                          if ( v97[3] > (unsigned __int16 *)7 )
                            v45 = v97[0];
                          if ( (int)OrchestratorDBManager::FindRequest(v42, v45, v44, v43, &v90) < 0 )
                          {
                            v57 = OrchestratorDCInfo::OrchestratorDCInfo(
                                    (OrchestratorDCInfo *)v96,
                                    (const struct OrchestratorDCInfo *)v97);
                            v59 = OrchestratorDBManager::CreateNewRequest(
                                    v58,
                                    v57,
                                    StateMachineTypeFromDefinedScenario,
                                    &v102);
                            if ( v59 < 0 )
                            {
                              v60 = CDeclaredConfigurationLogger::GetLogger();
                              CDeclaredConfigurationLogger::LogReconstructNewRequestEvent(
                                v60,
                                a1,
                                *(const unsigned __int16 **)(v83 + 8LL * i),
                                *(const unsigned __int16 **)(v84 + 8LL * j),
                                v59);
                              operator delete(v71);
                              v71 = 0;
                              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v75);
                              DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&p_hKey);
                              operator delete(Block);
                              Block = 0;
                              v88 = 0;
                              lambda_bec8b26cd41394074412db657cb61652_::operator()(v87);
                              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v74);
                              v86 = 0;
                              lambda_bec8b26cd41394074412db657cb61652_::operator()(v85);
                              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v72);
                              __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v73);
                              __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v68);
                              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                              OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v97);
                              std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                                v61,
                                v69);
                              std::_Deallocate<16>(v69, 0x30u);
                              result = (unsigned int)v59;
                              goto LABEL_74;
                            }
                          }
                          else
                          {
                            OrchestratorDCInfo::OrchestratorDCInfo((OrchestratorDCInfo *)v103);
                            v67 = 0;
                            v89 = 0;
                            v70 = 0;
                            v46 = v90;
                            Request = OrchestratorDBManager::GetRequest(
                                        v47,
                                        &v90,
                                        (struct OrchestratorDCInfo *)v103,
                                        (enum StateMachineTypeTag *)&v67,
                                        (enum DMOrchestratorState *)&v89,
                                        (enum DCLifecycleNotificationType *)&v70);
                            if ( Request < 0 )
                            {
                              v49 = CDeclaredConfigurationLogger::GetLogger();
                              CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                                v49,
                                L"DeclaredConfigurationStore_ReconstructQueueForEnrollment",
                                L"OrchestratorIDatabaseManagerSingleton::instance().GetRequest",
                                &word_180142E98,
                                Request);
                              OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v103);
                              operator delete(v71);
                              v71 = 0;
                              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v75);
                              DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&p_hKey);
                              operator delete(Block);
                              Block = 0;
                              v88 = 0;
                              lambda_bec8b26cd41394074412db657cb61652_::operator()(v87);
                              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v74);
                              v86 = 0;
                              lambda_bec8b26cd41394074412db657cb61652_::operator()(v85);
                              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v72);
                              __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v73);
                              __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v68);
                              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                              OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v97);
                              std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                                v50,
                                v69);
                              std::_Deallocate<16>(v69, 0x30u);
                              result = (unsigned int)Request;
                              goto LABEL_74;
                            }
                            v51 = v100;
                            if ( v100[3] > (char *)7 )
                              v51 = (char **)v100[0];
                            v52 = v104;
                            if ( v104[3] > 7u )
                              v52 = (_QWORD *)v104[0];
                            if ( (unsigned int)_o__wcsicmp(v52, v51) )
                            {
                              v53 = OrchestratorDCInfo::OrchestratorDCInfo(
                                      (OrchestratorDCInfo *)v96,
                                      (const struct OrchestratorDCInfo *)v97);
                              v90 = v46;
                              updated = OrchestratorDBManager::UpdateRequestDocVersion(
                                          v54,
                                          &v90,
                                          v53,
                                          (unsigned int)v67);
                              if ( updated < 0 )
                              {
                                v56 = CDeclaredConfigurationLogger::GetLogger();
                                CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                                  v56,
                                  L"DeclaredConfigurationStore_ReconstructQueueForEnrollment",
                                  L"OrchestratorIDatabaseManagerSingleton::instance().UpdateRequestDocVersion",
                                  &word_180142E98,
                                  updated);
                              }
                            }
                            OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v103);
                          }
                          v93 = 0;
                          operator delete(v71);
                          v71 = 0;
                          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v75);
                          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&p_hKey);
                          v95 = 0;
                          operator delete(Block);
                        }
                        v88 = 0;
                        lambda_bec8b26cd41394074412db657cb61652_::operator()(v87);
                      }
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v74);
                    }
                  }
                  v86 = 0;
                  lambda_bec8b26cd41394074412db657cb61652_::operator()(v85);
                }
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v72);
                __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v73);
                __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v68);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v97);
                std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                  v62,
                  v69);
                std::_Deallocate<16>(v69, 0x30u);
                result = 0;
              }
              else
              {
                v17 = CDeclaredConfigurationLogger::GetLogger();
                CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                  v17,
                  L"DeclaredConfigurationStore_ReconstructQueueForEnrollment",
                  L"DCGetReadonlyEnrollmentIdKey",
                  &word_180142E98,
                  v16);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v72);
                __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v73);
                __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v68);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v97);
                std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                  v18,
                  v69);
                std::_Deallocate<16>(v69, 0x30u);
                result = (unsigned int)v16;
              }
            }
            else
            {
              v14 = CDeclaredConfigurationLogger::GetLogger();
              CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                v14,
                L"DeclaredConfigurationStore_ReconstructQueueForEnrollment",
                L"DCCDNUtil_SetRegistryDWORD:Set _Container_ReprocessDocs",
                &word_180142E98,
                v13);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v72);
              __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v73);
              __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v68);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v97);
              std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                v15,
                v69);
              std::_Deallocate<16>(v69, 0x30u);
              result = (unsigned int)v13;
            }
          }
          else
          {
            v11 = CDeclaredConfigurationLogger::GetLogger();
            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
              v11,
              L"DeclaredConfigurationStore_ReconstructQueueForEnrollment",
              L"DCGetEnrollmentsRootKey",
              &word_180142E98,
              v10);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v72);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v73);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v68);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v97);
            std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
              v12,
              v69);
            std::_Deallocate<16>(v69, 0x30u);
            result = (unsigned int)v10;
          }
        }
        else
        {
          v8 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogEnrollmentInvalidOrUnenrolling(v8, a1, valid);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v73);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v68);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v97);
          std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
            v9,
            v69);
          std::_Deallocate<16>(v69, 0x30u);
          result = 2194669570LL;
        }
      }
    }
    catch ( ... )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v97);
      std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
        v63,
        v69);
      std::_Deallocate<16>(v69, 0x30u);
      result = 2147549183LL;
    }
LABEL_74:
    ;
  }
  else
  {
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v68);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v97);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(v3, v69);
    std::_Deallocate<16>(v69, 0x30u);
    return (unsigned int)v2;
  }
  return result;
}

```

## disassembly

```asm
0x180082930  mov     rax, rsp
0x180082933  mov     [rax+10h], rbx
0x180082937  mov     [rax+18h], rsi
0x18008293b  push    rdi
0x18008293c  push    r12
0x18008293e  push    r13
0x180082940  push    r14
0x180082942  push    r15
0x180082944  sub     rsp, 350h
0x18008294b  movaps  xmmword ptr [rax-38h], xmm6
0x18008294f  mov     rax, cs:__security_cookie
0x180082956  xor     rax, rsp
0x180082959  mov     [rsp+378h+var_48], rax
0x180082961  mov     rdi, rcx
0x180082964  lea     rcx, [rsp+378h+var_328]
0x180082969  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x18008296e  nop
0x18008296f  lea     rcx, [rsp+378h+var_198]; this
0x180082977  call    ??0OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::OrchestratorDCInfo(void)
0x18008297c  nop
0x18008297d  mov     [rsp+378h+var_338], 3Fh ; '?'
0x180082985  xor     r13d, r13d
0x180082988  mov     [rsp+378h+hKey], r13
0x18008298d  mov     [rsp+378h+var_2C8], r13d
0x180082995  mov     [rsp+378h+var_2CC], r13d
0x18008299d  mov     [rsp+378h+var_2C0], r13
0x1800829a5  mov     [rsp+378h+var_2B8], r13
0x1800829ad  mov     [rsp+378h+var_318], r13d
0x1800829b2  mov     [rsp+378h+var_330], r13
0x1800829b7  lea     rdx, aGlobalDeclared; "Global\\DeclaredConfigurationMutex"
0x1800829be  lea     rcx, [rsp+378h+var_330]
0x1800829c3  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800829c8  mov     ebx, eax
0x1800829ca  test    eax, eax
0x1800829cc  jns     short loc_180082A12
0x1800829ce  lea     rcx, [rsp+378h+var_330]
0x1800829d3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800829d8  nop
0x1800829d9  lea     rcx, [rsp+378h+hKey]
0x1800829de  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800829e3  nop
0x1800829e4  lea     rcx, [rsp+378h+var_198]; this
0x1800829ec  call    ??1OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::~OrchestratorDCInfo(void)
0x1800829f1  nop
0x1800829f2  mov     rdx, [rsp+378h+var_328]
0x1800829f7  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1800829fc  mov     edx, 30h ; '0'
0x180082a01  mov     rcx, [rsp+378h+var_328]
0x180082a06  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180082a0b  mov     eax, ebx
0x180082a0d  jmp     loc_180083AF2
0x180082a12  mov     [rsp+378h+var_2D0], r13d
0x180082a1a  mov     r9d, 7530h
0x180082a20  lea     r8, [rsp+378h+var_2D0]
0x180082a28  lea     rdx, [rsp+378h+var_300]
0x180082a2d  lea     rcx, [rsp+378h+var_330]
0x180082a32  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180082a37  nop
0x180082a38  test    [rsp+378h+var_2D0], 0FFFFFF7Fh
0x180082a43  jz      short loc_180082AC0
0x180082a45  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180082a4a  mov     ebx, 82D00004h
0x180082a4f  mov     dword ptr [rsp+378h+var_358], ebx; int
0x180082a53  lea     r9, word_180142E98; unsigned __int16 *
0x180082a5a  lea     r8, aDeclaredconfig_173; "DeclaredConfigurationGlobalMutex.acquir"...
0x180082a61  lea     rdx, aDeclaredconfig_190; "DeclaredConfigurationStore_ReconstructQ"...
0x180082a68  mov     rcx, rax; this
0x180082a6b  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180082a70  nop
0x180082a71  lea     rcx, [rsp+378h+var_300]
0x180082a76  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180082a7b  nop
0x180082a7c  lea     rcx, [rsp+378h+var_330]
0x180082a81  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180082a86  nop
0x180082a87  lea     rcx, [rsp+378h+hKey]
0x180082a8c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180082a91  nop
0x180082a92  lea     rcx, [rsp+378h+var_198]; this
0x180082a9a  call    ??1OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::~OrchestratorDCInfo(void)
0x180082a9f  nop
0x180082aa0  mov     rdx, [rsp+378h+var_328]
0x180082aa5  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180082aaa  mov     edx, 30h ; '0'
0x180082aaf  mov     rcx, [rsp+378h+var_328]
0x180082ab4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180082ab9  mov     eax, ebx
0x180082abb  jmp     loc_180083AF2
0x180082ac0  mov     byte ptr [rsp+378h+var_2D0+1], 1
0x180082ac8  lea     r8, [rsp+378h+var_338]; enum EnrollmentStateTag *
0x180082acd  lea     rdx, [rsp+378h+var_318]; int *
0x180082ad2  mov     rcx, rdi; StringUuid
0x180082ad5  call    ?DCIsValidEnrollment@@YAJPEBGPEAHPEAW4EnrollmentStateTag@@@Z; DCIsValidEnrollment(ushort const *,int *,EnrollmentStateTag *)
0x180082ada  mov     ebx, eax
0x180082adc  test    eax, eax
0x180082ade  js      short loc_180082B54
0x180082ae0  cmp     [rsp+378h+var_318], r13d
0x180082ae5  jz      short loc_180082AEE
0x180082ae7  cmp     [rsp+378h+var_338], 4
0x180082aec  jnz     short loc_180082B54
0x180082aee  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180082af3  mov     r8d, ebx; int
0x180082af6  mov     rdx, rdi; unsigned __int16 *
0x180082af9  mov     rcx, rax; this
0x180082afc  call    ?LogEnrollmentInvalidOrUnenrolling@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogEnrollmentInvalidOrUnenrolling(ushort const *,long)
0x180082b01  nop
0x180082b02  lea     rcx, [rsp+378h+var_300]
0x180082b07  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180082b0c  nop
0x180082b0d  lea     rcx, [rsp+378h+var_330]
0x180082b12  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180082b17  nop
0x180082b18  lea     rcx, [rsp+378h+hKey]
0x180082b1d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180082b22  nop
0x180082b23  lea     rcx, [rsp+378h+var_198]; this
0x180082b2b  call    ??1OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::~OrchestratorDCInfo(void)
0x180082b30  nop
0x180082b31  mov     rdx, [rsp+378h+var_328]
0x180082b36  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180082b3b  mov     edx, 30h ; '0'
0x180082b40  mov     rcx, [rsp+378h+var_328]
0x180082b45  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180082b4a  mov     eax, 82D00002h
0x180082b4f  jmp     loc_180083AF2
0x180082b54  mov     [rsp+378h+var_308], r13
0x180082b59  lea     rax, [rsp+378h+var_308]
0x180082b5e  mov     [rsp+378h+var_2E8], rax
0x180082b66  mov     [rsp+378h+var_2E0], r13
0x180082b6e  mov     byte ptr [rsp+378h+var_2D8], 1
0x180082b76  xor     edx, edx
0x180082b78  lea     rcx, [rsp+378h+var_2E0]
0x180082b80  call    DCGetEnrollmentsRootKey
0x180082b85  mov     ebx, eax
0x180082b87  lea     rcx, [rsp+378h+var_2E8]
0x180082b8f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180082b94  test    ebx, ebx
0x180082b96  jns     loc_180082C1D
0x180082b9c  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180082ba1  mov     dword ptr [rsp+378h+var_358], ebx; int
0x180082ba5  lea     r9, word_180142E98; unsigned __int16 *
0x180082bac  lea     r8, aDcgetenrollmen_1; "DCGetEnrollmentsRootKey"
0x180082bb3  lea     rdx, aDeclaredconfig_190; "DeclaredConfigurationStore_ReconstructQ"...
0x180082bba  mov     rcx, rax; this
0x180082bbd  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180082bc2  nop
0x180082bc3  lea     rcx, [rsp+378h+var_308]
0x180082bc8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180082bcd  nop
0x180082bce  lea     rcx, [rsp+378h+var_300]
0x180082bd3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180082bd8  nop
0x180082bd9  lea     rcx, [rsp+378h+var_330]
0x180082bde  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180082be3  nop
0x180082be4  lea     rcx, [rsp+378h+hKey]
0x180082be9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180082bee  nop
0x180082bef  lea     rcx, [rsp+378h+var_198]; this
0x180082bf7  call    ??1OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::~OrchestratorDCInfo(void)
0x180082bfc  nop
0x180082bfd  mov     rdx, [rsp+378h+var_328]
0x180082c02  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180082c07  mov     edx, 30h ; '0'
0x180082c0c  mov     rcx, [rsp+378h+var_328]
0x180082c11  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180082c16  mov     eax, ebx
0x180082c18  jmp     loc_180083AF2
0x180082c1d  mov     r9d, 1; unsigned int
0x180082c23  lea     r8, aContainerRepro; "_Container_ReprocessDocs"
0x180082c2a  xor     edx, edx; unsigned __int16 *
0x180082c2c  mov     rcx, [rsp+378h+var_308]; HKEY
0x180082c31  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180082c36  mov     ebx, eax
0x180082c38  test    eax, eax
0x180082c3a  jns     loc_180082CC1
0x180082c40  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180082c45  mov     dword ptr [rsp+378h+var_358], ebx; int
0x180082c49  lea     r9, word_180142E98; unsigned __int16 *
0x180082c50  lea     r8, aDccdnutilSetre_0; "DCCDNUtil_SetRegistryDWORD:Set _Contain"...
0x180082c57  lea     rdx, aDeclaredconfig_190; "DeclaredConfigurationStore_ReconstructQ"...
0x180082c5e  mov     rcx, rax; this
0x180082c61  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180082c66  nop
0x180082c67  lea     rcx, [rsp+378h+var_308]
0x180082c6c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180082c71  nop
0x180082c72  lea     rcx, [rsp+378h+var_300]
0x180082c77  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180082c7c  nop
0x180082c7d  lea     rcx, [rsp+378h+var_330]
0x180082c82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180082c87  nop
0x180082c88  lea     rcx, [rsp+378h+hKey]
0x180082c8d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180082c92  nop
0x180082c93  lea     rcx, [rsp+378h+var_198]; this
0x180082c9b  call    ??1OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::~OrchestratorDCInfo(void)
0x180082ca0  nop
0x180082ca1  mov     rdx, [rsp+378h+var_328]
0x180082ca6  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180082cab  mov     edx, 30h ; '0'
0x180082cb0  mov     rcx, [rsp+378h+var_328]
0x180082cb5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180082cba  mov     eax, ebx
0x180082cbc  jmp     loc_180083AF2
0x180082cc1  lea     rax, [rsp+378h+hKey]
0x180082cc6  mov     [rsp+378h+var_2E8], rax
0x180082cce  mov     [rsp+378h+var_2E0], r13
0x180082cd6  mov     byte ptr [rsp+378h+var_2D8], 1
0x180082cde  lea     rdx, [rsp+378h+var_2E0]
0x180082ce6  mov     rcx, rdi
0x180082ce9  call    DCGetReadonlyEnrollmentIdKey
0x180082cee  mov     ebx, eax
0x180082cf0  lea     rcx, [rsp+378h+var_2E8]
0x180082cf8  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180082cfd  test    ebx, ebx
0x180082cff  jns     loc_180082D86
0x180082d05  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180082d0a  mov     dword ptr [rsp+378h+var_358], ebx; int
0x180082d0e  lea     r9, word_180142E98; unsigned __int16 *
0x180082d15  lea     r8, aDcgetreadonlye_0; "DCGetReadonlyEnrollmentIdKey"
0x180082d1c  lea     rdx, aDeclaredconfig_190; "DeclaredConfigurationStore_ReconstructQ"...
0x180082d23  mov     rcx, rax; this
0x180082d26  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180082d2b  nop
0x180082d2c  lea     rcx, [rsp+378h+var_308]
0x180082d31  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180082d36  nop
0x180082d37  lea     rcx, [rsp+378h+var_300]
0x180082d3c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180082d41  nop
0x180082d42  lea     rcx, [rsp+378h+var_330]
0x180082d47  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180082d4c  nop
0x180082d4d  lea     rcx, [rsp+378h+hKey]
0x180082d52  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180082d57  nop
0x180082d58  lea     rcx, [rsp+378h+var_198]; this
0x180082d60  call    ??1OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::~OrchestratorDCInfo(void)
0x180082d65  nop
0x180082d66  mov     rdx, [rsp+378h+var_328]
0x180082d6b  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180082d70  mov     edx, 30h ; '0'
0x180082d75  mov     rcx, [rsp+378h+var_328]
0x180082d7a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180082d7f  mov     eax, ebx
0x180082d81  jmp     loc_180083AF2
0x180082d86  lea     r8, [rsp+378h+var_2C0]
0x180082d8e  lea     rdx, [rsp+378h+var_2CC]
0x180082d96  mov     rcx, [rsp+378h+hKey]; hKey
0x180082d9b  call    GetDocIdSubKeys
0x180082da0  cmp     eax, 80070002h
0x180082da5  jz      loc_180083A64
0x180082dab  lea     rax, [rsp+378h+var_2C0]
0x180082db3  mov     [rsp+378h+var_2B0], rax
0x180082dbb  lea     rax, [rsp+378h+var_2CC]
0x180082dc3  mov     [rsp+378h+var_2A8], rax
0x180082dcb  mov     [rsp+378h+var_2A0], 1
0x180082dd3  mov     r15d, r13d
0x180082dd6  cmp     r15d, [rsp+378h+var_2CC]
0x180082dde  jnb     loc_180083A4E
0x180082de4  mov     r12d, r15d
0x180082de7  mov     rax, [rsp+378h+var_2C0]
0x180082def  cmp     [rax+r12*8], r13
0x180082df3  jz      loc_180083A46
0x180082df9  mov     [rsp+378h+var_2F8], r13
0x180082e01  mov     [rsp+378h+var_338], r13d
0x180082e06  mov     [rsp+378h+var_318], 3Fh ; '?'
0x180082e0e  lea     r8, [rsp+378h+var_318]; enum EnrollmentStateTag *
0x180082e13  lea     rdx, [rsp+378h+var_338]; int *
0x180082e18  mov     rcx, rdi; StringUuid
0x180082e1b  call    ?DCIsValidEnrollment@@YAJPEBGPEAHPEAW4EnrollmentStateTag@@@Z; DCIsValidEnrollment(ushort const *,int *,EnrollmentStateTag *)
0x180082e20  mov     ebx, eax
0x180082e22  test    eax, eax
0x180082e24  js      loc_180082ED1
0x180082e2a  cmp     [rsp+378h+var_338], r13d
0x180082e2f  jz      short loc_180082E3C
0x180082e31  cmp     [rsp+378h+var_318], 4
0x180082e36  jnz     loc_180082ED1
0x180082e3c  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180082e41  mov     r8d, ebx; int
0x180082e44  mov     rdx, rdi; unsigned __int16 *
0x180082e47  mov     rcx, rax; this
0x180082e4a  call    ?LogEnrollmentInvalidOrUnenrolling@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogEnrollmentInvalidOrUnenrolling(ushort const *,long)
0x180082e4f  nop
0x180082e50  lea     rcx, [rsp+378h+var_2F8]
0x180082e58  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180082e5d  nop
0x180082e5e  mov     [rsp+378h+var_2A0], r13b
0x180082e66  lea     rcx, [rsp+378h+var_2B0]
0x180082e6e  call    _lambda_bec8b26cd41394074412db657cb61652___operator__
0x180082e73  nop
0x180082e74  lea     rcx, [rsp+378h+var_308]
0x180082e79  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180082e7e  nop
0x180082e7f  lea     rcx, [rsp+378h+var_300]
0x180082e84  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180082e89  nop
0x180082e8a  lea     rcx, [rsp+378h+var_330]
  ... truncated ...
```
