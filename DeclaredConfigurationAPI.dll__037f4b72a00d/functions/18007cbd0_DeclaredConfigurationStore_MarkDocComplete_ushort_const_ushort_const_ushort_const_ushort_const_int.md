# DeclaredConfigurationStore_MarkDocComplete(ushort const *,ushort const *,ushort const *,ushort const *,int)

- ea: `0x18007cbd0`
- end: `0x18007d28f`
- name: `?DeclaredConfigurationStore_MarkDocComplete@@YAJPEBG000H@Z`
- size: `1727`
- prototype: `__int64 __usercall@<rax>(OLECHAR *psz@<rcx>, OLECHAR *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, int)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801187d0`

## callees

- `0x18000be80`
- `0x18000e310`
- `0x18000e32c`
- `0x1800117dc`
- `0x180012dc4`
- `0x180018cc4`
- `0x18001ce5c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18004d158`
- `0x180058b08`
- `0x18005a400`
- `0x18005ebf0`
- `0x1800725e0`
- `0x18007cbd0`
- `0x18008cec8`
- `0x18008fc10`
- `0x18008fcd4`
- `0x18009a2e4`
- `0x18009aecc`
- `0x1800a0138`
- `0x1800a04fc`
- `0x1800a2184`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x1800f9e64`
- `0x1801006c8`
- `0x180100ad8`
- `0x180100e3c`
- `0x180119490`
- `0x180139010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007cd06`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007cdc9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007cf43`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007cd06`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007cdc9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007cf43`
- `DeclaredConfiguration!DMOrchestratorProcessDocsBasedOnState` at `0x18007d0ab`
- `DeclaredConfiguration!DMOrchestratorProcessDocsBasedOnState` at `0x18007d0ab`
- `OLEAUT32!__imp_SysAllocString` at `0x18007ccd7`
- `OLEAUT32!__imp_SysAllocString` at `0x18007cd44`
- `OLEAUT32!__imp_SysAllocString` at `0x18007cdda`
- `OLEAUT32!__imp_SysAllocString` at `0x18007ccd7`
- `OLEAUT32!__imp_SysAllocString` at `0x18007cd44`
- `OLEAUT32!__imp_SysAllocString` at `0x18007cdda`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18007cd23`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18007cd23`

## string_xrefs

