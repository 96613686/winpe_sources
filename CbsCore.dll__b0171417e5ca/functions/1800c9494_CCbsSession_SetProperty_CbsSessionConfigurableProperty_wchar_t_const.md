# CCbsSession::SetProperty(_CbsSessionConfigurableProperty,wchar_t const *)

- ea: `0x1800c9494`
- end: `0x1800ca248`
- name: `?SetProperty@CCbsSession@@QEAAJW4_CbsSessionConfigurableProperty@@PEB_W@Z`
- size: `3508`
- prototype: `__int64 __fastcall(CimSetup **, int, wchar_t *)`
- caller_count: `2`
- callee_count: `35`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a1118`
- `0x1802b77a4`

## callees

- `0x180011a14`
- `0x180013250`
- `0x180015420`
- `0x180023ca8`
- `0x180028e24`
- `0x18002a2bc`
- `0x18002a448`
- `0x180042448`
- `0x18004a6d8`
- `0x180057c28`
- `0x18005aa38`
- `0x18005dd58`
- `0x18005eef0`
- `0x180093c4c`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800b980c`
- `0x1800c0054`
- `0x1800c82d8`
- `0x1800c8fbc`
- `0x1800c9494`
- `0x1800eb920`
- `0x1800fa3ec`
- `0x180106ff4`
- `0x18010d444`
- `0x1801422bc`
- `0x1801c0448`
- `0x1801c1498`
- `0x1801c45a0`
- `0x1801c7944`
- `0x1801c8ac4`
- `0x1801c9e2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9a1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9c13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9c9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9a1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9c13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9c9b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800c9a07`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800c9a07`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x1800c99c9`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x1800c9bfb`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x1800c99c9`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x1800c9bfb`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x1800c9c6b`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x1800c9c6b`

## string_xrefs

- `0x1800c9a44`: `Failed to copy cim catalog from {} to staging root {}.`
- `0x1800c9c3f`: `Source: Could not hard-link file {} to {}. So forcing a copy from here on.`
- `0x1800c9cc2`: `Failed to copy cim file {} to {}`
- `0x1800c9e8e`: `Failed to get offline windows directory.`
- `0x1800c974a`: `Failed to remove directory {}`
- `0x1800c9f29`: `Failed to setup the environment for cimbased update`
- `0x1800c9563`: `Adding local UUP repository path to: {}`
- `0x1800c966a`: `Failed to get Staging directory path for staging cims.`
- `0x1800c96fc`: `Removing directory {}`
- `0x1800c97e0`: `Failed to create staging directory {} for staging cims.`
- `0x1800c98df`: `Failed to get staging root directory path for payload cims catalog.`
- `0x1800c99b1`: `Failed to delete existing cim catalog file {}`
- `0x1800c99ef`: `Source: Could not hard-link file {} to {}`

## pseudocode

```c
__int64 __fastcall CCbsSession::SetProperty(CimSetup **a1, int a2, wchar_t *a3)
{
  __int64 v3; // rdi
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  CimSetup *v8; // rdx
  int v9; // eax
  unsigned int v10; // edi
  int v11; // edx
  int ServicingDirectory; // eax
  int v13; // edx
  wchar_t *v14; // rdi
  int v15; // edx
  int v16; // eax
  unsigned int v17; // esi
  int v18; // edx
  __int64 v19; // rdx
  int Directory; // eax
  int v21; // edx
  int v22; // eax
  __int64 v23; // rdx
  const WCHAR *v24; // rsi
  int v25; // eax
  unsigned int v26; // r15d
  int v27; // edx
  const WCHAR *v28; // rbx
  int v29; // eax
  signed int LastError; // edi
  int v31; // edx
  unsigned int v32; // eax
  __int64 v33; // rcx
  int v34; // eax
  int v35; // edx
  const WCHAR *v36; // r15
  char v37; // r13
  const WCHAR *v38; // rax
  __int64 v39; // r8
  int v40; // eax
  __int64 v41; // r8
  int v42; // eax
  LPCWSTR v43; // rbx
  LPCWSTR v44; // rsi
  signed int v45; // eax
  signed int v46; // edi
  int v47; // edx
  unsigned int v48; // eax
  LPCWSTR *v49; // rcx
  int v50; // edx
  CCbsSession *v51; // rcx
  int OfflineWindowsDirectory; // eax
  int v53; // edx
  int IsOffline; // eax
  __int64 v55; // r8
  int v56; // eax
  int v57; // edx
  __int64 v58; // rdx
  int v59; // eax
  int v60; // edx
  int v61; // eax
  int v62; // edx
  __int64 v63; // rdx
  int v64; // edx
  unsigned int v65; // esi
  _QWORD *v66; // rbx
  _QWORD *v67; // r15
  int v68; // edx
  unsigned int v70; // [rsp+20h] [rbp-99h]
  int v71; // [rsp+20h] [rbp-99h]
  LPCWSTR v72; // [rsp+30h] [rbp-89h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-81h] BYREF
  wchar_t *v74; // [rsp+40h] [rbp-79h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+48h] [rbp-71h] BYREF
  LPCWSTR v76; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v77[2]; // [rsp+58h] [rbp-61h] BYREF
  unsigned int v78[2]; // [rsp+60h] [rbp-59h] BYREF
  CimSetup *v79; // [rsp+68h] [rbp-51h] BYREF
  LPCWSTR v80; // [rsp+70h] [rbp-49h] BYREF
  wchar_t *v81; // [rsp+78h] [rbp-41h] BYREF
  LPCWSTR v82; // [rsp+80h] [rbp-39h] BYREF
  wchar_t *v83; // [rsp+88h] [rbp-31h] BYREF
  _BYTE v84[24]; // [rsp+90h] [rbp-29h] BYREF
  __int64 v85; // [rsp+A8h] [rbp-11h]
  _QWORD *v86; // [rsp+B8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v3 = a2;
  v81 = a3;
  v79 = 0;
  v5 = SczAllocFromSz(&v79, a3);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 787;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)(unsigned int)v5,
      v70);
    goto LABEL_136;
  }
  if ( (((_DWORD)v3 - 1) & 0xFFFFFFFA) == 0 && (_DWORD)v3 != 6 )
  {
    v5 = SczEnsureBackslashTerminated(&v79);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = 796;
      goto LABEL_7;
    }
    v5 = PathPrefix(&v79);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = 797;
      goto LABEL_7;
    }
  }
  v8 = a1[v3 + 201];
  a1[v3 + 201] = v79;
  v79 = v8;
  if ( (_DWORD)v3 == 1 )
  {
    LogAdapter::TraceAtLevel<wchar_t const *>(1, "Adding local UUP repository path to: {}", &v81);
    v9 = CCbsSession::AddSource((CCbsSession *)a1, 1, 0, v81, 0);
    v10 = v9;
    if ( v9 >= 0 )
      goto LABEL_135;
    LODWORD(v82) = v9;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to add source");
      v72 = (LPCWSTR)&v82;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)&v72);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x328,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)v10,
      v71);
    goto LABEL_15;
  }
  if ( (_DWORD)v3 == 10 )
  {
    v5 = SczAllocFromSz(a1 + 292, v81);
    v6 = v5;
    if ( v5 >= 0 )
      goto LABEL_135;
    v7 = 812;
    goto LABEL_7;
  }
  if ( (_DWORD)v3 != 14 )
  {
    if ( (unsigned int)(v3 - 11) > 2 )
      goto LABEL_135;
    CCbsStringArray::CCbsStringArray((CCbsStringArray *)v84);
    v61 = CCbsStringArray::LoadFromStringList((CCbsStringArray *)v84, v81, L";");
    v17 = v61;
    if ( v61 < 0 )
    {
      LODWORD(v82) = v61;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to load OCs to finalize from string list.");
        *(_QWORD *)v77 = &v82;
        LOBYTE(v62) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v62,
          3,
          (unsigned int)": {}",
          (__int64)v77);
      }
      v63 = 927;
