# DCEngine::ReconstructQueueForInventoryDocs(ushort const *)

- ea: `0x180117904`
- end: `0x18011820b`
- name: `?ReconstructQueueForInventoryDocs@DCEngine@@AEAAJPEBG@Z`
- size: `2311`
- prototype: `__int64 __fastcall(DCEngine *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801187d0`

## callees

- `0x18000b9e0`
- `0x18000bebc`
- `0x18000e24c`
- `0x1800117dc`
- `0x180011fe0`
- `0x180013d4c`
- `0x18001438c`
- `0x180018cc4`
- `0x18001a60c`
- `0x18001c08c`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18004d158`
- `0x180056bcc`
- `0x180058b08`
- `0x180058b3c`
- `0x18009a2e4`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x1801006c8`
- `0x180100ad8`
- `0x18010a260`
- `0x18010abd8`
- `0x18010c084`
- `0x180110328`
- `0x180112a30`
- `0x180117904`
- `0x180119490`
- `0x18012d02c`
- `0x18012d270`
- `0x18012d2c4`
- `0x180139010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180117ac8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180117b99`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180117ac8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180117b99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180117a13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180117a13`
- `OLEAUT32!__imp_SysAllocString` at `0x180117a96`
- `OLEAUT32!__imp_SysAllocString` at `0x180117b5d`
- `OLEAUT32!__imp_SysAllocString` at `0x180117bba`
- `OLEAUT32!__imp_SysAllocString` at `0x180117a96`
- `OLEAUT32!__imp_SysAllocString` at `0x180117b5d`
- `OLEAUT32!__imp_SysAllocString` at `0x180117bba`
- `OLEAUT32!__imp_VariantInit` at `0x180117bd2`
- `OLEAUT32!__imp_VariantInit` at `0x180117bd2`
- `OLEAUT32!__imp_VariantClear` at `0x180117cef`
- `OLEAUT32!__imp_VariantClear` at `0x1801180e1`
- `OLEAUT32!__imp_VariantClear` at `0x180117cef`
- `OLEAUT32!__imp_VariantClear` at `0x1801180e1`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180117ae7`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180117ae7`

## string_xrefs

- `0x180117b15`: `DmGetActiveUserSid`
- `0x180117e06`: `GetEnrollmentIdSidStateDocIdVersionRawKey`
- `0x1801179d4`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x18011812a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x180117cd7`: `ReconstructQueueForInventoryDocs:DeclaredConfigurationStore_ReadResultData failed`
- `0x180117eb9`: `DCCDNUtil_GetRegistryDWORD(docIdVersionRawRegKey.get(),nullptr, c_szDCBehavior, &dwBehavior)`
- `0x180117e6b`: `DCCDNUtil_GetRegistryString(docIdVersionRawRegKey.get(),nullptr, c_szDCOSDefinedScenario, &pszOSDefinedScenario)`
- `0x180118097`: `meta->CreateNotifEventHandle`
- `0x18011817e`: `engine->StartExecutionThreadIfNotRunning`
- `0x18011807b`: `engine->ConfigDC`
- `0x1801181a4`: `WaitForAllInventoryRequestsToCompleteForEnrollmentId`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall DCEngine::ReconstructQueueForInventoryDocs(DCEngine *this, unsigned __int16 *a2)
{
  DCEngine *v2; // r14
  __int64 v3; // rcx
  int AllRequests; // ebx
  CDeclaredConfigurationLogger *Logger; // rax
  const unsigned __int16 *v6; // r8
  __int64 v7; // rsi
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  unsigned __int16 *v10; // rax
  const OLECHAR *v11; // rcx
  OLECHAR **v12; // rcx
  int ActiveUserSid; // r14d
  CDeclaredConfigurationLogger *v14; // rax
  const unsigned __int16 *v15; // r9
  OLECHAR **v16; // rcx
  const OLECHAR *v17; // rcx
  int v18; // r9d
  int *v19; // r8
  int *v20; // rdx
  int *v21; // rdx
  int *v22; // rcx
  OLECHAR **v23; // rax
  OLECHAR **v24; // r9
  int v25; // ecx
  int *v26; // r8
  int *v27; // rdx
  int EnrollmentIdSidStateDocIdVersionRawKey_0; // r14d
  int *v29; // rdx
  int *v30; // rcx
  OLECHAR **v31; // rax
  OLECHAR **v32; // r9
  CDeclaredConfigurationLogger *v33; // rax
  int RegistryString; // r14d
  CDeclaredConfigurationLogger *v35; // rax
  const unsigned __int16 *v36; // r8
  struct DCDocument *v37; // r13
  __int64 v38; // r12
  _QWORD *v39; // rdx
  __int64 v40; // r15
  int *v41; // rdx
  unsigned __int16 *v42; // r14
  int *v43; // rdx
  unsigned __int16 *v44; // rsi
  OLECHAR **v45; // rdx
  unsigned __int16 *v46; // rdi
  OLECHAR **v47; // rdx
  unsigned __int16 *v48; // rax
  DCMetaData *v49; // r14
  int NotifEventHandle; // edi
  __int64 v51; // r8
  __int64 v52; // rdx
  CDeclaredConfigurationLogger *v53; // rax
  const unsigned __int16 *v54; // r8
  OrchestratorDBManager *v55; // rcx
  int v56; // ebx
  CDeclaredConfigurationLogger *v57; // rax
  __int64 v58; // rcx
  DWORD v60; // [rsp+20h] [rbp-E0h]
  const char *hKey; // [rsp+28h] [rbp-D8h]
  HKEY hKeya; // [rsp+28h] [rbp-D8h]
  OLECHAR *v63; // [rsp+40h] [rbp-C0h] BYREF
  char *v64; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v65; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v66; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v67; // [rsp+60h] [rbp-A0h] BYREF
  int v68[2]; // [rsp+68h] [rbp-98h] BYREF
  BSTR v69; // [rsp+70h] [rbp-90h]
  int v70; // [rsp+78h] [rbp-88h]
  int v71; // [rsp+7Ch] [rbp-84h]
  struct HKEY__ v72; // [rsp+80h] [rbp-80h] BYREF
  void *v73[2]; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-68h] BYREF
  DWORD v75[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v76; // [rsp+B8h] [rbp-48h]
  __int64 v77; // [rsp+C0h] [rbp-40h]
  HKEY *v78; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v79; // [rsp+D0h] [rbp-30h] BYREF
  char v80; // [rsp+D8h] [rbp-28h]
  __int64 v81; // [rsp+E8h] [rbp-18h] BYREF
  DCEngine *v82; // [rsp+F0h] [rbp-10h]
  unsigned __int16 *v83; // [rsp+F8h] [rbp-8h]
  struct DCDocument *v84; // [rsp+100h] [rbp+0h]
  _BYTE *v85; // [rsp+108h] [rbp+8h]
  _BYTE *v86; // [rsp+110h] [rbp+10h]
  _BYTE *v87; // [rsp+118h] [rbp+18h]
  _BYTE *v88; // [rsp+120h] [rbp+20h]
  _BYTE v89[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v90[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v91[32]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v92[32]; // [rsp+190h] [rbp+90h] BYREF
  char v93[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  OLECHAR *psz[3]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int64 v95; // [rsp+1E8h] [rbp+E8h]
  OLECHAR *v96[3]; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int64 v97; // [rsp+208h] [rbp+108h]
  int v98[6]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int64 v99; // [rsp+228h] [rbp+128h]
  int v100[6]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int64 v101; // [rsp+248h] [rbp+148h]
  _QWORD v102[4]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 v103[264]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]

  v83 = a2;
  v2 = this;
  v82 = this;
  std::list<std::wstring>::list<std::wstring>(v73);
  v66 = 0;
  OrchestratorDCInfo::OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  v72.unused = 0;
  v81 = 0;
  AllRequests = OrchestratorDBManager::GetAllRequests(v3, v73);
  if ( AllRequests < 0 )
  {
    Logger = CDeclaredConfigurationLogger::GetLogger();
    v6 = L"OrchestratorIDatabaseManagerSingleton::instance().GetAllRequests(requestIds)";
    goto LABEL_102;
  }
  if ( !v73[1] )
    goto LABEL_103;
  v7 = *(_QWORD *)&qword_18018A6C8;
  v77 = *(_QWORD *)&qword_18018A6C8;
  if ( !*(_QWORD *)&qword_18018A6C8 )
  {
    InitOrchestratorEngine();
    v7 = *(_QWORD *)&qword_18018A6C8;
    v77 = *(_QWORD *)&qword_18018A6C8;
    if ( !*(_QWORD *)&qword_18018A6C8 )
    {
      AllRequests = -2147467259;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x963,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
        (const char *)0x80004005LL,
        (int)"could not get DC OrchestratorEngine",
        hKey);
      goto LABEL_103;
    }
  }
  v8 = v73[0];
  v9 = *(_QWORD **)v73[0];
  while ( 1 )
  {
    if ( v9 == v8 )
    {
      v56 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 56LL))(v7);
      if ( v56 < 0 )
      {
        v57 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v57,
          L"DCEngine::ReconstructQueueForInventoryDocs",
          L"engine->StartExecutionThreadIfNotRunning",
          &word_180142E98,
          v56);
      }
      AllRequests = OrchestratorDBManager::WaitForAllInventoryRequestsToCompleteForEnrollmentId(v55, v83);
      if ( AllRequests >= 0 )
        goto LABEL_103;
      Logger = CDeclaredConfigurationLogger::GetLogger();
      v6 = L"WaitForAllInventoryRequestsToCompleteForEnrollmentId";
LABEL_102:
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        Logger,
        L"DCEngine::ReconstructQueueForInventoryDocs",
        v6,
        &word_180142E98,
        AllRequests);
      goto LABEL_103;
    }
    v64 = (char *)v2 + 224;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v2 + 224));
    v10 = (unsigned __int16 *)(v9 + 2);
    v76 = (unsigned __int16 *)(v9 + 2);
    if ( v9[5] > 7u )
    {
      v10 = *(unsigned __int16 **)v10;
      v76 = v10;
    }
    if ( OrchestratorDBManager::GetRequest(
           (OrchestratorDBManager *)v75,
           v10,
           (struct OrchestratorDCInfo *)psz,
           (enum StateMachineTypeTag *)&v66,
           (enum DMOrchestratorState *)v75,
           (enum DCLifecycleNotificationType *)&v72) >= 0
      && v72.unused != 5 )
    {
      break;
    }
