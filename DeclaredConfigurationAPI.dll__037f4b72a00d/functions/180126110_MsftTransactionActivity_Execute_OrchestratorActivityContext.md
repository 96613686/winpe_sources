# MsftTransactionActivity::Execute(OrchestratorActivityContext *)

- ea: `0x180126110`
- end: `0x180126962`
- name: `?Execute@MsftTransactionActivity@@UEAAJPEAVOrchestratorActivityContext@@@Z`
- size: `2130`
- prototype: `__int64 __fastcall(MsftTransactionActivity *__hidden this, struct OrchestratorActivityContext *)`
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
- `0x180126110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012628b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180126321`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012628b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180126321`
- `OLEAUT32!__imp_SysAllocString` at `0x18012623c`
- `OLEAUT32!__imp_SysAllocString` at `0x1801262fd`
- `OLEAUT32!__imp_SysAllocString` at `0x18012633c`
- `OLEAUT32!__imp_SysAllocString` at `0x18012623c`
- `OLEAUT32!__imp_SysAllocString` at `0x1801262fd`
- `OLEAUT32!__imp_SysAllocString` at `0x18012633c`
- `OLEAUT32!__imp_VariantInit` at `0x18012657e`
- `OLEAUT32!__imp_VariantInit` at `0x18012657e`
- `OLEAUT32!__imp_VariantClear` at `0x180126613`
- `OLEAUT32!__imp_VariantClear` at `0x1801266a2`
- `OLEAUT32!__imp_VariantClear` at `0x18012675b`
- `OLEAUT32!__imp_VariantClear` at `0x18012679e`
- `OLEAUT32!__imp_VariantClear` at `0x180126613`
- `OLEAUT32!__imp_VariantClear` at `0x1801266a2`
- `OLEAUT32!__imp_VariantClear` at `0x18012675b`
- `OLEAUT32!__imp_VariantClear` at `0x18012679e`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1801262a6`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1801262a6`

## string_xrefs

- `0x180126739`: `DeclaredConfigurationStore_GetRefreshFlag`
- `0x18012667f`: `DeclaredConfiguration_UpdateAllCspUriState: failed to update csp/uri state`
- `0x1801265f0`: `DeclaredConfigurationStore_WriteResultData: failed to update doc state`
- `0x1801262c0`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\msfttransactionactivity.cpp`
- `0x18012651b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\msfttransactionactivity.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall MsftTransactionActivity::Execute(
        MsftTransactionActivity *this,
        struct OrchestratorActivityContext *a2)
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
  CDeclaredConfigurationLogger *v27; // rax
  int v28; // eax
  CDeclaredConfigurationLogger *v29; // rax
  const unsigned __int16 *v30; // r8
  const unsigned __int16 *v31; // rdx
  int v32; // eax
  int v33; // ecx
  CDeclaredConfigurationLogger *v34; // rax
  int updated; // eax
  __int64 v36; // rdx
  int v37; // ecx
  const unsigned __int16 *v38; // rdx
  CDeclaredConfigurationLogger *v39; // rax
  CDeclaredConfigurationLogger *v40; // rax
  const unsigned __int16 *v42; // r9
  unsigned __int16 *v43; // r8
  _QWORD *v44; // rdx
  unsigned __int16 **v45; // rcx
  unsigned __int16 **v46; // rax
  OLECHAR **v47; // r9
  OLECHAR **v48; // r8
  CDeclaredConfigurationLogger *v49; // rax
  CDeclaredConfigurationLogger *v50; // rax
  int v51; // [rsp+20h] [rbp-E0h]
  int v52; // [rsp+20h] [rbp-E0h]
  int EnrollmentIdSidStateDocIdKey; // [rsp+40h] [rbp-C0h] BYREF
  bool v54; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v55; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v56; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR *v57[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v58; // [rsp+68h] [rbp-98h]
  int v59; // [rsp+6Ch] [rbp-94h]
  OLECHAR *v60; // [rsp+70h] [rbp-90h] BYREF
  int v61; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  int v63; // [rsp+A0h] [rbp-60h] BYREF
  int v64; // [rsp+A4h] [rbp-5Ch] BYREF
  int *v65; // [rsp+A8h] [rbp-58h]
  char v66; // [rsp+B0h] [rbp-50h]
  OLECHAR *psz[3]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v68; // [rsp+D8h] [rbp-28h]
  OLECHAR *v69[3]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v70; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v71[3]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v72; // [rsp+118h] [rbp+18h]
  unsigned __int16 *v73[3]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int64 v74; // [rsp+138h] [rbp+38h]
  _QWORD v75[4]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 *v76[4]; // [rsp+160h] [rbp+60h] BYREF
  char *v77; // [rsp+180h] [rbp+80h] BYREF
  char *v78; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned int v79; // [rsp+404h] [rbp+304h]
  wil::details::in1diag3 *retaddr; // [rsp+498h] [rbp+398h]

  EnrollmentIdSidStateDocIdKey = 0;
  OrchestratorDCInfo::OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  v60 = 0;
  Logger = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogOrchestratorEnterFunction(Logger, L"MsftTransactionActivity::Execute");
  v65 = &EnrollmentIdSidStateDocIdKey;
  v66 = 1;
  v55 = 0;
  v64 = 0;
  v63 = 0;
  *(_OWORD *)&pvarg.vt = *(_OWORD *)((char *)a2 + 8);
  Request = OrchestratorDBManager::GetRequest(
              v4,
              (struct _GUID *)&pvarg,
              (struct OrchestratorDCInfo *)psz,
              (enum StateMachineTypeTag *)&v55,
              (enum DMOrchestratorState *)&v64,
              (enum DCLifecycleNotificationType *)&v63);
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
      L"MsftTransactionActivity::Execute",
      EnrollmentIdSidStateDocIdKey);
    goto LABEL_69;
  }
  if ( v55 != 5 )
  {
    v9 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v9,
      L"MsftTransactionActivity::Execute",
      EnrollmentIdSidStateDocIdKey);
    PersistedDocument = -2147024846;
LABEL_69:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
    OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)psz);
    return (unsigned int)PersistedDocument;
  }
  *(_OWORD *)v57 = 0;
  v58 = 0;
  v59 = 63;
  v10 = (const OLECHAR *)psz;
  if ( v68 > 7 )
    v10 = psz[0];
  v57[0] = SysAllocString(v10);
  if ( !v57[0] )
  {
LABEL_10:
    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v57);
    v11 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v11,
      L"MsftTransactionActivity::Execute",
      EnrollmentIdSidStateDocIdKey);
    PersistedDocument = -2147024882;
    goto LABEL_69;
  }
  v12 = v69;
  if ( v70 > 7 )
    v12 = (OLECHAR **)v69[0];
  if ( !(unsigned int)_o__wcsicmp(v12, L"user") )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v60,
      0);
    ActiveUserSid = DmGetActiveUserSid(&v60);
    PersistedDocument = ActiveUserSid;
    EnrollmentIdSidStateDocIdKey = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicies\\m"
                      "sfttransactionactivity.cpp",
        (const char *)(unsigned int)ActiveUserSid,
        v51);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v57);
      v14 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
        v14,
        L"MsftTransactionActivity::Execute",
        EnrollmentIdSidStateDocIdKey);
      goto LABEL_69;
    }
    v15 = SysAllocString(v60);
    v58 = 1;
LABEL_23:
    v57[1] = v15;
    if ( !v15 )
      goto LABEL_10;
    v56 = 0;
    *(_QWORD *)&pvarg.vt = &v56;
    pvarg.llVal = 0;
    *((_BYTE *)&pvarg.decVal + 16) = 1;
    v18 = (const unsigned __int16 *)v71;
    if ( v72 > 7 )
      v18 = v71[0];
    EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                                     (struct DeclaredConfigurationScopeData *)v57,
                                     v18,
                                     (HKEY *)&pvarg.llVal,
                                     0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&pvarg);
    PersistedDocument = EnrollmentIdSidStateDocIdKey;
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v56);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v57);
      v19 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
        v19,
        L"MsftTransactionActivity::Execute",
        EnrollmentIdSidStateDocIdKey);
      goto LABEL_69;
    }
    DCDocument::DCDocument((DCDocument *)v76);
    v20 = v71;
    if ( v72 > 7 )
      v20 = (unsigned __int16 **)v71[0];
    v21 = -1;
    v22 = -1;
    do
      ++v22;
    while ( *((_WORD *)v20 + v22) );
    std::wstring::_Assign<unsigned short>((char **)v76, v20, (char *)v22);
    v23 = v69;
    if ( v70 > 7 )
      v23 = (OLECHAR **)v69[0];
    v24 = -1;
    do
      ++v24;
    while ( *((_WORD *)v23 + v24) );
    std::wstring::_Assign<unsigned short>(&v77, v23, (char *)v24);
    v25 = v73;
    if ( v74 > 7 )
      v25 = (unsigned __int16 **)v73[0];
    do
      ++v21;
    while ( *((_WORD *)v25 + v21) );
    std::wstring::_Assign<unsigned short>(&v78, v25, (char *)v21);
    v26 = v73;
    if ( v74 > 7 )
      v26 = (unsigned __int16 **)v73[0];
    PersistedDocument = DeclaredConfigurationStore_GetPersistedDocument(
                          (struct DeclaredConfigurationScopeData *)v57,
                          v56,
                          (__int64)v26,
                          0,
                          (__int64)v76,
                          2);
    EnrollmentIdSidStateDocIdKey = PersistedDocument;
    if ( PersistedDocument < 0 )
    {
      DCDocument::~DCDocument((DCDocument *)v76);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v56);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v57);
      v27 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
        v27,
        L"MsftTransactionActivity::Execute",
        EnrollmentIdSidStateDocIdKey);
      goto LABEL_69;
    }
    if ( (v79 & 1) != 0 || (v79 & 2) != 0 )
    {
      v54 = 0;
      v28 = DeclaredConfigurationStore_CheckIfAllInstanceDataPresent(
              (struct DeclaredConfigurationScopeData *)v57,
              (struct DCDocument *)v76,
              &v54);
      PersistedDocument = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x73,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicies\\"
                        "msfttransactionactivity.cpp",
          (const char *)(unsigned int)v28,
          v52);
        DCDocument::~DCDocument((DCDocument *)v76);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v56);
        DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v57);
        v29 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
          v29,
          L"MsftTransactionActivity::Execute",
          EnrollmentIdSidStateDocIdKey);
        goto LABEL_69;
      }
      if ( v54 )
      {
        v79 = v79 & 0xFFFFFFF9 | 4;
      }
      else
      {
        v79 |= 2u;
        VariantInit(&pvarg);
        pvarg.vt = 3;
        pvarg.lVal = 41;
        v30 = (const unsigned __int16 *)v73;
        if ( v74 > 7 )
          v30 = v73[0];
        v31 = (const unsigned __int16 *)v71;
        if ( v72 > 7 )
          v31 = v71[0];
        v32 = DeclaredConfigurationStore_WriteResultData(
                (struct DeclaredConfigurationScopeData *)v57,
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
              (unsigned int)L"MsftTransactionActivity::Execute",
              (unsigned int)L"DeclaredConfigurationStore_WriteResultData: failed to update doc state",
              v32);
LABEL_55:
          PersistedDocument = -2147024875;
          EnrollmentIdSidStateDocIdKey = -2147024875;
          VariantClear(&pvarg);
          DCDocument::~DCDocument((DCDocument *)v76);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v56);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v57);
          v34 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
            v34,
            L"MsftTransactionActivity::Execute",
            EnrollmentIdSidStateDocIdKey);
          goto LABEL_69;
        }
        updated = DeclaredConfiguration_UpdateAllCspUriState(
                    (struct DeclaredConfigurationScopeData *)v57,
                    (struct DCDocument *)v76,
                    &pvarg,
                    0);
        EnrollmentIdSidStateDocIdKey = updated;
        if ( updated < 0 )
        {
          if ( byte_180189FC1 < 0 )
            McTemplateU0zzd_EventWriteTransfer(
              v37,
              (unsigned int)OrchestratorGenericFailure,
              (unsigned int)L"MsftTransactionActivity::Execute",
              (unsigned int)L"DeclaredConfiguration_UpdateAllCspUriState: failed to update csp/uri state",
              updated);
          goto LABEL_55;
        }
        v55 = 0;
        LOBYTE(v36) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::GetImpl'::`2'::impl,
          v36);
        v38 = (const unsigned __int16 *)v76;
        if ( v76[3] > (unsigned __int16 *)7 )
          v38 = v76[0];
        PersistedDocument = DeclaredConfigurationStore_GetRefreshFlag(v57[0], v38, &v55);
        EnrollmentIdSidStateDocIdKey = PersistedDocument;
        if ( (int)(PersistedDocument + 0x80000000) >= 0 && PersistedDocument != -2147024894 )
        {
          if ( byte_180189FC1 < 0 )
          {
            McTemplateU0zzd_EventWriteTransfer(
              PersistedDocument + 0x80000000,
              (unsigned int)OrchestratorGenericFailure,
              (unsigned int)L"ProcessDocsWithPendingInstanceVariable::",
              (unsigned int)L"DeclaredConfigurationStore_GetRefreshFlag",
              PersistedDocument);
            PersistedDocument = EnrollmentIdSidStateDocIdKey;
          }
          VariantClear(&pvarg);
          DCDocument::~DCDocument((DCDocument *)v76);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v56);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v57);
          v39 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
            v39,
            L"MsftTransactionActivity::Execute",
            EnrollmentIdSidStateDocIdKey);
          goto LABEL_69;
        }
        VariantClear(&pvarg);
        if ( !v55 )
        {
          DCDocument::~DCDocument((DCDocument *)v76);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v56);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v57);
          v40 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
            v40,
            L"MsftTransactionActivity::Execute",
            EnrollmentIdSidStateDocIdKey);
          PersistedDocument = -2147024875;
          goto LABEL_69;
        }
      }
    }
    v61 = 0;
    v42 = (const unsigned __int16 *)v69;
    if ( v70 > 7 )
      v42 = v69[0];
    v43 = (unsigned __int16 *)psz;
    if ( v68 > 7 )
      v43 = psz[0];
    PersistedDocument = DeclaredConfigurationStore_ProcessSingleDoc(
                          (struct DeclaredConfigurationScopeData *)v57,
                          (struct DCDocument *)v76,
                          v43,
                          v42,
                          0,
                          &v61);
    EnrollmentIdSidStateDocIdKey = PersistedDocument;
    if ( PersistedDocument < 0 && (byte_180189FC1 & 2) != 0 )
    {
      v44 = v75;
      if ( v75[3] > 7u )
        v44 = (_QWORD *)v75[0];
      v45 = v73;
      if ( v74 > 7 )
        v45 = (unsigned __int16 **)v73[0];
      v46 = v71;
      if ( v72 > 7 )
        v46 = (unsigned __int16 **)v71[0];
      v47 = v69;
      if ( v70 > 7 )
        LODWORD(v47) = v69[0];
      v48 = psz;
      if ( v68 > 7 )
        LODWORD(v48) = psz[0];
      McTemplateU0zzzzzd_EventWriteTransfer(
        (_DWORD)v45,
        (unsigned int)DMOrchestratorProcessSingleDocResult,
        (_DWORD)v48,
        (_DWORD)v47,
        (__int64)v46,
        (__int64)v45,
        (__int64)v44,
        PersistedDocument);
      PersistedDocument = EnrollmentIdSidStateDocIdKey;
    }
    *((_DWORD *)a2 + 146) = v61;
    DCDocument::~DCDocument((DCDocument *)v76);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v56);
    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v57);
    v49 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v49,
      L"MsftTransactionActivity::Execute",
      EnrollmentIdSidStateDocIdKey);
    goto LABEL_69;
  }
  v16 = v69;
  if ( v70 > 7 )
    v16 = (OLECHAR **)v69[0];
  if ( !(unsigned int)_o__wcsicmp(v16, L"device") )
  {
    v17 = (const OLECHAR *)v69;
    if ( v70 > 7 )
      v17 = v69[0];
    v15 = SysAllocString(v17);
    goto LABEL_23;
  }
  DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v57);
  v50 = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
    v50,
    L"MsftTransactionActivity::Execute",
    EnrollmentIdSidStateDocIdKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
  OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180126110  push    rbp
