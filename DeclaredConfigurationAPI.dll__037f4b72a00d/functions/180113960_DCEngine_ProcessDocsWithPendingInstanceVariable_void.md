# DCEngine::ProcessDocsWithPendingInstanceVariable(void)

- ea: `0x180113960`
- end: `0x1801142bb`
- name: `?ProcessDocsWithPendingInstanceVariable@DCEngine@@EEAAJXZ`
- size: `2395`
- prototype: `__int64 __fastcall(DCEngine *__hidden this)`
- caller_count: `0`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x18000e310`
- `0x18000e32c`
- `0x1800117dc`
- `0x180011fe0`
- `0x180012dc4`
- `0x180013d4c`
- `0x180018cc4`
- `0x180019d38`
- `0x18001a60c`
- `0x18001c08c`
- `0x18001c32c`
- `0x18001ce5c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18001d37c`
- `0x18004d158`
- `0x180056b5c`
- `0x180056bcc`
- `0x180058b08`
- `0x180058b3c`
- `0x1800641a0`
- `0x1800725e0`
- `0x180076c10`
- `0x180098e10`
- `0x1800a04fc`
- `0x1800aab60`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x18010a260`
- `0x18010abd8`
- `0x18010e580`
- `0x180112af4`
- `0x180113960`
- `0x180139010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180113b09`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180113b98`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180113b09`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180113b98`
- `OLEAUT32!__imp_SysAllocString` at `0x180113ae1`
- `OLEAUT32!__imp_SysAllocString` at `0x180113b66`
- `OLEAUT32!__imp_SysAllocString` at `0x180113bb3`
- `OLEAUT32!__imp_SysAllocString` at `0x180113ae1`
- `OLEAUT32!__imp_SysAllocString` at `0x180113b66`
- `OLEAUT32!__imp_SysAllocString` at `0x180113bb3`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180113b24`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180113b24`

## string_xrefs

- `0x1801140b8`: `DeclaredConfigurationStore_GetRefreshFlag`
- `0x180113b46`: `DmGetActiveUserSid`
- `0x1801140f6`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x180114151`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x1801141c0`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x1801141f1`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x18011424c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x180113de3`: `ProcessDocsWithPendingInstanceVariable:DeclaredConfigurationStore_GetPersistedDocument failed, continue with next doc`
- `0x180113d0e`: `ProcessDocsWithPendingInstanceVariable:DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey failed, continue with next doc`
- `0x180113e98`: `ProcessDocsWithPendingInstanceVariable:DeclaredConfigurationStore_CheckIfAllInstanceDataPresent failed, continue with next doc`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall DCEngine::ProcessDocsWithPendingInstanceVariable(DCEngine *this)
{
  __int64 v2; // rcx
  int AllRequests; // edi
  char v4; // r15
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  const unsigned __int16 *v7; // rsi
  int v8; // eax
  int v9; // eax
  int v10; // ecx
  OrchestratorDBManager *v11; // rcx
  int Request; // eax
  const OLECHAR *v13; // rcx
  OLECHAR **v14; // rcx
  CDeclaredConfigurationLogger *Logger; // rax
  const unsigned __int16 *v16; // r9
  OLECHAR **v17; // rcx
  const OLECHAR *v18; // rcx
  unsigned __int16 **v19; // rdx
  __int64 v20; // r8
  OLECHAR **v21; // rdx
  __int64 v22; // r8
  _QWORD *v23; // rdx
  __int64 v24; // r8
  const unsigned __int16 *v25; // rdx
  _QWORD *v26; // rdx
  unsigned __int16 **v27; // rcx
  OLECHAR **v28; // rax
  OLECHAR **v29; // r9
  int v30; // ecx
  const wchar_t *v31; // r8
  _QWORD *v32; // r8
  _QWORD *v33; // rdx
  unsigned __int16 **v34; // rcx
  OLECHAR **v35; // rax
  OLECHAR **v36; // r9
  __int64 v37; // rdx
  _QWORD *v38; // rdx
  unsigned __int16 **v39; // rcx
  OLECHAR **v40; // rax
  OLECHAR **v41; // r9
  const unsigned __int16 *v42; // rdx
  int v43; // eax
  int v44; // eax
  int v45; // ecx
  int GuidFromEnrollmentId; // eax
  OrchestratorDCInfo *v47; // rax
  _QWORD *v48; // rdx
  unsigned __int16 **v49; // rcx
  OLECHAR **v50; // rax
  OLECHAR **v51; // r9
  int v52; // ecx
  __int64 v53; // rdx
  __int64 v54; // rcx
  int v56; // [rsp+20h] [rbp-E0h]
  bool v57; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR *v58; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v59; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v60; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v61; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR *v62[2]; // [rsp+68h] [rbp-98h] BYREF
  int v63; // [rsp+78h] [rbp-88h]
  int v64; // [rsp+7Ch] [rbp-84h]
  int v65; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v66; // [rsp+84h] [rbp-7Ch] BYREF
  _BYTE v67[8]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v68[16]; // [rsp+90h] [rbp-70h] BYREF
  HKEY v69[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v70; // [rsp+B0h] [rbp-50h]
  void *v71[2]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR *psz[3]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v73; // [rsp+E8h] [rbp-18h]
  OLECHAR *v74[3]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v75; // [rsp+108h] [rbp+8h]
  unsigned __int16 *v76[3]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v77; // [rsp+128h] [rbp+28h]
  _QWORD v78[3]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v79; // [rsp+148h] [rbp+48h]
  unsigned __int16 *v80[4]; // [rsp+170h] [rbp+70h] BYREF
  char *v81; // [rsp+190h] [rbp+90h] BYREF
  char *v82; // [rsp+1D0h] [rbp+D0h] BYREF
  int v83; // [rsp+414h] [rbp+314h]
  unsigned __int16 v84[264]; // [rsp+460h] [rbp+360h] BYREF
  unsigned __int16 v85[264]; // [rsp+670h] [rbp+570h] BYREF
  unsigned __int16 v86[264]; // [rsp+880h] [rbp+780h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+AE8h] [rbp+9E8h]

  std::list<std::wstring>::list<std::wstring>(v71);
  AllRequests = OrchestratorDBManager::GetAllRequests(v2, v71);
  v4 = 0;
  OrchestratorDCInfo::OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  v66 = 63;
  v65 = 12;
  v5 = v71[0];
  v6 = *(_QWORD **)v71[0];
  while ( 1 )
  {
    if ( v6 == v5 )
    {
      if ( v4 )
        AllRequests = (*(__int64 (__fastcall **)(DCEngine *))(*(_QWORD *)this + 56LL))(this);
      goto LABEL_134;
    }
    v7 = (const unsigned __int16 *)(v6 + 2);
    if ( v6[5] > 7u )
      v7 = *(const unsigned __int16 **)v7;
    v8 = StringCchPrintfW(v85, 0x104u, L"Global\\%s", v7);
    AllRequests = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFE2,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
        (const char *)(unsigned int)v8,
        v56);
      goto LABEL_134;
    }
    v60 = 0;
    v9 = _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
           &v60,
           v85);
    AllRequests = v9;
    if ( v9 < 0 )
      break;
    v61 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v60,
      v68,
      &v61,
      30000);
    if ( v61 )
    {
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v68);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v60);
      goto LABEL_111;
    }
    Request = OrchestratorDBManager::GetRequest(
                v11,
                v7,
                (struct OrchestratorDCInfo *)psz,
                (enum StateMachineTypeTag *)&v66,
                (enum DMOrchestratorState *)&v61,
                (enum DCLifecycleNotificationType *)&v65);
    AllRequests = Request;
    if ( Request < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFF3,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
        (const char *)(unsigned int)Request,
        v56);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v68);
      goto LABEL_130;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v68);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v60);
    if ( v65 == 1 )
    {
      v57 = 0;
      *(_OWORD *)v62 = 0;
      v63 = 0;
      v64 = 63;
      v58 = 0;
      v13 = (const OLECHAR *)psz;
      if ( v73 > 7 )
        v13 = psz[0];
      v62[0] = SysAllocString(v13);
      if ( !v62[0] )
      {
        v53 = 4096;
LABEL_125:
        AllRequests = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v53,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
          (const char *)0x8007000ELL,
          v56);
LABEL_126:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
        DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v62);
        goto LABEL_134;
      }
      v14 = v74;
      if ( v75 > 7 )
        v14 = (OLECHAR **)v74[0];
      if ( (unsigned int)_o__wcsicmp(v14, L"user") )
      {
        v17 = v74;
        if ( v75 > 7 )
          v17 = (OLECHAR **)v74[0];
        if ( (unsigned int)_o__wcsicmp(v17, L"device") )
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v62);
          AllRequests = -2147024809;
          goto LABEL_134;
        }
        v18 = (const OLECHAR *)v74;
        if ( v75 > 7 )
          v18 = v74[0];
        v62[1] = SysAllocString(v18);
        if ( !v62[1] )
        {
          v53 = 4116;
          goto LABEL_125;
        }
      }
      else
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v58,
          0);
        AllRequests = DmGetActiveUserSid(&v58);
        if ( AllRequests < 0 )
        {
          Logger = CDeclaredConfigurationLogger::GetLogger();
          v16 = (const unsigned __int16 *)psz;
          if ( v73 > 7 )
            v16 = psz[0];
          CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
            Logger,
            L"DCEngine::ProcessDocsWithPendingInstanceVariable",
            L"DmGetActiveUserSid",
            v16,
            AllRequests);
          goto LABEL_110;
        }
        v62[1] = SysAllocString(v58);
        if ( !v62[1] )
        {
          v53 = 4110;
          goto LABEL_125;
        }
        v63 = 1;
      }
      if ( !v62[0] )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
        DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v62);
        AllRequests = -2147024882;
        goto LABEL_134;
      }
      DCDocument::DCDocument((DCDocument *)v80);
      v19 = v76;
      if ( v77 > 7 )
        v19 = (unsigned __int16 **)v76[0];
      v20 = -1;
      do
        ++v20;
      while ( *((_WORD *)v19 + v20) );
      std::wstring::_Assign<unsigned short>((char **)v80, v19, (char *)v20);
      v21 = v74;
      if ( v75 > 7 )
        v21 = (OLECHAR **)v74[0];
      v22 = -1;
      do
        ++v22;
      while ( *((_WORD *)v21 + v22) );
      std::wstring::_Assign<unsigned short>(&v81, v21, (char *)v22);
      v23 = v78;
      if ( v79 > 7 )
        v23 = (_QWORD *)v78[0];
      v24 = -1;
      do
        ++v24;
      while ( *((_WORD *)v23 + v24) );
      std::wstring::_Assign<unsigned short>(&v82, v23, (char *)v24);
      v59 = 0;
      v69[0] = (HKEY)&v59;
      v69[1] = 0;
      v70 = 1;
      v25 = (const unsigned __int16 *)v76;
      if ( v77 > 7 )
        v25 = v76[0];
      AllRequests = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                      (struct DeclaredConfigurationScopeData *)v62,
                      v25,
                      &v69[1],
                      0);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(v69);
      if ( AllRequests < 0 )
      {
        v84[0] = 0;
        v26 = v78;
        if ( v79 > 7 )
          v26 = (_QWORD *)v78[0];
        v27 = v76;
        if ( v77 > 7 )
          v27 = (unsigned __int16 **)v76[0];
        v28 = v74;
        if ( v75 > 7 )
          v28 = (OLECHAR **)v74[0];
        v29 = psz;
        if ( v73 > 7 )
          v29 = (OLECHAR **)psz[0];
        if ( StringCchPrintfW(v84, 0x104u, L"enrollmentId: %s, context:%s, docId:%s, docVersion:%s", v29, v28, v27, v26) >= 0
          && byte_180189FC1 < 0 )
        {
          v31 = L"ProcessDocsWithPendingInstanceVariable:DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey failed"
                 ", continue with next doc";
          goto LABEL_56;
        }
        goto LABEL_109;
      }
      v32 = v78;
      if ( v79 > 7 )
        v32 = (_QWORD *)v78[0];
      AllRequests = DeclaredConfigurationStore_GetPersistedDocument(
                      (struct DeclaredConfigurationScopeData *)v62,
                      v59,
                      (__int64)v32,
                      0,
                      (__int64)v80,
                      2);
      if ( AllRequests >= 0 )
      {
        if ( (v83 & 1) == 0 && (v83 & 2) == 0 )
          goto LABEL_109;
        AllRequests = DeclaredConfigurationStore_CheckIfAllInstanceDataPresent(
                        (struct DeclaredConfigurationScopeData *)v62,
                        (struct DCDocument *)v80,
                        &v57);
        if ( AllRequests >= 0 )
        {
          if ( v57 )
            goto LABEL_91;
          v61 = 0;
          LOBYTE(v37) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::GetImpl'::`2'::impl,
            v37);
          v42 = (const unsigned __int16 *)v80;
          if ( v80[3] > (unsigned __int16 *)7 )
            v42 = v80[0];
          AllRequests = DeclaredConfigurationStore_GetRefreshFlag(v62[0], v42, &v61);
          if ( (int)(AllRequests + 0x80000000) >= 0 && AllRequests != -2147024894 )
          {
            if ( byte_180189FC1 < 0 )
              McTemplateU0zzd_EventWriteTransfer(
                0x80000000,
                (unsigned int)OrchestratorGenericFailure,
                (unsigned int)L"ProcessDocsWithPendingInstanceVariable::",
                (unsigned int)L"DeclaredConfigurationStore_GetRefreshFlag",
                AllRequests);
            goto LABEL_115;
          }
          if ( v61 )
          {
LABEL_91:
            v43 = StringCchPrintfW(v86, 0x104u, L"Global\\%s", v7);
            AllRequests = v43;
            if ( v43 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x106F,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
                (const char *)(unsigned int)v43,
                v56);
              goto LABEL_115;
            }
            v60 = 0;
            v44 = _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                    &v60,
                    v86);
            AllRequests = v44;
            if ( v44 < 0 )
            {
              if ( byte_180189FC1 < 0 )
                McTemplateU0zzd_EventWriteTransfer(
                  v45,
                  (unsigned int)OrchestratorGenericFailure,
                  (unsigned int)L"ProcessDocsWithPendingInstanceVariable:PerOrchestratorRequestMutex",
                  (unsigned int)L"Creation failed",
                  v44);
LABEL_119:
              __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v60);
