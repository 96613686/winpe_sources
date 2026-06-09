# CCbsCapabilityManager::PopulateCapabilityListFromCompDbMetadata(CCbsCapabilityManager::FoDLoadingLocker &,CCbsSession *,CCbsStringArray &,wchar_t const * const)

- ea: `0x180197ea0`
- end: `0x18019891c`
- name: `?PopulateCapabilityListFromCompDbMetadata@CCbsCapabilityManager@@IEAAJAEAVFoDLoadingLocker@1@PEAVCCbsSession@@AEAVCCbsStringArray@@QEB_W@Z`
- size: `2684`
- prototype: `int(CCbsCapabilityManager *__hidden this, struct CCbsCapabilityManager::FoDLoadingLocker *, struct CCbsSession *, struct CCbsStringArray *, const wchar_t *const)`
- caller_count: `1`
- callee_count: `29`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180197954`

## callees

- `0x180013250`
- `0x1800150c0`
- `0x180015420`
- `0x180019bdc`
- `0x1800261e0`
- `0x180028e24`
- `0x180049ec0`
- `0x1800532d4`
- `0x180056864`
- `0x180059160`
- `0x18008f280`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800aab5c`
- `0x1800aac98`
- `0x1800ae508`
- `0x1800af8d8`
- `0x1800b980c`
- `0x1800d9578`
- `0x1800eb920`
- `0x18010a0b0`
- `0x180197ea0`
- `0x180199014`
- `0x18019e0f8`
- `0x18019e248`
- `0x1801c1498`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180198592`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180198592`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801983c9`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801983c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019822d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801983f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019822d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801983f0`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18019817b`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18019817b`

## string_xrefs

- `0x18019840f`: `Failed to load updateagent.dll`
- `0x180198488`: `ActionList.xml`
- `0x1801981e7`: `Failed to get path to UpdateAgent.dll`
- `0x1801981b6`: `UpdateAgent.dll`
- `0x18019824c`: `Failed to create link.`
- `0x1801984be`: `Failed appending ActionList to sandbox directory`
- `0x180198588`: `UA_CreateActionList2`
- `0x1801985ee`: `Failed to execute CreateActionList from updateagent.dll`
- `0x1801982f0`: `Failed appending current compDB filename to path`
- `0x180198347`: `Failed appending current compDB filename to path`
- `0x180198035`: `Failed to create session sandbox for FOD enumeration`

## pseudocode