LABEL_24:
    gate<critical_section>::~gate<critical_section>(&v64);
    v9 = (_QWORD *)*v9;
    v8 = v73[0];
    v2 = v82;
  }
  v69 = 0;
  v70 = 0;
  v71 = 63;
  v63 = 0;
  v11 = (const OLECHAR *)psz;
  if ( v95 > 7 )
    v11 = psz[0];
  *(_QWORD *)v68 = SysAllocString(v11);
  if ( *(_QWORD *)v68 )
  {
    v12 = v96;
    if ( v97 > 7 )
      v12 = (OLECHAR **)v96[0];
    if ( (unsigned int)_o__wcsicmp(v12, L"user") )
    {
      v16 = v96;
      if ( v97 > 7 )
        v16 = (OLECHAR **)v96[0];
      if ( (unsigned int)_o__wcsicmp(v16, L"device") )
        goto LABEL_23;
      v17 = (const OLECHAR *)v96;
      if ( v97 > 7 )
        v17 = v96[0];
      v69 = SysAllocString(v17);
      if ( !v69 )
      {
        v52 = 2446;
        goto LABEL_97;
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v63,
        0);
      ActiveUserSid = DmGetActiveUserSid(&v63);
      if ( ActiveUserSid < 0 )
      {
        v14 = CDeclaredConfigurationLogger::GetLogger();
        v15 = (const unsigned __int16 *)psz;
        if ( v95 > 7 )
          v15 = psz[0];
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v14,
          L"DCEngine::ReconstructQueueForInventoryDocs",
          L"DmGetActiveUserSid",
          v15,
          ActiveUserSid);
        goto LABEL_23;
      }
      v69 = SysAllocString(v63);
      if ( !v69 )
      {
        v52 = 2440;
        goto LABEL_97;
      }
      v70 = 1;
    }
    VariantInit(&pvarg);
    pvarg.vt = 3;
    v19 = v100;
    if ( v101 > 7 )
      LODWORD(v19) = v100[0];
    v20 = v98;
    if ( v99 > 7 )
      LODWORD(v20) = v98[0];
    if ( (int)DeclaredConfigurationStore_ReadResultData_3(
                (int)v68,
                (int)v20,
                (int)v19,
                v18,
                v60,
                hKeya,
                L"state",
                (DWORD)&pvarg) < 0 )
    {
      v103[0] = 0;
      v21 = v100;
      if ( v101 > 7 )
        v21 = *(int **)v100;
      v22 = v98;
      if ( v99 > 7 )
        v22 = *(int **)v98;
      v23 = v96;
      if ( v97 > 7 )
        v23 = (OLECHAR **)v96[0];
      v24 = psz;
      if ( v95 > 7 )
        v24 = (OLECHAR **)psz[0];
      if ( StringCchPrintfW(v103, 0x104u, L"enrollmentId: %s, context:%s, docId:%s, docVersion:%s", v24, v23, v22, v21) >= 0
        && byte_180189FC1 < 0 )
      {
        McTemplateU0zzd_EventWriteTransfer(
          v25,
          (unsigned int)OrchestratorGenericFailure,
          (unsigned int)L"ReconstructQueueForInventoryDocs:DeclaredConfigurationStore_ReadResultData failed",
          (unsigned int)v103,
          0);
      }
      goto LABEL_49;
    }
    v65 = 0;
    v78 = &v65;
    v79 = 0;
    v80 = 1;
    v26 = v100;
    if ( v101 > 7 )
      LODWORD(v26) = v100[0];
    v27 = v98;
    if ( v99 > 7 )
      LODWORD(v27) = v98[0];
    EnrollmentIdSidStateDocIdVersionRawKey_0 = GetEnrollmentIdSidStateDocIdVersionRawKey_0(
                                                 (unsigned int)v68,
                                                 (_DWORD)v27,
                                                 (_DWORD)v26,
                                                 (unsigned int)&v79,
                                                 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v78);
    if ( EnrollmentIdSidStateDocIdVersionRawKey_0 < 0 )
    {
      v103[0] = 0;
      v29 = v100;
      if ( v101 > 7 )
        v29 = *(int **)v100;
      v30 = v98;
      if ( v99 > 7 )
        v30 = *(int **)v98;
      v31 = v96;
      if ( v97 > 7 )
        v31 = (OLECHAR **)v96[0];
      v32 = psz;
      if ( v95 > 7 )
        v32 = (OLECHAR **)psz[0];
      if ( StringCchPrintfW(v103, 0x104u, L"enrollmentId: %s, context:%s, docId:%s, docVersion:%s", v32, v31, v30, v29) >= 0 )
      {
        v33 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v33,
          L"DCEngine::ReconstructQueueForInventoryDocs",
          L"GetEnrollmentIdSidStateDocIdVersionRawKey",
          v103,
          EnrollmentIdSidStateDocIdVersionRawKey_0);
      }
      goto LABEL_65;
    }
    v67 = 0;
    v78 = (HKEY *)&v67;
    v79 = 0;
    v80 = 1;
    RegistryString = DCCDNUtil_GetRegistryString(v65, 0, L"osdefinedscenario", &v79);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v78);
    if ( RegistryString >= 0 )
    {
      RegistryString = DCCDNUtil_GetRegistryDWORD(v65, 0, L"behavior", v75);
      if ( RegistryString >= 0 )
      {
        if ( v66 != 9 && v66 != 3 )
          goto LABEL_69;
        v37 = (struct DCDocument *)operator new(0x388u);
        v84 = v37;
        *(_QWORD *)v75 = &v78;
        v38 = std::wstring::wstring((__int64)&v78, v67);
        v85 = v89;
        v39 = v102;
        if ( v102[3] > 7u )
          v39 = (_QWORD *)v102[0];
        v40 = std::wstring::wstring((__int64)v89, (__int64)v39);
        v86 = v90;
        v41 = v100;
        if ( v101 > 7 )
          v41 = *(int **)v100;
        v42 = (unsigned __int16 *)std::wstring::wstring((__int64)v90, (__int64)v41);
        v87 = v91;
        v43 = v98;
        if ( v99 > 7 )
          v43 = *(int **)v98;
        v44 = (unsigned __int16 *)std::wstring::wstring((__int64)v91, (__int64)v43);
        v88 = v92;
        v45 = v96;
        if ( v97 > 7 )
          v45 = (OLECHAR **)v96[0];
        v46 = (unsigned __int16 *)std::wstring::wstring((__int64)v92, (__int64)v45);
        v47 = psz;
        if ( v95 > 7 )
          v47 = (OLECHAR **)psz[0];
        v48 = (unsigned __int16 *)std::wstring::wstring((__int64)v93, (__int64)v47);
        v49 = (DCMetaData *)DCMetaData::DCMetaData(v37, v48, v46, v44, v42, v40, v38);
        NotifEventHandle = DCMetaData::set_Key(v49, v76);
        if ( NotifEventHandle < 0 )
        {
          v53 = CDeclaredConfigurationLogger::GetLogger();
          v54 = L"meta->set_Key";
        }
        else
        {
          NotifEventHandle = DCMetaData::CreateNotifEventHandle(v49);
          if ( NotifEventHandle < 0 )
          {
            v53 = CDeclaredConfigurationLogger::GetLogger();
            v54 = L"meta->CreateNotifEventHandle";
          }
          else
          {
            *((_DWORD *)v49 + 218) = 3;
            v7 = v77;
            NotifEventHandle = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v77 + 48LL))(v77, v66);
            if ( NotifEventHandle < 0 )
            {
              v53 = CDeclaredConfigurationLogger::GetLogger();
              v54 = L"engine->SetStateMachine";
            }
            else
            {
              LOBYTE(v51) = 1;
              NotifEventHandle = (**(__int64 (__fastcall ***)(__int64, DCMetaData *, __int64, __int64 *))v7)(
                                   v7,
                                   v49,
                                   v51,
                                   &v81);
              if ( NotifEventHandle >= 0 )
                goto LABEL_69;
              v53 = CDeclaredConfigurationLogger::GetLogger();
              v54 = L"engine->ConfigDC";
            }
          }
        }
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v53,
          L"DCEngine::ReconstructQueueForInventoryDocs",
          v54,
          &word_180142E98,
          NotifEventHandle);
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v67);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v65);
        VariantClear(&pvarg);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
        DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v68);
        gate<critical_section>::~gate<critical_section>(&v64);
        AllRequests = NotifEventHandle;
        goto LABEL_103;
      }
      v35 = CDeclaredConfigurationLogger::GetLogger();
      v36 = L"DCCDNUtil_GetRegistryDWORD(docIdVersionRawRegKey.get(),nullptr, c_szDCBehavior, &dwBehavior)";
    }
    else
    {
      v35 = CDeclaredConfigurationLogger::GetLogger();
      v36 = L"DCCDNUtil_GetRegistryString(docIdVersionRawRegKey.get(),nullptr, c_szDCOSDefinedScenario, &pszOSDefinedScenario)";
    }
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v35,
      L"DCEngine::ReconstructQueueForInventoryDocs",
      v36,
      &word_180142E98,
      RegistryString);