LABEL_117:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v63,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
        (const char *)v17,
        v70);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v84);
      goto LABEL_34;
    }
    switch ( (_DWORD)v3 )
    {
      case 0xB:
        v65 = 96;
        break;
      case 0xC:
        v65 = 48;
        break;
      case 0xD:
        v65 = 5;
        break;
      default:
        v17 = -2146498560;
        LODWORD(v83) = -2146498560;
        if ( LogAdapter::g_Logger )
        {
          LODWORD(lpFileName) = v3;
          LogAdapter::Logger::LogNumObjects<long>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Unexpected property value: {}",
            (__int64)&lpFileName);
          *(_QWORD *)v77 = &v83;
          LOBYTE(v64) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v64,
            3,
            (unsigned int)": {}",
            (__int64)v77);
        }
        v63 = 943;
        goto LABEL_117;
    }
    v66 = v86;
    v67 = &v86[v85];
    while ( 1 )
    {
      if ( v66 == v67 )
      {
        CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v84);
        goto LABEL_135;
      }
      v10 = CCbsSession::AddFeatureToModify(a1, *v66, v65);
      if ( (v10 & 0x80000000) != 0 )
        break;
      ++v66;
    }
    LODWORD(v83) = v10;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to process feature action: {}",
        (__int64)v66);
      *(_QWORD *)v77 = &v83;
      LOBYTE(v68) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v68,
        3,
        (unsigned int)": {}",
        (__int64)v77);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B4,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)v10,
      v70);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v84);
    goto LABEL_15;
  }
  v83 = 0;
  ServicingDirectory = CCbsSession::GetServicingDirectory((CCbsSession *)a1, L"Staging\\Cims", &v83);
  v10 = ServicingDirectory;
  if ( ServicingDirectory < 0 )
  {
    LODWORD(v82) = ServicingDirectory;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Failed to get Staging directory path for staging cims.");
      v72 = (LPCWSTR)&v82;
      LOBYTE(v13) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v13,
        3,
        (unsigned int)": {}",
        (__int64)&v72);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x335,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)v10,
      v70);
    goto LABEL_24;
  }
  v14 = v83;
  if ( (unsigned __int8)DoesDirectoryExist(v83, 0) )
  {
    v72 = v14;
    if ( LogAdapter::g_Logger )
    {
      LOBYTE(v15) = 1;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        v15,
        1,
        (unsigned int)"Removing directory {}",
        (__int64)&v72);
    }
    v16 = RecursiveRemoveDirectory(0, v14);
    v17 = v16;
    if ( v16 < 0 )
    {
      LODWORD(v82) = v16;
      if ( LogAdapter::g_Logger )
      {
        v72 = v14;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to remove directory {}",
          (__int64)&v72);
        v76 = (LPCWSTR)&v82;
        LOBYTE(v18) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v18,
          3,
          (unsigned int)": {}",
          (__int64)&v76);
      }
      v19 = 828;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
        (const char *)v17,
        v70);
