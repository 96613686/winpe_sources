# MsftPoliciesScenarioActivity::Execute(OrchestratorActivityContext *)

- ea: `0x18011f0d0`
- end: `0x18011f98f`
- name: `?Execute@MsftPoliciesScenarioActivity@@UEAAJPEAVOrchestratorActivityContext@@@Z`
- size: `2239`
- prototype: `__int64 __fastcall(MsftPoliciesScenarioActivity *__hidden this, struct OrchestratorActivityContext *)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180018cc4`
- `0x180019d38`
- `0x18001c32c`
- `0x18001ce5c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18001d37c`
- `0x18004d158`
- `0x180056bcc`
- `0x180058b08`
- `0x180058b3c`
- `0x1800641a0`
- `0x1800725e0`
- `0x180076c10`
- `0x18007f370`
- `0x180086c10`
- `0x18008bb70`
- `0x180098e10`
- `0x1800a212c`
- `0x1800aab60`
- `0x1800f5c8c`
- `0x1800f9c1c`
- `0x1800f9cb4`
- `0x1800fbe70`
- `0x18010aedc`
- `0x18011f0d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011f261`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011f2f7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011f261`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011f2f7`
- `OLEAUT32!__imp_SysAllocString` at `0x18011f212`
- `OLEAUT32!__imp_SysAllocString` at `0x18011f2d3`
- `OLEAUT32!__imp_SysAllocString` at `0x18011f312`
- `OLEAUT32!__imp_SysAllocString` at `0x18011f212`
- `OLEAUT32!__imp_SysAllocString` at `0x18011f2d3`
- `OLEAUT32!__imp_SysAllocString` at `0x18011f312`
- `OLEAUT32!__imp_VariantInit` at `0x18011f5a6`
- `OLEAUT32!__imp_VariantInit` at `0x18011f5a6`
- `OLEAUT32!__imp_VariantClear` at `0x18011f637`
- `OLEAUT32!__imp_VariantClear` at `0x18011f6c2`
- `OLEAUT32!__imp_VariantClear` at `0x18011f778`
- `OLEAUT32!__imp_VariantClear` at `0x18011f7bd`
- `OLEAUT32!__imp_VariantClear` at `0x18011f637`
- `OLEAUT32!__imp_VariantClear` at `0x18011f6c2`
- `OLEAUT32!__imp_VariantClear` at `0x18011f778`
- `OLEAUT32!__imp_VariantClear` at `0x18011f7bd`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18011f27c`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18011f27c`

## string_xrefs

- `0x18011f486`: `DeclaredConfigurationStore_GetPersistedDocument`
- `0x18011f75a`: `DeclaredConfigurationStore_GetRefreshFlag`
- `0x18011f6a3`: `DeclaredConfiguration_UpdateAllCspUriState: failed to update csp/uri state`
- `0x18011f296`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\msftpoliciesscenarioactivity.cpp`
- `0x18011f519`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\msftpoliciesscenarioactivity.cpp`
- `0x18011f618`: `DeclaredConfigurationStore_WriteResultData: failed to update doc state`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall MsftPoliciesScenarioActivity::Execute(
        MsftPoliciesScenarioActivity *this,
        struct OrchestratorActivityContext *a2)
{
  CDeclaredConfigurationLogger *Logger; // rax
  OrchestratorDBManager *v4; // rcx
  int Request; // eax
  __int64 v6; // rcx
  int v7; // ebx
  CDeclaredConfigurationLogger *v8; // rax
  CDeclaredConfigurationLogger *v9; // rax
  const OLECHAR *v10; // rcx
  CDeclaredConfigurationLogger *v11; // rax
  OLECHAR **v12; // rcx
  int ActiveUserSid; // eax
  CDeclaredConfigurationLogger *v14; // rax
  OLECHAR *v15; // rax
  OLECHAR **v16; // rcx
  const OLECHAR *v17; // rcx
  const unsigned __int16 *v18; // rdx
  CDeclaredConfigurationLogger *v19; // rax
  unsigned __int16 **v20; // rdx
  __int64 v21; // rbx
  __int64 v22; // r8
  OLECHAR **v23; // rdx
  __int64 v24; // r8
  unsigned __int16 **v25; // rdx
  unsigned __int16 **v26; // r8
  int PersistedDocument; // eax
  int v28; // ecx
  CDeclaredConfigurationLogger *v29; // rax
  int v30; // eax
  int v31; // ecx
  CDeclaredConfigurationLogger *v32; // rax
  const unsigned __int16 *v33; // r8
  const unsigned __int16 *v34; // rdx
  int v35; // eax
  int v36; // ecx
  CDeclaredConfigurationLogger *v37; // rax
  int updated; // eax
  __int64 v39; // rdx
  int v40; // ecx
  const unsigned __int16 *v41; // rdx
  int RefreshFlag; // edi
  CDeclaredConfigurationLogger *v43; // rax
  CDeclaredConfigurationLogger *v44; // rax
  const unsigned __int16 *v46; // r9
  unsigned __int16 *v47; // r8
  _QWORD *v48; // rdx
  unsigned __int16 **v49; // rcx
  unsigned __int16 **v50; // rax
  OLECHAR **v51; // r9
  OLECHAR **v52; // r8
  CDeclaredConfigurationLogger *v53; // rax
  CDeclaredConfigurationLogger *v54; // rax
  int v55; // [rsp+20h] [rbp-E0h]
  int v56; // [rsp+20h] [rbp-E0h]
  int EnrollmentIdSidStateDocIdKey; // [rsp+40h] [rbp-C0h] BYREF
  bool v58; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v59; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v60; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR *v61[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v62; // [rsp+68h] [rbp-98h]
  int v63; // [rsp+6Ch] [rbp-94h]
  OLECHAR *v64; // [rsp+70h] [rbp-90h] BYREF
  int v65; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  int v67; // [rsp+A0h] [rbp-60h] BYREF
  int v68; // [rsp+A4h] [rbp-5Ch] BYREF
  int *v69; // [rsp+A8h] [rbp-58h]
  char v70; // [rsp+B0h] [rbp-50h]
  OLECHAR *psz[3]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v72; // [rsp+D8h] [rbp-28h]
  OLECHAR *v73[3]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v74; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v75[3]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v76; // [rsp+118h] [rbp+18h]
  unsigned __int16 *v77[3]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int64 v78; // [rsp+138h] [rbp+38h]
  _QWORD v79[4]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 *v80[4]; // [rsp+160h] [rbp+60h] BYREF
  char *v81; // [rsp+180h] [rbp+80h] BYREF
  char *v82; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned int v83; // [rsp+404h] [rbp+304h]
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+388h]