LABEL_115:
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v59);
              DCDocument::~DCDocument((DCDocument *)v80);
              goto LABEL_126;
            }
            v61 = 0;
            _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
              &v60,
              v67,
              &v61,
              30000);
            if ( !v61 )
            {
              *(_OWORD *)v69 = 0;
              GuidFromEnrollmentId = GetGuidFromEnrollmentId(v7, (struct _GUID *)v69);
              AllRequests = GuidFromEnrollmentId;
              if ( GuidFromEnrollmentId < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1080,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
                  (const char *)(unsigned int)GuidFromEnrollmentId,
                  v56);
                __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v67);
                goto LABEL_119;
              }
              v47 = OrchestratorDCInfo::OrchestratorDCInfo(
                      (OrchestratorDCInfo *)v84,
                      (const struct OrchestratorDCInfo *)psz);
              AllRequests = DCEngine::AddDocToQueue(this, v47, v69, v66);
              if ( AllRequests >= 0 )
              {
                v4 = 1;
              }
              else
              {
                v84[0] = 0;
                v48 = v78;
                if ( v79 > 7 )
                  v48 = (_QWORD *)v78[0];
                v49 = v76;
                if ( v77 > 7 )
                  v49 = (unsigned __int16 **)v76[0];
                v50 = v74;
                if ( v75 > 7 )
                  v50 = (OLECHAR **)v74[0];
                v51 = psz;
                if ( v73 > 7 )
                  v51 = (OLECHAR **)psz[0];
                if ( StringCchPrintfW(
                       v84,
                       0x104u,
                       L"enrollmentId: %s, context:%s, docId:%s, docVersion:%s",
                       v51,
                       v50,
                       v49,
                       v48) >= 0
                  && byte_180189FC1 < 0 )
                {
                  McTemplateU0zzd_EventWriteTransfer(
                    v52,
                    (unsigned int)OrchestratorGenericFailure,
                    (unsigned int)L"ProcessDocsWithPendingInstanceVariable:AddDocToQueue failed, continue with next doc",
                    (unsigned int)v84,
                    AllRequests);
                }
              }
            }
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v67);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v60);
          }
          goto LABEL_109;
        }
        v84[0] = 0;
        v38 = v78;
        if ( v79 > 7 )
          v38 = (_QWORD *)v78[0];
        v39 = v76;
        if ( v77 > 7 )
          v39 = (unsigned __int16 **)v76[0];
        v40 = v74;
        if ( v75 > 7 )
          v40 = (OLECHAR **)v74[0];
        v41 = psz;
        if ( v73 > 7 )
          v41 = (OLECHAR **)psz[0];
        if ( StringCchPrintfW(v84, 0x104u, L"enrollmentId: %s, context:%s, docId:%s, docVersion:%s", v41, v40, v39, v38) < 0
          || byte_180189FC1 >= 0 )
        {
LABEL_109:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v59);
          DCDocument::~DCDocument((DCDocument *)v80);