0x180126112  push    rbx
0x180126113  push    rsi
0x180126114  push    rdi
0x180126115  push    r14
0x180126117  push    r15
0x180126119  lea     rbp, [rsp-368h]
0x180126121  sub     rsp, 468h
0x180126128  mov     rax, cs:__security_cookie
0x18012612f  xor     rax, rsp
0x180126132  mov     [rbp+390h+var_40], rax
0x180126139  mov     rdi, rdx
0x18012613c  xor     esi, esi
0x18012613e  mov     [rsp+490h+var_450], esi
0x180126142  lea     rcx, [rbp+390h+psz]; this
0x180126146  call    ??0OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::OrchestratorDCInfo(void)
0x18012614b  nop
0x18012614c  mov     [rsp+490h+var_420], rsi
0x180126151  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180126156  lea     r14, aMsfttransactio_0; "MsftTransactionActivity::Execute"
0x18012615d  mov     rdx, r14; unsigned __int16 *
0x180126160  mov     rcx, rax; this
0x180126163  call    ?LogOrchestratorEnterFunction@CDeclaredConfigurationLogger@@QEAAXPEBG@Z; CDeclaredConfigurationLogger::LogOrchestratorEnterFunction(ushort const *)
0x180126168  lea     rax, [rsp+490h+var_450]
0x18012616d  mov     [rbp+390h+var_3E8], rax
0x180126171  mov     [rbp+390h+var_3E0], 1
0x180126175  mov     [rsp+490h+var_448], esi
0x180126179  mov     [rbp+390h+var_3EC], esi
0x18012617c  mov     [rbp+390h+var_3F0], esi
0x18012617f  movups  xmm0, xmmword ptr [rdi+8]
0x180126183  movdqu  xmmword ptr [rbp+390h+pvarg], xmm0
0x180126188  lea     rax, [rbp+390h+var_3F0]
0x18012618c  mov     [rsp+490h+var_468], rax; enum DCLifecycleNotificationType *
0x180126191  lea     rax, [rbp+390h+var_3EC]
0x180126195  mov     [rsp+490h+var_470], rax; int
0x18012619a  lea     r9, [rsp+490h+var_448]; enum StateMachineTypeTag *
0x18012619f  lea     r8, [rbp+390h+psz]; struct OrchestratorDCInfo *
0x1801261a3  lea     rdx, [rbp+390h+pvarg]; struct _GUID
0x1801261a7  call    ?GetRequest@OrchestratorDBManager@@QEAAJU_GUID@@PEAUOrchestratorDCInfo@@PEAW4StateMachineTypeTag@@PEAW4DMOrchestratorState@@PEAW4DCLifecycleNotificationType@@@Z; OrchestratorDBManager::GetRequest(_GUID,OrchestratorDCInfo *,StateMachineTypeTag *,DMOrchestratorState *,DCLifecycleNotificationType *)
0x1801261ac  mov     ebx, eax
0x1801261ae  mov     [rsp+490h+var_450], eax
0x1801261b2  test    eax, eax
0x1801261b4  jns     short loc_1801261ED
0x1801261b6  test    cs:byte_180189FC1, 2
0x1801261bd  jz      short loc_1801261D2
0x1801261bf  mov     r8d, eax
0x1801261c2  lea     rdx, EnterpriseDiagnosticsDeclaredConfigurationGetRequestFailure
0x1801261c9  call    McTemplateU0q_EventWriteTransfer
0x1801261ce  mov     ebx, [rsp+490h+var_450]
0x1801261d2  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1801261d7  mov     r8d, [rsp+490h+var_450]; int
0x1801261dc  mov     rdx, r14; unsigned __int16 *
0x1801261df  mov     rcx, rax; this
0x1801261e2  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1801261e7  nop
0x1801261e8  jmp     loc_1801267E5
0x1801261ed  cmp     [rsp+490h+var_448], 5
0x1801261f2  jz      short loc_180126214
0x1801261f4  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1801261f9  mov     r8d, [rsp+490h+var_450]; int
0x1801261fe  mov     rdx, r14; unsigned __int16 *
0x180126201  mov     rcx, rax; this
0x180126204  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180126209  nop
0x18012620a  mov     ebx, 80070032h
0x18012620f  jmp     loc_1801267E5
0x180126214  xorps   xmm0, xmm0
0x180126217  movdqu  xmmword ptr [rsp+490h+var_438], xmm0
0x18012621d  mov     [rsp+490h+var_428], esi
0x180126221  mov     [rsp+490h+var_424], 3Fh ; '?'
0x180126229  lea     rcx, [rbp+390h+psz]
0x18012622d  mov     r15d, 7
0x180126233  cmp     [rbp+390h+var_3B8], r15
0x180126237  cmova   rcx, [rbp+390h+psz]; psz
0x18012623c  call    cs:__imp_SysAllocString
0x180126242  mov     [rsp+490h+var_438], rax
0x180126247  test    rax, rax
0x18012624a  jnz     short loc_180126277
0x18012624c  lea     rcx, [rsp+490h+var_438]; this
0x180126251  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180126256  nop
0x180126257  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18012625c  mov     r8d, [rsp+490h+var_450]; int
0x180126261  mov     rdx, r14; unsigned __int16 *
0x180126264  mov     rcx, rax; this
0x180126267  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x18012626c  nop
0x18012626d  mov     ebx, 8007000Eh
0x180126272  jmp     loc_1801267E5
0x180126277  lea     rcx, [rbp+390h+var_3B0]
0x18012627b  cmp     [rbp+390h+var_398], r15
0x18012627f  cmova   rcx, [rbp+390h+var_3B0]
0x180126284  lea     rdx, aUser_0; "user"
0x18012628b  call    cs:__imp__o__wcsicmp
0x180126291  test    eax, eax
0x180126293  jnz     short loc_18012630D
0x180126295  xor     edx, edx
0x180126297  lea     rcx, [rsp+490h+var_420]
0x18012629c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801262a1  lea     rcx, [rsp+490h+var_420]
0x1801262a6  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1801262ac  mov     ebx, eax
0x1801262ae  mov     [rsp+490h+var_450], eax
0x1801262b2  test    eax, eax
0x1801262b4  jns     short loc_1801262F8
0x1801262b6  mov     rcx, [rbp+398h]; this
0x1801262bd  mov     r9d, eax; char *
0x1801262c0  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1801262c7  mov     edx, 45h ; 'E'; void *
0x1801262cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801262d1  nop
0x1801262d2  lea     rcx, [rsp+490h+var_438]; this
0x1801262d7  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x1801262dc  nop
0x1801262dd  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1801262e2  mov     r8d, [rsp+490h+var_450]; int
0x1801262e7  mov     rdx, r14; unsigned __int16 *
0x1801262ea  mov     rcx, rax; this
0x1801262ed  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1801262f2  nop
0x1801262f3  jmp     loc_1801267E5
0x1801262f8  mov     rcx, [rsp+490h+var_420]; psz
0x1801262fd  call    cs:__imp_SysAllocString
0x180126303  mov     [rsp+490h+var_428], 1
0x18012630b  jmp     short loc_180126342
0x18012630d  lea     rcx, [rbp+390h+var_3B0]
0x180126311  cmp     [rbp+390h+var_398], r15
0x180126315  cmova   rcx, [rbp+390h+var_3B0]
0x18012631a  lea     rdx, aDevice_4; "device"
0x180126321  call    cs:__imp__o__wcsicmp
0x180126327  test    eax, eax
0x180126329  jnz     loc_180126909
0x18012632f  lea     rcx, [rbp+390h+var_3B0]
0x180126333  cmp     [rbp+390h+var_398], r15
0x180126337  cmova   rcx, [rbp+390h+var_3B0]; psz
0x18012633c  call    cs:__imp_SysAllocString
0x180126342  mov     [rsp+490h+var_438+8], rax
0x180126347  test    rax, rax
0x18012634a  jnz     short loc_180126372
0x18012634c  lea     rcx, [rsp+490h+var_438]; this
0x180126351  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180126356  nop
0x180126357  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18012635c  mov     r8d, [rsp+490h+var_450]; int
0x180126361  mov     rdx, r14; unsigned __int16 *
0x180126364  mov     rcx, rax; this
0x180126367  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x18012636c  nop
0x18012636d  jmp     loc_18012626D
0x180126372  mov     [rsp+490h+var_440], rsi
0x180126377  lea     rax, [rsp+490h+var_440]
0x18012637c  mov     qword ptr [rbp+390h+pvarg], rax
0x180126380  mov     qword ptr [rbp+390h+pvarg+8], rsi
0x180126384  mov     byte ptr [rbp+390h+pvarg+10h], 1
0x180126388  lea     rdx, [rbp+390h+var_390]
0x18012638c  cmp     [rbp+390h+var_378], r15
0x180126390  cmova   rdx, [rbp+390h+var_390]; unsigned __int16 *
0x180126395  xor     r9d, r9d; int
0x180126398  lea     r8, [rbp+390h+pvarg+8]; HKEY *
0x18012639c  lea     rcx, [rsp+490h+var_438]; struct DeclaredConfigurationScopeData *
0x1801263a1  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x1801263a6  mov     [rsp+490h+var_450], eax
0x1801263aa  lea     rcx, [rbp+390h+pvarg]
0x1801263ae  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1801263b3  mov     ebx, [rsp+490h+var_450]
0x1801263b7  test    ebx, ebx
0x1801263b9  jns     short loc_1801263EC
0x1801263bb  lea     rcx, [rsp+490h+var_440]
0x1801263c0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801263c5  nop
0x1801263c6  lea     rcx, [rsp+490h+var_438]; this
0x1801263cb  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x1801263d0  nop
0x1801263d1  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1801263d6  mov     r8d, [rsp+490h+var_450]; int
0x1801263db  mov     rdx, r14; unsigned __int16 *
0x1801263de  mov     rcx, rax; this
0x1801263e1  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1801263e6  nop
0x1801263e7  jmp     loc_1801267E5
0x1801263ec  lea     rcx, [rbp+390h+var_330]; this
0x1801263f0  call    ??0DCDocument@@QEAA@XZ; DCDocument::DCDocument(void)
0x1801263f5  nop
0x1801263f6  lea     rdx, [rbp+390h+var_390]
0x1801263fa  cmp     [rbp+390h+var_378], r15
0x1801263fe  cmova   rdx, [rbp+390h+var_390]
0x180126403  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180126407  mov     r8, rbx
0x18012640a  inc     r8
0x18012640d  cmp     [rdx+r8*2], si
0x180126412  jnz     short loc_18012640A
0x180126414  lea     rcx, [rbp+390h+var_330]
0x180126418  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18012641d  lea     rdx, [rbp+390h+var_3B0]
0x180126421  cmp     [rbp+390h+var_398], r15
0x180126425  cmova   rdx, [rbp+390h+var_3B0]
0x18012642a  mov     r8, rbx
0x18012642d  inc     r8
0x180126430  cmp     [rdx+r8*2], si
0x180126435  jnz     short loc_18012642D
0x180126437  lea     rcx, [rbp+390h+var_310]
0x18012643e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180126443  lea     rdx, [rbp+390h+var_370]
0x180126447  cmp     [rbp+390h+var_358], r15
0x18012644b  cmova   rdx, [rbp+390h+var_370]
0x180126450  inc     rbx
0x180126453  cmp     [rdx+rbx*2], si
0x180126457  jnz     short loc_180126450
0x180126459  mov     r8, rbx
0x18012645c  lea     rcx, [rbp+390h+var_2D0]
0x180126463  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180126468  lea     r8, [rbp+390h+var_370]
0x18012646c  cmp     [rbp+390h+var_358], r15
0x180126470  cmova   r8, [rbp+390h+var_370]
0x180126475  mov     dword ptr [rsp+490h+var_468], 2
0x18012647d  lea     rax, [rbp+390h+var_330]
0x180126481  mov     [rsp+490h+var_470], rax; int
0x180126486  xor     r9d, r9d
0x180126489  mov     rdx, [rsp+490h+var_440]
0x18012648e  lea     rcx, [rsp+490h+var_438]
0x180126493  call    ?DeclaredConfigurationStore_GetPersistedDocument@@YAJPEAUDeclaredConfigurationScopeData@@PEAUHKEY__@@PEBG2PEAVDCDocument@@W4DCPersistedDocType@@@Z; DeclaredConfigurationStore_GetPersistedDocument(DeclaredConfigurationScopeData *,HKEY__ *,ushort const *,ushort const *,DCDocument *,DCPersistedDocType)
0x180126498  mov     ebx, eax
0x18012649a  mov     [rsp+490h+var_450], eax
0x18012649e  test    eax, eax
0x1801264a0  jns     short loc_1801264DD
0x1801264a2  lea     rcx, [rbp+390h+var_330]; this
0x1801264a6  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x1801264ab  nop
0x1801264ac  lea     rcx, [rsp+490h+var_440]
0x1801264b1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801264b6  nop
0x1801264b7  lea     rcx, [rsp+490h+var_438]; this
0x1801264bc  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x1801264c1  nop
0x1801264c2  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1801264c7  mov     r8d, [rsp+490h+var_450]; int
0x1801264cc  mov     rdx, r14; unsigned __int16 *
0x1801264cf  mov     rcx, rax; this
0x1801264d2  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1801264d7  nop
0x1801264d8  jmp     loc_1801267E5
0x1801264dd  test    byte ptr [rbp+390h+var_8C], 1
0x1801264e4  jnz     short loc_1801264F3
0x1801264e6  test    byte ptr [rbp+390h+var_8C], 2
0x1801264ed  jz      loc_180126812
0x1801264f3  mov     [rsp+490h+var_44C], sil
0x1801264f8  lea     r8, [rsp+490h+var_44C]; bool *
0x1801264fd  lea     rdx, [rbp+390h+var_330]; struct DCDocument *
0x180126501  lea     rcx, [rsp+490h+var_438]; struct DeclaredConfigurationScopeData *
0x180126506  call    ?DeclaredConfigurationStore_CheckIfAllInstanceDataPresent@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@PEA_N@Z; DeclaredConfigurationStore_CheckIfAllInstanceDataPresent(DeclaredConfigurationScopeData *,DCDocument *,bool *)
0x18012650b  mov     ebx, eax
0x18012650d  test    eax, eax
0x18012650f  jns     short loc_180126568
0x180126511  mov     rcx, [rbp+398h]; this
0x180126518  mov     r9d, eax; char *
0x18012651b  lea     r8, aOnecoreuapAdmi_38; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180126522  mov     edx, 73h ; 's'; void *
0x180126527  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012652c  nop
0x18012652d  lea     rcx, [rbp+390h+var_330]; this
0x180126531  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x180126536  nop
0x180126537  lea     rcx, [rsp+490h+var_440]
0x18012653c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180126541  nop
0x180126542  lea     rcx, [rsp+490h+var_438]; this
0x180126547  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18012654c  nop
0x18012654d  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180126552  mov     r8d, [rsp+490h+var_450]; int
0x180126557  mov     rdx, r14; unsigned __int16 *
0x18012655a  mov     rcx, rax; this
0x18012655d  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180126562  nop
0x180126563  jmp     loc_1801267E5
0x180126568  cmp     [rsp+490h+var_44C], sil
0x18012656d  jnz     loc_180126800
0x180126573  or      [rbp+390h+var_8C], 2
0x18012657a  lea     rcx, [rbp+390h+pvarg]; pvarg
0x18012657e  call    cs:__imp_VariantInit
0x180126584  nop
0x180126585  mov     eax, 3
0x18012658a  mov     word ptr [rbp+390h+pvarg], ax
0x18012658e  mov     dword ptr [rbp+390h+pvarg+8], 29h ; ')'
0x180126595  lea     r8, [rbp+390h+var_370]
0x180126599  cmp     [rbp+390h+var_358], r15
0x18012659d  cmova   r8, [rbp+390h+var_370]; unsigned __int16 *
0x1801265a2  lea     rdx, [rbp+390h+var_390]
0x1801265a6  cmp     [rbp+390h+var_378], r15
0x1801265aa  cmova   rdx, [rbp+390h+var_390]; unsigned __int16 *
0x1801265af  lea     rax, [rbp+390h+pvarg]
0x1801265b3  mov     [rsp+490h+var_458], rax; struct tagVARIANT *
0x1801265b8  lea     rax, ValueName; "state"
0x1801265bf  mov     [rsp+490h+lpValueName], rax; lpValueName
0x1801265c4  mov     [rsp+490h+var_468], rsi; unsigned __int16 *
0x1801265c9  mov     [rsp+490h+var_470], rsi; unsigned __int16 *
0x1801265ce  xor     r9d, r9d; unsigned __int16 *
0x1801265d1  lea     rcx, [rsp+490h+var_438]; struct DeclaredConfigurationScopeData *
0x1801265d6  call    ?DeclaredConfigurationStore_WriteResultData@@YAJPEAUDeclaredConfigurationScopeData@@PEBG11111PEAUtagVARIANT@@@Z; DeclaredConfigurationStore_WriteResultData(DeclaredConfigurationScopeData *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,tagVARIANT *)
0x1801265db  mov     [rsp+490h+var_450], eax
  ... truncated ...
```