  EnrollmentIdSidStateDocIdKey = 0;
  OrchestratorDCInfo::OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  v64 = 0;
  Logger = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogOrchestratorEnterFunction(Logger, L"MsftPoliciesScenarioActivity::Execute");
  v69 = &EnrollmentIdSidStateDocIdKey;
  v70 = 1;
  v59 = 0;
  v68 = 0;
  v67 = 0;
  *(_OWORD *)&pvarg.vt = *(_OWORD *)((char *)a2 + 8);
  Request = OrchestratorDBManager::GetRequest(
              v4,
              (struct _GUID *)&pvarg,
              (struct OrchestratorDCInfo *)psz,
              (enum StateMachineTypeTag *)&v59,
              (enum DMOrchestratorState *)&v68,
              (enum DCLifecycleNotificationType *)&v67);
  v7 = Request;
  EnrollmentIdSidStateDocIdKey = Request;
  if ( Request < 0 )
  {
    if ( (byte_180189FC1 & 2) != 0 )
    {
      McTemplateU0q_EventWriteTransfer(
        v6,
        EnterpriseDiagnosticsDeclaredConfigurationGetRequestFailure,
        (unsigned int)Request);
      v7 = EnrollmentIdSidStateDocIdKey;
    }
    v8 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v8,
      L"MsftPoliciesScenarioActivity::Execute",
      EnrollmentIdSidStateDocIdKey);
    goto LABEL_74;
  }
  if ( v59 != 1 && v59 != 12 )
  {
    v9 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v9,
      L"MsftPoliciesScenarioActivity::Execute",
      EnrollmentIdSidStateDocIdKey);
    v7 = -2147024846;
LABEL_74:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v64);
    OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)psz);
    return (unsigned int)v7;
  }
  *(_OWORD *)v61 = 0;
  v62 = 0;
  v63 = 63;
  v10 = (const OLECHAR *)psz;
  if ( v72 > 7 )
    v10 = psz[0];
  v61[0] = SysAllocString(v10);
  if ( !v61[0] )
  {
LABEL_11:
    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v61);
    v11 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v11,
      L"MsftPoliciesScenarioActivity::Execute",
      EnrollmentIdSidStateDocIdKey);
    v7 = -2147024882;
    goto LABEL_74;
  }
  v12 = v73;
  if ( v74 > 7 )
    v12 = (OLECHAR **)v73[0];
  if ( !(unsigned int)_o__wcsicmp(v12, L"user") )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v64,
      0);
    ActiveUserSid = DmGetActiveUserSid(&v64);
    v7 = ActiveUserSid;
    EnrollmentIdSidStateDocIdKey = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicies\\m"
                      "sftpoliciesscenarioactivity.cpp",
        (const char *)(unsigned int)ActiveUserSid,
        v55);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v61);
      v14 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
        v14,
        L"MsftPoliciesScenarioActivity::Execute",
        EnrollmentIdSidStateDocIdKey);
      goto LABEL_74;
    }
    v15 = SysAllocString(v64);
    v62 = 1;