LABEL_110:
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v62);
          goto LABEL_111;
        }
        v31 = L"ProcessDocsWithPendingInstanceVariable:DeclaredConfigurationStore_CheckIfAllInstanceDataPresent failed, co"
               "ntinue with next doc";
      }
      else
      {
        v84[0] = 0;
        v33 = v78;
        if ( v79 > 7 )
          v33 = (_QWORD *)v78[0];
        v34 = v76;
        if ( v77 > 7 )
          v34 = (unsigned __int16 **)v76[0];
        v35 = v74;
        if ( v75 > 7 )
          v35 = (OLECHAR **)v74[0];
        v36 = psz;
        if ( v73 > 7 )
          v36 = (OLECHAR **)psz[0];
        if ( StringCchPrintfW(v84, 0x104u, L"enrollmentId: %s, context:%s, docId:%s, docVersion:%s", v36, v35, v34, v33) < 0
          || byte_180189FC1 >= 0 )
        {
          goto LABEL_109;
        }
        v31 = L"ProcessDocsWithPendingInstanceVariable:DeclaredConfigurationStore_GetPersistedDocument failed, continue with next doc";
      }
LABEL_56:
      McTemplateU0zzd_EventWriteTransfer(
        v30,
        (unsigned int)OrchestratorGenericFailure,
        (_DWORD)v31,
        (unsigned int)v84,
        AllRequests);
      goto LABEL_109;
    }