```c
__int64 __fastcall CCbsCapabilityManager::PopulateCapabilityListFromCompDbMetadata(
        unsigned __int64 this,
        struct CCbsCapabilityManager::FoDLoadingLocker *a2,
        struct CCbsSession *a3,
        struct CCbsStringArray *a4,
        const wchar_t *a5)
{
  bool v9; // zf
  CCbsSession *v10; // rcx
  int OfflineWindowsDirectory; // eax
  int v12; // edi
  __int64 v13; // rdx
  char v14; // al
  char *v15; // rcx
  int v16; // eax
  unsigned __int64 v17; // r9
  int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 *v21; // r15
  __int64 v22; // rax
  wchar_t *v23; // rbx
  int Win32PathOfSiblingFile; // eax
  signed int v25; // edi
  unsigned int v26; // eax
  __int64 v27; // rdx
  const WCHAR *v28; // rax
  HMODULE Library; // rax
  HMODULE v30; // rdi
  signed int LastError; // edi
  unsigned int v32; // eax
  int v33; // eax
  unsigned int v34; // r15d
  __int64 v35; // rdx
  int v36; // eax
  FARPROC ProcAddress; // rax
  wchar_t *v38; // rdi
  int v39; // eax
  unsigned int v40; // esi
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // eax
  __int64 v45; // rcx
  unsigned int v47; // [rsp+20h] [rbp-E0h]
  int v48; // [rsp+20h] [rbp-E0h]
  unsigned int v49[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpSymlinkFileName; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpTargetFileName; // [rsp+60h] [rbp-A0h] BYREF
  CCbsCapabilityManager::FoDLoadingLocker *v52; // [rsp+68h] [rbp-98h] BYREF
  HMODULE hModule; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v54; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v55; // [rsp+80h] [rbp-80h] BYREF
  __int64 v56; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *v57; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *v58; // [rsp+98h] [rbp-68h] BYREF
  int v59[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v60; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v61; // [rsp+B8h] [rbp-48h]
  __int64 v62; // [rsp+C0h] [rbp-40h]
  char *v63; // [rsp+C8h] [rbp-38h]
  _QWORD v64[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v65[24]; // [rsp+E0h] [rbp-20h] BYREF
  struct CCbsSession *v66; // [rsp+F8h] [rbp-8h]
  __int64 v67; // [rsp+110h] [rbp+10h]
  _BYTE v68[48]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v69[16]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v64[0] = a5;
  v58 = 0;
  v57 = 0;
  v56 = 0;
  v55 = 0;
  v54 = 0;
  v52 = a2;
  CFeatureOnDemandPackageMetadataProcessor::CFeatureOnDemandPackageMetadataProcessor((CFeatureOnDemandPackageMetadataProcessor *)v65);
  hModule = 0;
  v9 = *(_DWORD *)a2 == 1;
  v60 = 0;
  v61 = 0;
  if ( !v9 )
  {
    v12 = -2147024809;
    LODWORD(v64[0]) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Caller must acquire enumeration lock");
      *(_QWORD *)v59 = v64;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v59);
    }
    v13 = 1374;
    goto LABEL_90;
  }
  if ( (unsigned int)CCbsSession::IsOffline(a3) )
  {
    OfflineWindowsDirectory = CCbsSession::GetOfflineWindowsDirectory(v10, &v55);
    v12 = OfflineWindowsDirectory;
    if ( OfflineWindowsDirectory < 0 )
    {
      LODWORD(v64[0]) = OfflineWindowsDirectory;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get offline windir");
        v52 = (CCbsCapabilityManager::FoDLoadingLocker *)v64;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v52);
      }
      v13 = 1378;
LABEL_90:
      v17 = (unsigned int)v12;
      goto LABEL_91;
    }
  }
  if ( *(_QWORD *)(this + 24) )
  {
    if ( *(_QWORD *)(this + 88) && *(_QWORD *)(this + 192) )
      goto LABEL_86;
    v14 = 0;
  }
  else
  {
    v14 = 1;
  }
  v66 = a3;
  v15 = (char *)(this + 64);
  v68[17] = 1;
  v9 = *(_QWORD *)(this + 88) == 0;
  *(_QWORD *)v59 = this & -(__int64)(v14 != 0);
  if ( !v9 )
    v15 = 0;
  v63 = v15;
  v16 = SczAllocSessionDataString(L"EnumerateFeatures", 0, 0, &v56);
  v12 = v16;
  if ( v16 < 0 )
  {
    v17 = (unsigned int)v16;
    v13 = 1405;
LABEL_91:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
      (const char *)v17,
      v47);
    goto LABEL_92;
  }
  v18 = CCbsSession::CreateSessionSandbox(a3, 0, L"LocalFoDEnum", &v58);
  v12 = v18;
  if ( v18 < 0 )
  {
    LODWORD(v64[0]) = v18;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create session sandbox for FOD enumeration");
      v52 = (CCbsCapabilityManager::FoDLoadingLocker *)v64;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v52);
    }
    v13 = 1408;
    goto LABEL_90;
  }
  v19 = CbsRegQueryStringValue(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Servicing",
          1u,
          L"CountryCode",
          &v57);
  if ( v19 < 0 )
  {
    LogAdapter::TraceAtLevelHr<long,>(
      2,
      (unsigned int)v19,
      "Not able to get WU country code, skip setting country code.");
  }
  else
  {
    lpSymlinkFileName = v57;
    v20 = PackageStoreSetStringProperty(a3, L"CountryCode", v57);
    if ( v20 < 0 )
      LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
        2,
        (unsigned int)v20,
        "Unable to set country code: {}",
        &lpSymlinkFileName);
  }
  v21 = (__int64 *)*((_QWORD *)a4 + 5);
  v22 = *((_QWORD *)a4 + 3);
  v23 = v58;
  *(_QWORD *)v49 = &v21[v22];
  if ( v21 == *(__int64 **)v49 )
  {
LABEL_29:
    Win32PathOfSiblingFile = Windows::COM::GetWin32PathOfSiblingFile(
                               LoadInBoxUpdateAgentIfNecessary,
                               L"UpdateAgent.dll",
                               &v60);
    v12 = Win32PathOfSiblingFile;
    if ( Win32PathOfSiblingFile < 0 )
    {
      LODWORD(v64[0]) = Win32PathOfSiblingFile;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get path to UpdateAgent.dll");
        *(_QWORD *)v49 = v64;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v49);
      }
      v13 = 1442;
      goto LABEL_90;
    }
    v28 = (const WCHAR *)Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v60);
    Library = LoadLibraryExW(v28, 0, 8u);
    Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(&hModule, Library);
    v30 = hModule;
    if ( !hModule )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load updateagent.dll");
        if ( LastError > 0 )
          v32 = (unsigned __int16)LastError | 0x80070000;
        else
          v32 = LastError;
        LODWORD(v64[0]) = v32;
        *(_QWORD *)v49 = v64;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v49);
      }
      if ( LastError )
      {
        v12 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x5A5,
                (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
                (const char *)(unsigned int)LastError,
                v47);
        goto LABEL_92;
      }
      goto LABEL_86;
    }
    v33 = SczAllocFormatted(&v54, L"%ws%ws", v23, L"ActionList.xml");
    v34 = v33;
    if ( v33 < 0 )
    {
      LODWORD(v64[0]) = v33;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed appending ActionList to sandbox directory");
        *(_QWORD *)v49 = v64;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v49);
      }
      v35 = 1448;
LABEL_61:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v35,
        (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
        (const char *)v34,
        v47);
      v12 = v34;
      goto LABEL_92;
    }
    v36 = CCbsCapabilityManager::FoDLoadingLocker::WaitForDownloadLock(v52);
    v34 = v36;
    if ( v36 < 0 )
    {
      LODWORD(v64[0]) = v36;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to acquire locks for FOD metadata download");
        *(_QWORD *)v49 = v64;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v49);
      }
      v35 = 1450;
      goto LABEL_61;
    }
    ProcAddress = GetProcAddress(v30, "UA_CreateActionList2");
    v38 = v54;
    v48 = 4;
    v39 = ((__int64 (__fastcall *)(__int64, __int64, wchar_t *))ProcAddress)(2, v56, v23);
    v40 = v39;
    if ( v39 < 0 )
    {
      LODWORD(v64[0]) = v39;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to execute CreateActionList from updateagent.dll");
        *(_QWORD *)v49 = v64;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v49);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5BB,
        (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
        (const char *)v40,
        v48);
      v12 = v40;
      goto LABEL_92;
    }
    v41 = CFeatureOnDemandPackageMetadataProcessor::Process(
            (CFeatureOnDemandPackageMetadataProcessor *)v69,
            0,
            v38,
            v23,
            0,
            0,
            0,
            0,
            0);
    v12 = v41;
    if ( v41 < 0 )
    {
      LODWORD(v64[0]) = v41;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process actionList");
        *(_QWORD *)v49 = v64;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v49);
      }
      v13 = 1479;
      goto LABEL_90;
    }
    v42 = SczAllocFromSz(v68, v64[0]);
    v12 = v42;
    if ( v42 < 0 )
    {
      v17 = (unsigned int)v42;
      v13 = 1481;
      goto LABEL_91;
    }
    v43 = CCbsCapabilityManager::FoDLoadingLocker::WaitForEnumerationLock(v52);
    v12 = v43;
    if ( v43 < 0 )
    {
      LODWORD(v64[0]) = v43;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to acquire locks for FOD enumeration");
        *(_QWORD *)v49 = v64;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v49);
      }
      v13 = 1483;
      goto LABEL_90;
    }
    v47 = (unsigned int)v63;
    v44 = CFeatureOnDemandPackageMetadataProcessor::PopulateFeaturesFromActionListMetadata(v65, a3, v23, *(_QWORD *)v59);
    v12 = v44;
    if ( v44 < 0 )
    {
      LODWORD(v64[0]) = v44;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to enumerate FOD from actionList");
        *(_QWORD *)v59 = v64;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v59);
      }
      v13 = 1491;
      goto LABEL_90;
    }
    v45 = v67;
    if ( v67 )
    {
      v67 = *(_QWORD *)(this + 192);
      *(_QWORD *)(this + 192) = v45;
    }
LABEL_86:
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v60);
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
    CFeatureOnDemandPackageMetadataProcessor::~CFeatureOnDemandPackageMetadataProcessor((CFeatureOnDemandPackageMetadataProcessor *)v65);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v54);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v55);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v56);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v57);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v58);
    return 0;
  }
  while ( 1 )
  {
    v62 = *v21;
    lpSymlinkFileName = 0;
    lpTargetFileName = 0;
    v12 = SczAllocFormatted(&lpSymlinkFileName, L"%ws%ws", v23, v62);
    if ( v12 < 0 )
    {
      LODWORD(v64[0]) = v12;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed appending current compDB filename to path");
        *(_QWORD *)v49 = v64;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v49);
      }
      v27 = 1429;
      goto LABEL_47;
    }
    v12 = SczAllocFormatted(&lpTargetFileName, L"%ws%ws", v64[0], v62);
    if ( v12 < 0 )
    {
      LODWORD(v64[0]) = v12;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed appending current compDB filename to path");
        *(_QWORD *)v49 = v64;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v49);
      }
      v27 = 1432;
LABEL_47:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
        (const char *)(unsigned int)v12,
        v47);
      goto LABEL_48;
    }
    if ( !CreateSymbolicLinkW(lpSymlinkFileName, lpTargetFileName, 0) )
      break;
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpTargetFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpSymlinkFileName);
    if ( ++v21 == *(__int64 **)v49 )
      goto LABEL_29;
  }
  v25 = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create link.");
    if ( v25 > 0 )
      v26 = (unsigned __int16)v25 | 0x80070000;
    else
      v26 = v25;
    LODWORD(v64[0]) = v26;
    *(_QWORD *)v49 = v64;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {0}",
      (__int64)v49);
  }
  if ( !v25 )
  {
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpTargetFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpSymlinkFileName);
    v12 = 0;
    goto LABEL_92;
  }
  v12 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x59B,
          (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
          (const char *)(unsigned int)v25,
          v47);
LABEL_48:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpTargetFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpSymlinkFileName);
LABEL_92:
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v60);
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
  CFeatureOnDemandPackageMetadataProcessor::~CFeatureOnDemandPackageMetadataProcessor((CFeatureOnDemandPackageMetadataProcessor *)v65);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v54);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v55);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v56);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v57);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v58);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180197ea0  push    rbp
0x180197ea2  push    rbx
0x180197ea3  push    rsi
0x180197ea4  push    rdi
0x180197ea5  push    r12
0x180197ea7  push    r13
0x180197ea9  push    r14
0x180197eab  push    r15
0x180197ead  lea     rbp, [rsp-78h]
0x180197eb2  sub     rsp, 178h
0x180197eb9  mov     rax, cs:__security_cookie
0x180197ec0  xor     rax, rsp
0x180197ec3  mov     [rbp+0B0h+var_50], rax
0x180197ec7  mov     rax, [rbp+0B0h+arg_20]
0x180197ece  xor     r15d, r15d
0x180197ed1  mov     r13, rcx
0x180197ed4  mov     [rbp+0B0h+var_E0], rax
0x180197ed8  lea     rcx, [rbp+0B0h+var_D0]; this
0x180197edc  mov     [rbp+0B0h+var_118], r15
0x180197ee0  mov     [rbp+0B0h+var_120], r15
0x180197ee4  mov     r14d, r15d
0x180197ee7  mov     [rbp+0B0h+var_128], r15
0x180197eeb  mov     rbx, r9
0x180197eee  mov     [rbp+0B0h+var_130], r15
0x180197ef2  mov     r12, r8
0x180197ef5  mov     [rsp+1B0h+var_138], r15
0x180197efa  mov     rdi, rdx
0x180197efd  mov     [rsp+1B0h+var_148], rdx
0x180197f02  call    ??0CFeatureOnDemandPackageMetadataProcessor@@QEAA@XZ; CFeatureOnDemandPackageMetadataProcessor::CFeatureOnDemandPackageMetadataProcessor(void)
0x180197f07  xor     eax, eax
0x180197f09  mov     [rsp+1B0h+hModule], r15
0x180197f0e  cmp     dword ptr [rdi], 1
0x180197f11  xorps   xmm0, xmm0
0x180197f14  movups  [rbp+0B0h+var_108], xmm0
0x180197f18  mov     [rbp+0B0h+var_F8], rax
0x180197f1c  jnz     loc_180198841
0x180197f22  mov     rcx, r12; this
0x180197f25  call    ?IsOffline@CCbsSession@@QEBAHXZ; CCbsSession::IsOffline(void)
0x180197f2a  test    eax, eax
0x180197f2c  jz      short loc_180197F9A
0x180197f2e  lea     rdx, [rbp+0B0h+var_130]; wchar_t **
0x180197f32  call    ?GetOfflineWindowsDirectory@CCbsSession@@QEBAJPEAPEA_W@Z; CCbsSession::GetOfflineWindowsDirectory(wchar_t * *)
0x180197f37  mov     edi, eax
0x180197f39  test    eax, eax
0x180197f3b  jns     short loc_180197F96
0x180197f3d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180197f44  mov     dword ptr [rbp+0B0h+var_E0], eax
0x180197f47  test    rcx, rcx
0x180197f4a  jz      short loc_180197F8C
0x180197f4c  lea     ebx, [r15+3]
0x180197f50  xor     edx, edx
0x180197f52  mov     r8d, ebx
0x180197f55  lea     r9, aFailedToGetOff_11; "Failed to get offline windir"
0x180197f5c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180197f61  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180197f68  lea     rax, [rbp+0B0h+var_E0]
0x180197f6c  mov     [rsp+1B0h+var_148], rax
0x180197f71  lea     r9, asc_1802EE7AC; ": {}"
0x180197f78  lea     rax, [rsp+1B0h+var_148]
0x180197f7d  mov     r8d, ebx
0x180197f80  mov     dl, 1
0x180197f82  mov     [rsp+1B0h+var_190], rax
0x180197f87  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180197f8c  mov     edx, 562h
0x180197f91  jmp     loc_180198899
0x180197f96  mov     r14, [rbp+0B0h+var_130]
0x180197f9a  cmp     [r13+18h], r15
0x180197f9e  jnz     short loc_180197FA4
0x180197fa0  mov     al, 1
0x180197fa2  jmp     short loc_180197FBA
0x180197fa4  cmp     [r13+58h], r15
0x180197fa8  jz      short loc_180197FB7
0x180197faa  cmp     [r13+0C0h], r15
0x180197fb1  jnz     loc_1801987F0
0x180197fb7  mov     al, r15b
0x180197fba  neg     al
0x180197fbc  mov     [rbp+0B0h+var_B8], r12
0x180197fc0  lea     rcx, [r13+40h]
0x180197fc4  mov     [rbp+0B0h+var_7F], 1
0x180197fc8  sbb     rax, rax
0x180197fcb  lea     r9, [rbp+0B0h+var_128]
0x180197fcf  and     rax, r13
0x180197fd2  cmp     [rcx+18h], r15
0x180197fd6  mov     qword ptr [rbp+0B0h+var_110], rax
0x180197fda  cmovnz  rcx, r15
0x180197fde  xor     r8d, r8d
0x180197fe1  mov     [rbp+0B0h+var_E8], rcx
0x180197fe5  xor     edx, edx
0x180197fe7  lea     rcx, aEnumeratefeatu; "EnumerateFeatures"
0x180197fee  call    SczAllocSessionDataString
0x180197ff3  mov     edi, eax
0x180197ff5  test    eax, eax
0x180197ff7  jns     short loc_180198006
0x180197ff9  mov     r9d, eax
0x180197ffc  mov     edx, 57Dh
0x180198001  jmp     loc_18019889C
0x180198006  lea     r9, [rbp+0B0h+var_118]; wchar_t **
0x18019800a  xor     edx, edx; void *
0x18019800c  lea     r8, aLocalfodenum; "LocalFoDEnum"
0x180198013  mov     rcx, r12; this
0x180198016  call    ?CreateSessionSandbox@CCbsSession@@QEAAJPEAXPEB_WPEAPEA_W@Z; CCbsSession::CreateSessionSandbox(void *,wchar_t const *,wchar_t * *)
0x18019801b  mov     edi, eax
0x18019801d  test    eax, eax
0x18019801f  jns     short loc_18019807B
0x180198021  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180198028  mov     dword ptr [rbp+0B0h+var_E0], eax
0x18019802b  test    rcx, rcx
0x18019802e  jz      short loc_180198071
0x180198030  mov     ebx, 3
0x180198035  lea     r9, aFailedToCreate_9; "Failed to create session sandbox for FO"...
0x18019803c  mov     r8d, ebx
0x18019803f  xor     edx, edx
0x180198041  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180198046  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18019804d  lea     rax, [rbp+0B0h+var_E0]
0x180198051  mov     [rsp+1B0h+var_148], rax
0x180198056  lea     r9, asc_1802EE7AC; ": {}"
0x18019805d  lea     rax, [rsp+1B0h+var_148]
0x180198062  mov     r8d, ebx
0x180198065  mov     dl, 1
0x180198067  mov     [rsp+1B0h+var_190], rax
0x18019806c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180198071  mov     edx, 580h
0x180198076  jmp     loc_180198899
0x18019807b  lea     rax, [rbp+0B0h+var_120]
0x18019807f  mov     r8d, 1; unsigned int
0x180198085  lea     r9, aCountrycode; "CountryCode"
0x18019808c  mov     [rsp+1B0h+var_190], rax; wchar_t **
0x180198091  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180198098  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18019809f  call    ?CbsRegQueryStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAPEA_W@Z; CbsRegQueryStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t * *)
0x1801980a4  mov     rsi, [rbp+0B0h+var_120]
0x1801980a8  mov     edi, 2
0x1801980ad  test    eax, eax
0x1801980af  js      short loc_1801980E3
0x1801980b1  mov     r8, rsi; wchar_t *
0x1801980b4  mov     [rsp+1B0h+lpSymlinkFileName], rsi
0x1801980b9  lea     rdx, aCountrycode; "CountryCode"
0x1801980c0  mov     rcx, r12; struct CCbsSession *
0x1801980c3  call    ?PackageStoreSetStringProperty@@YAJPEAVCCbsSession@@PEB_W1@Z; PackageStoreSetStringProperty(CCbsSession *,wchar_t const *,wchar_t const *)
0x1801980c8  test    eax, eax
0x1801980ca  jns     short loc_1801980F3
0x1801980cc  lea     r9, [rsp+1B0h+lpSymlinkFileName]
0x1801980d1  mov     edx, eax
0x1801980d3  lea     r8, aUnableToSetCou; "Unable to set country code: {}"
0x1801980da  mov     ecx, edi
0x1801980dc  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x1801980e1  jmp     short loc_1801980F3
0x1801980e3  lea     r8, aNotAbleToGetWu; "Not able to get WU country code, skip s"...
0x1801980ea  mov     edx, eax
0x1801980ec  mov     ecx, edi
0x1801980ee  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x1801980f3  mov     r15, [rbx+28h]
0x1801980f7  mov     rax, [rbx+18h]
0x1801980fb  mov     rbx, [rbp+0B0h+var_118]
0x1801980ff  lea     rax, [r15+rax*8]
0x180198103  mov     qword ptr [rsp+1B0h+var_160], rax
0x180198108  cmp     r15, rax
0x18019810b  jz      loc_1801981B2
0x180198111  mov     rax, [r15]
0x180198114  lea     rdx, aWsWs_1; "%ws%ws"
0x18019811b  mov     r9, rax
0x18019811e  mov     [rbp+0B0h+var_F0], rax
0x180198122  mov     r8, rbx
0x180198125  mov     [rsp+1B0h+lpSymlinkFileName], 0
0x18019812e  lea     rcx, [rsp+1B0h+lpSymlinkFileName]
0x180198133  mov     [rsp+1B0h+lpTargetFileName], 0
0x18019813c  call    SczAllocFormatted
0x180198141  mov     edi, eax
0x180198143  test    eax, eax
0x180198145  js      loc_180198333
0x18019814b  mov     r9, [rbp+0B0h+var_F0]
0x18019814f  lea     rdx, aWsWs_1; "%ws%ws"
0x180198156  mov     r8, [rbp+0B0h+var_E0]
0x18019815a  lea     rcx, [rsp+1B0h+lpTargetFileName]
0x18019815f  call    SczAllocFormatted
0x180198164  mov     edi, eax
0x180198166  test    eax, eax
0x180198168  js      loc_1801982DC
0x18019816e  mov     rdx, [rsp+1B0h+lpTargetFileName]; lpTargetFileName
0x180198173  xor     r8d, r8d; dwFlags
0x180198176  mov     rcx, [rsp+1B0h+lpSymlinkFileName]; lpSymlinkFileName
0x18019817b  call    cs:__imp_CreateSymbolicLinkW
0x180198182  nop     dword ptr [rax+rax+00h]
0x180198187  test    al, al
0x180198189  jz      loc_18019822D
0x18019818f  lea     rcx, [rsp+1B0h+lpTargetFileName]
0x180198194  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180198199  lea     rcx, [rsp+1B0h+lpSymlinkFileName]
0x18019819e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801981a3  add     r15, 8
0x1801981a7  cmp     r15, qword ptr [rsp+1B0h+var_160]
0x1801981ac  jnz     loc_180198111
0x1801981b2  lea     r8, [rbp+0B0h+var_108]
0x1801981b6  lea     rdx, aUpdateagentDll_1; "UpdateAgent.dll"
0x1801981bd  lea     rcx, LoadInBoxUpdateAgentIfNecessary
0x1801981c4  call    ?GetWin32PathOfSiblingFile@COM@Windows@@YAJPEAXPEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::GetWin32PathOfSiblingFile(void *,wchar_t const *,Windows::Auto<_LUNICODE_STRING> *)
0x1801981c9  mov     edi, eax
0x1801981cb  test    eax, eax
0x1801981cd  jns     loc_1801983B7
0x1801981d3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801981da  mov     dword ptr [rbp+0B0h+var_E0], eax
0x1801981dd  test    rcx, rcx
0x1801981e0  jz      short loc_180198223
0x1801981e2  mov     ebx, 3
0x1801981e7  lea     r9, aFailedToGetPat_0; "Failed to get path to UpdateAgent.dll"
0x1801981ee  mov     r8d, ebx
0x1801981f1  xor     edx, edx
0x1801981f3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801981f8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801981ff  lea     rax, [rbp+0B0h+var_E0]
0x180198203  mov     qword ptr [rsp+1B0h+var_160], rax
0x180198208  lea     r9, asc_1802EE7AC; ": {}"
0x18019820f  lea     rax, [rsp+1B0h+var_160]
0x180198214  mov     r8d, ebx
0x180198217  mov     dl, 1
0x180198219  mov     [rsp+1B0h+var_190], rax
0x18019821e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180198223  mov     edx, 5A2h
0x180198228  jmp     loc_180198899
0x18019822d  call    cs:__imp_GetLastError
0x180198234  nop     dword ptr [rax+rax+00h]
0x180198239  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180198240  mov     edi, eax
0x180198242  test    rcx, rcx
0x180198245  jz      short loc_18019829B
0x180198247  mov     ebx, 3
0x18019824c  lea     r9, aFailedToCreate_86; "Failed to create link."
0x180198253  mov     r8d, ebx
0x180198256  xor     edx, edx
0x180198258  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18019825d  test    edi, edi
0x18019825f  jg      short loc_180198265
0x180198261  mov     eax, edi
0x180198263  jmp     short loc_18019826D
0x180198265  movzx   eax, di
0x180198268  or      eax, 80070000h
0x18019826d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180198274  lea     r9, a0; ": {0}"
0x18019827b  mov     dword ptr [rbp+0B0h+var_E0], eax
0x18019827e  mov     r8d, ebx
0x180198281  lea     rax, [rbp+0B0h+var_E0]
0x180198285  mov     dl, 1
0x180198287  mov     qword ptr [rsp+1B0h+var_160], rax
0x18019828c  lea     rax, [rsp+1B0h+var_160]
0x180198291  mov     [rsp+1B0h+var_190], rax; unsigned int
0x180198296  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18019829b  test    edi, edi
0x18019829d  jz      short loc_1801982C1
0x18019829f  mov     rcx, [rbp+0B8h]; this
0x1801982a6  lea     r8, aOnecoreBaseCbs_141; "onecore\\base\\cbs\\core\\capabilityman"...
0x1801982ad  mov     r9d, edi; char *
0x1801982b0  mov     edx, 59Bh; void *
0x1801982b5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801982ba  mov     edi, eax
0x1801982bc  jmp     loc_18019839E
0x1801982c1  lea     rcx, [rsp+1B0h+lpTargetFileName]
0x1801982c6  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801982cb  lea     rcx, [rsp+1B0h+lpSymlinkFileName]
0x1801982d0  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801982d5  xor     edi, edi
0x1801982d7  jmp     loc_1801988AF
0x1801982dc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801982e3  mov     dword ptr [rbp+0B0h+var_E0], edi
0x1801982e6  test    rcx, rcx
0x1801982e9  jz      short loc_18019832C
0x1801982eb  mov     ebx, 3
0x1801982f0  lea     r9, aFailedAppendin_0; "Failed appending current compDB filenam"...
0x1801982f7  mov     r8d, ebx
0x1801982fa  xor     edx, edx
0x1801982fc  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180198301  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180198308  lea     rax, [rbp+0B0h+var_E0]
0x18019830c  mov     qword ptr [rsp+1B0h+var_160], rax
0x180198311  lea     r9, asc_1802EE7AC; ": {}"
0x180198318  lea     rax, [rsp+1B0h+var_160]
0x18019831d  mov     r8d, ebx
0x180198320  mov     dl, 1
0x180198322  mov     [rsp+1B0h+var_190], rax
0x180198327  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18019832c  mov     edx, 598h
0x180198331  jmp     short loc_180198388
0x180198333  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18019833a  mov     dword ptr [rbp+0B0h+var_E0], edi
0x18019833d  test    rcx, rcx
0x180198340  jz      short loc_180198383
0x180198342  mov     ebx, 3
0x180198347  lea     r9, aFailedAppendin_0; "Failed appending current compDB filenam"...
0x18019834e  mov     r8d, ebx
0x180198351  xor     edx, edx
0x180198353  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180198358  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18019835f  lea     rax, [rbp+0B0h+var_E0]
0x180198363  mov     qword ptr [rsp+1B0h+var_160], rax
0x180198368  lea     r9, asc_1802EE7AC; ": {}"
0x18019836f  lea     rax, [rsp+1B0h+var_160]
0x180198374  mov     r8d, ebx
0x180198377  mov     dl, 1
0x180198379  mov     [rsp+1B0h+var_190], rax; int
0x18019837e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
  ... truncated ...
```