LABEL_33:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v83);
LABEL_34:
      v6 = v17;
      goto LABEL_136;
    }
  }
  Directory = RecursivelyCreateDirectory(v14, 0);
  v17 = Directory;
  if ( Directory < 0 )
  {
    LODWORD(v82) = Directory;
    if ( LogAdapter::g_Logger )
    {
      v72 = v14;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to create staging directory {} for staging cims.",
        (__int64)&v72);
      v76 = (LPCWSTR)&v82;
      LOBYTE(v21) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v21,
        3,
        (unsigned int)": {}",
        (__int64)&v76);
    }
    v19 = 834;
    goto LABEL_32;
  }
  lpExistingFileName = 0;
  v74 = 0;
  lpFileName = 0;
  v22 = SczAllocCombinePath2Sz(&lpExistingFileName, v81, L"microsoft-windows-cimcatalog.cat");
  v6 = v22;
  if ( v22 < 0 )
  {
    v23 = 840;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)(unsigned int)v22,
      v70);
LABEL_42:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v74);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v83);
    goto LABEL_136;
  }
  v24 = lpExistingFileName;
  if ( (unsigned int)DoesFileExist(lpExistingFileName, 0) )
  {
    v25 = CCbsSession::GetServicingDirectory((CCbsSession *)a1, L"Staging\\", &v74);
    v26 = v25;
    if ( v25 < 0 )
    {
      LODWORD(v82) = v25;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to get staging root directory path for payload cims catalog.");
        v72 = (LPCWSTR)&v82;
        LOBYTE(v27) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v27,
          3,
          (unsigned int)": {}",
          (__int64)&v72);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34E,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
        (const char *)v26,
        v70);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v74);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v83);
      v6 = v26;
      goto LABEL_136;
    }
    v22 = SczAllocCombinePath2Sz(&lpFileName, v74, L"microsoft-windows-cimcatalog.cat");
    v6 = v22;
    if ( v22 < 0 )
    {
      v23 = 848;
      goto LABEL_41;
    }
    v28 = lpFileName;
    if ( (unsigned int)DoesFileExist(lpFileName, 0) )
    {
      v72 = v28;
      v29 = CbsSetAttrAndDeleteFile(v28);
      if ( v29 < 0 )
        LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
          1,
          (unsigned int)v29,
          "Failed to delete existing cim catalog file {}",
          &v72);
    }
    if ( !CreateHardLinkW(v28, v24, 0) )
    {
      v72 = v28;
      v76 = v24;
      LogAdapter::TraceAtLevelLastError<wchar_t *,wchar_t *>(1, "Source: Could not hard-link file {} to {}", &v76, &v72);
      if ( !CopyFileW(v24, v28, 0) )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          v72 = v28;
          v76 = v24;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to copy cim catalog from {} to staging root {}.",
            (__int64)&v76,
            (__int64)&v72);
          if ( LastError > 0 )
            v32 = (unsigned __int16)LastError | 0x80070000;
          else
            v32 = LastError;
          LODWORD(v82) = v32;
          LOBYTE(v31) = 1;
          *(_QWORD *)v78 = &v82;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v31,
            3,
            (unsigned int)": {0}",
            (__int64)v78);
        }
        if ( !LastError )
          goto LABEL_111;
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x360,
               (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
               (const char *)(unsigned int)LastError,
               v70);
        goto LABEL_42;
      }
    }
  }
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v84);
  v34 = CbsEnumFiles(v33, v81, L"payload-*", v84);
  v17 = v34;
  if ( v34 < 0 )
  {
    LODWORD(v82) = v34;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to enumerate cim payload directories");
      *(_QWORD *)v78 = &v82;
      LOBYTE(v35) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v35,
        3,
        (unsigned int)": {}",
        (__int64)v78);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x366,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)v17,
      v70);