- `0x18007cc3c`: `Global\DeclaredConfigurationMutex`
- `0x18007cc1a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18007cca7`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18007cd5d`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18007cfa4`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18007cffe`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18007d19e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18007d1d9`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18007d231`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18007cd2f`: `Failed DmGetActiveUserSid`
- `0x18007d1ca`: `Failed to find reg path for dc doc`
- `0x18007d186`: `Failed to find reg path for dc doc/version`
- `0x18007d178`: `Failed to read doc result status`
- `0x18007d16a`: `Failed to read doc unique Id`
- `0x18007cfef`: `Failed to update doc result status`
- `0x18007d059`: `Resource installed, reapplying pending docs`
- `0x18007d080`: `Resource installed, reapplying pending docs`
- `0x18007d060`: `DeclaredConfigurationStore_MarkDocComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall DeclaredConfigurationStore_MarkDocComplete(
        OLECHAR *psz,
        OLECHAR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  unsigned int ActiveUserSid; // ebx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  const char *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  int ResultsEnrollmentIdSidStateKey; // ebx
  unsigned int v17; // ebx
  int EnrollmentIdSidStateDocIdKey; // edi
  CDeclaredConfigurationLogger *Logger; // rax
  int v20; // ecx
  int v21; // eax
  __int64 v22; // rcx
  int v23; // ebx
  CDeclaredConfigurationLogger *v24; // rax
  const char *v26; // rax
  __int64 v27; // rdx
  int v28; // [rsp+20h] [rbp-91h]
  const char *v29; // [rsp+28h] [rbp-89h]
  unsigned __int16 *v30; // [rsp+30h] [rbp-81h] BYREF
  OLECHAR *psza; // [rsp+38h] [rbp-79h] BYREF
  unsigned int v32; // [rsp+40h] [rbp-71h] BYREF
  _BYTE v33[8]; // [rsp+48h] [rbp-69h] BYREF
  void *Block; // [rsp+50h] [rbp-61h] BYREF
  HKEY v35; // [rsp+58h] [rbp-59h] BYREF
  HKEY v36; // [rsp+60h] [rbp-51h] BYREF
  __int128 v37; // [rsp+68h] [rbp-49h] BYREF
  int v38; // [rsp+78h] [rbp-39h]
  int v39; // [rsp+7Ch] [rbp-35h]
  __int64 v40; // [rsp+80h] [rbp-31h] BYREF
  __int64 v41; // [rsp+88h] [rbp-29h] BYREF
  void **p_Block; // [rsp+90h] [rbp-21h] BYREF
  unsigned int *v43; // [rsp+98h] [rbp-19h] BYREF
  char v44; // [rsp+A0h] [rbp-11h]
  HKEY *v45; // [rsp+A8h] [rbp-9h] BYREF
  HKEY v46; // [rsp+B0h] [rbp-1h] BYREF
  char v47; // [rsp+B8h] [rbp+7h]
  void **v48; // [rsp+C0h] [rbp+Fh]
  char v49; // [rsp+C8h] [rbp+17h]
  unsigned __int16 **v50; // [rsp+D0h] [rbp+1Fh]
  char v51; // [rsp+D8h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]
  unsigned int v53; // [rsp+128h] [rbp+77h] BYREF

  if ( a4 )
  {
    v40 = 0;
    v53 = 0;
    v41 = 0;
    v10 = _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            &v41,
            L"Global\\DeclaredConfigurationMutex");
    ActiveUserSid = v10;
    if ( v10 < 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
        McTemplateU0dd_EventWriteTransfer(
          v11,
          EnterpriseDiagnosticsDeclaredConfigurationDCWatchDogTaskHandlerLockCreationFailure,
          (unsigned int)v10,
          (unsigned int)v10);
      goto LABEL_59;
    }
    v32 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v41,
      v33,
      &v32,
      180000);
    v12 = DCCheckAcquireStatus(v32);
    ActiveUserSid = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x530A,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v12,
        v28);
LABEL_58:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v33);
LABEL_59:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v41);
      return ActiveUserSid;
    }
    psza = 0;
    v37 = 0;
    v38 = 0;
    v39 = 63;
    *(_QWORD *)&v37 = SysAllocString(psz);
    if ( !(_QWORD)v37 )
    {
      v13 = "Out of memory allocating scopeData.m_pszEnrollmentId";
      ActiveUserSid = -2147024882;
      v14 = 21266;
LABEL_56:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)ActiveUserSid,
        (int)v13,
        v29);
      goto LABEL_57;
    }
    if ( (unsigned int)_o__wcsicmp(a2, L"user") )
    {
      if ( (unsigned int)_o__wcsicmp(a2, L"device") )
      {
        v13 = "info.userId is not user or device";
        ActiveUserSid = -2147024809;
        v14 = 21283;
        goto LABEL_56;
      }
      *((_QWORD *)&v37 + 1) = SysAllocString(a2);
      if ( !*((_QWORD *)&v37 + 1) )
      {
        v15 = 21279;
        goto LABEL_15;
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &psza,
        0);
      ActiveUserSid = DmGetActiveUserSid(&psza);
      if ( (ActiveUserSid & 0x80000000) != 0 )
      {
        v13 = "Failed DmGetActiveUserSid";
        v14 = 21271;
        goto LABEL_56;
      }
      *((_QWORD *)&v37 + 1) = SysAllocString(psza);
      if ( !*((_QWORD *)&v37 + 1) )
      {
        v15 = 21273;
LABEL_15:
        ActiveUserSid = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x8007000ELL,
          v28);
LABEL_57:
        DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v37);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psza);
        goto LABEL_58;
      }
      v38 = 1;
    }
    Block = 0;
    p_Block = &Block;
    v43 = 0;
    v44 = 1;
    ResultsEnrollmentIdSidStateKey = GetResultsEnrollmentIdSidStateKey(&v37, &v43);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_Block);
    if ( ResultsEnrollmentIdSidStateKey < 0 )
    {
      if ( ResultsEnrollmentIdSidStateKey == -2147024894 )
      {
        v40 = 0;
        v53 = 0;
      }
    }
    else
    {
      GetDocIdSubKeys((HKEY)Block);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&Block);
    p_Block = (void **)&v40;
    v43 = &v53;
    v44 = 1;
    v30 = 0;
    v17 = 0;
    if ( v53 )
    {
      while ( 1 )
      {
        v36 = 0;
        v45 = &v36;
        v46 = 0;
        v47 = 1;
        EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                                         (struct DeclaredConfigurationScopeData *)&v37,
                                         *(const unsigned __int16 **)(v40 + 8LL * v17),
                                         &v46,
                                         0);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v45);
        if ( EnrollmentIdSidStateDocIdKey < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x534E,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)(unsigned int)EnrollmentIdSidStateDocIdKey,
            (int)"Failed to find reg path for dc doc",
            v29);
          goto LABEL_54;
        }
        DCCDNUtil_GetRegistryString(v36, 0, L"MostRecentVersion", &v30);
        v50 = &v30;
        v51 = 1;
        v35 = 0;
        v45 = &v35;
        v46 = 0;
        v47 = 1;
        EnrollmentIdSidStateDocIdKey = GetResultsEnrollmentIdSidStateDocIdVersionKey(
                                         (unsigned int)&v37,
                                         *(_QWORD *)(v40 + 8LL * v17),
                                         (_DWORD)v30,
                                         (unsigned int)&v46,
                                         1);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v45);
        if ( EnrollmentIdSidStateDocIdKey < 0 )
          break;
        v32 = 0;
        EnrollmentIdSidStateDocIdKey = DCCDNUtil_GetRegistryDWORD(v35, 0, L"state", &v32);
        if ( EnrollmentIdSidStateDocIdKey < 0 )
        {
          v26 = "Failed to read doc result status";
          v27 = 21359;
          goto LABEL_51;
        }
        if ( v32 == 3 || v32 == 110 )
        {
          Block = 0;
          EnrollmentIdSidStateDocIdKey = DCCDNUtil_GetRegistryString(v35, 0, a3, (unsigned __int16 **)&Block);
          if ( EnrollmentIdSidStateDocIdKey < 0 )
          {
            v26 = "Failed to read doc unique Id";
            v27 = 21368;
            goto LABEL_51;
          }
          v48 = &Block;
          v49 = 1;
          if ( !(unsigned int)_o__wcsicmp(a4, Block) )
          {
            EnrollmentIdSidStateDocIdKey = DCCDNUtil_SetRegistryDWORD(v35, 0, L"state", (a5 != 1) + 60);
            if ( EnrollmentIdSidStateDocIdKey < 0 )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x5388,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
                (const char *)(unsigned int)EnrollmentIdSidStateDocIdKey,
                (int)"Failed to update doc result status",
                v29);
              operator delete(Block);
              Block = 0;
              goto LABEL_52;
            }
            if ( a5 == 1
              && !(unsigned int)UpdateOrchestration(
                                  (struct DeclaredConfigurationScopeData *)&v37,
                                  *(const unsigned __int16 **)(v40 + 8LL * v17),
                                  v30) )
            {
              Logger = CDeclaredConfigurationLogger::GetLogger();
              CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(
                Logger,
                L"DeclaredConfigurationStore_MarkDocComplete",
                L"Resource installed, reapplying pending docs",
                &word_180142E98);
              if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
                McTemplateU0zzd_EventWriteTransfer(
                  v20,
                  (unsigned int)OrchestratorGenericInformation,
                  (unsigned int)L"DeclaredConfigurationStore_MarkDocComplete",
                  (unsigned int)L"Resource installed, reapplying pending docs",
                  0);
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl'::`2'::impl) )
              {
                v21 = DMOrchestratorProcessDocsBasedOnState(43);
                goto LABEL_46;
              }
              v22 = *(_QWORD *)&qword_18018A6C8;
              if ( *(_QWORD *)&qword_18018A6C8 || (InitOrchestratorEngine(), (v22 = *(_QWORD *)&qword_18018A6C8) != 0) )
              {
                v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 40LL))(v22, 43);
