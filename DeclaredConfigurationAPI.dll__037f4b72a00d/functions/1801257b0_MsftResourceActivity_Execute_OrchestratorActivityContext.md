# MsftResourceActivity::Execute(OrchestratorActivityContext *)

- ea: `0x1801257b0`
- end: `0x1801260cc`
- name: `?Execute@MsftResourceActivity@@UEAAJPEAVOrchestratorActivityContext@@@Z`
- size: `2332`
- prototype: `__int64 __fastcall(MsftResourceActivity *__hidden this, struct OrchestratorActivityContext *)`
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
- `0x18005a9e0`
- `0x1800641a0`
- `0x1800725e0`
- `0x180076c10`
- `0x18007f370`
- `0x180086c10`
- `0x18008bb70`
- `0x1800a212c`
- `0x1800aab60`
- `0x1800f5c8c`
- `0x1800f9c1c`
- `0x1800f9cb4`
- `0x1800fbe70`
- `0x18010aedc`
- `0x1801257b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012593a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801259d0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012593a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801259d0`
- `OLEAUT32!__imp_SysAllocString` at `0x1801258eb`
- `OLEAUT32!__imp_SysAllocString` at `0x1801259ac`
- `OLEAUT32!__imp_SysAllocString` at `0x1801259eb`
- `OLEAUT32!__imp_SysAllocString` at `0x1801258eb`
- `OLEAUT32!__imp_SysAllocString` at `0x1801259ac`
- `OLEAUT32!__imp_SysAllocString` at `0x1801259eb`
- `OLEAUT32!__imp_VariantInit` at `0x180125c2e`
- `OLEAUT32!__imp_VariantInit` at `0x180125c2e`
- `OLEAUT32!__imp_VariantClear` at `0x180125cc3`
- `OLEAUT32!__imp_VariantClear` at `0x180125d52`
- `OLEAUT32!__imp_VariantClear` at `0x180125e03`
- `OLEAUT32!__imp_VariantClear` at `0x180125e86`
- `OLEAUT32!__imp_VariantClear` at `0x180125ef9`
- `OLEAUT32!__imp_VariantClear` at `0x180125f55`
- `OLEAUT32!__imp_VariantClear` at `0x180125cc3`
- `OLEAUT32!__imp_VariantClear` at `0x180125d52`
- `OLEAUT32!__imp_VariantClear` at `0x180125e03`
- `OLEAUT32!__imp_VariantClear` at `0x180125e86`
- `OLEAUT32!__imp_VariantClear` at `0x180125ef9`
- `OLEAUT32!__imp_VariantClear` at `0x180125f55`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180125955`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180125955`

## string_xrefs

