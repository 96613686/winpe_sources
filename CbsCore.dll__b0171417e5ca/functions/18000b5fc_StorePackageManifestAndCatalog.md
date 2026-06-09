# StorePackageManifestAndCatalog

- ea: `0x18000b5fc`
- end: `0x18000c23f`
- name: `StorePackageManifestAndCatalog`
- size: `3139`
- prototype: ``
- caller_count: `2`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000c7e8`
- `0x180027790`

## callees

- `0x18000b5fc`
- `0x18000c284`
- `0x18000c5e0`
- `0x18000c70c`
- `0x180010b60`
- `0x180010cc0`
- `0x180010f54`
- `0x1800110d0`
- `0x180012fe4`
- `0x180013250`
- `0x180015420`
- `0x180016250`
- `0x180016d40`
- `0x18004b1b8`
- `0x1800576cc`
- `0x1800603c8`
- `0x180073b74`
- `0x180093c4c`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad504`
- `0x1800b980c`
- `0x1800cbe5c`
- `0x1800eb920`
- `0x1801064b0`
- `0x1801a428c`
- `0x1801a43e0`
- `0x1801c1498`
- `0x1801c3524`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c094`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000bf1d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c055`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000bf1d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c055`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000bf06`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c03e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000bf06`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c03e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000bf45`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000c080`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000bf45`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000c080`

## string_xrefs

- `0x18000c0bc`: `Failed to move package manifest '{}' to store: {}`
- `0x18000bf80`: `Failed to move package session guide '{}' to store: {}`
- `0x18000bbc4`: `Failed to get catalog path for package: {}`
- `0x18000ba88`: `Failed to replace extension for session guide source`
- `0x18000be79`: `Failed to install catalog for package: {}`
- `0x18000bc99`: `Failed to parse manifest: {}`
- `0x18000bd30`: `Failed to convert from package assembly to CBSIdentity on manifest: {}`
- `0x18000bf29`: `File already exists when adding the manifest.`
- `0x18000c061`: `File already exists when adding the manifest.`
- `0x18000c167`: `Failed to set security info on '{}'`
- `0x18000b731`: `CIM: Skipping copy of package {}.`
- `0x18000b940`: `Failed to get manifest path for package: {}`
- `0x18000bb2d`: `Failed to replace extension for session guide target`
- `0x18000b7b2`: `Failed to get offline windows directory when trying to store manifest for package: {}`
- `0x18000b881`: `Failed to get package store directory to store manifest for package: {}`

## pseudocode

```c
__int64 __fastcall StorePackageManifestAndCatalog(struct CCbsSession *a1, CCbsPackage **this, void *a3)
{
  CCbsPackage *v6; // r13
  unsigned int v7; // r12d
  int OfflineWindowsDirectory; // eax
  CCbsPackage *v9; // r13
  int PackageStoreDirectory; // eax
  CCbsPackage *v11; // r13
  int ManifestPath; // eax
  CCbsPackage *v13; // r13
  int v14; // eax
  __int64 v15; // rdx
  CCbsPackage *v16; // r13
  const wchar_t *v17; // rdx
  CCbsPackage *v18; // rax
  const WCHAR *v19; // rbx
  wchar_t *v20; // rdi
  void *v21; // r14
  wchar_t *v22; // rsi
  int v23; // eax
  __int64 v24; // rdx
  int v25; // eax
  int CatalogPath; // eax
  struct Windows::Rtl::StopWatch *v27; // r9
  __int64 v28; // rdx
  __int64 v29; // r12
  struct CCbsIdentity **InitPointer; // rax
  int CbsIdentityFromAssemblyIdentity; // eax
  const wchar_t *v32; // r9
  int v33; // eax
  signed int LastError; // edi
  unsigned int v35; // eax
  unsigned __int64 v36; // r9
  __int64 v37; // rdx
  int v38; // eax
  signed int v39; // r14d
  unsigned int v40; // eax
  int v41; // eax
  unsigned int v42; // [rsp+20h] [rbp-E0h]
  CCbsPackage *v43; // [rsp+30h] [rbp-D0h] BYREF
  struct CCbsIdentity *v44; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *v45; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v46; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v47; // [rsp+50h] [rbp-B0h] BYREF
  void *FastCbsIdentityString; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+68h] [rbp-98h] BYREF
  const WCHAR *v51; // [rsp+70h] [rbp-90h] BYREF
  void *v52; // [rsp+78h] [rbp-88h] BYREF
  void *v53; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v54[2]; // [rsp+88h] [rbp-78h] BYREF
  char v55; // [rsp+98h] [rbp-68h]
  _BYTE v56[56]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v57; // [rsp+D8h] [rbp-28h]
  struct CCbsSession *v58; // [rsp+2D0h] [rbp+1D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  FastCbsIdentityString = a3;
  v43 = (CCbsPackage *)this;
  v58 = a1;
  if ( a1 )
  {
    ParsingSession::ParsingSession((ParsingSession *)v56);
    v44 = 0;
    v54[1] = &vPackageStoreLock;
    v55 = 0;
    v54[0] = &PackageTrackerLocker::`vftable';
    MonitoredCritSecLocker::Lock((MonitoredCritSecLocker *)v54);
    if ( (*((_DWORD *)a1 + 173) & 0x80000) != 0 )
    {
      v6 = (CCbsPackage *)&qword_1802EB518;
      if ( this[15] )
        v6 = this[15];
      v43 = v6;
      if ( LogAdapter::g_Logger )
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          1,
          1,
          (__int64)"CIM: Skipping copy of package {}.",
          (__int64)&v43);
      MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v54);
      if ( v44 )
      {
        (*(void (__fastcall **)(struct CCbsIdentity *))(*(_QWORD *)v44 + 16LL))(v44);
        v44 = 0;
      }
      v7 = 0;
      goto LABEL_114;
    }
    v46 = 0;
    OfflineWindowsDirectory = CCbsSession::GetOfflineWindowsDirectory(a1, &v46);
    v7 = OfflineWindowsDirectory;
    if ( OfflineWindowsDirectory < 0 )
    {
      LODWORD(v58) = OfflineWindowsDirectory;
      if ( LogAdapter::g_Logger )
      {
        v9 = (CCbsPackage *)&qword_1802EB518;
        if ( this[15] )
          v9 = this[15];
        v43 = v9;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to get offline windows directory when trying to store manifest for package: {}",
          (__int64)&v43);
        v47 = (wchar_t *)&v58;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v47);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE4F,
        (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
        (const char *)v7,
        v42);
      goto LABEL_19;
    }
    v45 = 0;
    PackageStoreDirectory = CCbsSession::GetPackageStoreDirectory(a1, &v45);
    v7 = PackageStoreDirectory;
    if ( PackageStoreDirectory < 0 )
    {
      LODWORD(v58) = PackageStoreDirectory;
      if ( LogAdapter::g_Logger )
      {
        v11 = (CCbsPackage *)&qword_1802EB518;
        if ( this[15] )
          v11 = this[15];
        v43 = v11;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to get package store directory to store manifest for package: {}",
          (__int64)&v43);
        v47 = (wchar_t *)&v58;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v47);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE53,
        (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
        (const char *)v7,
        v42);
      goto LABEL_26;
    }
    lpExistingFileName = 0;
    ManifestPath = CCbsPackage::GetManifestPath((CCbsPackage *)this, a1, (wchar_t **)&lpExistingFileName);
    v7 = ManifestPath;
    if ( ManifestPath < 0 )
    {
      LODWORD(v58) = ManifestPath;
      if ( LogAdapter::g_Logger )
      {
        v13 = (CCbsPackage *)&qword_1802EB518;
        if ( this[15] )
          v13 = this[15];
        v43 = v13;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to get manifest path for package: {}",
          (__int64)&v43);
        v47 = (wchar_t *)&v58;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v47);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE57,
        (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
        (const char *)v7,
        v42);
      goto LABEL_33;
    }
    lpFileName = 0;
    v14 = SczAllocFromSz(&lpFileName, v45);
    v7 = v14;
    if ( v14 < 0 )
    {
      v15 = 3674;
LABEL_36:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
        (const char *)(unsigned int)v14,
        v42);
LABEL_37:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
LABEL_33:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
LABEL_26:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v45);
LABEL_19:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v46);
      MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v54);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v44);
LABEL_114:
      ParsingSession::~ParsingSession((ParsingSession *)v56);
      return v7;
    }
    v16 = (CCbsPackage *)&qword_1802EB518;
    v17 = &qword_1802EB518;
    if ( this[15] )
      v17 = (const wchar_t *)this[15];
    v14 = SczAllocConcat2Sz(&lpFileName, v17, L".mum");
    v7 = v14;
    if ( v14 < 0 )
    {
      v15 = 3676;
      goto LABEL_36;
    }
    v18 = v43;
    v19 = 0;
    v20 = (wchar_t *)lpFileName;
    v21 = 0;
    v52 = 0;
    v22 = (wchar_t *)lpExistingFileName;
    v51 = 0;
    if ( *((_DWORD *)v43 + 221) )
    {
      v23 = FileReplaceExtension((wchar_t *)lpExistingFileName);
      v7 = v23;
      if ( v23 < 0 )
      {
        LODWORD(v58) = v23;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to replace extension for session guide source");
          v43 = (CCbsPackage *)&v58;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v43);
        }
        v24 = 3683;
LABEL_47:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
          (const char *)v7,
          v42);
LABEL_48:
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v51);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v52);
        goto LABEL_37;
      }
      v25 = FileReplaceExtension(v20);
      v7 = v25;
      if ( v25 < 0 )
      {
        LODWORD(v58) = v25;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to replace extension for session guide target");
          v43 = (CCbsPackage *)&v58;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v43);
        }
        v24 = 3686;
        goto LABEL_47;
      }
      v21 = v52;
      v19 = v51;
      v18 = v43;
    }
    v47 = 0;
    CatalogPath = CCbsPackage::GetCatalogPath(v18, v58, &v47);
    v7 = CatalogPath;
    if ( CatalogPath < 0 )
    {
      LODWORD(v58) = CatalogPath;
      if ( LogAdapter::g_Logger )
      {
        if ( *((_QWORD *)v43 + 15) )
          v16 = (CCbsPackage *)*((_QWORD *)v43 + 15);
        v43 = v16;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to get catalog path for package: {}",
          (__int64)&v43);
        FastCbsIdentityString = &v58;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&FastCbsIdentityString);
      }
      v28 = 3691;
LABEL_60:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
        (const char *)v7,
        v42);
LABEL_61:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v47);
      goto LABEL_48;
    }
    v7 = ParseCbsPackage(FastCbsIdentityString, v22, (struct ParsingSession *)v56, v27);
    if ( (v7 & 0x80000000) != 0 )
    {
      CCbsSession::MarkPackageStoreCorrupt(v58);
      LODWORD(v58) = v7;
      if ( LogAdapter::g_Logger )
      {
        FastCbsIdentityString = v22;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to parse manifest: {}",
          (__int64)&FastCbsIdentityString);
        v43 = (CCbsPackage *)&v58;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v43);
      }
      v28 = 3700;
      goto LABEL_60;
    }
    v29 = v57;
    InitPointer = (struct CCbsIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v44);
    CbsIdentityFromAssemblyIdentity = GetCbsIdentityFromAssemblyIdentity(
                                        (const struct IDENTITY_TYPE *)(v29 + 304),
                                        InitPointer,
                                        0);
    v7 = CbsIdentityFromAssemblyIdentity;
    if ( CbsIdentityFromAssemblyIdentity < 0 )
    {
      LODWORD(v58) = CbsIdentityFromAssemblyIdentity;
      if ( LogAdapter::g_Logger )
      {
        FastCbsIdentityString = v22;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to convert from package assembly to CBSIdentity on manifest: {}",
          (__int64)&FastCbsIdentityString);
        v43 = (CCbsPackage *)&v58;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v43);
      }
      v28 = 3705;
      goto LABEL_60;
    }
    if ( (unsigned int)CCbsIdentity::IsFastEqual(*((CCbsIdentity **)v43 + 14), v44) != 1 )
    {
      v7 = -2146498536;
      LODWORD(v58) = -2146498536;
      if ( LogAdapter::g_Logger )
      {
        FastCbsIdentityString = GetFastCbsIdentityString(v44);
        if ( *((_QWORD *)v43 + 15) )
          v16 = (CCbsPackage *)*((_QWORD *)v43 + 15);
        v53 = v16;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Identity mismatch on storing the package: Specified Identity: {}, actual package Identity: {}",
          (__int64)&v53,
          (__int64)&FastCbsIdentityString);
        v43 = (CCbsPackage *)&v58;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v43);
      }
      v28 = 3711;
      goto LABEL_60;
    }
    v32 = &qword_1802EB518;
    if ( *((_QWORD *)v43 + 15) )
      v32 = (const wchar_t *)*((_QWORD *)v43 + 15);
    v33 = StorePackageCatalog(v47, v46, v45, v32);
    v7 = v33;
    if ( v33 < 0 )
    {
      LODWORD(v58) = v33;
      if ( LogAdapter::g_Logger )
      {
        if ( *((_QWORD *)v43 + 15) )
          v16 = (CCbsPackage *)*((_QWORD *)v43 + 15);
        v53 = v16;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to install catalog for package: {}",
          (__int64)&v53);
        FastCbsIdentityString = &v58;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&FastCbsIdentityString);
      }
      v28 = 3720;
      goto LABEL_60;
    }
    if ( *((_DWORD *)v43 + 221) && v19 )
    {
      if ( GetFileAttributesW(v19) != -1 )
      {
        SetFileAttributesW(v19, 0x80u);
        LogAdapter::TraceAtLevel<>(1, "File already exists when adding the manifest.");
      }
      if ( !MoveFileExW((LPCWSTR)v21, v19, 1u) )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          v53 = (void *)v19;
          FastCbsIdentityString = v21;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to move package session guide '{}' to store: {}",
            (__int64)&FastCbsIdentityString,
            (__int64)&v53);
          if ( LastError > 0 )
            v35 = (unsigned __int16)LastError | 0x80070000;
          else
            v35 = LastError;
          LODWORD(v58) = v35;
          v43 = (CCbsPackage *)&v58;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)&v43);
        }
        if ( LastError )
        {
          v36 = (unsigned int)LastError;
          v37 = 3737;
LABEL_96:
          v7 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v37,
                 (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
                 (const char *)v36,
                 v42);
          goto LABEL_61;
        }
        goto LABEL_113;
      }
      v53 = (void *)v19;
      v38 = FlushFileToDisk(v19);
      if ( v38 < 0 )
        LogAdapter::TraceAtLevelHr<long,wchar_t const *>(2, (unsigned int)v38, "Unable to flush {}", &v53);
    }
    if ( GetFileAttributesW(v20) != -1 )
    {
      SetFileAttributesW(v20, 0x80u);
      LogAdapter::TraceAtLevel<>(1, "File already exists when adding the manifest.");
    }
    if ( MoveFileExW(v22, v20, 3u) )
    {
      v41 = SetSecurityInfoFromFileTemplate(v20, v45);
      v7 = v41;
      if ( v41 < 0 )
      {
        LODWORD(v58) = v41;
        if ( LogAdapter::g_Logger )
        {
          v53 = v20;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to set security info on '{}'",
            (__int64)&v53);
          FastCbsIdentityString = &v58;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&FastCbsIdentityString);
        }
        v28 = 3756;
        goto LABEL_60;
      }
    }
    else
    {
      v39 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        v53 = v20;
        FastCbsIdentityString = v22;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to move package manifest '{}' to store: {}",
          (__int64)&FastCbsIdentityString,
          (__int64)&v53);
        if ( v39 > 0 )
          v40 = (unsigned __int16)v39 | 0x80070000;
        else
          v40 = v39;
        LODWORD(v58) = v40;
        v43 = (CCbsPackage *)&v58;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)&v43);
      }
      if ( v39 )
      {
        v36 = (unsigned int)v39;
        v37 = 3753;
        goto LABEL_96;
      }
    }
LABEL_113:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v47);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v51);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v52);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v45);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v46);
    MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v54);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v44);
    v7 = 0;
    goto LABEL_114;
  }
  LODWORD(v58) = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No session specified");
    v43 = (CCbsPackage *)&v58;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)&v43);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE3E,
    (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
    (const char *)0x80070057LL,
    v42);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000b5fc  push    rbp
0x18000b5fe  push    rbx
0x18000b5ff  push    rsi
0x18000b600  push    rdi
0x18000b601  push    r12
0x18000b603  push    r13
0x18000b605  push    r14
0x18000b607  lea     rbp, [rsp-1E0h]
0x18000b60f  sub     rsp, 2E0h
0x18000b616  mov     rax, cs:__security_cookie
0x18000b61d  xor     rax, rsp
0x18000b620  mov     [rbp+210h+var_38], rax
0x18000b627  xor     esi, esi
0x18000b629  mov     [rsp+310h+var_2B8], r8
0x18000b62e  mov     [rsp+310h+var_2E0], rdx
0x18000b633  mov     rbx, rdx
0x18000b636  mov     [rbp+210h+var_40], rcx
0x18000b63d  mov     rdi, rcx
0x18000b640  test    rcx, rcx
0x18000b643  jnz     short loc_18000B6C0
0x18000b645  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b64c  mov     edi, 80070057h
0x18000b651  mov     dword ptr [rbp+210h+var_40], edi
0x18000b657  test    rcx, rcx
0x18000b65a  jz      short loc_18000B69E
0x18000b65c  lea     ebx, [rsi+3]
0x18000b65f  xor     edx, edx
0x18000b661  mov     r8d, ebx
0x18000b664  lea     r9, aNoSessionSpeci_0; "No session specified"
0x18000b66b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18000b670  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b677  lea     rax, [rbp+210h+var_40]
0x18000b67e  mov     [rsp+310h+var_2E0], rax
0x18000b683  lea     r9, asc_1802EE7AC; ": {}"
0x18000b68a  lea     rax, [rsp+310h+var_2E0]
0x18000b68f  mov     r8d, ebx
0x18000b692  mov     dl, 1
0x18000b694  mov     qword ptr [rsp+310h+var_2F0], rax; int
0x18000b699  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000b69e  mov     rcx, [rbp+218h]; this
0x18000b6a5  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000b6ac  mov     r9d, edi; char *
0x18000b6af  mov     edx, 0E3Eh; void *
0x18000b6b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b6b9  mov     eax, edi
0x18000b6bb  jmp     loc_18000C21D
0x18000b6c0  lea     rcx, [rbp+210h+var_270]; this
0x18000b6c4  call    ??0ParsingSession@@QEAA@XZ; ParsingSession::ParsingSession(void)
0x18000b6c9  lea     rax, ?vPackageStoreLock@@3UMonitoredCritSec@@A; MonitoredCritSec vPackageStoreLock
0x18000b6d0  mov     [rsp+310h+var_2D8], rsi
0x18000b6d5  mov     [rbp+210h+var_280], rax
0x18000b6d9  lea     rcx, [rbp+210h+var_288]; this
0x18000b6dd  lea     rax, ??_7PackageTrackerLocker@@6B@; const PackageTrackerLocker::`vftable'
0x18000b6e4  mov     [rbp+210h+var_278], sil
0x18000b6e8  mov     [rbp+210h+var_288], rax
0x18000b6ec  call    ?Lock@MonitoredCritSecLocker@@UEAAXXZ; MonitoredCritSecLocker::Lock(void)
0x18000b6f1  test    dword ptr [rdi+2B4h], 80000h
0x18000b6fb  jz      short loc_18000B769
0x18000b6fd  cmp     [rbx+78h], rsi
0x18000b701  lea     r13, qword_1802EB518
0x18000b708  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b70f  cmovnz  r13, [rbx+78h]
0x18000b714  mov     [rsp+310h+var_2E0], r13
0x18000b719  test    rcx, rcx
0x18000b71c  jz      short loc_18000B73D
0x18000b71e  mov     r8d, 1
0x18000b724  lea     rax, [rsp+310h+var_2E0]
0x18000b729  mov     dl, r8b
0x18000b72c  mov     qword ptr [rsp+310h+var_2F0], rax
0x18000b731  lea     r9, aCimSkippingCop; "CIM: Skipping copy of package {}."
0x18000b738  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18000b73d  lea     rcx, [rbp+210h+var_288]; this
0x18000b741  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x18000b746  mov     rcx, [rsp+310h+var_2D8]
0x18000b74b  test    rcx, rcx
0x18000b74e  jz      short loc_18000B761
0x18000b750  mov     rax, [rcx]
0x18000b753  mov     rax, [rax+10h]
0x18000b757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b75c  mov     [rsp+310h+var_2D8], rsi
0x18000b761  mov     r12d, esi
0x18000b764  jmp     loc_18000C211
0x18000b769  lea     rdx, [rsp+310h+var_2C8]; wchar_t **
0x18000b76e  mov     [rsp+310h+var_2C8], rsi
0x18000b773  mov     rcx, rdi; this
0x18000b776  call    ?GetOfflineWindowsDirectory@CCbsSession@@QEBAJPEAPEA_W@Z; CCbsSession::GetOfflineWindowsDirectory(wchar_t * *)
0x18000b77b  mov     r12d, eax
0x18000b77e  test    eax, eax
0x18000b780  jns     loc_18000B838
0x18000b786  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b78d  mov     dword ptr [rbp+210h+var_40], eax
0x18000b793  test    rcx, rcx
0x18000b796  jz      short loc_18000B7FB
0x18000b798  cmp     [rbx+78h], rsi
0x18000b79c  lea     rax, [rsp+310h+var_2E0]
0x18000b7a1  lea     r13, qword_1802EB518
0x18000b7a8  mov     qword ptr [rsp+310h+var_2F0], rax
0x18000b7ad  cmovnz  r13, [rbx+78h]
0x18000b7b2  lea     r9, aFailedToGetOff_16; "Failed to get offline windows directory"...
0x18000b7b9  mov     ebx, 3
0x18000b7be  mov     [rsp+310h+var_2E0], r13
0x18000b7c3  mov     r8d, ebx
0x18000b7c6  xor     edx, edx
0x18000b7c8  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18000b7cd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b7d4  lea     rax, [rbp+210h+var_40]
0x18000b7db  mov     [rsp+310h+var_2C0], rax
0x18000b7e0  lea     r9, asc_1802EE7AC; ": {}"
0x18000b7e7  lea     rax, [rsp+310h+var_2C0]
0x18000b7ec  mov     r8d, ebx
0x18000b7ef  mov     dl, 1
0x18000b7f1  mov     qword ptr [rsp+310h+var_2F0], rax; int
0x18000b7f6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000b7fb  mov     rcx, [rbp+218h]; this
0x18000b802  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000b809  mov     r9d, r12d; char *
0x18000b80c  mov     edx, 0E4Fh; void *
0x18000b811  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b816  lea     rcx, [rsp+310h+var_2C8]
0x18000b81b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18000b820  lea     rcx, [rbp+210h+var_288]; this
0x18000b824  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x18000b829  lea     rcx, [rsp+310h+var_2D8]
0x18000b82e  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x18000b833  jmp     loc_18000C211
0x18000b838  lea     rdx, [rsp+310h+var_2D0]; wchar_t **
0x18000b83d  mov     [rsp+310h+var_2D0], rsi
0x18000b842  mov     rcx, rdi; this
0x18000b845  call    ?GetPackageStoreDirectory@CCbsSession@@QEAAJPEAPEA_W@Z; CCbsSession::GetPackageStoreDirectory(wchar_t * *)
0x18000b84a  mov     r12d, eax
0x18000b84d  test    eax, eax
0x18000b84f  jns     loc_18000B8F4
0x18000b855  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b85c  mov     dword ptr [rbp+210h+var_40], eax
0x18000b862  test    rcx, rcx
0x18000b865  jz      short loc_18000B8CA
0x18000b867  cmp     [rbx+78h], rsi
0x18000b86b  lea     rax, [rsp+310h+var_2E0]
0x18000b870  lea     r13, qword_1802EB518
0x18000b877  mov     qword ptr [rsp+310h+var_2F0], rax
0x18000b87c  cmovnz  r13, [rbx+78h]
0x18000b881  lea     r9, aFailedToGetPac_40; "Failed to get package store directory t"...
0x18000b888  mov     ebx, 3
0x18000b88d  mov     [rsp+310h+var_2E0], r13
0x18000b892  mov     r8d, ebx
0x18000b895  xor     edx, edx
0x18000b897  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18000b89c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b8a3  lea     rax, [rbp+210h+var_40]
0x18000b8aa  mov     [rsp+310h+var_2C0], rax
0x18000b8af  lea     r9, asc_1802EE7AC; ": {}"
0x18000b8b6  lea     rax, [rsp+310h+var_2C0]
0x18000b8bb  mov     r8d, ebx
0x18000b8be  mov     dl, 1
0x18000b8c0  mov     qword ptr [rsp+310h+var_2F0], rax; int
0x18000b8c5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000b8ca  mov     rcx, [rbp+218h]; this
0x18000b8d1  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000b8d8  mov     r9d, r12d; char *
0x18000b8db  mov     edx, 0E53h; void *
0x18000b8e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8e5  lea     rcx, [rsp+310h+var_2D0]
0x18000b8ea  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18000b8ef  jmp     loc_18000B816
0x18000b8f4  lea     r8, [rsp+310h+lpExistingFileName]; wchar_t **
0x18000b8f9  mov     [rsp+310h+lpExistingFileName], rsi
0x18000b8fe  mov     rdx, rdi; struct CCbsSession *
0x18000b901  mov     rcx, rbx; this
0x18000b904  call    ?GetManifestPath@CCbsPackage@@QEAAJPEAVCCbsSession@@PEAPEA_W@Z; CCbsPackage::GetManifestPath(CCbsSession *,wchar_t * *)
0x18000b909  mov     r12d, eax
0x18000b90c  test    eax, eax
0x18000b90e  jns     loc_18000B9B3
0x18000b914  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b91b  mov     dword ptr [rbp+210h+var_40], eax
0x18000b921  test    rcx, rcx
0x18000b924  jz      short loc_18000B989
0x18000b926  cmp     [rbx+78h], rsi
0x18000b92a  lea     rax, [rsp+310h+var_2E0]
0x18000b92f  lea     r13, qword_1802EB518
0x18000b936  mov     qword ptr [rsp+310h+var_2F0], rax
0x18000b93b  cmovnz  r13, [rbx+78h]
0x18000b940  lea     r9, aFailedToGetMan_0; "Failed to get manifest path for package"...
0x18000b947  mov     ebx, 3
0x18000b94c  mov     [rsp+310h+var_2E0], r13
0x18000b951  mov     r8d, ebx
0x18000b954  xor     edx, edx
0x18000b956  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18000b95b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b962  lea     rax, [rbp+210h+var_40]
0x18000b969  mov     [rsp+310h+var_2C0], rax
0x18000b96e  lea     r9, asc_1802EE7AC; ": {}"
0x18000b975  lea     rax, [rsp+310h+var_2C0]
0x18000b97a  mov     r8d, ebx
0x18000b97d  mov     dl, 1
0x18000b97f  mov     qword ptr [rsp+310h+var_2F0], rax; int
0x18000b984  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000b989  mov     rcx, [rbp+218h]; this
0x18000b990  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000b997  mov     r9d, r12d; char *
0x18000b99a  mov     edx, 0E57h; void *
0x18000b99f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9a4  lea     rcx, [rsp+310h+lpExistingFileName]
0x18000b9a9  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18000b9ae  jmp     loc_18000B8E5
0x18000b9b3  mov     rdx, [rsp+310h+var_2D0]
0x18000b9b8  lea     rcx, [rsp+310h+lpFileName]
0x18000b9bd  mov     [rsp+310h+lpFileName], rsi
0x18000b9c2  call    SczAllocFromSz
0x18000b9c7  mov     r12d, eax
0x18000b9ca  test    eax, eax
0x18000b9cc  jns     short loc_18000B9F5
0x18000b9ce  mov     edx, 0E5Ah; void *
0x18000b9d3  mov     rcx, [rbp+218h]; this
0x18000b9da  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000b9e1  mov     r9d, eax; char *
0x18000b9e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9e9  lea     rcx, [rsp+310h+lpFileName]
0x18000b9ee  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18000b9f3  jmp     short loc_18000B9A4
0x18000b9f5  cmp     [rbx+78h], rsi
0x18000b9f9  lea     r13, qword_1802EB518
0x18000ba00  mov     rdx, r13
0x18000ba03  lea     r8, aMum_0; ".mum"
0x18000ba0a  cmovnz  rdx, [rbx+78h]
0x18000ba0f  lea     rcx, [rsp+310h+lpFileName]
0x18000ba14  call    SczAllocConcat2Sz
0x18000ba19  mov     r12d, eax
0x18000ba1c  test    eax, eax
0x18000ba1e  jns     short loc_18000BA27
0x18000ba20  mov     edx, 0E5Ch
0x18000ba25  jmp     short loc_18000B9D3
0x18000ba27  mov     rax, [rsp+310h+var_2E0]
0x18000ba2c  mov     rbx, rsi
0x18000ba2f  mov     rdi, [rsp+310h+lpFileName]
0x18000ba34  mov     r14, rsi
0x18000ba37  mov     [rsp+310h+var_298], rsi
0x18000ba3c  mov     rsi, [rsp+310h+lpExistingFileName]
0x18000ba41  mov     [rsp+310h+var_2A0], rbx
0x18000ba46  cmp     [rax+374h], ebx
0x18000ba4c  jz      loc_18000BB85
0x18000ba52  lea     r8, [rsp+310h+var_298]
0x18000ba57  mov     rcx, rsi; wchar_t *
0x18000ba5a  lea     rdx, aSes; "ses"
0x18000ba61  call    FileReplaceExtension
0x18000ba66  mov     r12d, eax
0x18000ba69  test    eax, eax
0x18000ba6b  jns     loc_18000BAFB
0x18000ba71  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000ba78  mov     dword ptr [rbp+210h+var_40], eax
0x18000ba7e  test    rcx, rcx
0x18000ba81  jz      short loc_18000BAC7
0x18000ba83  mov     ebx, 3
0x18000ba88  lea     r9, aFailedToReplac_0; "Failed to replace extension for session"...
0x18000ba8f  mov     r8d, ebx
0x18000ba92  xor     edx, edx
0x18000ba94  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18000ba99  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000baa0  lea     rax, [rbp+210h+var_40]
0x18000baa7  mov     [rsp+310h+var_2E0], rax
0x18000baac  lea     r9, asc_1802EE7AC; ": {}"
0x18000bab3  lea     rax, [rsp+310h+var_2E0]
0x18000bab8  mov     r8d, ebx
0x18000babb  mov     dl, 1
0x18000babd  mov     qword ptr [rsp+310h+var_2F0], rax; int
0x18000bac2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000bac7  mov     edx, 0E63h; void *
0x18000bacc  mov     rcx, [rbp+218h]; this
0x18000bad3  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000bada  mov     r9d, r12d; char *
0x18000badd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bae2  lea     rcx, [rsp+310h+var_2A0]
0x18000bae7  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18000baec  lea     rcx, [rsp+310h+var_298]
0x18000baf1  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18000baf6  jmp     loc_18000B9E9
0x18000bafb  lea     r8, [rsp+310h+var_2A0]
0x18000bb00  mov     rcx, rdi; wchar_t *
0x18000bb03  lea     rdx, aSes; "ses"
0x18000bb0a  call    FileReplaceExtension
0x18000bb0f  mov     r12d, eax
0x18000bb12  test    eax, eax
0x18000bb14  jns     short loc_18000BB76
0x18000bb16  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000bb1d  mov     dword ptr [rbp+210h+var_40], eax
0x18000bb23  test    rcx, rcx
0x18000bb26  jz      short loc_18000BB6C
0x18000bb28  mov     ebx, 3
0x18000bb2d  lea     r9, aFailedToReplac; "Failed to replace extension for session"...
0x18000bb34  mov     r8d, ebx
0x18000bb37  xor     edx, edx
0x18000bb39  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18000bb3e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000bb45  lea     rax, [rbp+210h+var_40]
0x18000bb4c  mov     [rsp+310h+var_2E0], rax
0x18000bb51  lea     r9, asc_1802EE7AC; ": {}"
0x18000bb58  lea     rax, [rsp+310h+var_2E0]
0x18000bb5d  mov     r8d, ebx
0x18000bb60  mov     dl, 1
0x18000bb62  mov     qword ptr [rsp+310h+var_2F0], rax
0x18000bb67  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
  ... truncated ...
```