LABEL_111:
    v6 = (_QWORD *)*v6;
    v5 = v71[0];
  }
  if ( byte_180189FC1 < 0 )
    McTemplateU0zzd_EventWriteTransfer(
      v10,
      (unsigned int)OrchestratorGenericFailure,
      (unsigned int)L"ProcessDocsWithPendingInstanceVariable:PerOrchestratorRequestMutex",
      (unsigned int)L"Creation failed",
      v9);
LABEL_130:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v60);
LABEL_134:
  OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
    v54,
    v71[0]);
  std::_Deallocate<16>(v71[0], 0x30u);
  return (unsigned int)AllRequests;
}

```

## disassembly

```asm
0x180113960  push    rbp
0x180113962  push    rbx
0x180113963  push    rsi
0x180113964  push    rdi
0x180113965  push    r12
0x180113967  push    r13
0x180113969  push    r14
0x18011396b  push    r15
0x18011396d  lea     rbp, [rsp-9A8h]
0x180113975  sub     rsp, 0AA8h
0x18011397c  mov     rax, cs:__security_cookie
0x180113983  xor     rax, rsp
0x180113986  mov     [rbp+9E0h+var_50], rax
0x18011398d  mov     r14, rcx
0x180113990  lea     rcx, [rbp+9E0h+var_A20]
0x180113994  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x180113999  nop
0x18011399a  lea     rdx, [rbp+9E0h+var_A20]
0x18011399e  call    ?GetAllRequests@OrchestratorDBManager@@QEAAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; OrchestratorDBManager::GetAllRequests(std::list<std::wstring> &)
0x1801139a3  mov     edi, eax
0x1801139a5  xor     r12d, r12d
0x1801139a8  mov     r15b, r12b
0x1801139ab  lea     rcx, [rbp+9E0h+psz]; this
0x1801139af  call    ??0OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::OrchestratorDCInfo(void)
0x1801139b4  nop
0x1801139b5  mov     [rbp+9E0h+var_A5C], 3Fh ; '?'
0x1801139bc  mov     [rbp+9E0h+var_A60], 0Ch
0x1801139c3  mov     rax, [rbp+9E0h+var_A20]
0x1801139c7  mov     rbx, [rax]
0x1801139ca  lea     r13d, [r12+7]
0x1801139cf  cmp     rbx, rax
0x1801139d2  jz      loc_18011425F
0x1801139d8  lea     rsi, [rbx+10h]
0x1801139dc  cmp     [rbx+28h], r13
0x1801139e0  jbe     short loc_1801139E5
0x1801139e2  mov     rsi, [rsi]
0x1801139e5  mov     r9, rsi
0x1801139e8  lea     r8, aGlobalS; "Global\\%s"
0x1801139ef  mov     edx, 104h; unsigned __int64
0x1801139f4  lea     rcx, [rbp+9E0h+var_470]; unsigned __int16 *
0x1801139fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180113a00  mov     edi, eax
0x180113a02  test    eax, eax
0x180113a04  js      loc_180114242
0x180113a0a  mov     [rsp+0AE0h+var_A88], r12
0x180113a0f  lea     rdx, [rbp+9E0h+var_470]
0x180113a16  lea     rcx, [rsp+0AE0h+var_A88]
0x180113a1b  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180113a20  mov     edi, eax
0x180113a22  test    eax, eax
0x180113a24  js      loc_18011420E
0x180113a2a  mov     [rsp+0AE0h+var_A80], r12d
0x180113a2f  mov     r9d, 7530h
0x180113a35  lea     r8, [rsp+0AE0h+var_A80]
0x180113a3a  lea     rdx, [rbp+9E0h+var_A50]
0x180113a3e  lea     rcx, [rsp+0AE0h+var_A88]
0x180113a43  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180113a48  nop
0x180113a49  cmp     [rsp+0AE0h+var_A80], r12d
0x180113a4e  jz      short loc_180113A69
0x180113a50  lea     rcx, [rbp+9E0h+var_A50]
0x180113a54  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180113a59  nop
0x180113a5a  lea     rcx, [rsp+0AE0h+var_A88]
0x180113a5f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180113a64  jmp     loc_180114095
0x180113a69  lea     rax, [rbp+9E0h+var_A60]
0x180113a6d  mov     [rsp+0AE0h+var_AB8], rax; enum DCLifecycleNotificationType *
0x180113a72  lea     rax, [rsp+0AE0h+var_A80]
0x180113a77  mov     [rsp+0AE0h+var_AC0], rax; int
0x180113a7c  lea     r9, [rbp+9E0h+var_A5C]; enum StateMachineTypeTag *
0x180113a80  lea     r8, [rbp+9E0h+psz]; struct OrchestratorDCInfo *
0x180113a84  mov     rdx, rsi; unsigned __int16 *
0x180113a87  call    ?GetRequest@OrchestratorDBManager@@QEAAJPEBGPEAUOrchestratorDCInfo@@PEAW4StateMachineTypeTag@@PEAW4DMOrchestratorState@@PEAW4DCLifecycleNotificationType@@@Z; OrchestratorDBManager::GetRequest(ushort const *,OrchestratorDCInfo *,StateMachineTypeTag *,DMOrchestratorState *,DCLifecycleNotificationType *)
0x180113a8c  mov     edi, eax
0x180113a8e  test    eax, eax
0x180113a90  js      loc_1801141E7
0x180113a96  lea     rcx, [rbp+9E0h+var_A50]
0x180113a9a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180113a9f  nop
0x180113aa0  lea     rcx, [rsp+0AE0h+var_A88]
0x180113aa5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180113aaa  cmp     [rbp+9E0h+var_A60], 1
0x180113aae  jnz     loc_180114095
0x180113ab4  mov     [rsp+0AE0h+var_AA0], r12b
0x180113ab9  xorps   xmm0, xmm0
0x180113abc  movdqu  xmmword ptr [rsp+0AE0h+var_A78], xmm0
0x180113ac2  mov     [rsp+0AE0h+var_A68], r12d
0x180113ac7  mov     [rsp+0AE0h+var_A64], 3Fh ; '?'
0x180113acf  mov     [rsp+0AE0h+var_A98], r12
0x180113ad4  lea     rcx, [rbp+9E0h+psz]
0x180113ad8  cmp     [rbp+9E0h+var_9F8], r13
0x180113adc  cmova   rcx, [rbp+9E0h+psz]; psz
0x180113ae1  call    cs:__imp_SysAllocString
0x180113ae7  mov     [rsp+0AE0h+var_A78], rax
0x180113aec  test    rax, rax
0x180113aef  jz      loc_1801141AC
0x180113af5  lea     rcx, [rbp+9E0h+var_9F0]
0x180113af9  cmp     [rbp+9E0h+var_9D8], r13
0x180113afd  cmova   rcx, [rbp+9E0h+var_9F0]
0x180113b02  lea     rdx, aUser_0; "user"
0x180113b09  call    cs:__imp__o__wcsicmp
0x180113b0f  test    eax, eax
0x180113b11  jnz     short loc_180113B84
0x180113b13  xor     edx, edx
0x180113b15  lea     rcx, [rsp+0AE0h+var_A98]
0x180113b1a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180113b1f  lea     rcx, [rsp+0AE0h+var_A98]
0x180113b24  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180113b2a  mov     edi, eax
0x180113b2c  test    eax, eax
0x180113b2e  jns     short loc_180113B61
0x180113b30  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180113b35  lea     r9, [rbp+9E0h+psz]
0x180113b39  cmp     [rbp+9E0h+var_9F8], r13
0x180113b3d  cmova   r9, [rbp+9E0h+psz]; unsigned __int16 *
0x180113b42  mov     dword ptr [rsp+0AE0h+var_AC0], edi; int
0x180113b46  lea     r8, aDmgetactiveuse_1; "DmGetActiveUserSid"
0x180113b4d  lea     rdx, aDcengineProces; "DCEngine::ProcessDocsWithPendingInstanc"...
0x180113b54  mov     rcx, rax; this
0x180113b57  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180113b5c  jmp     loc_180114080
0x180113b61  mov     rcx, [rsp+0AE0h+var_A98]; psz
0x180113b66  call    cs:__imp_SysAllocString
0x180113b6c  mov     [rsp+0AE0h+var_A78+8], rax
0x180113b71  test    rax, rax
0x180113b74  jz      loc_1801140A1
0x180113b7a  mov     [rsp+0AE0h+var_A68], 1
0x180113b82  jmp     short loc_180113BC7
0x180113b84  lea     rcx, [rbp+9E0h+var_9F0]
0x180113b88  cmp     [rbp+9E0h+var_9D8], r13
0x180113b8c  cmova   rcx, [rbp+9E0h+var_9F0]
0x180113b91  lea     rdx, aDevice_4; "device"
0x180113b98  call    cs:__imp__o__wcsicmp
0x180113b9e  test    eax, eax
0x180113ba0  jnz     loc_18011418D
0x180113ba6  lea     rcx, [rbp+9E0h+var_9F0]
0x180113baa  cmp     [rbp+9E0h+var_9D8], r13
0x180113bae  cmova   rcx, [rbp+9E0h+var_9F0]; psz
0x180113bb3  call    cs:__imp_SysAllocString
0x180113bb9  mov     [rsp+0AE0h+var_A78+8], rax
0x180113bbe  test    rax, rax
0x180113bc1  jz      loc_180114186
0x180113bc7  cmp     [rsp+0AE0h+var_A78], r12
0x180113bcc  jz      loc_180114167
0x180113bd2  lea     rcx, [rbp+9E0h+var_970]; this
0x180113bd6  call    ??0DCDocument@@QEAA@XZ; DCDocument::DCDocument(void)
0x180113bdb  nop
0x180113bdc  lea     rdx, [rbp+9E0h+var_9D0]
0x180113be0  cmp     [rbp+9E0h+var_9B8], r13
0x180113be4  cmova   rdx, [rbp+9E0h+var_9D0]
0x180113be9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180113bed  mov     r8, rdi
0x180113bf0  inc     r8
0x180113bf3  cmp     [rdx+r8*2], r12w
0x180113bf8  jnz     short loc_180113BF0
0x180113bfa  lea     rcx, [rbp+9E0h+var_970]
0x180113bfe  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180113c03  lea     rdx, [rbp+9E0h+var_9F0]
0x180113c07  cmp     [rbp+9E0h+var_9D8], r13
0x180113c0b  cmova   rdx, [rbp+9E0h+var_9F0]
0x180113c10  mov     r8, rdi
0x180113c13  inc     r8
0x180113c16  cmp     [rdx+r8*2], r12w
0x180113c1b  jnz     short loc_180113C13
0x180113c1d  lea     rcx, [rbp+9E0h+var_950]
0x180113c24  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180113c29  lea     rdx, [rbp+9E0h+var_9B0]
0x180113c2d  cmp     [rbp+9E0h+var_998], r13
0x180113c31  cmova   rdx, [rbp+9E0h+var_9B0]
0x180113c36  mov     r8, rdi
0x180113c39  inc     r8
0x180113c3c  cmp     [rdx+r8*2], r12w
0x180113c41  jnz     short loc_180113C39
0x180113c43  lea     rcx, [rbp+9E0h+var_910]
0x180113c4a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180113c4f  mov     [rsp+0AE0h+var_A90], r12
0x180113c54  lea     rax, [rsp+0AE0h+var_A90]
0x180113c59  mov     [rbp+9E0h+var_A40], rax
0x180113c5d  mov     [rbp+9E0h+var_A40+8], r12
0x180113c61  mov     [rbp+9E0h+var_A30], 1
0x180113c65  lea     rdx, [rbp+9E0h+var_9D0]
0x180113c69  cmp     [rbp+9E0h+var_9B8], r13
0x180113c6d  cmova   rdx, [rbp+9E0h+var_9D0]; unsigned __int16 *
0x180113c72  xor     r9d, r9d; int
0x180113c75  lea     r8, [rbp+9E0h+var_A40+8]; HKEY *
0x180113c79  lea     rcx, [rsp+0AE0h+var_A78]; struct DeclaredConfigurationScopeData *
0x180113c7e  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x180113c83  mov     edi, eax
0x180113c85  lea     rcx, [rbp+9E0h+var_A40]
0x180113c89  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180113c8e  test    edi, edi
0x180113c90  jns     loc_180113D31
0x180113c96  mov     [rbp+9E0h+var_680], r12w
0x180113c9e  lea     rdx, [rbp+9E0h+var_9B0]
0x180113ca2  cmp     [rbp+9E0h+var_998], r13
0x180113ca6  cmova   rdx, [rbp+9E0h+var_9B0]
0x180113cab  lea     rcx, [rbp+9E0h+var_9D0]
0x180113caf  cmp     [rbp+9E0h+var_9B8], r13
0x180113cb3  cmova   rcx, [rbp+9E0h+var_9D0]
0x180113cb8  lea     rax, [rbp+9E0h+var_9F0]
0x180113cbc  cmp     [rbp+9E0h+var_9D8], r13
0x180113cc0  cmova   rax, [rbp+9E0h+var_9F0]
0x180113cc5  lea     r9, [rbp+9E0h+psz]
0x180113cc9  cmp     [rbp+9E0h+var_9F8], r13
0x180113ccd  cmova   r9, [rbp+9E0h+psz]
0x180113cd2  mov     [rsp+0AE0h+var_AB0], rdx
0x180113cd7  mov     [rsp+0AE0h+var_AB8], rcx
0x180113cdc  mov     [rsp+0AE0h+var_AC0], rax
0x180113ce1  lea     r8, aEnrollmentidSC; "enrollmentId: %s, context:%s, docId:%s,"...
0x180113ce8  mov     edx, 104h; unsigned __int64
0x180113ced  lea     rcx, [rbp+9E0h+var_680]; unsigned __int16 *
0x180113cf4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180113cf9  test    eax, eax
0x180113cfb  js      loc_18011406B
0x180113d01  cmp     cs:byte_180189FC1, r12b
0x180113d08  jge     loc_18011406B
0x180113d0e  lea     r8, aProcessdocswit_2; "ProcessDocsWithPendingInstanceVariable:"...
0x180113d15  mov     dword ptr [rsp+0AE0h+var_AC0], edi
0x180113d19  lea     r9, [rbp+9E0h+var_680]
0x180113d20  lea     rdx, OrchestratorGenericFailure
0x180113d27  call    McTemplateU0zzd_EventWriteTransfer
0x180113d2c  jmp     loc_18011406B
0x180113d31  lea     r8, [rbp+9E0h+var_9B0]
0x180113d35  cmp     [rbp+9E0h+var_998], r13
0x180113d39  cmova   r8, [rbp+9E0h+var_9B0]
0x180113d3e  mov     dword ptr [rsp+0AE0h+var_AB8], 2
0x180113d46  lea     rax, [rbp+9E0h+var_970]
0x180113d4a  mov     [rsp+0AE0h+var_AC0], rax; int
0x180113d4f  xor     r9d, r9d
0x180113d52  mov     rdx, [rsp+0AE0h+var_A90]
0x180113d57  lea     rcx, [rsp+0AE0h+var_A78]
0x180113d5c  call    ?DeclaredConfigurationStore_GetPersistedDocument@@YAJPEAUDeclaredConfigurationScopeData@@PEAUHKEY__@@PEBG2PEAVDCDocument@@W4DCPersistedDocType@@@Z; DeclaredConfigurationStore_GetPersistedDocument(DeclaredConfigurationScopeData *,HKEY__ *,ushort const *,ushort const *,DCDocument *,DCPersistedDocType)
0x180113d61  mov     edi, eax
0x180113d63  test    eax, eax
0x180113d65  jns     loc_180113DEF
0x180113d6b  mov     [rbp+9E0h+var_680], r12w
0x180113d73  lea     rdx, [rbp+9E0h+var_9B0]
0x180113d77  cmp     [rbp+9E0h+var_998], r13
0x180113d7b  cmova   rdx, [rbp+9E0h+var_9B0]
0x180113d80  lea     rcx, [rbp+9E0h+var_9D0]
0x180113d84  cmp     [rbp+9E0h+var_9B8], r13
0x180113d88  cmova   rcx, [rbp+9E0h+var_9D0]
0x180113d8d  lea     rax, [rbp+9E0h+var_9F0]
0x180113d91  cmp     [rbp+9E0h+var_9D8], r13
0x180113d95  cmova   rax, [rbp+9E0h+var_9F0]
0x180113d9a  lea     r9, [rbp+9E0h+psz]
0x180113d9e  cmp     [rbp+9E0h+var_9F8], r13
0x180113da2  cmova   r9, [rbp+9E0h+psz]
0x180113da7  mov     [rsp+0AE0h+var_AB0], rdx
0x180113dac  mov     [rsp+0AE0h+var_AB8], rcx
0x180113db1  mov     [rsp+0AE0h+var_AC0], rax
0x180113db6  lea     r8, aEnrollmentidSC; "enrollmentId: %s, context:%s, docId:%s,"...
0x180113dbd  mov     edx, 104h; unsigned __int64
0x180113dc2  lea     rcx, [rbp+9E0h+var_680]; unsigned __int16 *
0x180113dc9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180113dce  test    eax, eax
0x180113dd0  js      loc_18011406B
0x180113dd6  cmp     cs:byte_180189FC1, r12b
0x180113ddd  jge     loc_18011406B
0x180113de3  lea     r8, aProcessdocswit; "ProcessDocsWithPendingInstanceVariable:"...
0x180113dea  jmp     loc_180113D15
0x180113def  mov     ecx, [rbp+9E0h+var_6CC]
0x180113df5  test    cl, 1
0x180113df8  jnz     short loc_180113E03
0x180113dfa  test    cl, 2
0x180113dfd  jz      loc_18011406B
0x180113e03  lea     r8, [rsp+0AE0h+var_AA0]; bool *
0x180113e08  lea     rdx, [rbp+9E0h+var_970]; struct DCDocument *
0x180113e0c  lea     rcx, [rsp+0AE0h+var_A78]; struct DeclaredConfigurationScopeData *
0x180113e11  call    ?DeclaredConfigurationStore_CheckIfAllInstanceDataPresent@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@PEA_N@Z; DeclaredConfigurationStore_CheckIfAllInstanceDataPresent(DeclaredConfigurationScopeData *,DCDocument *,bool *)
0x180113e16  mov     edi, eax
0x180113e18  test    eax, eax
0x180113e1a  jns     loc_180113EA4
0x180113e20  mov     [rbp+9E0h+var_680], r12w
0x180113e28  lea     rdx, [rbp+9E0h+var_9B0]
0x180113e2c  cmp     [rbp+9E0h+var_998], r13
0x180113e30  cmova   rdx, [rbp+9E0h+var_9B0]
0x180113e35  lea     rcx, [rbp+9E0h+var_9D0]
0x180113e39  cmp     [rbp+9E0h+var_9B8], r13
0x180113e3d  cmova   rcx, [rbp+9E0h+var_9D0]
0x180113e42  lea     rax, [rbp+9E0h+var_9F0]
0x180113e46  cmp     [rbp+9E0h+var_9D8], r13
0x180113e4a  cmova   rax, [rbp+9E0h+var_9F0]
0x180113e4f  lea     r9, [rbp+9E0h+psz]
0x180113e53  cmp     [rbp+9E0h+var_9F8], r13
0x180113e57  cmova   r9, [rbp+9E0h+psz]
0x180113e5c  mov     [rsp+0AE0h+var_AB0], rdx
0x180113e61  mov     [rsp+0AE0h+var_AB8], rcx
0x180113e66  mov     [rsp+0AE0h+var_AC0], rax
0x180113e6b  lea     r8, aEnrollmentidSC; "enrollmentId: %s, context:%s, docId:%s,"...
0x180113e72  mov     edx, 104h; unsigned __int64
0x180113e77  lea     rcx, [rbp+9E0h+var_680]; unsigned __int16 *
0x180113e7e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180113e83  test    eax, eax
0x180113e85  js      loc_18011406B
0x180113e8b  cmp     cs:byte_180189FC1, r12b
0x180113e92  jge     loc_18011406B
0x180113e98  lea     r8, aProcessdocswit_3; "ProcessDocsWithPendingInstanceVariable:"...
0x180113e9f  jmp     loc_180113D15
  ... truncated ...
```