- `0x180125d2f`: `DeclaredConfiguration_UpdateAllCspUriState: failed to update csp/uri state`
- `0x180125ca0`: `DeclaredConfigurationStore_WriteResultData: failed to update doc state`
- `0x180125de0`: `DCCDNUtil_GetRegistryDWORD:Read isRefresh`
- `0x18012596f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\msftresourceactivity.cpp`
- `0x180125bcb`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\msftresourceactivity.cpp`
- `0x180125e70`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\msftresourceactivity.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall MsftResourceActivity::Execute(MsftResourceActivity *this, struct OrchestratorActivityContext *a2)
{
  CDeclaredConfigurationLogger *Logger; // rax
  OrchestratorDBManager *v4; // rcx
  int Request; // eax
  __int64 v6; // rcx
  int PersistedDocument; // ebx
  CDeclaredConfigurationLogger *v8; // rax
  CDeclaredConfigurationLogger *v9; // rax
  const OLECHAR *v10; // rcx
  CDeclaredConfigurationLogger *v11; // rax
  OLECHAR **v12; // rcx
  int ActiveUserSid; // eax
  CDeclaredConfigurationLogger *v14; // rax
  BSTR v15; // rax
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
  CDeclaredConfigurationLogger *v27; // rax
  int v28; // eax
  CDeclaredConfigurationLogger *v29; // rax
  const unsigned __int16 *v30; // r8
  const unsigned __int16 *v31; // rdx
  int v32; // eax
  int v33; // ecx
  int updated; // eax
  int v35; // ecx
  const unsigned __int16 *v36; // rdx
  OLECHAR *v37; // rcx
  int RefreshFlag; // edi
  CDeclaredConfigurationLogger *v39; // rax
  int v40; // eax
  int v41; // ecx
  CDeclaredConfigurationLogger *v42; // rax
  CDeclaredConfigurationLogger *v43; // rax
  const unsigned __int16 *v45; // r9
  unsigned __int16 *v46; // r8
  _QWORD *v47; // rdx
  unsigned __int16 **v48; // rcx
  unsigned __int16 **v49; // rax
  OLECHAR **v50; // r9
  OLECHAR **v51; // r8
  CDeclaredConfigurationLogger *v52; // rax
  CDeclaredConfigurationLogger *v53; // rax
  int v54; // [rsp+20h] [rbp-E0h]
  int v55; // [rsp+20h] [rbp-E0h]
  int v56; // [rsp+20h] [rbp-E0h]
  int EnrollmentIdSidStateDocIdKey; // [rsp+40h] [rbp-C0h] BYREF
  bool v58; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v59; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v60; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v61; // [rsp+58h] [rbp-A8h] BYREF
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
  int v80[8]; // [rsp+160h] [rbp+60h] BYREF
  char *v81; // [rsp+180h] [rbp+80h] BYREF
  char *v82; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned int v83; // [rsp+404h] [rbp+304h]
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+388h]

  EnrollmentIdSidStateDocIdKey = 0;
  OrchestratorDCInfo::OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  v64 = 0;
  Logger = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogOrchestratorEnterFunction(Logger, L"MsftResourceActivity::Execute");
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
  PersistedDocument = Request;
  EnrollmentIdSidStateDocIdKey = Request;
  if ( Request < 0 )
  {
    if ( (byte_180189FC1 & 2) != 0 )
    {
      McTemplateU0q_EventWriteTransfer(
        v6,
        EnterpriseDiagnosticsDeclaredConfigurationGetRequestFailure,
        (unsigned int)Request);
      PersistedDocument = EnrollmentIdSidStateDocIdKey;
    }
    v8 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v8,
      L"MsftResourceActivity::Execute",
      EnrollmentIdSidStateDocIdKey);
    goto LABEL_75;
  }
  if ( v59 != 2 )
  {
    v9 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v9,
      L"MsftResourceActivity::Execute",
      EnrollmentIdSidStateDocIdKey);
    PersistedDocument = -2147024846;
LABEL_75:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v64);
    OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)psz);
    return (unsigned int)PersistedDocument;
  }
  v61 = 0;
  v62 = 0;
  v63 = 63;
  v10 = (const OLECHAR *)psz;
  if ( v72 > 7 )
    v10 = psz[0];
  *(_QWORD *)&v61 = SysAllocString(v10);
  if ( !(_QWORD)v61 )
  {
LABEL_10:
    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v61);
    v11 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v11,
      L"MsftResourceActivity::Execute",
      EnrollmentIdSidStateDocIdKey);
    PersistedDocument = -2147024882;
    goto LABEL_75;
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
    PersistedDocument = ActiveUserSid;
    EnrollmentIdSidStateDocIdKey = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicies\\m"
                      "sftresourceactivity.cpp",
        (const char *)(unsigned int)ActiveUserSid,
        v54);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v61);
      v14 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
        v14,
        L"MsftResourceActivity::Execute",
        EnrollmentIdSidStateDocIdKey);
      goto LABEL_75;
    }
    v15 = SysAllocString(v64);
    v62 = 1;
LABEL_23:
    *((_QWORD *)&v61 + 1) = v15;
    if ( !v15 )
      goto LABEL_10;
    v60 = 0;
    *(_QWORD *)&pvarg.vt = &v60;
    pvarg.llVal = 0;
    *((_BYTE *)&pvarg.decVal + 16) = 1;
    v18 = (const unsigned __int16 *)v75;
    if ( v76 > 7 )
      v18 = v75[0];
    EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                                     (struct DeclaredConfigurationScopeData *)&v61,
                                     v18,
                                     (HKEY *)&pvarg.llVal,
                                     0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&pvarg);
    PersistedDocument = EnrollmentIdSidStateDocIdKey;
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v60);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v61);
      v19 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
        v19,
        L"MsftResourceActivity::Execute",
        EnrollmentIdSidStateDocIdKey);
      goto LABEL_75;
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
                          (struct DeclaredConfigurationScopeData *)&v61,
                          v60,
                          (__int64)v26,
                          0,
                          (__int64)v80,
                          2);
    EnrollmentIdSidStateDocIdKey = PersistedDocument;
    if ( PersistedDocument < 0 )
    {
      DCDocument::~DCDocument((DCDocument *)v80);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v60);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v61);
      v27 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
        v27,
        L"MsftResourceActivity::Execute",
        EnrollmentIdSidStateDocIdKey);
      goto LABEL_75;
    }
    if ( (v83 & 1) != 0 || (v83 & 2) != 0 )
    {
      v58 = 0;
      v28 = DeclaredConfigurationStore_CheckIfAllInstanceDataPresent(
              (struct DeclaredConfigurationScopeData *)&v61,
              (struct DCDocument *)v80,
              &v58);
      PersistedDocument = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x72,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicies\\"
                        "msftresourceactivity.cpp",
          (const char *)(unsigned int)v28,
          v55);
        DCDocument::~DCDocument((DCDocument *)v80);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v60);
        DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v61);
        v29 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
          v29,
          L"MsftResourceActivity::Execute",
          EnrollmentIdSidStateDocIdKey);
        goto LABEL_75;
      }
      if ( v58 )
      {
        v83 = v83 & 0xFFFFFFF9 | 4;
      }
      else
      {
        v83 |= 2u;
        VariantInit(&pvarg);
        pvarg.vt = 3;
        pvarg.lVal = 41;
        v30 = (const unsigned __int16 *)v77;
        if ( v78 > 7 )
          v30 = v77[0];
        v31 = (const unsigned __int16 *)v75;
        if ( v76 > 7 )
          v31 = v75[0];
        v32 = DeclaredConfigurationStore_WriteResultData(
                (struct DeclaredConfigurationScopeData *)&v61,
                v31,
                v30,
                0,
                0,
                0,
                L"state",
                &pvarg);
        EnrollmentIdSidStateDocIdKey = v32;
        if ( v32 < 0 )
        {
          if ( byte_180189FC1 < 0 )
            McTemplateU0zzd_EventWriteTransfer(
              v33,
              (unsigned int)OrchestratorGenericFailure,
              (unsigned int)L"MsftResourceActivity::Execute",
              (unsigned int)L"DeclaredConfigurationStore_WriteResultData: failed to update doc state",
              v32);
          goto LABEL_74;
        }
        updated = DeclaredConfiguration_UpdateAllCspUriState(
                    (struct DeclaredConfigurationScopeData *)&v61,
                    (struct DCDocument *)v80,
                    &pvarg,
                    0);
        EnrollmentIdSidStateDocIdKey = updated;
        if ( updated < 0 )
        {
          if ( byte_180189FC1 < 0 )
            McTemplateU0zzd_EventWriteTransfer(
              v35,
              (unsigned int)OrchestratorGenericFailure,
              (unsigned int)L"MsftResourceActivity::Execute",
              (unsigned int)L"DeclaredConfiguration_UpdateAllCspUriState: failed to update csp/uri state",
              updated);
          goto LABEL_74;
        }
        v59 = 0;
        v36 = (const unsigned __int16 *)v75;
        if ( v76 > 7 )
          v36 = v75[0];
        v37 = (OLECHAR *)psz;
        if ( v72 > 7 )
          v37 = psz[0];
        RefreshFlag = DeclaredConfigurationStore_GetRefreshFlag(v37, v36, &v59);
        if ( (int)(RefreshFlag + 0x80000000) >= 0 && RefreshFlag != -2147024894 )
        {
          if ( byte_180189FC1 < 0 )
            McTemplateU0zzd_EventWriteTransfer(
              RefreshFlag + 0x80000000,
              (unsigned int)OrchestratorGenericFailure,
              (unsigned int)L"MsftResourceActivity::Execute",
              (unsigned int)L"DCCDNUtil_GetRegistryDWORD:Read isRefresh",
              RefreshFlag);
          EnrollmentIdSidStateDocIdKey = -2147024875;
          VariantClear(&pvarg);
          DCDocument::~DCDocument((DCDocument *)v80);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v60);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v61);
          v39 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
            v39,
            L"MsftResourceActivity::Execute",
            EnrollmentIdSidStateDocIdKey);
          PersistedDocument = RefreshFlag;
          goto LABEL_75;
        }
        if ( !v59 )
        {
          v40 = AddResultTimeStamp((struct DeclaredConfigurationScopeData *)&v61, (struct DCDocument *)v80);
          PersistedDocument = v40;
          if ( v40 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA0,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolic"
                            "ies\\msftresourceactivity.cpp",
              (const char *)(unsigned int)v40,
              v56);
            VariantClear(&pvarg);
            DCDocument::~DCDocument((DCDocument *)v80);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v60);
            DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v61);
            v42 = CDeclaredConfigurationLogger::GetLogger();
            CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
              v42,
              L"MsftResourceActivity::Execute",
              EnrollmentIdSidStateDocIdKey);
            goto LABEL_75;
          }
          if ( byte_180189FC1 < 0 )
            McTemplateU0zzd_EventWriteTransfer(
              v41,
              (unsigned int)OrchestratorGenericFailure,
              (unsigned int)L"MsftResourceActivity::Execute",
              (unsigned int)L"NotAllInstanceData are available",
              EnrollmentIdSidStateDocIdKey);
LABEL_74:
          PersistedDocument = -2147024875;
          EnrollmentIdSidStateDocIdKey = -2147024875;
          VariantClear(&pvarg);
          DCDocument::~DCDocument((DCDocument *)v80);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v60);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v61);
          v43 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
            v43,
            L"MsftResourceActivity::Execute",
            EnrollmentIdSidStateDocIdKey);
          goto LABEL_75;
        }
        VariantClear(&pvarg);
      }
    }
    v65 = 0;
    v45 = (const unsigned __int16 *)v73;
    if ( v74 > 7 )
      v45 = v73[0];
    v46 = (unsigned __int16 *)psz;
    if ( v72 > 7 )
      v46 = psz[0];
    PersistedDocument = DeclaredConfigurationStore_ProcessSingleDoc(
                          (struct DeclaredConfigurationScopeData *)&v61,
                          (struct DCDocument *)v80,
                          v46,
                          v45,
                          0,
                          &v65);
    EnrollmentIdSidStateDocIdKey = PersistedDocument;
    if ( PersistedDocument < 0 && (byte_180189FC1 & 2) != 0 )
    {
      v47 = v79;
      if ( v79[3] > 7u )
        v47 = (_QWORD *)v79[0];
      v48 = v77;
      if ( v78 > 7 )
        v48 = (unsigned __int16 **)v77[0];
      v49 = v75;
      if ( v76 > 7 )
        v49 = (unsigned __int16 **)v75[0];
      v50 = v73;
      if ( v74 > 7 )
        LODWORD(v50) = v73[0];
      v51 = psz;
      if ( v72 > 7 )
        LODWORD(v51) = psz[0];
      McTemplateU0zzzzzd_EventWriteTransfer(
        (_DWORD)v48,
        (unsigned int)DMOrchestratorProcessSingleDocResult,
        (_DWORD)v51,
        (_DWORD)v50,
        (__int64)v49,
        (__int64)v48,
        (__int64)v47,
        PersistedDocument);
      PersistedDocument = EnrollmentIdSidStateDocIdKey;
    }
    *((_DWORD *)a2 + 146) = v65;
    DCDocument::~DCDocument((DCDocument *)v80);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v60);
    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v61);
    v52 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v52,
      L"MsftResourceActivity::Execute",
      EnrollmentIdSidStateDocIdKey);
    goto LABEL_75;
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
    goto LABEL_23;
  }
  DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v61);
  v53 = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
    v53,
    L"MsftResourceActivity::Execute",
    EnrollmentIdSidStateDocIdKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v64);
  OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1801257b0  mov     [rsp-8+arg_0], rbx
0x1801257b5  mov     [rsp-8+arg_10], rsi
0x1801257ba  push    rbp
0x1801257bb  push    rdi
0x1801257bc  push    r12
0x1801257be  push    r14
0x1801257c0  push    r15
0x1801257c2  lea     rbp, [rsp-360h]
0x1801257ca  sub     rsp, 460h
0x1801257d1  mov     rax, cs:__security_cookie
0x1801257d8  xor     rax, rsp
0x1801257db  mov     [rbp+380h+var_30], rax
0x1801257e2  mov     rsi, rdx
0x1801257e5  xor     r14d, r14d
0x1801257e8  mov     [rsp+480h+var_440], r14d
0x1801257ed  lea     rcx, [rbp+380h+psz]; this
0x1801257f1  call    ??0OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::OrchestratorDCInfo(void)
0x1801257f6  nop
0x1801257f7  mov     [rsp+480h+var_410], r14
0x1801257fc  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180125801  lea     r15, aMsftresourceac; "MsftResourceActivity::Execute"
0x180125808  mov     rdx, r15; unsigned __int16 *
0x18012580b  mov     rcx, rax; this
0x18012580e  call    ?LogOrchestratorEnterFunction@CDeclaredConfigurationLogger@@QEAAXPEBG@Z; CDeclaredConfigurationLogger::LogOrchestratorEnterFunction(ushort const *)
0x180125813  lea     rax, [rsp+480h+var_440]
0x180125818  mov     [rbp+380h+var_3D8], rax
0x18012581c  mov     [rbp+380h+var_3D0], 1
0x180125820  mov     [rsp+480h+var_438], r14d
0x180125825  mov     [rbp+380h+var_3DC], r14d
0x180125829  mov     [rbp+380h+var_3E0], r14d
0x18012582d  movups  xmm0, xmmword ptr [rsi+8]
0x180125831  movdqu  xmmword ptr [rbp+380h+pvarg], xmm0
0x180125836  lea     rax, [rbp+380h+var_3E0]
0x18012583a  mov     [rsp+480h+var_458], rax; enum DCLifecycleNotificationType *
0x18012583f  lea     rax, [rbp+380h+var_3DC]
0x180125843  mov     [rsp+480h+var_460], rax; int
0x180125848  lea     r9, [rsp+480h+var_438]; enum StateMachineTypeTag *
0x18012584d  lea     r8, [rbp+380h+psz]; struct OrchestratorDCInfo *
0x180125851  lea     rdx, [rbp+380h+pvarg]; struct _GUID
0x180125855  call    ?GetRequest@OrchestratorDBManager@@QEAAJU_GUID@@PEAUOrchestratorDCInfo@@PEAW4StateMachineTypeTag@@PEAW4DMOrchestratorState@@PEAW4DCLifecycleNotificationType@@@Z; OrchestratorDBManager::GetRequest(_GUID,OrchestratorDCInfo *,StateMachineTypeTag *,DMOrchestratorState *,DCLifecycleNotificationType *)
0x18012585a  mov     ebx, eax
0x18012585c  mov     [rsp+480h+var_440], eax
0x180125860  test    eax, eax
0x180125862  jns     short loc_18012589B
0x180125864  test    cs:byte_180189FC1, 2
0x18012586b  jz      short loc_180125880
0x18012586d  mov     r8d, eax
0x180125870  lea     rdx, EnterpriseDiagnosticsDeclaredConfigurationGetRequestFailure
0x180125877  call    McTemplateU0q_EventWriteTransfer
0x18012587c  mov     ebx, [rsp+480h+var_440]
0x180125880  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180125885  mov     r8d, [rsp+480h+var_440]; int
0x18012588a  mov     rdx, r15; unsigned __int16 *
0x18012588d  mov     rcx, rax; this
0x180125890  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180125895  nop
0x180125896  jmp     loc_180125F36
0x18012589b  cmp     [rsp+480h+var_438], 2
0x1801258a0  jz      short loc_1801258C2
0x1801258a2  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1801258a7  mov     r8d, [rsp+480h+var_440]; int
0x1801258ac  mov     rdx, r15; unsigned __int16 *
0x1801258af  mov     rcx, rax; this
0x1801258b2  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1801258b7  nop
0x1801258b8  mov     ebx, 80070032h
0x1801258bd  jmp     loc_180125F36
0x1801258c2  xorps   xmm0, xmm0
0x1801258c5  movdqu  [rsp+480h+var_428], xmm0
0x1801258cb  mov     [rsp+480h+var_418], r14d
0x1801258d0  mov     [rsp+480h+var_414], 3Fh ; '?'
0x1801258d8  lea     rcx, [rbp+380h+psz]
0x1801258dc  mov     r12d, 7
0x1801258e2  cmp     [rbp+380h+var_3A8], r12
0x1801258e6  cmova   rcx, [rbp+380h+psz]; psz
0x1801258eb  call    cs:__imp_SysAllocString
0x1801258f1  mov     qword ptr [rsp+480h+var_428], rax
0x1801258f6  test    rax, rax
0x1801258f9  jnz     short loc_180125926
0x1801258fb  lea     rcx, [rsp+480h+var_428]; this
0x180125900  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180125905  nop
0x180125906  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18012590b  mov     r8d, [rsp+480h+var_440]; int
0x180125910  mov     rdx, r15; unsigned __int16 *
0x180125913  mov     rcx, rax; this
0x180125916  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x18012591b  nop
0x18012591c  mov     ebx, 8007000Eh
0x180125921  jmp     loc_180125F36
0x180125926  lea     rcx, [rbp+380h+var_3A0]
0x18012592a  cmp     [rbp+380h+var_388], r12
0x18012592e  cmova   rcx, [rbp+380h+var_3A0]
0x180125933  lea     rdx, aUser_0; "user"
0x18012593a  call    cs:__imp__o__wcsicmp
0x180125940  test    eax, eax
0x180125942  jnz     short loc_1801259BC
0x180125944  xor     edx, edx
0x180125946  lea     rcx, [rsp+480h+var_410]
0x18012594b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180125950  lea     rcx, [rsp+480h+var_410]
0x180125955  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18012595b  mov     ebx, eax
0x18012595d  mov     [rsp+480h+var_440], eax
0x180125961  test    eax, eax
0x180125963  jns     short loc_1801259A7
0x180125965  mov     rcx, [rbp+388h]; this
0x18012596c  mov     r9d, eax; char *
0x18012596f  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180125976  mov     edx, 44h ; 'D'; void *
0x18012597b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125980  nop
0x180125981  lea     rcx, [rsp+480h+var_428]; this
0x180125986  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18012598b  nop
0x18012598c  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180125991  mov     r8d, [rsp+480h+var_440]; int
0x180125996  mov     rdx, r15; unsigned __int16 *
0x180125999  mov     rcx, rax; this
0x18012599c  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1801259a1  nop
0x1801259a2  jmp     loc_180125F36
0x1801259a7  mov     rcx, [rsp+480h+var_410]; psz
0x1801259ac  call    cs:__imp_SysAllocString
0x1801259b2  mov     [rsp+480h+var_418], 1
0x1801259ba  jmp     short loc_1801259F1
0x1801259bc  lea     rcx, [rbp+380h+var_3A0]
0x1801259c0  cmp     [rbp+380h+var_388], r12
0x1801259c4  cmova   rcx, [rbp+380h+var_3A0]
0x1801259c9  lea     rdx, aDevice_4; "device"
0x1801259d0  call    cs:__imp__o__wcsicmp
0x1801259d6  test    eax, eax
0x1801259d8  jnz     loc_180126067
0x1801259de  lea     rcx, [rbp+380h+var_3A0]
0x1801259e2  cmp     [rbp+380h+var_388], r12
0x1801259e6  cmova   rcx, [rbp+380h+var_3A0]; psz
0x1801259eb  call    cs:__imp_SysAllocString
0x1801259f1  mov     qword ptr [rsp+480h+var_428+8], rax
0x1801259f6  test    rax, rax
0x1801259f9  jnz     short loc_180125A21
0x1801259fb  lea     rcx, [rsp+480h+var_428]; this
0x180125a00  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180125a05  nop
0x180125a06  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180125a0b  mov     r8d, [rsp+480h+var_440]; int
0x180125a10  mov     rdx, r15; unsigned __int16 *
0x180125a13  mov     rcx, rax; this
0x180125a16  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180125a1b  nop
0x180125a1c  jmp     loc_18012591C
0x180125a21  mov     [rsp+480h+var_430], r14
0x180125a26  lea     rax, [rsp+480h+var_430]
0x180125a2b  mov     qword ptr [rbp+380h+pvarg], rax
0x180125a2f  mov     qword ptr [rbp+380h+pvarg+8], r14
0x180125a33  mov     byte ptr [rbp+380h+pvarg+10h], 1
0x180125a37  lea     rdx, [rbp+380h+var_380]
0x180125a3b  cmp     [rbp+380h+var_368], r12
0x180125a3f  cmova   rdx, [rbp+380h+var_380]; unsigned __int16 *
0x180125a44  xor     r9d, r9d; int
0x180125a47  lea     r8, [rbp+380h+pvarg+8]; HKEY *
0x180125a4b  lea     rcx, [rsp+480h+var_428]; struct DeclaredConfigurationScopeData *
0x180125a50  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x180125a55  mov     [rsp+480h+var_440], eax
0x180125a59  lea     rcx, [rbp+380h+pvarg]
0x180125a5d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180125a62  mov     ebx, [rsp+480h+var_440]
0x180125a66  test    ebx, ebx
0x180125a68  jns     short loc_180125A9B
0x180125a6a  lea     rcx, [rsp+480h+var_430]
0x180125a6f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180125a74  nop
0x180125a75  lea     rcx, [rsp+480h+var_428]; this
0x180125a7a  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180125a7f  nop
0x180125a80  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180125a85  mov     r8d, [rsp+480h+var_440]; int
0x180125a8a  mov     rdx, r15; unsigned __int16 *
0x180125a8d  mov     rcx, rax; this
0x180125a90  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180125a95  nop
0x180125a96  jmp     loc_180125F36
0x180125a9b  lea     rcx, [rbp+380h+var_320]; this
0x180125a9f  call    ??0DCDocument@@QEAA@XZ; DCDocument::DCDocument(void)
0x180125aa4  nop
0x180125aa5  lea     rdx, [rbp+380h+var_380]
0x180125aa9  cmp     [rbp+380h+var_368], r12
0x180125aad  cmova   rdx, [rbp+380h+var_380]
0x180125ab2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180125ab6  mov     r8, rbx
0x180125ab9  inc     r8
0x180125abc  cmp     [rdx+r8*2], r14w
0x180125ac1  jnz     short loc_180125AB9
0x180125ac3  lea     rcx, [rbp+380h+var_320]
0x180125ac7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180125acc  lea     rdx, [rbp+380h+var_3A0]
0x180125ad0  cmp     [rbp+380h+var_388], r12
0x180125ad4  cmova   rdx, [rbp+380h+var_3A0]
0x180125ad9  mov     r8, rbx
0x180125adc  inc     r8
0x180125adf  cmp     [rdx+r8*2], r14w
0x180125ae4  jnz     short loc_180125ADC
0x180125ae6  lea     rcx, [rbp+380h+var_300]
0x180125aed  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180125af2  lea     rdx, [rbp+380h+var_360]
0x180125af6  cmp     [rbp+380h+var_348], r12
0x180125afa  cmova   rdx, [rbp+380h+var_360]
0x180125aff  inc     rbx
0x180125b02  cmp     [rdx+rbx*2], r14w
0x180125b07  jnz     short loc_180125AFF
0x180125b09  mov     r8, rbx
0x180125b0c  lea     rcx, [rbp+380h+var_2C0]
0x180125b13  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180125b18  lea     r8, [rbp+380h+var_360]
0x180125b1c  cmp     [rbp+380h+var_348], r12
0x180125b20  cmova   r8, [rbp+380h+var_360]
0x180125b25  mov     dword ptr [rsp+480h+var_458], 2
0x180125b2d  lea     rax, [rbp+380h+var_320]
0x180125b31  mov     [rsp+480h+var_460], rax; int
0x180125b36  xor     r9d, r9d
0x180125b39  mov     rdx, [rsp+480h+var_430]
0x180125b3e  lea     rcx, [rsp+480h+var_428]
0x180125b43  call    ?DeclaredConfigurationStore_GetPersistedDocument@@YAJPEAUDeclaredConfigurationScopeData@@PEAUHKEY__@@PEBG2PEAVDCDocument@@W4DCPersistedDocType@@@Z; DeclaredConfigurationStore_GetPersistedDocument(DeclaredConfigurationScopeData *,HKEY__ *,ushort const *,ushort const *,DCDocument *,DCPersistedDocType)
0x180125b48  mov     ebx, eax
0x180125b4a  mov     [rsp+480h+var_440], eax
0x180125b4e  test    eax, eax
0x180125b50  jns     short loc_180125B8D
0x180125b52  lea     rcx, [rbp+380h+var_320]; this
0x180125b56  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x180125b5b  nop
0x180125b5c  lea     rcx, [rsp+480h+var_430]
0x180125b61  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180125b66  nop
0x180125b67  lea     rcx, [rsp+480h+var_428]; this
0x180125b6c  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180125b71  nop
0x180125b72  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180125b77  mov     r8d, [rsp+480h+var_440]; int
0x180125b7c  mov     rdx, r15; unsigned __int16 *
0x180125b7f  mov     rcx, rax; this
0x180125b82  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180125b87  nop
0x180125b88  jmp     loc_180125F36
0x180125b8d  test    byte ptr [rbp+380h+var_7C], 1
0x180125b94  jnz     short loc_180125BA3
0x180125b96  test    byte ptr [rbp+380h+var_7C], 2
0x180125b9d  jz      loc_180125F6F
0x180125ba3  mov     [rsp+480h+var_43C], r14b
0x180125ba8  lea     r8, [rsp+480h+var_43C]; bool *
0x180125bad  lea     rdx, [rbp+380h+var_320]; struct DCDocument *
0x180125bb1  lea     rcx, [rsp+480h+var_428]; struct DeclaredConfigurationScopeData *
0x180125bb6  call    ?DeclaredConfigurationStore_CheckIfAllInstanceDataPresent@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@PEA_N@Z; DeclaredConfigurationStore_CheckIfAllInstanceDataPresent(DeclaredConfigurationScopeData *,DCDocument *,bool *)
0x180125bbb  mov     ebx, eax
0x180125bbd  test    eax, eax
0x180125bbf  jns     short loc_180125C18
0x180125bc1  mov     rcx, [rbp+388h]; this
0x180125bc8  mov     r9d, eax; char *
0x180125bcb  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180125bd2  mov     edx, 72h ; 'r'; void *
0x180125bd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125bdc  nop
0x180125bdd  lea     rcx, [rbp+380h+var_320]; this
0x180125be1  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x180125be6  nop
0x180125be7  lea     rcx, [rsp+480h+var_430]
0x180125bec  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180125bf1  nop
0x180125bf2  lea     rcx, [rsp+480h+var_428]; this
0x180125bf7  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180125bfc  nop
0x180125bfd  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180125c02  mov     r8d, [rsp+480h+var_440]; int
0x180125c07  mov     rdx, r15; unsigned __int16 *
0x180125c0a  mov     rcx, rax; this
0x180125c0d  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180125c12  nop
0x180125c13  jmp     loc_180125F36
0x180125c18  cmp     [rsp+480h+var_43C], r14b
0x180125c1d  jnz     loc_180125F5D
0x180125c23  or      [rbp+380h+var_7C], 2
0x180125c2a  lea     rcx, [rbp+380h+pvarg]; pvarg
0x180125c2e  call    cs:__imp_VariantInit
0x180125c34  nop
0x180125c35  mov     eax, 3
0x180125c3a  mov     word ptr [rbp+380h+pvarg], ax
0x180125c3e  mov     dword ptr [rbp+380h+pvarg+8], 29h ; ')'
0x180125c45  lea     r8, [rbp+380h+var_360]
0x180125c49  cmp     [rbp+380h+var_348], r12
0x180125c4d  cmova   r8, [rbp+380h+var_360]; unsigned __int16 *
0x180125c52  lea     rdx, [rbp+380h+var_380]
0x180125c56  cmp     [rbp+380h+var_368], r12
0x180125c5a  cmova   rdx, [rbp+380h+var_380]; unsigned __int16 *
0x180125c5f  lea     rax, [rbp+380h+pvarg]
0x180125c63  mov     [rsp+480h+var_448], rax; struct tagVARIANT *
0x180125c68  lea     rax, ValueName; "state"
0x180125c6f  mov     [rsp+480h+lpValueName], rax; lpValueName
0x180125c74  mov     [rsp+480h+var_458], r14; unsigned __int16 *
0x180125c79  mov     [rsp+480h+var_460], r14; int
0x180125c7e  xor     r9d, r9d; unsigned __int16 *
0x180125c81  lea     rcx, [rsp+480h+var_428]; struct DeclaredConfigurationScopeData *
0x180125c86  call    ?DeclaredConfigurationStore_WriteResultData@@YAJPEAUDeclaredConfigurationScopeData@@PEBG11111PEAUtagVARIANT@@@Z; DeclaredConfigurationStore_WriteResultData(DeclaredConfigurationScopeData *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,tagVARIANT *)
  ... truncated ...
```