LABEL_46:
                v23 = v21;
                v24 = CDeclaredConfigurationLogger::GetLogger();
                CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                  v24,
                  L"DeclaredConfigurationStore_MarkDocComplete",
                  L"ProcessDocsBasedOnState",
                  &word_180142E98,
                  v23);
              }
            }
            operator delete(Block);
            Block = 0;
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v35);
            operator delete(v30);
            v30 = 0;
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
            wil::details::ScopeExitFn__lambda_f984c43bf46297e92d14b60ba967b075___::operator()(&p_Block);
            DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v37);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psza);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v33);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v41);
            return (unsigned int)EnrollmentIdSidStateDocIdKey;
          }
          v49 = 0;
          operator delete(Block);
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v35);
        v51 = 0;
        operator delete(v30);
        v30 = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
        if ( ++v17 >= v53 )
          goto LABEL_34;
      }
      v26 = "Failed to find reg path for dc doc/version";
      v27 = 21350;
LABEL_51:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v27,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)EnrollmentIdSidStateDocIdKey,
        (int)v26,
        v29);
LABEL_52:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v35);
      operator delete(v30);
      v30 = 0;
LABEL_54:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
      wil::details::ScopeExitFn__lambda_f984c43bf46297e92d14b60ba967b075___::operator()(&p_Block);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v37);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psza);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v33);
      ActiveUserSid = EnrollmentIdSidStateDocIdKey;
      goto LABEL_59;
    }