LABEL_66:
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v84);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v74);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
    goto LABEL_33;
  }
  v36 = (const WCHAR *)v86;
  v37 = 0;
  v38 = (const WCHAR *)&v86[v85];
  v80 = v38;
  while ( 1 )
  {
    if ( v36 == v38 )
    {
      if ( Windows::AutoNewPtr<CimSetup>::Allocate<>(a1 + 307) )
      {
        v72 = 0;
        if ( (unsigned int)CCbsSession::IsOffline((CCbsSession *)a1) )
        {
          OfflineWindowsDirectory = CCbsSession::GetOfflineWindowsDirectory(v51, (wchar_t **)&v72);
          v17 = OfflineWindowsDirectory;
          if ( OfflineWindowsDirectory < 0 )
          {
            LODWORD(v82) = OfflineWindowsDirectory;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed to get offline windows directory.");
              *(_QWORD *)v77 = &v82;
              LOBYTE(v53) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v53,
                3,
                (unsigned int)": {}",
                (__int64)v77);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x390,
              (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
              (const char *)v17,
              v70);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v72);
            goto LABEL_66;
          }
        }
        IsOffline = CCbsSession::IsOffline((CCbsSession *)a1);
        v56 = CimSetup::Initialize(a1[307], v14, (const wchar_t *)(-(__int64)(IsOffline != 0) & v55));
        v10 = v56;
        if ( v56 >= 0 )
        {
          v59 = CCbsSession::SetEnhancedOptions((CCbsSession *)a1, 0x80000u);
          v10 = v59;
          if ( v59 >= 0 )
          {
            v49 = &v72;
            goto LABEL_110;
          }
          LODWORD(v82) = v59;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              LogAdapter::g_Logger,
              0,
              3,
              "Failed to set the enhanced option on the session.");
            *(_QWORD *)v77 = &v82;
            LOBYTE(v60) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v60,
              3,
              (unsigned int)": {}",
              (__int64)v77);
          }
          v58 = 919;
        }
        else
        {
          LODWORD(v82) = v56;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              LogAdapter::g_Logger,
              0,
              3,
              "Failed to setup the environment for cimbased update");
            *(_QWORD *)v77 = &v82;
            LOBYTE(v57) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v57,
              3,
              (unsigned int)": {}",
              (__int64)v77);
          }
          v58 = 916;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v58,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
          (const char *)v10,
          v70);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v72);
      }
      else
      {
        v10 = -2147024882;
        LODWORD(v82) = -2147024882;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate CimSetup helper.");
          *(_QWORD *)v77 = &v82;
          LOBYTE(v50) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v50,
            3,
            (unsigned int)": {}",
            (__int64)v77);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x38B,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
          (const char *)0x8007000ELL,
          v70);
      }
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v84);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v74);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
LABEL_24:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v83);
LABEL_15:
      v6 = v10;
      goto LABEL_136;
    }
    v39 = *(_QWORD *)v36;
    v76 = 0;
    v40 = SczAllocCombinePath2Sz(&v76, v81, v39);
    v6 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36D,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
        (const char *)(unsigned int)v40,
        v70);
      goto LABEL_89;
    }
    v41 = *(_QWORD *)v36;
    v72 = 0;
    v42 = SczAllocCombinePath2Sz(&v72, v14, v41);
    v6 = v42;
    if ( v42 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x370,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
        (const char *)(unsigned int)v42,
        v70);