LABEL_24:
    v61[1] = v15;
    if ( !v15 )
      goto LABEL_11;
    v60 = 0;
    *(_QWORD *)&pvarg.vt = &v60;
    pvarg.llVal = 0;
    *((_BYTE *)&pvarg.decVal + 16) = 1;
    v18 = (const unsigned __int16 *)v75;
    if ( v76 > 7 )
      v18 = v75[0];
    EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                                     (struct DeclaredConfigurationScopeData *)v61,
                                     v18,
                                     (HKEY *)&pvarg.llVal,
                                     0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&pvarg);
    v7 = EnrollmentIdSidStateDocIdKey;
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v60);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v61);
      v19 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
        v19,
        L"MsftPoliciesScenarioActivity::Execute",
        EnrollmentIdSidStateDocIdKey);
      goto LABEL_74;
    }
    DCDocument::DCDocument((DCDocument *)v80);
    v20 = v75;
    if ( v76 > 7 )
      v20 = (unsigned __int16 **)v75[0];
    v21 = -1;
    v22 = -1;
    do
      ++v22;
    while ( *((_WORD *)v20 + v22) );
    std::wstring::_Assign<unsigned short>((char **)v80, v20, (char *)v22);
    v23 = v73;
    if ( v74 > 7 )
      v23 = (OLECHAR **)v73[0];
    v24 = -1;
    do
      ++v24;
    while ( *((_WORD *)v23 + v24) );
    std::wstring::_Assign<unsigned short>(&v81, v23, (char *)v24);
    v25 = v77;
    if ( v78 > 7 )
      v25 = (unsigned __int16 **)v77[0];
    do
      ++v21;
    while ( *((_WORD *)v25 + v21) );
    std::wstring::_Assign<unsigned short>(&v82, v25, (char *)v21);
    v26 = v77;
    if ( v78 > 7 )
      v26 = (unsigned __int16 **)v77[0];
    PersistedDocument = DeclaredConfigurationStore_GetPersistedDocument(
                          (struct DeclaredConfigurationScopeData *)v61,
                          v60,
                          (__int64)v26,
                          0,
                          (__int64)v80,
                          2);
    v7 = PersistedDocument;
    EnrollmentIdSidStateDocIdKey = PersistedDocument;
    if ( PersistedDocument < 0 )
    {
      if ( byte_180189FC1 < 0 )
      {
        McTemplateU0zzd_EventWriteTransfer(
          v28,
          (unsigned int)OrchestratorGenericFailure,
          (unsigned int)L"MsftPoliciesScenarioActivity::Execute",
          (unsigned int)L"DeclaredConfigurationStore_GetPersistedDocument",
          PersistedDocument);
        v7 = EnrollmentIdSidStateDocIdKey;
      }
      DCDocument::~DCDocument((DCDocument *)v80);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v60);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v61);
      v29 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
        v29,
        L"MsftPoliciesScenarioActivity::Execute",
        EnrollmentIdSidStateDocIdKey);
      goto LABEL_74;
    }
    if ( (v83 & 1) != 0 || (v83 & 2) != 0 )
    {
      v58 = 0;
      v30 = DeclaredConfigurationStore_CheckIfAllInstanceDataPresent(
              (struct DeclaredConfigurationScopeData *)v61,
              (struct DCDocument *)v80,
              &v58);
      v7 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x85,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicies\\"
                        "msftpoliciesscenarioactivity.cpp",
          (const char *)(unsigned int)v30,
          v56);
        DCDocument::~DCDocument((DCDocument *)v80);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v60);
        DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v61);
        v32 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
          v32,
          L"MsftPoliciesScenarioActivity::Execute",
          EnrollmentIdSidStateDocIdKey);
        goto LABEL_74;
      }
      if ( v58 )
      {
        v83 = v83 & 0xFFFFFFF9 | 4;
      }
      else
      {
        v83 |= 2u;
        if ( byte_180189FC1 < 0 )
          McTemplateU0zzd_EventWriteTransfer(
            v31,
            (unsigned int)OrchestratorGenericFailure,
            (unsigned int)L"MsftPoliciesScenarioActivity::Execute",
            (unsigned int)L"NotAllInstanceData are available",
            EnrollmentIdSidStateDocIdKey);
        VariantInit(&pvarg);
        pvarg.vt = 3;
        pvarg.lVal = 41;
        v33 = (const unsigned __int16 *)v77;
        if ( v78 > 7 )
          v33 = v77[0];
        v34 = (const unsigned __int16 *)v75;
        if ( v76 > 7 )
          v34 = v75[0];
        v35 = DeclaredConfigurationStore_WriteResultData(
                (struct DeclaredConfigurationScopeData *)v61,
                v34,
                v33,
                0,
                0,
                0,
                L"state",
                &pvarg);
        EnrollmentIdSidStateDocIdKey = v35;
        if ( v35 < 0 )
        {
          if ( byte_180189FC1 < 0 )
            McTemplateU0zzd_EventWriteTransfer(
              v36,
              (unsigned int)OrchestratorGenericFailure,
              (unsigned int)L"MsftPoliciesScenarioActivity::Execute",
              (unsigned int)L"DeclaredConfigurationStore_WriteResultData: failed to update doc state",
              v35);
LABEL_60:
          v7 = -2147024875;
          EnrollmentIdSidStateDocIdKey = -2147024875;
          VariantClear(&pvarg);
          DCDocument::~DCDocument((DCDocument *)v80);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v60);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v61);
          v37 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
            v37,
            L"MsftPoliciesScenarioActivity::Execute",
            EnrollmentIdSidStateDocIdKey);
          goto LABEL_74;
        }
        updated = DeclaredConfiguration_UpdateAllCspUriState(
                    (struct DeclaredConfigurationScopeData *)v61,
                    (struct DCDocument *)v80,
                    &pvarg,
                    0);
        EnrollmentIdSidStateDocIdKey = updated;
        if ( updated < 0 )
        {
          if ( byte_180189FC1 < 0 )
            McTemplateU0zzd_EventWriteTransfer(
              v40,
              (unsigned int)OrchestratorGenericFailure,
              (unsigned int)L"MsftPoliciesScenarioActivity::Execute",
              (unsigned int)L"DeclaredConfiguration_UpdateAllCspUriState: failed to update csp/uri state",
              updated);
          goto LABEL_60;
        }
        v59 = 0;
        LOBYTE(v39) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::GetImpl'::`2'::impl,
          v39);
        v41 = (const unsigned __int16 *)v80;
        if ( v80[3] > (unsigned __int16 *)7 )
          v41 = v80[0];
        RefreshFlag = DeclaredConfigurationStore_GetRefreshFlag(v61[0], v41, &v59);
        EnrollmentIdSidStateDocIdKey = RefreshFlag;
        if ( (int)(RefreshFlag + 0x80000000) >= 0 && RefreshFlag != -2147024894 )
        {
          if ( byte_180189FC1 < 0 )
          {
            McTemplateU0zzd_EventWriteTransfer(
              RefreshFlag + 0x80000000,
              (unsigned int)OrchestratorGenericFailure,
              (unsigned int)L"ProcessDocsWithPendingInstanceVariable::",
              (unsigned int)L"DeclaredConfigurationStore_GetRefreshFlag",
              RefreshFlag);
            RefreshFlag = EnrollmentIdSidStateDocIdKey;
          }
          VariantClear(&pvarg);
          DCDocument::~DCDocument((DCDocument *)v80);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v60);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v61);
          v43 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
            v43,
            L"MsftPoliciesScenarioActivity::Execute",
            EnrollmentIdSidStateDocIdKey);
          v7 = RefreshFlag;
          goto LABEL_74;
        }
        VariantClear(&pvarg);
        if ( !v59 )
        {
          DCDocument::~DCDocument((DCDocument *)v80);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v60);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v61);
          v44 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
            v44,
            L"MsftPoliciesScenarioActivity::Execute",
            EnrollmentIdSidStateDocIdKey);
          v7 = -2147024875;
          goto LABEL_74;
        }
      }
    }
    v65 = 0;
    v46 = (const unsigned __int16 *)v73;
    if ( v74 > 7 )
      v46 = v73[0];
    v47 = (unsigned __int16 *)psz;
    if ( v72 > 7 )
      v47 = psz[0];
    v7 = DeclaredConfigurationStore_ProcessSingleDoc(
           (struct DeclaredConfigurationScopeData *)v61,
           (struct DCDocument *)v80,
           v47,
           v46,
           0,
           &v65);
    EnrollmentIdSidStateDocIdKey = v7;
    if ( v7 < 0 && (byte_180189FC1 & 2) != 0 )
    {
      v48 = v79;
      if ( v79[3] > 7u )
        v48 = (_QWORD *)v79[0];
      v49 = v77;
      if ( v78 > 7 )
        v49 = (unsigned __int16 **)v77[0];
      v50 = v75;
      if ( v76 > 7 )
        v50 = (unsigned __int16 **)v75[0];
      v51 = v73;
      if ( v74 > 7 )
        LODWORD(v51) = v73[0];
      v52 = psz;
      if ( v72 > 7 )
        LODWORD(v52) = psz[0];
      McTemplateU0zzzzzd_EventWriteTransfer(
        (_DWORD)v49,
        (unsigned int)DMOrchestratorProcessSingleDocResult,
        (_DWORD)v52,
        (_DWORD)v51,
        (__int64)v50,
        (__int64)v49,
        (__int64)v48,
        v7);
      v7 = EnrollmentIdSidStateDocIdKey;
    }
    *((_DWORD *)a2 + 146) = v65;
    DCDocument::~DCDocument((DCDocument *)v80);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v60);
    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v61);
    v53 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v53,
      L"MsftPoliciesScenarioActivity::Execute",
      EnrollmentIdSidStateDocIdKey);
    goto LABEL_74;
  }
  v16 = v73;
  if ( v74 > 7 )
    v16 = (OLECHAR **)v73[0];
  if ( !(unsigned int)_o__wcsicmp(v16, L"device") )
  {
    v17 = (const OLECHAR *)v73;
    if ( v74 > 7 )
      v17 = v73[0];
    v15 = SysAllocString(v17);
    goto LABEL_24;
  }
  DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v61);
  v54 = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
    v54,
    L"MsftPoliciesScenarioActivity::Execute",
    EnrollmentIdSidStateDocIdKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v64);
  OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18011f0d0  mov     [rsp-8+arg_0], rbx