LABEL_69:
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v67);
LABEL_65:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v65);
LABEL_49:
    VariantClear(&pvarg);
LABEL_23:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v68);
    goto LABEL_24;
  }
  v52 = 2426;
LABEL_97:
  AllRequests = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v52,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
    (const char *)0x8007000ELL,
    v60);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
  DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v68);
  gate<critical_section>::~gate<critical_section>(&v64);
LABEL_103:
  OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
    v58,
    v73[0]);
  std::_Deallocate<16>(v73[0], 0x30u);
  return (unsigned int)AllRequests;
}

```

## disassembly

```asm
0x180117904  push    rbp
0x180117906  push    rbx
0x180117907  push    rsi
0x180117908  push    rdi
0x180117909  push    r12
0x18011790b  push    r13
0x18011790d  push    r14
0x18011790f  push    r15
0x180117911  lea     rbp, [rsp-398h]
0x180117919  sub     rsp, 498h
0x180117920  mov     rax, cs:__security_cookie
0x180117927  xor     rax, rsp
0x18011792a  mov     [rbp+3D0h+var_50], rax
0x180117931  mov     [rbp+3D0h+var_3D8], rdx
0x180117935  mov     r14, rcx
0x180117938  mov     [rbp+3D0h+var_3E0], rcx
0x18011793c  lea     rcx, [rbp+3D0h+var_448]
0x180117940  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x180117945  nop
0x180117946  xor     r15d, r15d
0x180117949  mov     [rsp+4D0h+var_478], r15d
0x18011794e  lea     rcx, [rbp+3D0h+psz]; this
0x180117955  call    ??0OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::OrchestratorDCInfo(void)
0x18011795a  nop
0x18011795b  mov     [rbp+3D0h+var_450.unused], r15d
0x18011795f  mov     [rbp+3D0h+var_3E8], r15
0x180117963  lea     rdx, [rbp+3D0h+var_448]
0x180117967  call    ?GetAllRequests@OrchestratorDBManager@@QEAAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; OrchestratorDBManager::GetAllRequests(std::list<std::wstring> &)
0x18011796c  mov     ebx, eax
0x18011796e  test    eax, eax
0x180117970  jns     short loc_18011798A
0x180117972  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180117977  lea     r8, aOrchestratorid_1; "OrchestratorIDatabaseManagerSingleton::"...
0x18011797e  lea     rdx, aDcengineRecons_0; "DCEngine::ReconstructQueueForInventoryD"...
0x180117985  jmp     loc_1801181AE
0x18011798a  cmp     [rbp+3D0h+var_440], r15
0x18011798e  jz      loc_1801181C2
0x180117994  mov     rsi, cs:qword_18018A6C8
0x18011799b  mov     [rbp+3D0h+var_410], rsi
0x18011799f  test    rsi, rsi
0x1801179a2  jnz     short loc_1801179EA
0x1801179a4  call    InitOrchestratorEngine
0x1801179a9  mov     rsi, cs:qword_18018A6C8
0x1801179b0  mov     [rbp+3D0h+var_410], rsi
0x1801179b4  test    rsi, rsi
0x1801179b7  jnz     short loc_1801179EA
0x1801179b9  mov     rcx, [rbp+3D8h]; this
0x1801179c0  lea     rax, aCouldNotGetDcO; "could not get DC OrchestratorEngine"
0x1801179c7  mov     qword ptr [rsp+4D0h+var_4B0], rax; int
0x1801179cc  mov     ebx, 80004005h
0x1801179d1  mov     r9d, ebx; char *
0x1801179d4  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1801179db  mov     edx, 963h; void *
0x1801179e0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801179e5  jmp     loc_1801181C2
0x1801179ea  mov     rax, [rbp+3D0h+var_448]
0x1801179ee  mov     rbx, [rax]
0x1801179f1  lea     rdi, aDcengineRecons_0; "DCEngine::ReconstructQueueForInventoryD"...
0x1801179f8  mov     r12d, 3
0x1801179fe  cmp     rbx, rax
0x180117a01  jz      loc_180118159
0x180117a07  lea     rcx, [r14+0E0h]; lpCriticalSection
0x180117a0e  mov     [rsp+4D0h+var_488], rcx
0x180117a13  call    cs:__imp_EnterCriticalSection
0x180117a19  nop
0x180117a1a  lea     rax, [rbx+10h]
0x180117a1e  mov     [rbp+3D0h+var_418], rax
0x180117a22  cmp     qword ptr [rax+18h], 7
0x180117a27  jbe     short loc_180117A30
0x180117a29  mov     rax, [rax]
0x180117a2c  mov     [rbp+3D0h+var_418], rax
0x180117a30  lea     rcx, [rbp+3D0h+var_450]
0x180117a34  mov     [rsp+4D0h+hKey], rcx; hKey
0x180117a39  lea     rcx, [rbp+3D0h+var_420]; this
0x180117a3d  mov     qword ptr [rsp+4D0h+var_4B0], rcx; int
0x180117a42  lea     r9, [rsp+4D0h+var_478]; enum StateMachineTypeTag *
0x180117a47  lea     r8, [rbp+3D0h+psz]; struct OrchestratorDCInfo *
0x180117a4e  mov     rdx, rax; unsigned __int16 *
0x180117a51  call    ?GetRequest@OrchestratorDBManager@@QEAAJPEBGPEAUOrchestratorDCInfo@@PEAW4StateMachineTypeTag@@PEAW4DMOrchestratorState@@PEAW4DCLifecycleNotificationType@@@Z; OrchestratorDBManager::GetRequest(ushort const *,OrchestratorDCInfo *,StateMachineTypeTag *,DMOrchestratorState *,DCLifecycleNotificationType *)
0x180117a56  test    eax, eax
0x180117a58  js      loc_180117B3E
0x180117a5e  cmp     [rbp+3D0h+var_450.unused], 5
0x180117a62  jz      loc_180117B3E
0x180117a68  mov     [rsp+4D0h+var_460], r15
0x180117a6d  mov     [rsp+4D0h+var_458], r15d
0x180117a72  mov     [rsp+4D0h+var_454], 3Fh ; '?'
0x180117a7a  mov     [rsp+4D0h+var_490], r15
0x180117a7f  lea     rcx, [rbp+3D0h+psz]
0x180117a86  cmp     [rbp+3D0h+var_2E8], 7
0x180117a8e  cmova   rcx, [rbp+3D0h+psz]; psz
0x180117a96  call    cs:__imp_SysAllocString
0x180117a9c  mov     qword ptr [rsp+4D0h+var_468], rax
0x180117aa1  test    rax, rax
0x180117aa4  jz      loc_180118116
0x180117aaa  lea     rcx, [rbp+3D0h+var_2E0]
0x180117ab1  cmp     [rbp+3D0h+var_2C8], 7
0x180117ab9  cmova   rcx, [rbp+3D0h+var_2E0]
0x180117ac1  lea     rdx, aUser_0; "user"
0x180117ac8  call    cs:__imp__o__wcsicmp
0x180117ace  test    eax, eax
0x180117ad0  jnz     loc_180117B7B
0x180117ad6  xor     edx, edx
0x180117ad8  lea     rcx, [rsp+4D0h+var_490]
0x180117add  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180117ae2  lea     rcx, [rsp+4D0h+var_490]
0x180117ae7  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180117aed  mov     r14d, eax
0x180117af0  test    eax, eax
0x180117af2  jns     short loc_180117B58
0x180117af4  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180117af9  lea     r9, [rbp+3D0h+psz]
0x180117b00  cmp     [rbp+3D0h+var_2E8], 7
0x180117b08  cmova   r9, [rbp+3D0h+psz]; unsigned __int16 *
0x180117b10  mov     [rsp+4D0h+var_4B0], r14d; int
0x180117b15  lea     r8, aDmgetactiveuse_1; "DmGetActiveUserSid"
0x180117b1c  mov     rdx, rdi; unsigned __int16 *
0x180117b1f  mov     rcx, rax; this
0x180117b22  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180117b27  nop
0x180117b28  lea     rcx, [rsp+4D0h+var_490]
0x180117b2d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180117b32  nop
0x180117b33  lea     rcx, [rsp+4D0h+var_468]; this
0x180117b38  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180117b3d  nop
0x180117b3e  lea     rcx, [rsp+4D0h+var_488]
0x180117b43  call    ??1?$gate@Vcritical_section@@@@QEAA@XZ; gate<critical_section>::~gate<critical_section>(void)
0x180117b48  mov     rbx, [rbx]
0x180117b4b  mov     rax, [rbp+3D0h+var_448]
0x180117b4f  mov     r14, [rbp+3D0h+var_3E0]
0x180117b53  jmp     loc_1801179FE
0x180117b58  mov     rcx, [rsp+4D0h+var_490]; psz
0x180117b5d  call    cs:__imp_SysAllocString
0x180117b63  mov     [rsp+4D0h+var_460], rax
0x180117b68  test    rax, rax
0x180117b6b  jz      loc_18011806C
0x180117b71  mov     [rsp+4D0h+var_458], 1
0x180117b79  jmp     short loc_180117BCE
0x180117b7b  lea     rcx, [rbp+3D0h+var_2E0]
0x180117b82  cmp     [rbp+3D0h+var_2C8], 7
0x180117b8a  cmova   rcx, [rbp+3D0h+var_2E0]
0x180117b92  lea     rdx, aDevice_4; "device"
0x180117b99  call    cs:__imp__o__wcsicmp
0x180117b9f  test    eax, eax
0x180117ba1  jnz     short loc_180117B28
0x180117ba3  lea     rcx, [rbp+3D0h+var_2E0]
0x180117baa  cmp     [rbp+3D0h+var_2C8], 7
0x180117bb2  cmova   rcx, [rbp+3D0h+var_2E0]; psz
0x180117bba  call    cs:__imp_SysAllocString
0x180117bc0  mov     [rsp+4D0h+var_460], rax
0x180117bc5  test    rax, rax
0x180117bc8  jz      loc_18011810F
0x180117bce  lea     rcx, [rbp+3D0h+pvarg]; pvarg
0x180117bd2  call    cs:__imp_VariantInit
0x180117bd8  nop
0x180117bd9  mov     word ptr [rbp+3D0h+pvarg], r12w
0x180117bde  lea     r8, [rbp+3D0h+var_2A0]
0x180117be5  cmp     [rbp+3D0h+var_288], 7
0x180117bed  cmova   r8, qword ptr [rbp+3D0h+var_2A0]; int
0x180117bf5  lea     rdx, [rbp+3D0h+var_2C0]
0x180117bfc  cmp     [rbp+3D0h+var_2A8], 7
0x180117c04  cmova   rdx, qword ptr [rbp+3D0h+var_2C0]; int
0x180117c0c  lea     rax, [rbp+3D0h+pvarg]
0x180117c10  mov     qword ptr [rsp+4D0h+Type], rax; Type
0x180117c15  lea     rax, ValueName; "state"
0x180117c1c  mov     [rsp+4D0h+lpValueName], rax; lpValueName
0x180117c21  lea     rcx, [rsp+4D0h+var_468]; int
0x180117c26  call    DeclaredConfigurationStore_ReadResultData_3
0x180117c2b  test    eax, eax
0x180117c2d  jns     loc_180117CFA
0x180117c33  mov     [rbp+3D0h+var_260], r15w
0x180117c3b  lea     rdx, [rbp+3D0h+var_2A0]
0x180117c42  cmp     [rbp+3D0h+var_288], 7
0x180117c4a  cmova   rdx, qword ptr [rbp+3D0h+var_2A0]
0x180117c52  lea     rcx, [rbp+3D0h+var_2C0]
0x180117c59  cmp     [rbp+3D0h+var_2A8], 7
0x180117c61  cmova   rcx, qword ptr [rbp+3D0h+var_2C0]
0x180117c69  lea     rax, [rbp+3D0h+var_2E0]
0x180117c70  cmp     [rbp+3D0h+var_2C8], 7
0x180117c78  cmova   rax, [rbp+3D0h+var_2E0]
0x180117c80  lea     r9, [rbp+3D0h+psz]
0x180117c87  cmp     [rbp+3D0h+var_2E8], 7
0x180117c8f  cmova   r9, [rbp+3D0h+psz]
0x180117c97  mov     [rsp+4D0h+lpValueName], rdx
0x180117c9c  mov     [rsp+4D0h+hKey], rcx
0x180117ca1  mov     qword ptr [rsp+4D0h+var_4B0], rax
0x180117ca6  lea     r8, aEnrollmentidSC; "enrollmentId: %s, context:%s, docId:%s,"...
0x180117cad  mov     edx, 104h; unsigned __int64
0x180117cb2  lea     rcx, [rbp+3D0h+var_260]; unsigned __int16 *
0x180117cb9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180117cbe  test    eax, eax
0x180117cc0  js      short loc_180117CEB
0x180117cc2  test    cs:byte_180189FC1, 80h
0x180117cc9  jz      short loc_180117CEB
0x180117ccb  mov     [rsp+4D0h+var_4B0], r15d
0x180117cd0  lea     r9, [rbp+3D0h+var_260]
0x180117cd7  lea     r8, aReconstructque_1; "ReconstructQueueForInventoryDocs:Declar"...
0x180117cde  lea     rdx, OrchestratorGenericFailure
0x180117ce5  call    McTemplateU0zzd_EventWriteTransfer
0x180117cea  nop
0x180117ceb  lea     rcx, [rbp+3D0h+pvarg]; pvarg
0x180117cef  call    cs:__imp_VariantClear
0x180117cf5  jmp     loc_180117B28
0x180117cfa  mov     [rsp+4D0h+var_480], r15
0x180117cff  lea     rax, [rsp+4D0h+var_480]
0x180117d04  mov     [rbp+3D0h+var_408], rax
0x180117d08  mov     [rbp+3D0h+var_400], r15
0x180117d0c  mov     [rbp+3D0h+var_3F8], 1
0x180117d10  lea     r8, [rbp+3D0h+var_2A0]
0x180117d17  cmp     [rbp+3D0h+var_288], 7
0x180117d1f  cmova   r8, qword ptr [rbp+3D0h+var_2A0]
0x180117d27  lea     rdx, [rbp+3D0h+var_2C0]
0x180117d2e  cmp     [rbp+3D0h+var_2A8], 7
0x180117d36  cmova   rdx, qword ptr [rbp+3D0h+var_2C0]
0x180117d3e  mov     [rsp+4D0h+var_4B0], r15d
0x180117d43  lea     r9, [rbp+3D0h+var_400]
0x180117d47  lea     rcx, [rsp+4D0h+var_468]
0x180117d4c  call    GetEnrollmentIdSidStateDocIdVersionRawKey_0
0x180117d51  mov     r14d, eax
0x180117d54  lea     rcx, [rbp+3D0h+var_408]
0x180117d58  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180117d5d  test    r14d, r14d
0x180117d60  jns     loc_180117E28
0x180117d66  mov     [rbp+3D0h+var_260], r15w
0x180117d6e  lea     rdx, [rbp+3D0h+var_2A0]
0x180117d75  cmp     [rbp+3D0h+var_288], 7
0x180117d7d  cmova   rdx, qword ptr [rbp+3D0h+var_2A0]
0x180117d85  lea     rcx, [rbp+3D0h+var_2C0]
0x180117d8c  cmp     [rbp+3D0h+var_2A8], 7
0x180117d94  cmova   rcx, qword ptr [rbp+3D0h+var_2C0]
0x180117d9c  lea     rax, [rbp+3D0h+var_2E0]
0x180117da3  cmp     [rbp+3D0h+var_2C8], 7
0x180117dab  cmova   rax, [rbp+3D0h+var_2E0]
0x180117db3  lea     r9, [rbp+3D0h+psz]
0x180117dba  cmp     [rbp+3D0h+var_2E8], 7
0x180117dc2  cmova   r9, [rbp+3D0h+psz]
0x180117dca  mov     [rsp+4D0h+lpValueName], rdx
0x180117dcf  mov     [rsp+4D0h+hKey], rcx
0x180117dd4  mov     qword ptr [rsp+4D0h+var_4B0], rax
0x180117dd9  lea     r8, aEnrollmentidSC; "enrollmentId: %s, context:%s, docId:%s,"...
0x180117de0  mov     edx, 104h; unsigned __int64
0x180117de5  lea     rcx, [rbp+3D0h+var_260]; unsigned __int16 *
0x180117dec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180117df1  test    eax, eax
0x180117df3  js      short loc_180117E19
0x180117df5  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180117dfa  mov     [rsp+4D0h+var_4B0], r14d; int
0x180117dff  lea     r9, [rbp+3D0h+var_260]; unsigned __int16 *
0x180117e06  lea     r8, aGetenrollmenti_5; "GetEnrollmentIdSidStateDocIdVersionRawK"...
0x180117e0d  mov     rdx, rdi; unsigned __int16 *
0x180117e10  mov     rcx, rax; this
0x180117e13  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180117e18  nop
0x180117e19  lea     rcx, [rsp+4D0h+var_480]
0x180117e1e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117e23  jmp     loc_180117CEB
0x180117e28  mov     [rsp+4D0h+var_470], r15
0x180117e2d  lea     rax, [rsp+4D0h+var_470]
0x180117e32  mov     [rbp+3D0h+var_408], rax
0x180117e36  mov     [rbp+3D0h+var_400], r15
0x180117e3a  mov     [rbp+3D0h+var_3F8], 1
0x180117e3e  lea     r9, [rbp+3D0h+var_400]; unsigned __int16 **
0x180117e42  lea     r8, aOsdefinedscena; "osdefinedscenario"
0x180117e49  xor     edx, edx; unsigned __int16 *
0x180117e4b  mov     rcx, [rsp+4D0h+var_480]; HKEY
0x180117e50  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180117e55  mov     r14d, eax
0x180117e58  lea     rcx, [rbp+3D0h+var_408]
0x180117e5c  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x180117e61  test    r14d, r14d
0x180117e64  jns     short loc_180117E96
0x180117e66  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180117e6b  lea     r8, aDccdnutilGetre_11; "DCCDNUtil_GetRegistryString(docIdVersio"...
0x180117e72  lea     r9, word_180142E98; unsigned __int16 *
0x180117e79  mov     [rsp+4D0h+var_4B0], r14d; int
0x180117e7e  mov     rdx, rdi; unsigned __int16 *
0x180117e81  mov     rcx, rax; this
0x180117e84  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180117e89  nop
0x180117e8a  lea     rcx, [rsp+4D0h+var_470]
0x180117e8f  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180117e94  jmp     short loc_180117E19
0x180117e96  lea     r9, [rbp+3D0h+var_420]; unsigned int *
0x180117e9a  lea     r8, aBehavior_0; "behavior"
0x180117ea1  xor     edx, edx; unsigned __int16 *
0x180117ea3  mov     rcx, [rsp+4D0h+var_480]; HKEY
0x180117ea8  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180117ead  mov     r14d, eax
0x180117eb0  test    eax, eax
0x180117eb2  jns     short loc_180117EC2
0x180117eb4  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180117eb9  lea     r8, aDccdnutilGetre_5; "DCCDNUtil_GetRegistryDWORD(docIdVersion"...
0x180117ec0  jmp     short loc_180117E72
0x180117ec2  cmp     [rsp+4D0h+var_478], 9
0x180117ec7  jz      short loc_180117ED0
0x180117ec9  cmp     [rsp+4D0h+var_478], r12d
0x180117ece  jnz     short loc_180117E8A
0x180117ed0  mov     ecx, 388h; Size
0x180117ed5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180117eda  mov     r13, rax
  ... truncated ...
```