LABEL_34:
    ActiveUserSid = -2147467259;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x53C8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x80004005LL,
      (int)"Failed to find pending doc that has request",
      v29);
    wil::details::ScopeExitFn__lambda_f984c43bf46297e92d14b60ba967b075___::operator()(&p_Block);
    goto LABEL_57;
  }
  ActiveUserSid = -2147024809;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x52FA,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
    (const char *)0x80070057LL,
    (int)"uniqueId can't be null",
    v29);
  return ActiveUserSid;
}

```

## disassembly

```asm
0x18007cbd0  mov     [rsp-8+arg_0], rbx
0x18007cbd5  mov     [rsp-8+arg_8], rsi
0x18007cbda  push    rbp
0x18007cbdb  push    rdi
0x18007cbdc  push    r12
0x18007cbde  push    r14
0x18007cbe0  push    r15
0x18007cbe2  lea     rbp, [rsp-2Fh]
0x18007cbe7  sub     rsp, 0E0h
0x18007cbee  mov     r14, r9
0x18007cbf1  mov     r15, r8
0x18007cbf4  mov     rdi, rdx
0x18007cbf7  mov     rsi, rcx
0x18007cbfa  xor     r12d, r12d
0x18007cbfd  test    r9, r9
0x18007cc00  jnz     short loc_18007CC30
0x18007cc02  mov     rcx, [rbp+57h]; this
0x18007cc06  lea     rax, aUniqueidCanTBe; "uniqueId can't be null"
0x18007cc0d  mov     qword ptr [rsp+100h+var_E0], rax; int
0x18007cc12  mov     ebx, 80070057h
0x18007cc17  mov     r9d, ebx; char *
0x18007cc1a  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18007cc21  mov     edx, 52FAh; void *
0x18007cc26  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007cc2b  jmp     loc_18007D271
0x18007cc30  mov     [rbp+4Fh+var_80], r12
0x18007cc34  mov     [rbp+4Fh+arg_18], r12d
0x18007cc38  mov     [rbp+4Fh+var_78], r12
0x18007cc3c  lea     rdx, aGlobalDeclared; "Global\\DeclaredConfigurationMutex"
0x18007cc43  lea     rcx, [rbp+4Fh+var_78]
0x18007cc47  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18007cc4c  mov     ebx, eax
0x18007cc4e  test    eax, eax
0x18007cc50  jns     short loc_18007CC76
0x18007cc52  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x18007cc59  jz      loc_18007D268
0x18007cc5f  mov     r9d, eax
0x18007cc62  mov     r8d, eax
0x18007cc65  lea     rdx, EnterpriseDiagnosticsDeclaredConfigurationDCWatchDogTaskHandlerLockCreationFailure
0x18007cc6c  call    McTemplateU0dd_EventWriteTransfer
0x18007cc71  jmp     loc_18007D268
0x18007cc76  mov     [rbp+4Fh+var_C0], r12d
0x18007cc7a  mov     r9d, 2BF20h
0x18007cc80  lea     r8, [rbp+4Fh+var_C0]
0x18007cc84  lea     rdx, [rbp+4Fh+var_B8]
0x18007cc88  lea     rcx, [rbp+4Fh+var_78]
0x18007cc8c  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18007cc91  nop
0x18007cc92  mov     ecx, [rbp+4Fh+var_C0]; unsigned int
0x18007cc95  call    ?DCCheckAcquireStatus@@YAJK@Z; DCCheckAcquireStatus(ulong)
0x18007cc9a  mov     ebx, eax
0x18007cc9c  test    eax, eax
0x18007cc9e  jns     short loc_18007CCBD
0x18007cca0  mov     rcx, [rbp+57h]; this
0x18007cca4  mov     r9d, eax; char *
0x18007cca7  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18007ccae  mov     edx, 530Ah; void *
0x18007ccb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ccb8  jmp     loc_18007D25E
0x18007ccbd  mov     [rbp+4Fh+psz], r12
0x18007ccc1  xorps   xmm0, xmm0
0x18007ccc4  movdqu  [rbp+4Fh+var_98], xmm0
0x18007ccc9  mov     [rbp+4Fh+var_88], r12d
0x18007cccd  mov     [rbp+4Fh+var_84], 3Fh ; '?'
0x18007ccd4  mov     rcx, rsi; psz
0x18007ccd7  call    cs:__imp_SysAllocString
0x18007ccdd  mov     qword ptr [rbp+4Fh+var_98], rax
0x18007cce1  test    rax, rax
0x18007cce4  jnz     short loc_18007CCFC
0x18007cce6  lea     rax, aOutOfMemoryAll_0; "Out of memory allocating scopeData.m_ps"...
0x18007cced  mov     ebx, 8007000Eh
0x18007ccf2  mov     edx, 5312h
0x18007ccf7  jmp     loc_18007D231
0x18007ccfc  lea     rdx, aUser_0; "user"
0x18007cd03  mov     rcx, rdi
0x18007cd06  call    cs:__imp__o__wcsicmp
0x18007cd0c  test    eax, eax
0x18007cd0e  jnz     loc_18007CDBF
0x18007cd14  xor     edx, edx
0x18007cd16  lea     rcx, [rbp+4Fh+psz]
0x18007cd1a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18007cd1f  lea     rcx, [rbp+4Fh+psz]
0x18007cd23  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18007cd29  mov     ebx, eax
0x18007cd2b  test    eax, eax
0x18007cd2d  jns     short loc_18007CD40
0x18007cd2f  lea     rax, aFailedDmgetact_0; "Failed DmGetActiveUserSid"
0x18007cd36  mov     edx, 5317h
0x18007cd3b  jmp     loc_18007D231
0x18007cd40  mov     rcx, [rbp+4Fh+psz]; psz
0x18007cd44  call    cs:__imp_SysAllocString
0x18007cd4a  mov     qword ptr [rbp+4Fh+var_98+8], rax
0x18007cd4e  test    rax, rax
0x18007cd51  jnz     short loc_18007CD75
0x18007cd53  mov     edx, 5319h; void *
0x18007cd58  mov     ebx, 8007000Eh
0x18007cd5d  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18007cd64  mov     r9d, ebx; char *
0x18007cd67  mov     rcx, [rbp+57h]; this
0x18007cd6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cd70  jmp     loc_18007D24A
0x18007cd75  mov     [rbp+4Fh+var_88], 1
0x18007cd7c  mov     [rbp+4Fh+Block], r12
0x18007cd80  lea     rax, [rbp+4Fh+Block]
0x18007cd84  mov     [rbp+4Fh+var_70], rax
0x18007cd88  mov     [rbp+4Fh+var_68], r12
0x18007cd8c  mov     [rbp+4Fh+var_60], 1
0x18007cd90  lea     rdx, [rbp+4Fh+var_68]
0x18007cd94  lea     rcx, [rbp+4Fh+var_98]
0x18007cd98  call    GetResultsEnrollmentIdSidStateKey
0x18007cd9d  mov     ebx, eax
0x18007cd9f  lea     rcx, [rbp+4Fh+var_70]
0x18007cda3  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18007cda8  test    ebx, ebx
0x18007cdaa  js      short loc_18007CDF3
0x18007cdac  lea     r8, [rbp+4Fh+var_80]
0x18007cdb0  lea     rdx, [rbp+4Fh+arg_18]
0x18007cdb4  mov     rcx, [rbp+4Fh+Block]; hKey
0x18007cdb8  call    GetDocIdSubKeys
0x18007cdbd  jmp     short loc_18007CE03
0x18007cdbf  lea     rdx, aDevice_4; "device"
0x18007cdc6  mov     rcx, rdi
0x18007cdc9  call    cs:__imp__o__wcsicmp
0x18007cdcf  test    eax, eax
0x18007cdd1  jnz     loc_18007D220
0x18007cdd7  mov     rcx, rdi; psz
0x18007cdda  call    cs:__imp_SysAllocString
0x18007cde0  mov     qword ptr [rbp+4Fh+var_98+8], rax
0x18007cde4  test    rax, rax
0x18007cde7  jnz     short loc_18007CD7C
0x18007cde9  mov     edx, 531Fh
0x18007cdee  jmp     loc_18007CD58
0x18007cdf3  cmp     ebx, 80070002h
0x18007cdf9  jnz     short loc_18007CE03
0x18007cdfb  mov     [rbp+4Fh+var_80], r12
0x18007cdff  mov     [rbp+4Fh+arg_18], r12d
0x18007ce03  lea     rcx, [rbp+4Fh+Block]
0x18007ce07  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007ce0c  lea     rax, [rbp+4Fh+var_80]
0x18007ce10  mov     [rbp+4Fh+var_70], rax
0x18007ce14  lea     rax, [rbp+4Fh+arg_18]
0x18007ce18  mov     [rbp+4Fh+var_68], rax
0x18007ce1c  mov     [rbp+4Fh+var_60], 1
0x18007ce20  mov     [rsp+100h+var_D0], r12
0x18007ce25  mov     ebx, r12d
0x18007ce28  cmp     [rbp+4Fh+arg_18], r12d
0x18007ce2c  jbe     loc_18007CF8C
0x18007ce32  mov     [rbp+4Fh+var_A0], r12
0x18007ce36  lea     rax, [rbp+4Fh+var_A0]
0x18007ce3a  mov     [rbp+4Fh+var_58], rax
0x18007ce3e  mov     [rbp+4Fh+var_50], r12
0x18007ce42  mov     [rbp+4Fh+var_48], 1
0x18007ce46  mov     esi, ebx
0x18007ce48  xor     r9d, r9d; int
0x18007ce4b  lea     r8, [rbp+4Fh+var_50]; HKEY *
0x18007ce4f  mov     rdx, [rbp+4Fh+var_80]
0x18007ce53  mov     rdx, [rdx+rsi*8]; unsigned __int16 *
0x18007ce57  lea     rcx, [rbp+4Fh+var_98]; struct DeclaredConfigurationScopeData *
0x18007ce5b  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x18007ce60  mov     edi, eax
0x18007ce62  lea     rcx, [rbp+4Fh+var_58]
0x18007ce66  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18007ce6b  test    edi, edi
0x18007ce6d  js      loc_18007D1C6
0x18007ce73  lea     r9, [rsp+100h+var_D0]; unsigned __int16 **
0x18007ce78  lea     r8, aMostrecentvers; "MostRecentVersion"
0x18007ce7f  xor     edx, edx; unsigned __int16 *
0x18007ce81  mov     rcx, [rbp+4Fh+var_A0]; HKEY
0x18007ce85  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18007ce8a  lea     rax, [rsp+100h+var_D0]
0x18007ce8f  mov     [rbp+4Fh+var_30], rax
0x18007ce93  mov     [rbp+4Fh+var_28], 1
0x18007ce97  mov     [rbp+4Fh+var_A8], r12
0x18007ce9b  lea     rax, [rbp+4Fh+var_A8]
0x18007ce9f  mov     [rbp+4Fh+var_58], rax
0x18007cea3  mov     [rbp+4Fh+var_50], r12
0x18007cea7  mov     [rbp+4Fh+var_48], 1
0x18007ceab  mov     [rsp+100h+var_E0], 1
0x18007ceb3  lea     r9, [rbp+4Fh+var_50]
0x18007ceb7  mov     r8, [rsp+100h+var_D0]
0x18007cebc  mov     rdx, [rbp+4Fh+var_80]
0x18007cec0  mov     rdx, [rdx+rsi*8]
0x18007cec4  lea     rcx, [rbp+4Fh+var_98]
0x18007cec8  call    GetResultsEnrollmentIdSidStateDocIdVersionKey
0x18007cecd  mov     edi, eax
0x18007cecf  lea     rcx, [rbp+4Fh+var_58]
0x18007ced3  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18007ced8  test    edi, edi
0x18007ceda  js      loc_18007D186
0x18007cee0  mov     [rbp+4Fh+var_C0], r12d
0x18007cee4  lea     r9, [rbp+4Fh+var_C0]; unsigned int *
0x18007cee8  lea     r8, ValueName; "state"
0x18007ceef  xor     edx, edx; unsigned __int16 *
0x18007cef1  mov     rcx, [rbp+4Fh+var_A8]; HKEY
0x18007cef5  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18007cefa  mov     edi, eax
0x18007cefc  test    eax, eax
0x18007cefe  js      loc_18007D178
0x18007cf04  cmp     [rbp+4Fh+var_C0], 3
0x18007cf08  jz      short loc_18007CF10
0x18007cf0a  cmp     [rbp+4Fh+var_C0], 6Eh ; 'n'
0x18007cf0e  jnz     short loc_18007CF5B
0x18007cf10  mov     [rbp+4Fh+Block], r12
0x18007cf14  lea     r9, [rbp+4Fh+Block]; unsigned __int16 **
0x18007cf18  mov     r8, r15; unsigned __int16 *
0x18007cf1b  xor     edx, edx; unsigned __int16 *
0x18007cf1d  mov     rcx, [rbp+4Fh+var_A8]; HKEY
0x18007cf21  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18007cf26  mov     edi, eax
0x18007cf28  test    eax, eax
0x18007cf2a  js      loc_18007D16A
0x18007cf30  lea     rax, [rbp+4Fh+Block]
0x18007cf34  mov     [rbp+4Fh+var_40], rax
0x18007cf38  mov     [rbp+4Fh+var_38], 1
0x18007cf3c  mov     rdx, [rbp+4Fh+Block]
0x18007cf40  mov     rcx, r14
0x18007cf43  call    cs:__imp__o__wcsicmp
0x18007cf49  test    eax, eax
0x18007cf4b  jz      short loc_18007CFC4
0x18007cf4d  mov     [rbp+4Fh+var_38], r12b
0x18007cf51  mov     rcx, [rbp+4Fh+Block]; Block
0x18007cf55  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007cf5a  nop
0x18007cf5b  lea     rcx, [rbp+4Fh+var_A8]
0x18007cf5f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007cf64  nop
0x18007cf65  mov     [rbp+4Fh+var_28], r12b
0x18007cf69  mov     rcx, [rsp+100h+var_D0]; Block
0x18007cf6e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007cf73  mov     [rsp+100h+var_D0], r12
0x18007cf78  lea     rcx, [rbp+4Fh+var_A0]
0x18007cf7c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007cf81  inc     ebx
0x18007cf83  cmp     ebx, [rbp+4Fh+arg_18]
0x18007cf86  jb      loc_18007CE32
0x18007cf8c  mov     rcx, [rbp+57h]; this
0x18007cf90  lea     rax, aFailedToFindPe; "Failed to find pending doc that has req"...
0x18007cf97  mov     qword ptr [rsp+100h+var_E0], rax; int
0x18007cf9c  mov     ebx, 80004005h
0x18007cfa1  mov     r9d, ebx; char *
0x18007cfa4  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18007cfab  mov     edx, 53C8h; void *
0x18007cfb0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007cfb5  nop
0x18007cfb6  lea     rcx, [rbp+4Fh+var_70]
0x18007cfba  call    wil__details__ScopeExitFn__lambda_f984c43bf46297e92d14b60ba967b075_____operator__
0x18007cfbf  jmp     loc_18007D24A
0x18007cfc4  mov     r9d, r12d
0x18007cfc7  cmp     [rbp+4Fh+arg_20], 1
0x18007cfcb  setnz   r9b
0x18007cfcf  add     r9d, 3Ch ; '<'; unsigned int
0x18007cfd3  lea     r8, ValueName; "state"
0x18007cfda  xor     edx, edx; unsigned __int16 *
0x18007cfdc  mov     rcx, [rbp+4Fh+var_A8]; HKEY
0x18007cfe0  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18007cfe5  mov     edi, eax
0x18007cfe7  test    eax, eax
0x18007cfe9  jns     short loc_18007D022
0x18007cfeb  mov     rcx, [rbp+57h]; this
0x18007cfef  lea     rax, aFailedToUpdate_3; "Failed to update doc result status"
0x18007cff6  mov     qword ptr [rsp+100h+var_E0], rax; int
0x18007cffb  mov     r9d, edi; char *
0x18007cffe  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18007d005  mov     edx, 5388h; void *
0x18007d00a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007d00f  nop
0x18007d010  mov     rcx, [rbp+4Fh+Block]; Block
0x18007d014  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007d019  mov     [rbp+4Fh+Block], r12
0x18007d01d  jmp     loc_18007D1AB
0x18007d022  cmp     [rbp+4Fh+arg_20], 1
0x18007d026  jnz     loc_18007D102
0x18007d02c  mov     r8, [rsp+100h+var_D0]; unsigned __int16 *
0x18007d031  mov     rdx, [rbp+4Fh+var_80]
0x18007d035  mov     rdx, [rdx+rsi*8]; unsigned __int16 *
0x18007d039  lea     rcx, [rbp+4Fh+var_98]; struct DeclaredConfigurationScopeData *
0x18007d03d  call    ?UpdateOrchestration@@YAJPEAUDeclaredConfigurationScopeData@@PEBG1@Z; UpdateOrchestration(DeclaredConfigurationScopeData *,ushort const *,ushort const *)
0x18007d042  test    eax, eax
0x18007d044  jnz     loc_18007D102
0x18007d04a  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18007d04f  lea     r14, word_180142E98
0x18007d056  mov     r9, r14; unsigned __int16 *
0x18007d059  lea     r8, aResourceInstal; "Resource installed, reapplying pending "...
0x18007d060  lea     rsi, aDeclaredconfig_231; "DeclaredConfigurationStore_MarkDocCompl"...
0x18007d067  mov     rdx, rsi; unsigned __int16 *
0x18007d06a  mov     rcx, rax; this
0x18007d06d  call    ?LogOrchestratorGenericInfo@CDeclaredConfigurationLogger@@QEAAXPEBG00@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(ushort const *,ushort const *,ushort const *)
0x18007d072  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x18007d079  jz      short loc_18007D096
0x18007d07b  mov     [rsp+100h+var_E0], r12d
0x18007d080  lea     r9, aResourceInstal; "Resource installed, reapplying pending "...
0x18007d087  mov     r8, rsi
0x18007d08a  lea     rdx, OrchestratorGenericInformation
0x18007d091  call    McTemplateU0zzd_EventWriteTransfer
0x18007d096  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl(void)'::`2'::impl
0x18007d09d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(void)
0x18007d0a2  test    al, al
0x18007d0a4  jz      short loc_18007D0B3
0x18007d0a6  mov     ecx, 2Bh ; '+'
0x18007d0ab  call    cs:__imp_DMOrchestratorProcessDocsBasedOnState
  ... truncated ...
```