0x18011f0d5  mov     [rsp-8+arg_10], rsi
0x18011f0da  push    rbp
0x18011f0db  push    rdi
0x18011f0dc  push    r12
0x18011f0de  push    r14
0x18011f0e0  push    r15
0x18011f0e2  lea     rbp, [rsp-360h]
0x18011f0ea  sub     rsp, 460h
0x18011f0f1  mov     rax, cs:__security_cookie
0x18011f0f8  xor     rax, rsp
0x18011f0fb  mov     [rbp+380h+var_30], rax
0x18011f102  mov     rsi, rdx
0x18011f105  xor     r14d, r14d
0x18011f108  mov     [rsp+480h+var_440], r14d
0x18011f10d  lea     rcx, [rbp+380h+psz]; this
0x18011f111  call    ??0OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::OrchestratorDCInfo(void)
0x18011f116  nop
0x18011f117  mov     [rsp+480h+var_410], r14
0x18011f11c  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18011f121  lea     r15, aMsftpoliciessc; "MsftPoliciesScenarioActivity::Execute"
0x18011f128  mov     rdx, r15; unsigned __int16 *
0x18011f12b  mov     rcx, rax; this
0x18011f12e  call    ?LogOrchestratorEnterFunction@CDeclaredConfigurationLogger@@QEAAXPEBG@Z; CDeclaredConfigurationLogger::LogOrchestratorEnterFunction(ushort const *)
0x18011f133  lea     rax, [rsp+480h+var_440]
0x18011f138  mov     [rbp+380h+var_3D8], rax
0x18011f13c  mov     [rbp+380h+var_3D0], 1
0x18011f140  mov     [rsp+480h+var_438], r14d
0x18011f145  mov     [rbp+380h+var_3DC], r14d
0x18011f149  mov     [rbp+380h+var_3E0], r14d
0x18011f14d  movups  xmm0, xmmword ptr [rsi+8]
0x18011f151  movdqu  xmmword ptr [rbp+380h+pvarg], xmm0
0x18011f156  lea     rax, [rbp+380h+var_3E0]
0x18011f15a  mov     [rsp+480h+var_458], rax; enum DCLifecycleNotificationType *
0x18011f15f  lea     rax, [rbp+380h+var_3DC]
0x18011f163  mov     [rsp+480h+var_460], rax; int
0x18011f168  lea     r9, [rsp+480h+var_438]; enum StateMachineTypeTag *
0x18011f16d  lea     r8, [rbp+380h+psz]; struct OrchestratorDCInfo *
0x18011f171  lea     rdx, [rbp+380h+pvarg]; struct _GUID
0x18011f175  call    ?GetRequest@OrchestratorDBManager@@QEAAJU_GUID@@PEAUOrchestratorDCInfo@@PEAW4StateMachineTypeTag@@PEAW4DMOrchestratorState@@PEAW4DCLifecycleNotificationType@@@Z; OrchestratorDBManager::GetRequest(_GUID,OrchestratorDCInfo *,StateMachineTypeTag *,DMOrchestratorState *,DCLifecycleNotificationType *)
0x18011f17a  mov     ebx, eax
0x18011f17c  mov     [rsp+480h+var_440], eax
0x18011f180  test    eax, eax
0x18011f182  jns     short loc_18011F1BB
0x18011f184  test    cs:byte_180189FC1, 2
0x18011f18b  jz      short loc_18011F1A0
0x18011f18d  mov     r8d, eax
0x18011f190  lea     rdx, EnterpriseDiagnosticsDeclaredConfigurationGetRequestFailure
0x18011f197  call    McTemplateU0q_EventWriteTransfer
0x18011f19c  mov     ebx, [rsp+480h+var_440]
0x18011f1a0  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18011f1a5  mov     r8d, [rsp+480h+var_440]; int
0x18011f1aa  mov     rdx, r15; unsigned __int16 *
0x18011f1ad  mov     rcx, rax; this
0x18011f1b0  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x18011f1b5  nop
0x18011f1b6  jmp     loc_18011F805
0x18011f1bb  cmp     [rsp+480h+var_438], 1
0x18011f1c0  jz      short loc_18011F1E9
0x18011f1c2  cmp     [rsp+480h+var_438], 0Ch
0x18011f1c7  jz      short loc_18011F1E9
0x18011f1c9  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18011f1ce  mov     r8d, [rsp+480h+var_440]; int
0x18011f1d3  mov     rdx, r15; unsigned __int16 *
0x18011f1d6  mov     rcx, rax; this
0x18011f1d9  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x18011f1de  nop
0x18011f1df  mov     ebx, 80070032h
0x18011f1e4  jmp     loc_18011F805
0x18011f1e9  xorps   xmm0, xmm0
0x18011f1ec  movdqu  xmmword ptr [rsp+480h+var_428], xmm0
0x18011f1f2  mov     [rsp+480h+var_418], r14d
0x18011f1f7  mov     [rsp+480h+var_414], 3Fh ; '?'
0x18011f1ff  lea     rcx, [rbp+380h+psz]
0x18011f203  mov     r12d, 7
0x18011f209  cmp     [rbp+380h+var_3A8], r12
0x18011f20d  cmova   rcx, [rbp+380h+psz]; psz
0x18011f212  call    cs:__imp_SysAllocString
0x18011f218  mov     [rsp+480h+var_428], rax
0x18011f21d  test    rax, rax
0x18011f220  jnz     short loc_18011F24D
0x18011f222  lea     rcx, [rsp+480h+var_428]; this
0x18011f227  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18011f22c  nop
0x18011f22d  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18011f232  mov     r8d, [rsp+480h+var_440]; int
0x18011f237  mov     rdx, r15; unsigned __int16 *
0x18011f23a  mov     rcx, rax; this
0x18011f23d  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x18011f242  nop
0x18011f243  mov     ebx, 8007000Eh
0x18011f248  jmp     loc_18011F805
0x18011f24d  lea     rcx, [rbp+380h+var_3A0]
0x18011f251  cmp     [rbp+380h+var_388], r12
0x18011f255  cmova   rcx, [rbp+380h+var_3A0]
0x18011f25a  lea     rdx, aUser_0; "user"
0x18011f261  call    cs:__imp__o__wcsicmp
0x18011f267  test    eax, eax
0x18011f269  jnz     short loc_18011F2E3
0x18011f26b  xor     edx, edx
0x18011f26d  lea     rcx, [rsp+480h+var_410]
0x18011f272  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18011f277  lea     rcx, [rsp+480h+var_410]
0x18011f27c  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18011f282  mov     ebx, eax
0x18011f284  mov     [rsp+480h+var_440], eax
0x18011f288  test    eax, eax
0x18011f28a  jns     short loc_18011F2CE
0x18011f28c  mov     rcx, [rbp+388h]; this
0x18011f293  mov     r9d, eax; char *
0x18011f296  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18011f29d  mov     edx, 55h ; 'U'; void *
0x18011f2a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011f2a7  nop
0x18011f2a8  lea     rcx, [rsp+480h+var_428]; this
0x18011f2ad  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18011f2b2  nop
0x18011f2b3  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18011f2b8  mov     r8d, [rsp+480h+var_440]; int
0x18011f2bd  mov     rdx, r15; unsigned __int16 *
0x18011f2c0  mov     rcx, rax; this
0x18011f2c3  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x18011f2c8  nop
0x18011f2c9  jmp     loc_18011F805
0x18011f2ce  mov     rcx, [rsp+480h+var_410]; psz
0x18011f2d3  call    cs:__imp_SysAllocString
0x18011f2d9  mov     [rsp+480h+var_418], 1
0x18011f2e1  jmp     short loc_18011F318
0x18011f2e3  lea     rcx, [rbp+380h+var_3A0]
0x18011f2e7  cmp     [rbp+380h+var_388], r12
0x18011f2eb  cmova   rcx, [rbp+380h+var_3A0]
0x18011f2f0  lea     rdx, aDevice_4; "device"
0x18011f2f7  call    cs:__imp__o__wcsicmp
0x18011f2fd  test    eax, eax
0x18011f2ff  jnz     loc_18011F92A
0x18011f305  lea     rcx, [rbp+380h+var_3A0]
0x18011f309  cmp     [rbp+380h+var_388], r12
0x18011f30d  cmova   rcx, [rbp+380h+var_3A0]; psz
0x18011f312  call    cs:__imp_SysAllocString
0x18011f318  mov     [rsp+480h+var_428+8], rax
0x18011f31d  test    rax, rax
0x18011f320  jnz     short loc_18011F348
0x18011f322  lea     rcx, [rsp+480h+var_428]; this
0x18011f327  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18011f32c  nop
0x18011f32d  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18011f332  mov     r8d, [rsp+480h+var_440]; int
0x18011f337  mov     rdx, r15; unsigned __int16 *
0x18011f33a  mov     rcx, rax; this
0x18011f33d  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x18011f342  nop
0x18011f343  jmp     loc_18011F243
0x18011f348  mov     [rsp+480h+var_430], r14
0x18011f34d  lea     rax, [rsp+480h+var_430]
0x18011f352  mov     qword ptr [rbp+380h+pvarg], rax
0x18011f356  mov     qword ptr [rbp+380h+pvarg+8], r14
0x18011f35a  mov     byte ptr [rbp+380h+pvarg+10h], 1
0x18011f35e  lea     rdx, [rbp+380h+var_380]
0x18011f362  cmp     [rbp+380h+var_368], r12
0x18011f366  cmova   rdx, [rbp+380h+var_380]; unsigned __int16 *
0x18011f36b  xor     r9d, r9d; int
0x18011f36e  lea     r8, [rbp+380h+pvarg+8]; HKEY *
0x18011f372  lea     rcx, [rsp+480h+var_428]; struct DeclaredConfigurationScopeData *
0x18011f377  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x18011f37c  mov     [rsp+480h+var_440], eax
0x18011f380  lea     rcx, [rbp+380h+pvarg]
0x18011f384  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18011f389  mov     ebx, [rsp+480h+var_440]
0x18011f38d  test    ebx, ebx
0x18011f38f  jns     short loc_18011F3C2
0x18011f391  lea     rcx, [rsp+480h+var_430]
0x18011f396  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011f39b  nop
0x18011f39c  lea     rcx, [rsp+480h+var_428]; this
0x18011f3a1  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18011f3a6  nop
0x18011f3a7  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18011f3ac  mov     r8d, [rsp+480h+var_440]; int
0x18011f3b1  mov     rdx, r15; unsigned __int16 *
0x18011f3b4  mov     rcx, rax; this
0x18011f3b7  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x18011f3bc  nop
0x18011f3bd  jmp     loc_18011F805
0x18011f3c2  lea     rcx, [rbp+380h+var_320]; this
0x18011f3c6  call    ??0DCDocument@@QEAA@XZ; DCDocument::DCDocument(void)
0x18011f3cb  nop
0x18011f3cc  lea     rdx, [rbp+380h+var_380]
0x18011f3d0  cmp     [rbp+380h+var_368], r12
0x18011f3d4  cmova   rdx, [rbp+380h+var_380]
0x18011f3d9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18011f3dd  mov     r8, rbx
0x18011f3e0  inc     r8
0x18011f3e3  cmp     [rdx+r8*2], r14w
0x18011f3e8  jnz     short loc_18011F3E0
0x18011f3ea  lea     rcx, [rbp+380h+var_320]
0x18011f3ee  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18011f3f3  lea     rdx, [rbp+380h+var_3A0]
0x18011f3f7  cmp     [rbp+380h+var_388], r12
0x18011f3fb  cmova   rdx, [rbp+380h+var_3A0]
0x18011f400  mov     r8, rbx
0x18011f403  inc     r8
0x18011f406  cmp     [rdx+r8*2], r14w
0x18011f40b  jnz     short loc_18011F403
0x18011f40d  lea     rcx, [rbp+380h+var_300]
0x18011f414  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18011f419  lea     rdx, [rbp+380h+var_360]
0x18011f41d  cmp     [rbp+380h+var_348], r12
0x18011f421  cmova   rdx, [rbp+380h+var_360]
0x18011f426  inc     rbx
0x18011f429  cmp     [rdx+rbx*2], r14w
0x18011f42e  jnz     short loc_18011F426
0x18011f430  mov     r8, rbx
0x18011f433  lea     rcx, [rbp+380h+var_2C0]
0x18011f43a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18011f43f  lea     r8, [rbp+380h+var_360]
0x18011f443  cmp     [rbp+380h+var_348], r12
0x18011f447  cmova   r8, [rbp+380h+var_360]
0x18011f44c  mov     dword ptr [rsp+480h+var_458], 2
0x18011f454  lea     rax, [rbp+380h+var_320]
0x18011f458  mov     [rsp+480h+var_460], rax; int
0x18011f45d  xor     r9d, r9d
0x18011f460  mov     rdx, [rsp+480h+var_430]
0x18011f465  lea     rcx, [rsp+480h+var_428]
0x18011f46a  call    ?DeclaredConfigurationStore_GetPersistedDocument@@YAJPEAUDeclaredConfigurationScopeData@@PEAUHKEY__@@PEBG2PEAVDCDocument@@W4DCPersistedDocType@@@Z; DeclaredConfigurationStore_GetPersistedDocument(DeclaredConfigurationScopeData *,HKEY__ *,ushort const *,ushort const *,DCDocument *,DCPersistedDocType)
0x18011f46f  mov     ebx, eax
0x18011f471  mov     [rsp+480h+var_440], eax
0x18011f475  test    eax, eax
0x18011f477  jns     short loc_18011F4DB
0x18011f479  cmp     cs:byte_180189FC1, r14b
0x18011f480  jge     short loc_18011F4A0
0x18011f482  mov     dword ptr [rsp+480h+var_460], eax
0x18011f486  lea     r9, aDeclaredconfig_143; "DeclaredConfigurationStore_GetPersisted"...
0x18011f48d  mov     r8, r15
0x18011f490  lea     rdx, OrchestratorGenericFailure
0x18011f497  call    McTemplateU0zzd_EventWriteTransfer
0x18011f49c  mov     ebx, [rsp+480h+var_440]
0x18011f4a0  lea     rcx, [rbp+380h+var_320]; this
0x18011f4a4  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x18011f4a9  nop
0x18011f4aa  lea     rcx, [rsp+480h+var_430]
0x18011f4af  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011f4b4  nop
0x18011f4b5  lea     rcx, [rsp+480h+var_428]; this
0x18011f4ba  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18011f4bf  nop
0x18011f4c0  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18011f4c5  mov     r8d, [rsp+480h+var_440]; int
0x18011f4ca  mov     rdx, r15; unsigned __int16 *
0x18011f4cd  mov     rcx, rax; this
0x18011f4d0  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x18011f4d5  nop
0x18011f4d6  jmp     loc_18011F805
0x18011f4db  test    byte ptr [rbp+380h+var_7C], 1
0x18011f4e2  jnz     short loc_18011F4F1
0x18011f4e4  test    byte ptr [rbp+380h+var_7C], 2
0x18011f4eb  jz      loc_18011F832
0x18011f4f1  mov     [rsp+480h+var_43C], r14b
0x18011f4f6  lea     r8, [rsp+480h+var_43C]; bool *
0x18011f4fb  lea     rdx, [rbp+380h+var_320]; struct DCDocument *
0x18011f4ff  lea     rcx, [rsp+480h+var_428]; struct DeclaredConfigurationScopeData *
0x18011f504  call    ?DeclaredConfigurationStore_CheckIfAllInstanceDataPresent@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@PEA_N@Z; DeclaredConfigurationStore_CheckIfAllInstanceDataPresent(DeclaredConfigurationScopeData *,DCDocument *,bool *)
0x18011f509  mov     ebx, eax
0x18011f50b  test    eax, eax
0x18011f50d  jns     short loc_18011F566
0x18011f50f  mov     rcx, [rbp+388h]; this
0x18011f516  mov     r9d, eax; char *
0x18011f519  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18011f520  mov     edx, 85h; void *
0x18011f525  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011f52a  nop
0x18011f52b  lea     rcx, [rbp+380h+var_320]; this
0x18011f52f  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x18011f534  nop
0x18011f535  lea     rcx, [rsp+480h+var_430]
0x18011f53a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011f53f  nop
0x18011f540  lea     rcx, [rsp+480h+var_428]; this
0x18011f545  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18011f54a  nop
0x18011f54b  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18011f550  mov     r8d, [rsp+480h+var_440]; int
0x18011f555  mov     rdx, r15; unsigned __int16 *
0x18011f558  mov     rcx, rax; this
0x18011f55b  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x18011f560  nop
0x18011f561  jmp     loc_18011F805
0x18011f566  cmp     [rsp+480h+var_43C], r14b
0x18011f56b  jnz     loc_18011F820
0x18011f571  or      [rbp+380h+var_7C], 2
0x18011f578  lea     rbx, OrchestratorGenericFailure
0x18011f57f  cmp     cs:byte_180189FC1, r14b
0x18011f586  jge     short loc_18011F5A2
0x18011f588  mov     eax, [rsp+480h+var_440]
0x18011f58c  mov     dword ptr [rsp+480h+var_460], eax
0x18011f590  lea     r9, aNotallinstance; "NotAllInstanceData are available"
0x18011f597  mov     r8, r15
0x18011f59a  mov     rdx, rbx
0x18011f59d  call    McTemplateU0zzd_EventWriteTransfer
0x18011f5a2  lea     rcx, [rbp+380h+pvarg]; pvarg
0x18011f5a6  call    cs:__imp_VariantInit
  ... truncated ...
```