LABEL_87:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v72);
LABEL_89:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v76);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v84);
      goto LABEL_42;
    }
    v43 = v76;
    v44 = v72;
    if ( !v37 )
    {
      if ( CreateHardLinkW(v72, v76, 0) )
        goto LABEL_77;
      *(_QWORD *)v78 = v44;
      v82 = v43;
      v45 = GetLastError();
      if ( v45 > 0 )
        v45 = (unsigned __int16)v45 | 0x80070000;
      LogAdapter::TraceAtLevelHr<long,wchar_t *,wchar_t const *>(
        1,
        v45,
        (unsigned int)"Source: Could not hard-link file {} to {}. So forcing a copy from here on.",
        (unsigned int)&v82,
        (__int64)v78);
      v37 = 1;
    }
    v70 = 0;
    if ( !(unsigned int)PrivCopyFileExW(v43, v44, 0, 0) )
      break;
LABEL_77:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v72);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v76);
    v38 = v80;
    v36 += 4;
  }
  v46 = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    *(_QWORD *)v78 = v43;
    v80 = v44;
    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"Failed to copy cim file {} to {}",
      (__int64)v78,
      (__int64)&v80);
    if ( v46 > 0 )
      v48 = (unsigned __int16)v46 | 0x80070000;
    else
      v48 = v46;
    LODWORD(v82) = v48;
    LOBYTE(v47) = 1;
    *(_QWORD *)v77 = &v82;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v47,
      3,
      (unsigned int)": {0}",
      (__int64)v77);
  }
  if ( v46 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x387,
           (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
           (const char *)(unsigned int)v46,
           v70);
    goto LABEL_87;
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v72);
  v49 = &v76;
LABEL_110:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v49);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v84);
LABEL_111:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v74);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v83);
LABEL_135:
  v6 = 0;
LABEL_136:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v79);
  return v6;
}

