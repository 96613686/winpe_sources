# AdmxDocumentActivity::Execute(OrchestratorActivityContext *)

- ea: `0x180123d20`
- end: `0x18012460c`
- name: `?Execute@AdmxDocumentActivity@@UEAAJPEAVOrchestratorActivityContext@@@Z`
- size: `2284`
- prototype: `__int64 __fastcall(AdmxDocumentActivity *__hidden this, struct OrchestratorActivityContext *)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180018cc4`
- `0x18001c32c`
- `0x18001ce5c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18001d37c`
- `0x18001def8`
- `0x18004d158`
- `0x180056bcc`
- `0x180058b08`
- `0x180058b3c`
- `0x1800725e0`
- `0x180076c10`
- `0x18007f370`
- `0x180086c10`
- `0x18008bb70`
- `0x1800a212c`
- `0x1800f5c8c`
- `0x1800f9c1c`
- `0x1800f9cb4`
- `0x1800fbe70`
- `0x18010995c`
- `0x18010aedc`
- `0x18010b200`
- `0x18010bf10`
- `0x180123d20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180123ea7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180123f3d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124111`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124484`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180123ea7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180123f3d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124111`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124484`
- `OLEAUT32!__imp_SysAllocString` at `0x180123e58`
- `OLEAUT32!__imp_SysAllocString` at `0x180123f19`
- `OLEAUT32!__imp_SysAllocString` at `0x180123f58`
- `OLEAUT32!__imp_SysAllocString` at `0x180123e58`
- `OLEAUT32!__imp_SysAllocString` at `0x180123f19`
- `OLEAUT32!__imp_SysAllocString` at `0x180123f58`
- `OLEAUT32!__imp_VariantInit` at `0x180124172`
- `OLEAUT32!__imp_VariantInit` at `0x180124172`
- `OLEAUT32!__imp_VariantClear` at `0x180124204`
- `OLEAUT32!__imp_VariantClear` at `0x180124293`
- `OLEAUT32!__imp_VariantClear` at `0x1801242fd`
- `OLEAUT32!__imp_VariantClear` at `0x180124204`
- `OLEAUT32!__imp_VariantClear` at `0x180124293`
- `OLEAUT32!__imp_VariantClear` at `0x1801242fd`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180123ec2`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180123ec2`

## string_xrefs

- `0x18012447d`: `msftadmxinstall`
- `0x18012410a`: `msftadmxconfig`
- `0x18012409f`: `DeclaredConfigurationStore_GetPersistedDocument`
- `0x1801241e6`: `DeclaredConfigurationStore_WriteResultData update doc state to DocMissingInstanceData`
- `0x180124270`: `DeclaredConfiguration_UpdateAllCspUriState: failed to update csp/uri state`
- `0x1801242e2`: `ADMX config can't proceed due to missing ADMX install doc`
- `0x180123edc`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\admxdocumentactivity.cpp`
- `0x180123fe1`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\admxdocumentactivity.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall AdmxDocumentActivity::Execute(AdmxDocumentActivity *this, struct OrchestratorActivityContext *a2)
{
  CDeclaredConfigurationLogger *Logger; // rax
  __int128 v4; // xmm6
  OrchestratorDBManager *v5; // rcx
  int Request; // eax
  __int64 v7; // rcx
  unsigned int v8; // ebx
  CDeclaredConfigurationLogger *v9; // rax
  CDeclaredConfigurationLogger *v10; // rax
  const OLECHAR *v11; // rcx
  CDeclaredConfigurationLogger *v12; // rax
  OLECHAR **v13; // rcx
  int ActiveUserSid; // eax
  CDeclaredConfigurationLogger *v15; // rax
  BSTR v16; // rax
  OLECHAR **v17; // rcx
  const OLECHAR *v18; // rcx
  const unsigned __int16 *v19; // rdx
  CDeclaredConfigurationLogger *v20; // rax
  unsigned __int16 **v21; // r8
  int PersistedDocument; // eax
  int v23; // ecx
  _QWORD *v24; // rcx
  OrchestratorDBManager *v25; // rcx
  int CompleteAdmxInstallRequest; // eax
  __int64 v27; // rcx
  unsigned int updated; // edi
  const unsigned __int16 *v29; // r8
  const unsigned __int16 *v30; // rdx
  int v31; // eax
  int v32; // ecx
  CDeclaredConfigurationLogger *v33; // rax
  int v34; // ecx
  CDeclaredConfigurationLogger *v35; // rax
  CDeclaredConfigurationLogger *v36; // rax
  const unsigned __int16 *v37; // r9
  unsigned __int16 *v38; // r8
  OrchestratorDBManager *v39; // rcx
  _QWORD *v40; // rdx
  unsigned __int16 **v41; // rcx
  unsigned __int16 **v42; // rax
  OLECHAR **v43; // r9
  OLECHAR **v44; // r8
  CDeclaredConfigurationLogger *v45; // rax
  _QWORD *v47; // rcx
  const unsigned __int16 *v48; // r9
  unsigned __int16 *v49; // r8
  int v50; // eax
  OrchestratorDBManager *v51; // rcx
  char v52; // r10
  _QWORD *v53; // rdx
  unsigned __int16 **v54; // rcx
  unsigned __int16 **v55; // rax
  OLECHAR **v56; // r9
  OLECHAR **v57; // r8
  CDeclaredConfigurationLogger *v58; // rax
  CDeclaredConfigurationLogger *v59; // rax
  int v60; // [rsp+28h] [rbp-E0h]
  char *v61; // [rsp+48h] [rbp-C0h] BYREF
  HKEY v62; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int16 *v63[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v64; // [rsp+68h] [rbp-A0h]
  unsigned __int16 *v65[3]; // [rsp+70h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-80h] BYREF
  int v67; // [rsp+A0h] [rbp-68h] BYREF
  int v68; // [rsp+A4h] [rbp-64h] BYREF
  char **v69; // [rsp+A8h] [rbp-60h]
  char v70; // [rsp+B0h] [rbp-58h]
  OLECHAR *psz[3]; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int64 v72; // [rsp+D0h] [rbp-38h]
  OLECHAR *v73[3]; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int64 v74; // [rsp+F0h] [rbp-18h]
  unsigned __int16 *v75[3]; // [rsp+F8h] [rbp-10h] BYREF
  unsigned __int64 v76; // [rsp+110h] [rbp+8h]
  unsigned __int16 *v77[3]; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int64 v78; // [rsp+130h] [rbp+28h]
  _QWORD v79[3]; // [rsp+138h] [rbp+30h] BYREF
  unsigned __int64 v80; // [rsp+150h] [rbp+48h]
  _BYTE v81[32]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v82[64]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v83[416]; // [rsp+1B8h] [rbp+B0h] BYREF
  _QWORD v84[3]; // [rsp+358h] [rbp+250h] BYREF
  unsigned __int64 v85; // [rsp+370h] [rbp+268h]
  wil::details::in1diag3 *retaddr; // [rsp+4A0h] [rbp+398h]

  v61 = 0;
  OrchestratorDCInfo::OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  v65[0] = 0;
  Logger = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogOrchestratorEnterFunction(Logger, L"AdmxDocumentActivity::Execute");
  v69 = &v61;
  v70 = 1;
  v4 = *(_OWORD *)((char *)a2 + 8);
  v68 = 0;
  v67 = 0;
  *(_OWORD *)&v65[1] = v4;
  Request = OrchestratorDBManager::GetRequest(
              v5,
              (struct _GUID *)&v65[1],
              (struct OrchestratorDCInfo *)psz,
              (enum StateMachineTypeTag *)((char *)&v61 + 4),
              (enum DMOrchestratorState *)&v68,
              (enum DCLifecycleNotificationType *)&v67);
  v8 = Request;
  LODWORD(v61) = Request;
  if ( Request < 0 )
  {
    if ( (byte_180189FC1 & 2) != 0 )
    {
      McTemplateU0q_EventWriteTransfer(
        v7,
        EnterpriseDiagnosticsDeclaredConfigurationGetRequestFailure,
        (unsigned int)Request);
      v8 = (unsigned int)v61;
    }
    v9 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(v9, L"AdmxDocumentActivity::Execute", (int)v61);
    goto LABEL_73;
  }
  if ( (unsigned int)(HIDWORD(v61) - 10) > 1 )
  {
    v10 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(v10, L"AdmxDocumentActivity::Execute", (int)v61);
    v8 = -2147024846;
LABEL_73:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v65);
    OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)psz);
    return v8;
  }
  *(_OWORD *)v63 = 0;
  v64 = 0x3F00000000LL;
  v11 = (const OLECHAR *)psz;
  if ( v72 > 7 )
    v11 = psz[0];
  v63[0] = SysAllocString(v11);
  if ( !v63[0] )
  {
LABEL_10:
    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v63);
    v12 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(v12, L"AdmxDocumentActivity::Execute", (int)v61);
    v8 = -2147024882;
    goto LABEL_73;
  }
  v13 = v73;
  if ( v74 > 7 )
    v13 = (OLECHAR **)v73[0];
  if ( !(unsigned int)_o__wcsicmp(v13, L"user") )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v65,
      0);
    ActiveUserSid = DmGetActiveUserSid(v65);
    v8 = ActiveUserSid;
    LODWORD(v61) = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicies\\a"
                      "dmxdocumentactivity.cpp",
        (const char *)(unsigned int)ActiveUserSid,
        v60);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v63);
      v15 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(v15, L"AdmxDocumentActivity::Execute", (int)v61);
      goto LABEL_73;
    }
    v16 = SysAllocString(v65[0]);
    LODWORD(v64) = 1;
LABEL_23:
    v63[1] = v16;
    if ( !v16 )
      goto LABEL_10;
    v62 = 0;
    *(_QWORD *)&pvarg.vt = &v62;
    pvarg.llVal = 0;
    *((_BYTE *)&pvarg.decVal + 16) = 1;
    v19 = (const unsigned __int16 *)v75;
    if ( v76 > 7 )
      v19 = v75[0];
    LODWORD(v61) = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                     (struct DeclaredConfigurationScopeData *)v63,
                     v19,
                     (HKEY *)&pvarg.llVal,
                     0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&pvarg);
    v8 = (unsigned int)v61;
    if ( (int)v61 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicies\\a"
                      "dmxdocumentactivity.cpp",
        (const char *)(unsigned int)v61,
        v60);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v62);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v63);
      v20 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(v20, L"AdmxDocumentActivity::Execute", (int)v61);
      goto LABEL_73;
    }
    DCDocument::DCDocument((DCDocument *)v81);
    std::wstring::operator=(v81, v75);
    std::wstring::operator=(v82, v73);
    std::wstring::operator=(v83, v77);
    v21 = v77;
    if ( v78 > 7 )
      v21 = (unsigned __int16 **)v77[0];
    PersistedDocument = DeclaredConfigurationStore_GetPersistedDocument(
                          (struct DeclaredConfigurationScopeData *)v63,
                          v62,
                          (__int64)v21,
                          0,
                          (__int64)v81,
                          2);
    v8 = PersistedDocument;
    LODWORD(v61) = PersistedDocument;
    if ( PersistedDocument < 0 )
    {
      if ( byte_180189FC1 < 0 )
      {
        McTemplateU0zzd_EventWriteTransfer(
          v23,
          (unsigned int)OrchestratorGenericFailure,
          (unsigned int)L"AdmxDocumentActivity::Execute",
          (unsigned int)L"DeclaredConfigurationStore_GetPersistedDocument",
          PersistedDocument);
        v8 = (unsigned int)v61;
      }
LABEL_72:
      DCDocument::~DCDocument((DCDocument *)v81);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v62);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v63);
      v45 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(v45, L"AdmxDocumentActivity::Execute", (int)v61);
      goto LABEL_73;
    }
    v24 = v84;
    if ( v85 > 7 )
      v24 = (_QWORD *)v84[0];
    if ( !(unsigned int)_o__wcsicmp(v24, L"msftadmxconfig") )
    {
      *(_OWORD *)&v65[1] = 0;
      CompleteAdmxInstallRequest = OrchestratorDBManager::FindCompleteAdmxInstallRequest(
                                     v25,
                                     v63[0],
                                     (struct _GUID *)&v65[1]);
      if ( CompleteAdmxInstallRequest < 0 )
      {
        if ( (byte_180189FC1 & 2) != 0 )
          McTemplateU0q_EventWriteTransfer(
            v27,
            EnterpriseDiagnosticsDeclaredConfigurationGetRequestFailure,
            (unsigned int)CompleteAdmxInstallRequest);
        *(_OWORD *)&v65[1] = v4;
        updated = OrchestratorDBManager::UpdateRequestState(v27, &v65[1], 4);
        VariantInit(&pvarg);
        pvarg.vt = 3;
        pvarg.lVal = 42;
        v29 = (const unsigned __int16 *)v77;
        if ( v78 > 7 )
          v29 = v77[0];
        v30 = (const unsigned __int16 *)v75;
        if ( v76 > 7 )
          v30 = v75[0];
        v31 = DeclaredConfigurationStore_WriteResultData(
                (struct DeclaredConfigurationScopeData *)v63,
                v30,
                v29,
                0,
                0,
                0,
                L"state",
                &pvarg);
        v8 = v31;
        LODWORD(v61) = v31;
        if ( v31 >= 0 )
        {
          DeclaredConfiguration_UpdateAllCspUriState(
            (struct DeclaredConfigurationScopeData *)v63,
            (struct DCDocument *)v81,
            &pvarg,
            0);
          if ( (int)v61 >= 0 )
          {
            if ( byte_180189FC1 < 0 )
              McTemplateU0zzd_EventWriteTransfer(
                v34,
                (unsigned int)OrchestratorGenericWarning,
                (unsigned int)L"AdmxDocumentActivity::Execute",
                (unsigned int)L"ADMX config can't proceed due to missing ADMX install doc",
                (char)v61);
            VariantClear(&pvarg);
            DCDocument::~DCDocument((DCDocument *)v81);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v62);
            DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v63);
            v36 = CDeclaredConfigurationLogger::GetLogger();
            CDeclaredConfigurationLogger::LogOrchestratorExitFunction(v36, L"AdmxDocumentActivity::Execute", (int)v61);
            v8 = updated;
          }
          else
          {
            if ( byte_180189FC1 < 0 )
              McTemplateU0zzd_EventWriteTransfer(
                v34,
                (unsigned int)OrchestratorGenericFailure,
                (unsigned int)L"AdmxDocumentActivity::Execute",
                (unsigned int)L"DeclaredConfiguration_UpdateAllCspUriState: failed to update csp/uri state",
                (char)v61);
            v8 = -2147024875;
            LODWORD(v61) = -2147024875;
            VariantClear(&pvarg);
            DCDocument::~DCDocument((DCDocument *)v81);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v62);
            DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v63);
            v35 = CDeclaredConfigurationLogger::GetLogger();
            CDeclaredConfigurationLogger::LogOrchestratorExitFunction(v35, L"AdmxDocumentActivity::Execute", (int)v61);
          }
        }
        else
        {
          if ( byte_180189FC1 < 0 )
          {
            McTemplateU0zzd_EventWriteTransfer(
              v32,
              (unsigned int)OrchestratorGenericFailure,
              (unsigned int)L"AdmxDocumentActivity::Execute",
              (unsigned int)L"DeclaredConfigurationStore_WriteResultData update doc state to DocMissingInstanceData",
              v31);
            v8 = (unsigned int)v61;
          }
          VariantClear(&pvarg);
          DCDocument::~DCDocument((DCDocument *)v81);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v62);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v63);
          v33 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorExitFunction(v33, L"AdmxDocumentActivity::Execute", (int)v61);
        }
        goto LABEL_73;
      }
      HIDWORD(v61) = 0;
      v37 = (const unsigned __int16 *)v73;
      if ( v74 > 7 )
        v37 = v73[0];
      v38 = (unsigned __int16 *)psz;
      if ( v72 > 7 )
        v38 = psz[0];
      LODWORD(v61) = DeclaredConfigurationStore_ProcessSingleDoc(
                       (struct DeclaredConfigurationScopeData *)v63,
                       (struct DCDocument *)v81,
                       v38,
                       v37,
                       0,
                       (int *)&v61 + 1);
      *(_OWORD *)&v65[1] = v4;
      OrchestratorDBManager::SetADMXInstallFlag(v39, (struct _GUID *)&v65[1], 0);
      v8 = (unsigned int)v61;
      if ( (int)v61 < 0 )
      {
        if ( (byte_180189FC1 & 2) != 0 )
        {
          v40 = v79;
          if ( v80 > 7 )
            v40 = (_QWORD *)v79[0];
          v41 = v77;
          if ( v78 > 7 )
            v41 = (unsigned __int16 **)v77[0];
          v42 = v75;
          if ( v76 > 7 )
            v42 = (unsigned __int16 **)v75[0];
          v43 = v73;
          if ( v74 > 7 )
            LODWORD(v43) = v73[0];
          v44 = psz;
          if ( v72 > 7 )
            LODWORD(v44) = psz[0];
          McTemplateU0zzzzzd_EventWriteTransfer(
            (_DWORD)v41,
            (unsigned int)DMOrchestratorProcessSingleDocResult,
            (_DWORD)v44,
            (_DWORD)v43,
            (__int64)v42,
            (__int64)v41,
            (__int64)v40,
            (char)v61);
          v8 = (unsigned int)v61;
        }
        goto LABEL_72;
      }
      *((_DWORD *)a2 + 146) = HIDWORD(v61);
    }
    v47 = v84;
    if ( v85 > 7 )
      v47 = (_QWORD *)v84[0];
    if ( !(unsigned int)_o__wcsicmp(v47, L"msftadmxinstall") )
    {
      HIDWORD(v61) = 0;
      v48 = (const unsigned __int16 *)v73;
      if ( v74 > 7 )
        v48 = v73[0];
      v49 = (unsigned __int16 *)psz;
      if ( v72 > 7 )
        v49 = psz[0];
      v50 = DeclaredConfigurationStore_ProcessSingleDoc(
              (struct DeclaredConfigurationScopeData *)v63,
              (struct DCDocument *)v81,
              v49,
              v48,
              0,
              (int *)&v61 + 1);
      v52 = v50;
      LODWORD(v61) = v50;
      if ( v50 >= 0 )
      {
        *(_OWORD *)&v65[1] = v4;
        OrchestratorDBManager::SetADMXInstallFlag(v51, (struct _GUID *)&v65[1], 1u);
      }
      else if ( (byte_180189FC1 & 2) != 0 )
      {
        v53 = v79;
        if ( v80 > 7 )
          v53 = (_QWORD *)v79[0];
        v54 = v77;
        if ( v78 > 7 )
          v54 = (unsigned __int16 **)v77[0];
        v55 = v75;
        if ( v76 > 7 )
          v55 = (unsigned __int16 **)v75[0];
        v56 = v73;
        if ( v74 > 7 )
          LODWORD(v56) = v73[0];
        v57 = psz;
        if ( v72 > 7 )
          LODWORD(v57) = psz[0];
        McTemplateU0zzzzzd_EventWriteTransfer(
          (_DWORD)v54,
          (unsigned int)DMOrchestratorProcessSingleDocResult,
          (_DWORD)v57,
          (_DWORD)v56,
          (__int64)v55,
          (__int64)v54,
          (__int64)v53,
          v52);
      }
      if ( *((int *)a2 + 146) >= 0 )
        *((_DWORD *)a2 + 146) = HIDWORD(v61);
    }
    v8 = (unsigned int)v61;
    DCDocument::~DCDocument((DCDocument *)v81);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v62);
    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v63);
    v58 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(v58, L"AdmxDocumentActivity::Execute", (int)v61);
    goto LABEL_73;
  }
  v17 = v73;
  if ( v74 > 7 )
    v17 = (OLECHAR **)v73[0];
  if ( !(unsigned int)_o__wcsicmp(v17, L"device") )
  {
    v18 = (const OLECHAR *)v73;
    if ( v74 > 7 )
      v18 = v73[0];
    v16 = SysAllocString(v18);
    goto LABEL_23;
  }
  DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v63);
  v59 = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogOrchestratorExitFunction(v59, L"AdmxDocumentActivity::Execute", (int)v61);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v65);
  OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180123d20  mov     rax, rsp
0x180123d23  push    rbp
0x180123d24  push    rbx
0x180123d25  push    rsi
0x180123d26  push    rdi
0x180123d27  push    r14
0x180123d29  push    r15
0x180123d2b  lea     rbp, [rax-398h]
0x180123d32  sub     rsp, 468h
0x180123d39  movaps  xmmword ptr [rax-48h], xmm6
0x180123d3d  mov     rax, cs:__security_cookie
0x180123d44  xor     rax, rsp
0x180123d47  mov     [rbp+390h+var_50], rax
0x180123d4e  mov     rdi, rdx
0x180123d51  xor     esi, esi
0x180123d53  mov     dword ptr [rsp+490h+var_450], esi
0x180123d57  lea     rcx, [rbp+390h+psz]; this
0x180123d5b  call    ??0OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::OrchestratorDCInfo(void)
0x180123d60  nop
0x180123d61  mov     qword ptr [rsp+490h+var_428], rsi
0x180123d66  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180123d6b  lea     r14, aAdmxdocumentac; "AdmxDocumentActivity::Execute"
0x180123d72  mov     rdx, r14; unsigned __int16 *
0x180123d75  mov     rcx, rax; this
0x180123d78  call    ?LogOrchestratorEnterFunction@CDeclaredConfigurationLogger@@QEAAXPEBG@Z; CDeclaredConfigurationLogger::LogOrchestratorEnterFunction(ushort const *)
0x180123d7d  lea     rax, [rsp+490h+var_450]
0x180123d82  mov     [rbp+390h+var_3F0], rax
0x180123d86  mov     [rbp+390h+var_3E8], 1
0x180123d8a  movups  xmm6, xmmword ptr [rdi+8]
0x180123d8e  mov     dword ptr [rsp+490h+var_450+4], esi
0x180123d92  mov     [rbp+390h+var_3F4], esi
0x180123d95  mov     [rbp+390h+var_3F8], esi
0x180123d98  movdqu  xmmword ptr [rsp+490h+var_428+8], xmm6
0x180123d9e  lea     rax, [rbp+390h+var_3F8]
0x180123da2  mov     [rsp+490h+var_468], rax; enum DCLifecycleNotificationType *
0x180123da7  lea     rax, [rbp+390h+var_3F4]
0x180123dab  mov     [rsp+490h+var_470], rax; int
0x180123db0  lea     r9, [rsp+490h+var_450+4]; enum StateMachineTypeTag *
0x180123db5  lea     r8, [rbp+390h+psz]; struct OrchestratorDCInfo *
0x180123db9  lea     rdx, [rsp+490h+var_428+8]; struct _GUID
0x180123dbe  call    ?GetRequest@OrchestratorDBManager@@QEAAJU_GUID@@PEAUOrchestratorDCInfo@@PEAW4StateMachineTypeTag@@PEAW4DMOrchestratorState@@PEAW4DCLifecycleNotificationType@@@Z; OrchestratorDBManager::GetRequest(_GUID,OrchestratorDCInfo *,StateMachineTypeTag *,DMOrchestratorState *,DCLifecycleNotificationType *)
0x180123dc3  mov     ebx, eax
0x180123dc5  mov     dword ptr [rsp+490h+var_450], eax
0x180123dc9  test    eax, eax
0x180123dcb  jns     short loc_180123E04
0x180123dcd  test    cs:byte_180189FC1, 2
0x180123dd4  jz      short loc_180123DE9
0x180123dd6  mov     r8d, eax
0x180123dd9  lea     rdx, EnterpriseDiagnosticsDeclaredConfigurationGetRequestFailure
0x180123de0  call    McTemplateU0q_EventWriteTransfer
0x180123de5  mov     ebx, dword ptr [rsp+490h+var_450]
0x180123de9  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180123dee  mov     r8d, dword ptr [rsp+490h+var_450]; int
0x180123df3  mov     rdx, r14; unsigned __int16 *
0x180123df6  mov     rcx, rax; this
0x180123df9  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180123dfe  nop
0x180123dff  jmp     loc_180124442
0x180123e04  mov     eax, dword ptr [rsp+490h+var_450+4]
0x180123e08  add     eax, 0FFFFFFF6h
0x180123e0b  cmp     eax, 1
0x180123e0e  jbe     short loc_180123E30
0x180123e10  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180123e15  mov     r8d, dword ptr [rsp+490h+var_450]; int
0x180123e1a  mov     rdx, r14; unsigned __int16 *
0x180123e1d  mov     rcx, rax; this
0x180123e20  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180123e25  nop
0x180123e26  mov     ebx, 80070032h
0x180123e2b  jmp     loc_180124442
0x180123e30  xorps   xmm0, xmm0
0x180123e33  movdqu  xmmword ptr [rsp+490h+var_448+8], xmm0
0x180123e39  mov     dword ptr [rsp+490h+var_430], esi
0x180123e3d  mov     dword ptr [rsp+490h+var_430+4], 3Fh ; '?'
0x180123e45  lea     rcx, [rbp+390h+psz]
0x180123e49  mov     r15d, 7
0x180123e4f  cmp     [rbp+390h+var_3C8], r15
0x180123e53  cmova   rcx, [rbp+390h+psz]; psz
0x180123e58  call    cs:__imp_SysAllocString
0x180123e5e  mov     [rsp+490h+var_448+8], rax
0x180123e63  test    rax, rax
0x180123e66  jnz     short loc_180123E93
0x180123e68  lea     rcx, [rsp+490h+var_448+8]; this
0x180123e6d  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180123e72  nop
0x180123e73  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180123e78  mov     r8d, dword ptr [rsp+490h+var_450]; int
0x180123e7d  mov     rdx, r14; unsigned __int16 *
0x180123e80  mov     rcx, rax; this
0x180123e83  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180123e88  nop
0x180123e89  mov     ebx, 8007000Eh
0x180123e8e  jmp     loc_180124442
0x180123e93  lea     rcx, [rbp+390h+var_3C0]
0x180123e97  cmp     [rbp+390h+var_3A8], r15
0x180123e9b  cmova   rcx, [rbp+390h+var_3C0]
0x180123ea0  lea     rdx, aUser_0; "user"
0x180123ea7  call    cs:__imp__o__wcsicmp
0x180123ead  test    eax, eax
0x180123eaf  jnz     short loc_180123F29
0x180123eb1  xor     edx, edx
0x180123eb3  lea     rcx, [rsp+490h+var_428]
0x180123eb8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180123ebd  lea     rcx, [rsp+490h+var_428]
0x180123ec2  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180123ec8  mov     ebx, eax
0x180123eca  mov     dword ptr [rsp+490h+var_450], eax
0x180123ece  test    eax, eax
0x180123ed0  jns     short loc_180123F14
0x180123ed2  mov     rcx, [rbp+398h]; this
0x180123ed9  mov     r9d, eax; char *
0x180123edc  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180123ee3  mov     edx, 42h ; 'B'; void *
0x180123ee8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123eed  nop
0x180123eee  lea     rcx, [rsp+490h+var_448+8]; this
0x180123ef3  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180123ef8  nop
0x180123ef9  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180123efe  mov     r8d, dword ptr [rsp+490h+var_450]; int
0x180123f03  mov     rdx, r14; unsigned __int16 *
0x180123f06  mov     rcx, rax; this
0x180123f09  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180123f0e  nop
0x180123f0f  jmp     loc_180124442
0x180123f14  mov     rcx, qword ptr [rsp+490h+var_428]; psz
0x180123f19  call    cs:__imp_SysAllocString
0x180123f1f  mov     dword ptr [rsp+490h+var_430], 1
0x180123f27  jmp     short loc_180123F5E
0x180123f29  lea     rcx, [rbp+390h+var_3C0]
0x180123f2d  cmp     [rbp+390h+var_3A8], r15
0x180123f31  cmova   rcx, [rbp+390h+var_3C0]
0x180123f36  lea     rdx, aDevice_4; "device"
0x180123f3d  call    cs:__imp__o__wcsicmp
0x180123f43  test    eax, eax
0x180123f45  jnz     loc_1801245AB
0x180123f4b  lea     rcx, [rbp+390h+var_3C0]
0x180123f4f  cmp     [rbp+390h+var_3A8], r15
0x180123f53  cmova   rcx, [rbp+390h+var_3C0]; psz
0x180123f58  call    cs:__imp_SysAllocString
0x180123f5e  mov     qword ptr [rsp+490h+var_438], rax
0x180123f63  test    rax, rax
0x180123f66  jnz     short loc_180123F8E
0x180123f68  lea     rcx, [rsp+490h+var_448+8]; this
0x180123f6d  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180123f72  nop
0x180123f73  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180123f78  mov     r8d, dword ptr [rsp+490h+var_450]; int
0x180123f7d  mov     rdx, r14; unsigned __int16 *
0x180123f80  mov     rcx, rax; this
0x180123f83  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180123f88  nop
0x180123f89  jmp     loc_180123E89
0x180123f8e  mov     [rsp+490h+var_448], rsi
0x180123f93  lea     rax, [rsp+490h+var_448]
0x180123f98  mov     qword ptr [rbp+390h+pvarg], rax
0x180123f9c  mov     qword ptr [rbp+390h+pvarg+8], rsi
0x180123fa0  mov     byte ptr [rbp+390h+pvarg+10h], 1
0x180123fa4  lea     rdx, [rbp+390h+var_3A0]
0x180123fa8  cmp     [rbp+390h+var_388], r15
0x180123fac  cmova   rdx, [rbp+390h+var_3A0]; unsigned __int16 *
0x180123fb1  xor     r9d, r9d; int
0x180123fb4  lea     r8, [rbp+390h+pvarg+8]; HKEY *
0x180123fb8  lea     rcx, [rsp+490h+var_448+8]; struct DeclaredConfigurationScopeData *
0x180123fbd  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x180123fc2  mov     dword ptr [rsp+490h+var_450], eax
0x180123fc6  lea     rcx, [rbp+390h+pvarg]
0x180123fca  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180123fcf  mov     ebx, dword ptr [rsp+490h+var_450]
0x180123fd3  test    ebx, ebx
0x180123fd5  jns     short loc_180124024
0x180123fd7  mov     rcx, [rbp+398h]; this
0x180123fde  mov     r9d, ebx; char *
0x180123fe1  lea     r8, aOnecoreuapAdmi_49; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180123fe8  mov     edx, 5Ch ; '\'; void *
0x180123fed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123ff2  nop
0x180123ff3  lea     rcx, [rsp+490h+var_448]
0x180123ff8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123ffd  nop
0x180123ffe  lea     rcx, [rsp+490h+var_448+8]; this
0x180124003  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180124008  nop
0x180124009  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18012400e  mov     r8d, dword ptr [rsp+490h+var_450]; int
0x180124013  mov     rdx, r14; unsigned __int16 *
0x180124016  mov     rcx, rax; this
0x180124019  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x18012401e  nop
0x18012401f  jmp     loc_180124442
0x180124024  lea     rcx, [rbp+390h+var_340]; this
0x180124028  call    ??0DCDocument@@QEAA@XZ; DCDocument::DCDocument(void)
0x18012402d  nop
0x18012402e  lea     rdx, [rbp+390h+var_3A0]
0x180124032  lea     rcx, [rbp+390h+var_340]
0x180124036  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18012403b  lea     rdx, [rbp+390h+var_3C0]
0x18012403f  lea     rcx, [rbp+390h+var_320]
0x180124043  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180124048  lea     rdx, [rbp+390h+var_380]
0x18012404c  lea     rcx, [rbp+390h+var_2E0]
0x180124053  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180124058  lea     r8, [rbp+390h+var_380]
0x18012405c  cmp     [rbp+390h+var_368], r15
0x180124060  cmova   r8, [rbp+390h+var_380]
0x180124065  mov     dword ptr [rsp+490h+var_468], 2
0x18012406d  lea     rax, [rbp+390h+var_340]
0x180124071  mov     [rsp+490h+var_470], rax
0x180124076  xor     r9d, r9d
0x180124079  mov     rdx, [rsp+490h+var_448]
0x18012407e  lea     rcx, [rsp+490h+var_448+8]
0x180124083  call    ?DeclaredConfigurationStore_GetPersistedDocument@@YAJPEAUDeclaredConfigurationScopeData@@PEAUHKEY__@@PEBG2PEAVDCDocument@@W4DCPersistedDocType@@@Z; DeclaredConfigurationStore_GetPersistedDocument(DeclaredConfigurationScopeData *,HKEY__ *,ushort const *,ushort const *,DCDocument *,DCPersistedDocType)
0x180124088  mov     ebx, eax
0x18012408a  mov     dword ptr [rsp+490h+var_450], eax
0x18012408e  test    eax, eax
0x180124090  jns     short loc_1801240F4
0x180124092  cmp     cs:byte_180189FC1, sil
0x180124099  jge     short loc_1801240B9
0x18012409b  mov     dword ptr [rsp+490h+var_470], eax
0x18012409f  lea     r9, aDeclaredconfig_143; "DeclaredConfigurationStore_GetPersisted"...
0x1801240a6  mov     r8, r14
0x1801240a9  lea     rdx, OrchestratorGenericFailure
0x1801240b0  call    McTemplateU0zzd_EventWriteTransfer
0x1801240b5  mov     ebx, dword ptr [rsp+490h+var_450]
0x1801240b9  lea     rcx, [rbp+390h+var_340]; this
0x1801240bd  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x1801240c2  nop
0x1801240c3  lea     rcx, [rsp+490h+var_448]
0x1801240c8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801240cd  nop
0x1801240ce  lea     rcx, [rsp+490h+var_448+8]; this
0x1801240d3  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x1801240d8  nop
0x1801240d9  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1801240de  mov     r8d, dword ptr [rsp+490h+var_450]; int
0x1801240e3  mov     rdx, r14; unsigned __int16 *
0x1801240e6  mov     rcx, rax; this
0x1801240e9  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1801240ee  nop
0x1801240ef  jmp     loc_180124442
0x1801240f4  lea     rcx, [rbp+390h+var_140]
0x1801240fb  cmp     [rbp+390h+var_128], r15
0x180124102  cmova   rcx, [rbp+390h+var_140]
0x18012410a  lea     rdx, aMsftadmxconfig; "msftadmxconfig"
0x180124111  call    cs:__imp__o__wcsicmp
0x180124117  test    eax, eax
0x180124119  jnz     loc_180124467
0x18012411f  xorps   xmm0, xmm0
0x180124122  movups  xmmword ptr [rsp+490h+var_428+8], xmm0
0x180124127  lea     r8, [rsp+490h+var_428+8]; struct _GUID *
0x18012412c  mov     rdx, [rsp+490h+var_448+8]; unsigned __int16 *
0x180124131  call    ?FindCompleteAdmxInstallRequest@OrchestratorDBManager@@QEAAJPEBGPEAU_GUID@@@Z; OrchestratorDBManager::FindCompleteAdmxInstallRequest(ushort const *,_GUID *)
0x180124136  test    eax, eax
0x180124138  jns     loc_180124341
0x18012413e  test    cs:byte_180189FC1, 2
0x180124145  jz      short loc_180124156
0x180124147  mov     r8d, eax
0x18012414a  lea     rdx, EnterpriseDiagnosticsDeclaredConfigurationGetRequestFailure
0x180124151  call    McTemplateU0q_EventWriteTransfer
0x180124156  movdqa  xmmword ptr [rsp+490h+var_428+8], xmm6
0x18012415c  mov     r8d, 4
0x180124162  lea     rdx, [rsp+490h+var_428+8]
0x180124167  call    ?UpdateRequestState@OrchestratorDBManager@@QEAAJU_GUID@@W4DMOrchestratorState@@@Z; OrchestratorDBManager::UpdateRequestState(_GUID,DMOrchestratorState)
0x18012416c  mov     edi, eax
0x18012416e  lea     rcx, [rbp+390h+pvarg]; pvarg
0x180124172  call    cs:__imp_VariantInit
0x180124178  nop
0x180124179  mov     eax, 3
0x18012417e  mov     word ptr [rbp+390h+pvarg], ax
0x180124182  mov     dword ptr [rbp+390h+pvarg+8], 2Ah ; '*'
0x180124189  lea     r8, [rbp+390h+var_380]
0x18012418d  cmp     [rbp+390h+var_368], r15
0x180124191  cmova   r8, [rbp+390h+var_380]; unsigned __int16 *
0x180124196  lea     rdx, [rbp+390h+var_3A0]
0x18012419a  cmp     [rbp+390h+var_388], r15
0x18012419e  cmova   rdx, [rbp+390h+var_3A0]; unsigned __int16 *
0x1801241a3  lea     rax, [rbp+390h+pvarg]
0x1801241a7  mov     [rsp+490h+var_458], rax; struct tagVARIANT *
0x1801241ac  lea     rax, ValueName; "state"
0x1801241b3  mov     [rsp+490h+lpValueName], rax; lpValueName
0x1801241b8  mov     [rsp+490h+var_468], rsi; unsigned __int16 *
0x1801241bd  mov     [rsp+490h+var_470], rsi; unsigned __int16 *
0x1801241c2  xor     r9d, r9d; unsigned __int16 *
0x1801241c5  lea     rcx, [rsp+490h+var_448+8]; struct DeclaredConfigurationScopeData *
0x1801241ca  call    ?DeclaredConfigurationStore_WriteResultData@@YAJPEAUDeclaredConfigurationScopeData@@PEBG11111PEAUtagVARIANT@@@Z; DeclaredConfigurationStore_WriteResultData(DeclaredConfigurationScopeData *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,tagVARIANT *)
0x1801241cf  mov     ebx, eax
0x1801241d1  mov     dword ptr [rsp+490h+var_450], eax
0x1801241d5  test    eax, eax
0x1801241d7  jns     short loc_180124246
0x1801241d9  cmp     cs:byte_180189FC1, sil
0x1801241e0  jge     short loc_180124200
0x1801241e2  mov     dword ptr [rsp+490h+var_470], eax
0x1801241e6  lea     r9, aDeclaredconfig_216; "DeclaredConfigurationStore_WriteResultD"...
0x1801241ed  mov     r8, r14
0x1801241f0  lea     rdx, OrchestratorGenericFailure
0x1801241f7  call    McTemplateU0zzd_EventWriteTransfer
0x1801241fc  mov     ebx, dword ptr [rsp+490h+var_450]
0x180124200  lea     rcx, [rbp+390h+pvarg]; pvarg
0x180124204  call    cs:__imp_VariantClear
0x18012420a  nop
  ... truncated ...
```