```

## disassembly

```asm
0x1800c9494  push    rbp
0x1800c9496  push    rbx
0x1800c9497  push    rsi
0x1800c9498  push    rdi
0x1800c9499  push    r13
0x1800c949b  push    r14
0x1800c949d  push    r15
0x1800c949f  lea     rbp, [rsp-27h]
0x1800c94a4  sub     rsp, 0E0h
0x1800c94ab  mov     rax, cs:__security_cookie
0x1800c94b2  xor     rax, rsp
0x1800c94b5  mov     [rbp+57h+var_40], rax
0x1800c94b9  movsxd  rdi, edx
0x1800c94bc  mov     r14, rcx
0x1800c94bf  mov     rdx, r8
0x1800c94c2  mov     [rbp+57h+var_98], r8
0x1800c94c6  lea     rcx, [rbp+57h+var_A8]
0x1800c94ca  mov     [rbp+57h+var_A8], 0
0x1800c94d2  call    SczAllocFromSz
0x1800c94d7  mov     ebx, eax
0x1800c94d9  test    eax, eax
0x1800c94db  jns     short loc_1800C94E4
0x1800c94dd  mov     edx, 313h
0x1800c94e2  jmp     short loc_1800C9507
0x1800c94e4  lea     eax, [rdi-1]
0x1800c94e7  test    eax, 0FFFFFFFAh
0x1800c94ec  jnz     short loc_1800C9535
0x1800c94ee  cmp     edi, 6
0x1800c94f1  jz      short loc_1800C9535
0x1800c94f3  lea     rcx, [rbp+57h+var_A8]
0x1800c94f7  call    SczEnsureBackslashTerminated
0x1800c94fc  mov     ebx, eax
0x1800c94fe  test    eax, eax
0x1800c9500  jns     short loc_1800C951F
0x1800c9502  mov     edx, 31Ch; void *
0x1800c9507  mov     rcx, [rbp+5Fh]; this
0x1800c950b  lea     r8, aOnecoreBaseCbs_67; "onecore\\base\\cbs\\core\\cbssessionpro"...
0x1800c9512  mov     r9d, eax; char *
0x1800c9515  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c951a  jmp     loc_1800CA21E
0x1800c951f  lea     rcx, [rbp+57h+var_A8]
0x1800c9523  call    PathPrefix
0x1800c9528  mov     ebx, eax
0x1800c952a  test    eax, eax
0x1800c952c  jns     short loc_1800C9535
0x1800c952e  mov     edx, 31Dh
0x1800c9533  jmp     short loc_1800C9507
0x1800c9535  mov     rdx, [r14+rdi*8+648h]
0x1800c953d  mov     r13d, 1
0x1800c9543  mov     rax, [rbp+57h+var_A8]
0x1800c9547  mov     [r14+rdi*8+648h], rax
0x1800c954f  mov     [rbp+57h+var_A8], rdx
0x1800c9553  cmp     edi, r13d
0x1800c9556  jnz     loc_1800C9603
0x1800c955c  lea     r8, [rbp+57h+var_98]
0x1800c9560  mov     ecx, r13d
0x1800c9563  lea     rdx, aAddingLocalUup; "Adding local UUP repository path to: {}"
0x1800c956a  call    ??$TraceAtLevel@PEB_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEB_W@Z; LogAdapter::TraceAtLevel<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800c956f  mov     r9, [rbp+57h+var_98]; wchar_t *
0x1800c9573  xor     r8d, r8d; unsigned int
0x1800c9576  mov     edx, r13d; int
0x1800c9579  mov     [rsp+110h+var_F0], 0; int *
0x1800c9582  mov     rcx, r14; this
0x1800c9585  call    ?AddSource@CCbsSession@@QEAAJHIPEB_WPEAH@Z; CCbsSession::AddSource(int,uint,wchar_t const *,int *)
0x1800c958a  mov     edi, eax
0x1800c958c  test    eax, eax
0x1800c958e  jns     loc_1800CA21C
0x1800c9594  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c959b  mov     dword ptr [rbp+57h+var_90], eax
0x1800c959e  test    rcx, rcx
0x1800c95a1  jz      short loc_1800C95E4
0x1800c95a3  lea     ebx, [r13+2]
0x1800c95a7  xor     edx, edx
0x1800c95a9  mov     r8d, ebx
0x1800c95ac  lea     r9, aFailedToAddSou; "Failed to add source"
0x1800c95b3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c95b8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c95bf  lea     rax, [rbp+57h+var_90]
0x1800c95c3  mov     [rsp+110h+var_E0], rax
0x1800c95c8  lea     r9, asc_1802EE7AC; ": {}"
0x1800c95cf  lea     rax, [rsp+110h+var_E0]
0x1800c95d4  mov     r8d, ebx
0x1800c95d7  mov     dl, r13b
0x1800c95da  mov     [rsp+110h+var_F0], rax; int
0x1800c95df  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c95e4  mov     rcx, [rbp+5Fh]; this
0x1800c95e8  lea     r8, aOnecoreBaseCbs_67; "onecore\\base\\cbs\\core\\cbssessionpro"...
0x1800c95ef  mov     r9d, edi; char *
0x1800c95f2  mov     edx, 328h; void *
0x1800c95f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c95fc  mov     ebx, edi
0x1800c95fe  jmp     loc_1800CA21E
0x1800c9603  cmp     edi, 0Ah
0x1800c9606  jnz     short loc_1800C962C
0x1800c9608  mov     rdx, [rbp+57h+var_98]
0x1800c960c  lea     rcx, [r14+920h]
0x1800c9613  call    SczAllocFromSz
0x1800c9618  mov     ebx, eax
0x1800c961a  test    eax, eax
0x1800c961c  jns     loc_1800CA21C
0x1800c9622  mov     edx, 32Ch
0x1800c9627  jmp     loc_1800C9507
0x1800c962c  cmp     edi, 0Eh
0x1800c962f  jnz     loc_1800CA032
0x1800c9635  lea     r8, [rbp+57h+var_88]; wchar_t **
0x1800c9639  mov     [rbp+57h+var_88], 0
0x1800c9641  lea     rdx, aStagingCims_0; "Staging\\Cims"
0x1800c9648  mov     rcx, r14; this
0x1800c964b  call    ?GetServicingDirectory@CCbsSession@@QEAAJPEB_WPEAPEA_W@Z; CCbsSession::GetServicingDirectory(wchar_t const *,wchar_t * *)
0x1800c9650  mov     edi, eax
0x1800c9652  test    eax, eax
0x1800c9654  jns     short loc_1800C96CD
0x1800c9656  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c965d  mov     dword ptr [rbp+57h+var_90], eax
0x1800c9660  test    rcx, rcx
0x1800c9663  jz      short loc_1800C96A7
0x1800c9665  mov     ebx, 3
0x1800c966a  lea     r9, aFailedToGetSta_0; "Failed to get Staging directory path fo"...
0x1800c9671  mov     r8d, ebx
0x1800c9674  xor     edx, edx
0x1800c9676  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c967b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c9682  lea     rax, [rbp+57h+var_90]
0x1800c9686  mov     [rsp+110h+var_E0], rax
0x1800c968b  lea     r9, asc_1802EE7AC; ": {}"
0x1800c9692  lea     rax, [rsp+110h+var_E0]
0x1800c9697  mov     r8d, ebx
0x1800c969a  mov     dl, r13b
0x1800c969d  mov     [rsp+110h+var_F0], rax; int
0x1800c96a2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c96a7  mov     rcx, [rbp+5Fh]; this
0x1800c96ab  lea     r8, aOnecoreBaseCbs_67; "onecore\\base\\cbs\\core\\cbssessionpro"...
0x1800c96b2  mov     r9d, edi; char *
0x1800c96b5  mov     edx, 335h; void *
0x1800c96ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c96bf  lea     rcx, [rbp+57h+var_88]
0x1800c96c3  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c96c8  jmp     loc_1800C95FC
0x1800c96cd  mov     rdi, [rbp+57h+var_88]
0x1800c96d1  xor     edx, edx
0x1800c96d3  mov     rcx, rdi
0x1800c96d6  call    DoesDirectoryExist
0x1800c96db  test    al, al
0x1800c96dd  jz      loc_1800C97AA
0x1800c96e3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c96ea  mov     [rsp+110h+var_E0], rdi
0x1800c96ef  test    rcx, rcx
0x1800c96f2  jz      short loc_1800C9710
0x1800c96f4  lea     rax, [rsp+110h+var_E0]
0x1800c96f9  mov     r8d, r13d
0x1800c96fc  lea     r9, aRemovingDirect; "Removing directory {}"
0x1800c9703  mov     [rsp+110h+var_F0], rax
0x1800c9708  mov     dl, r13b
0x1800c970b  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800c9710  mov     rdx, rdi
0x1800c9713  xor     ecx, ecx
0x1800c9715  call    RecursiveRemoveDirectory
0x1800c971a  mov     esi, eax
0x1800c971c  test    eax, eax
0x1800c971e  jns     loc_1800C97AA
0x1800c9724  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c972b  mov     dword ptr [rbp+57h+var_90], eax
0x1800c972e  test    rcx, rcx
0x1800c9731  jz      short loc_1800C9782
0x1800c9733  lea     rax, [rsp+110h+var_E0]
0x1800c9738  mov     [rsp+110h+var_E0], rdi
0x1800c973d  mov     ebx, 3
0x1800c9742  mov     [rsp+110h+var_F0], rax
0x1800c9747  mov     r8d, ebx
0x1800c974a  lea     r9, aFailedToRemove_0; "Failed to remove directory {}"
0x1800c9751  xor     edx, edx
0x1800c9753  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800c9758  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c975f  lea     rax, [rbp+57h+var_90]
0x1800c9763  mov     [rbp+57h+var_C0], rax
0x1800c9767  lea     r9, asc_1802EE7AC; ": {}"
0x1800c976e  lea     rax, [rbp+57h+var_C0]
0x1800c9772  mov     r8d, ebx
0x1800c9775  mov     dl, r13b
0x1800c9778  mov     [rsp+110h+var_F0], rax; int
0x1800c977d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c9782  mov     edx, 33Ch; void *
0x1800c9787  mov     rcx, [rbp+5Fh]; this
0x1800c978b  lea     r8, aOnecoreBaseCbs_67; "onecore\\base\\cbs\\core\\cbssessionpro"...
0x1800c9792  mov     r9d, esi; char *
0x1800c9795  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c979a  lea     rcx, [rbp+57h+var_88]
0x1800c979e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c97a3  mov     ebx, esi
0x1800c97a5  jmp     loc_1800CA21E
0x1800c97aa  xor     edx, edx
0x1800c97ac  mov     rcx, rdi
0x1800c97af  call    RecursivelyCreateDirectory
0x1800c97b4  mov     esi, eax
0x1800c97b6  test    eax, eax
0x1800c97b8  jns     short loc_1800C9822
0x1800c97ba  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c97c1  mov     dword ptr [rbp+57h+var_90], eax
0x1800c97c4  test    rcx, rcx
0x1800c97c7  jz      short loc_1800C9818
0x1800c97c9  lea     rax, [rsp+110h+var_E0]
0x1800c97ce  mov     [rsp+110h+var_E0], rdi
0x1800c97d3  mov     ebx, 3
0x1800c97d8  mov     [rsp+110h+var_F0], rax
0x1800c97dd  mov     r8d, ebx
0x1800c97e0  lea     r9, aFailedToCreate_49; "Failed to create staging directory {} f"...
0x1800c97e7  xor     edx, edx
0x1800c97e9  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800c97ee  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c97f5  lea     rax, [rbp+57h+var_90]
0x1800c97f9  mov     [rbp+57h+var_C0], rax
0x1800c97fd  lea     r9, asc_1802EE7AC; ": {}"
0x1800c9804  lea     rax, [rbp+57h+var_C0]
0x1800c9808  mov     r8d, ebx
0x1800c980b  mov     dl, r13b
0x1800c980e  mov     [rsp+110h+var_F0], rax
0x1800c9813  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c9818  mov     edx, 342h
0x1800c981d  jmp     loc_1800C9787
0x1800c9822  mov     rdx, [rbp+57h+var_98]
0x1800c9826  lea     r8, aMicrosoftWindo_0; "microsoft-windows-cimcatalog.cat"
0x1800c982d  lea     rcx, [rbp+57h+lpExistingFileName]
0x1800c9831  mov     [rbp+57h+lpExistingFileName], 0
0x1800c9839  mov     [rbp+57h+var_D0], 0
0x1800c9841  mov     [rsp+110h+lpFileName], 0
0x1800c984a  call    SczAllocCombinePath2Sz
0x1800c984f  mov     ebx, eax
0x1800c9851  test    eax, eax
0x1800c9853  jns     short loc_1800C9897
0x1800c9855  mov     edx, 348h; void *
0x1800c985a  mov     rcx, [rbp+5Fh]; this
0x1800c985e  lea     r8, aOnecoreBaseCbs_67; "onecore\\base\\cbs\\core\\cbssessionpro"...
0x1800c9865  mov     r9d, eax; char *
0x1800c9868  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c986d  lea     rcx, [rsp+110h+lpFileName]
0x1800c9872  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c9877  lea     rcx, [rbp+57h+var_D0]
0x1800c987b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c9880  lea     rcx, [rbp+57h+lpExistingFileName]
0x1800c9884  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c9889  lea     rcx, [rbp+57h+var_88]
0x1800c988d  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c9892  jmp     loc_1800CA21E
0x1800c9897  mov     rsi, [rbp+57h+lpExistingFileName]
0x1800c989b  xor     edx, edx
0x1800c989d  mov     rcx, rsi
0x1800c98a0  call    DoesFileExist
0x1800c98a5  test    eax, eax
0x1800c98a7  jz      loc_1800C9ACB
0x1800c98ad  lea     r8, [rbp+57h+var_D0]; wchar_t **
0x1800c98b1  mov     rcx, r14; this
0x1800c98b4  lea     rdx, aStaging_0; "Staging\\"
0x1800c98bb  call    ?GetServicingDirectory@CCbsSession@@QEAAJPEB_WPEAPEA_W@Z; CCbsSession::GetServicingDirectory(wchar_t const *,wchar_t * *)
0x1800c98c0  mov     r15d, eax
0x1800c98c3  test    eax, eax
0x1800c98c5  jns     loc_1800C9961
0x1800c98cb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c98d2  mov     dword ptr [rbp+57h+var_90], eax
0x1800c98d5  test    rcx, rcx
0x1800c98d8  jz      short loc_1800C991C
0x1800c98da  mov     ebx, 3
0x1800c98df  lea     r9, aFailedToGetSta_4; "Failed to get staging root directory pa"...
0x1800c98e6  mov     r8d, ebx
0x1800c98e9  xor     edx, edx
0x1800c98eb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c98f0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c98f7  lea     rax, [rbp+57h+var_90]
0x1800c98fb  mov     [rsp+110h+var_E0], rax
0x1800c9900  lea     r9, asc_1802EE7AC; ": {}"
0x1800c9907  lea     rax, [rsp+110h+var_E0]
0x1800c990c  mov     r8d, ebx
0x1800c990f  mov     dl, r13b
0x1800c9912  mov     [rsp+110h+var_F0], rax; int
0x1800c9917  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c991c  mov     rcx, [rbp+5Fh]; this
0x1800c9920  lea     r8, aOnecoreBaseCbs_67; "onecore\\base\\cbs\\core\\cbssessionpro"...
0x1800c9927  mov     r9d, r15d; char *
0x1800c992a  mov     edx, 34Eh; void *
0x1800c992f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9934  lea     rcx, [rsp+110h+lpFileName]
0x1800c9939  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c993e  lea     rcx, [rbp+57h+var_D0]
0x1800c9942  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c9947  lea     rcx, [rbp+57h+lpExistingFileName]
0x1800c994b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c9950  lea     rcx, [rbp+57h+var_88]
0x1800c9954  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c9959  mov     ebx, r15d
0x1800c995c  jmp     loc_1800CA21E
0x1800c9961  mov     rdx, [rbp+57h+var_D0]
0x1800c9965  lea     r8, aMicrosoftWindo_0; "microsoft-windows-cimcatalog.cat"
0x1800c996c  lea     rcx, [rsp+110h+lpFileName]
0x1800c9971  call    SczAllocCombinePath2Sz
0x1800c9976  mov     ebx, eax
0x1800c9978  test    eax, eax
0x1800c997a  jns     short loc_1800C9986
0x1800c997c  mov     edx, 350h
0x1800c9981  jmp     loc_1800C985A
0x1800c9986  mov     rbx, [rsp+110h+lpFileName]
0x1800c998b  xor     edx, edx
  ... truncated ...
```
