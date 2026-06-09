# CCbsSession::PrepareForPostponedReserveExecution(void)

- ea: `0x1800caa88`
- end: `0x1800cb9ad`
- name: `?PrepareForPostponedReserveExecution@CCbsSession@@QEAAJXZ`
- size: `3877`
- prototype: `__int64 __fastcall(CCbsSession *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, installer_update`

## callers

- `0x180172330`

## callees

- `0x180011a14`
- `0x180013250`
- `0x180015420`
- `0x180023ca8`
- `0x1800261e0`
- `0x18002a2bc`
- `0x180048fc0`
- `0x18004e388`
- `0x180057c28`
- `0x180059a00`
- `0x18005aa38`
- `0x180093c4c`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a108c`
- `0x1800a658c`
- `0x1800caa88`
- `0x1800e4f40`
- `0x1800eb920`
- `0x18010ddd8`
- `0x180158a44`
- `0x1801c10d0`
- `0x1801cf788`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800cadc6`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800cadc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cae25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800caf07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb1c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb2d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cae25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800caf07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb1c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb2d9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800cae15`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800caef3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800cae15`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800caef3`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800cae86`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800caf76`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800cae86`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800caf76`

## string_xrefs

- `0x1800caf2a`: `Failed to copy cab into sandbox. Source: {} Target: {}`
- `0x1800cae52`: `Failed to copy metadata container into sandbox. Source: {} Target: {}`
- `0x1800cb1ea`: `Failed to move metadata container into sandbox. Source: {} Target: {}`
- `0x1800cb2f8`: `Failed to move cab into sandbox. Source: {} Target: {}`
- `0x1800caaff`: `Failed to get servicing directory sandboxes path`
- `0x1800cabc3`: `Failed to remove directory {}`
- `0x1800cb5e5`: `Failed to remove postponed package from package tracker`
- `0x1800cb07e`: `Failed to move directory. Source: {} Target: {}`
- `0x1800cb3db`: `Failed to move directory. Source: {} Target: {}`
- `0x1800cb463`: `Failed to move directory. Source: {} Target: {}`
- `0x1800cb4e0`: `Failed to move directory. Source: {} Target: {}`
- `0x1800cb568`: `Failed to move directory. Source: {} Target: {}`
- `0x1800cb894`: `Failed to move contents of local file system source directory. Source: {} Target: {}`
- `0x1800cb8f9`: `Failed to move contents of local file system source directory. Source: {} Target: {}`
- `0x1800cb7f0`: `Moving source directory top level contents {} to {}`
- `0x1800cb842`: `Moving source directory contents recursively {} to {}`
- `0x1800cac3b`: `Failed creating {} directory.`
- `0x1800cb655`: `Failed creating {} directory.`

## pseudocode

```c
__int64 __fastcall CCbsSession::PrepareForPostponedReserveExecution(CCbsSession *this)
{
  __int64 v1; // rsi
  int ServicingDirectory; // eax
  unsigned int v4; // ebx
  unsigned __int64 v5; // r9
  __int64 v6; // rdx
  int v7; // eax
  wchar_t *v8; // rdi
  int v9; // eax
  int Directory; // eax
  int v11; // eax
  CCbsPackage ***v12; // r13
  LPCWSTR *v13; // rax
  CCbsPackage **v14; // r12
  int v15; // eax
  const wchar_t *v16; // rdx
  CCbsPackage ****v17; // rbx
  int v18; // r14d
  const WCHAR *v19; // rcx
  wchar_t *v20; // rax
  int v21; // eax
  bool v22; // al
  LPCWSTR v23; // r14
  signed int LastError; // ebx
  unsigned int v25; // eax
  int v26; // eax
  bool v27; // al
  LPCWSTR v28; // rbx
  const WCHAR *v29; // rcx
  signed int v30; // esi
  unsigned int v31; // eax
  BOOL v32; // r13d
  int v33; // esi
  int v34; // eax
  CCbsPackage *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rdx
  unsigned __int64 v38; // r9
  unsigned int v39; // eax
  signed int v40; // esi
  unsigned int v41; // eax
  __int64 v42; // rdx
  CCbsPackage *v43; // rax
  unsigned __int64 v44; // r9
  __int64 v45; // rdx
  BOOL IsOfflineUnitTestMode; // edi
  CCbsSession *v47; // rcx
  int LocalFileSystemSources; // eax
  __int64 v49; // rbx
  BOOL v50; // r15d
  _QWORD *v51; // rdi
  _QWORD *v52; // r12
  __int64 v53; // rdx
  unsigned int v55; // [rsp+20h] [rbp-A9h]
  int v56; // [rsp+20h] [rbp-A9h]
  unsigned int v57[2]; // [rsp+30h] [rbp-99h] BYREF
  int v58[2]; // [rsp+38h] [rbp-91h] BYREF
  LPCWSTR *v59; // [rsp+40h] [rbp-89h] BYREF
  wchar_t *v60; // [rsp+48h] [rbp-81h] BYREF
  __int64 v61; // [rsp+50h] [rbp-79h] BYREF
  __int64 v62; // [rsp+58h] [rbp-71h] BYREF
  int v63[2]; // [rsp+60h] [rbp-69h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+68h] [rbp-61h] BYREF
  CCbsPackage ***v65; // [rsp+70h] [rbp-59h] BYREF
  CCbsPackage ****v66; // [rsp+78h] [rbp-51h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v68[24]; // [rsp+90h] [rbp-39h] BYREF
  __int64 v69; // [rsp+A8h] [rbp-21h]
  _QWORD *v70; // [rsp+B8h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  *((_DWORD *)this + 552) |= 0x20000u;
  v1 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  ServicingDirectory = CCbsSession::GetServicingDirectory(this, L"Sandboxes\\", &v60);
  v4 = ServicingDirectory;
  if ( ServicingDirectory < 0 )
  {
    LODWORD(v65) = ServicingDirectory;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get servicing directory sandboxes path");
      lpExistingFileName = (LPCWSTR)&v65;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&lpExistingFileName);
    }
    v5 = v4;
    v6 = 309;
    goto LABEL_8;
  }
  v7 = SczAllocConcatSz(&v60, *((_QWORD *)this + 80));
  v4 = v7;
  if ( v7 < 0 )
  {
    v6 = 311;
LABEL_7:
    v5 = (unsigned int)v7;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
      (const char *)v5,
      v55);
    goto LABEL_152;
  }
  v7 = SczEnsureBackslashTerminated(&v60);
  v4 = v7;
  if ( v7 < 0 )
  {
    v6 = 313;
    goto LABEL_7;
  }
  v8 = v60;
  v9 = CCbsSession::RemoveDirectoryViaCbsTemp(this, v60);
  v4 = v9;
  if ( v9 < 0 )
  {
    LODWORD(v65) = v9;
    if ( LogAdapter::g_Logger )
    {
      lpExistingFileName = v8;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to remove directory {}",
        (__int64)&lpExistingFileName);
      v66 = &v65;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v66);
    }
    v5 = v4;
    v6 = 316;
    goto LABEL_8;
  }
  Directory = RecursivelyCreateDirectory(v8, 0);
  v4 = Directory;
  if ( Directory < 0 )
  {
    LODWORD(v65) = Directory;
    if ( LogAdapter::g_Logger )
    {
      lpExistingFileName = v8;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed creating {} directory.",
        (__int64)&lpExistingFileName);
      v66 = &v65;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v66);
    }
    v5 = v4;
    v6 = 319;
    goto LABEL_8;
  }
  v11 = CCbsSession::TagEmptyDirectory(this, v8);
  v4 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v65) = v11;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to put servicing sandbox in reserve");
      lpExistingFileName = (LPCWSTR)&v65;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&lpExistingFileName);
    }
    v5 = v4;
    v6 = 322;
    goto LABEL_8;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::GetImpl'::`2'::impl) )
    Windows::AutoGenericHandleBase<IMultiSourceUpdateContainer *,0,Windows::AutoReleasePtr<IMultiSourceUpdateContainer>>::Close((char *)this + 2368);
  v12 = (CCbsPackage ***)*((_QWORD *)this + 102);
  v13 = (LPCWSTR *)&v12[*((_QWORD *)this + 100)];
  v59 = v13;
  while ( 1 )
  {
    v65 = v12;
    if ( v12 == (CCbsPackage ***)v13 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::GetImpl'::`2'::impl)
        && *((_BYTE *)this + 2254) )
      {
        CCbsStringArray::CCbsStringArray((CCbsStringArray *)v68);
        IsOfflineUnitTestMode = CCbsSession::IsOfflineUnitTestMode(this);
        LocalFileSystemSources = CCbsSession::GetLocalFileSystemSources(v47, (struct CCbsStringArray *)v68, 0, 1, 0);
        v4 = LocalFileSystemSources;
        if ( LocalFileSystemSources < 0 )
        {
          LODWORD(v65) = LocalFileSystemSources;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get local file system sources");
            *(_QWORD *)v58 = &v65;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v58);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1CB,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
            (const char *)v4,
            v56);
          CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v68);
          goto LABEL_152;
        }
        if ( v69 )
        {
          v49 = v62;
          v50 = IsOfflineUnitTestMode;
          v51 = v70;
          v52 = &v70[v69];
          while ( 1 )
          {
            if ( v51 == v52 )
              goto LABEL_150;
            *(_QWORD *)v57 = v49;
            if ( LogAdapter::g_Logger )
              LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                (__int64)LogAdapter::g_Logger,
                1,
                1,
                (__int64)"Moving source directory top level contents {} to {}",
                (__int64)v51,
                (__int64)v57);
            v18 = CbsMoveDirectoryContents((v50 + 2) | 4u, *v51, v49);
            if ( v18 < 0 )
              break;
            *(_QWORD *)v57 = v1;
            if ( LogAdapter::g_Logger )
              LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                (__int64)LogAdapter::g_Logger,
                1,
                1,
                (__int64)"Moving source directory contents recursively {} to {}",
                (__int64)v51,
                (__int64)v57);
            v18 = CbsMoveDirectoryContents((unsigned int)(v50 + 2), *v51, v1);
            if ( v18 < 0 )
            {
              LODWORD(lpNewFileName[0]) = v18;
              if ( LogAdapter::g_Logger )
              {
                *(_QWORD *)v58 = v1;
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (__int64)"Failed to move contents of local file system source directory. Source: {} Target: {}",
                  (__int64)v51,
                  (__int64)v58);
                v59 = lpNewFileName;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v59);
              }
              v53 = 480;
LABEL_149:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v53,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
                (const char *)(unsigned int)v18,
                v56);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v68);
              goto LABEL_121;
            }
            ++v51;
          }
          LODWORD(v66) = v18;
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v58 = v1;
            LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to move contents of local file system source directory. Source: {} Target: {}",
              (__int64)v51,
              (__int64)v58);
            *(_QWORD *)v63 = &v66;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v63);
          }
          v53 = 474;
          goto LABEL_149;
        }
LABEL_150:
        CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v68);
      }
LABEL_151:
      v4 = 0;
      goto LABEL_152;
    }
    v14 = *v12;
    v66 = 0;
    v15 = SczAllocConcatSz(&v66, v8);
    v4 = v15;
    if ( v15 < 0 )
    {
      v45 = 335;
LABEL_124:
      v44 = (unsigned int)v15;
      goto LABEL_125;
    }
    v16 = &qword_1802EB518;
    if ( *((_QWORD *)*v14 + 15) )
      v16 = (const wchar_t *)*((_QWORD *)*v14 + 15);
    v15 = SczAllocConcatSz(&v66, v16);
    v4 = v15;
    if ( v15 < 0 )
    {
      v45 = 337;
      goto LABEL_124;
    }
    v17 = v66;
    v18 = RecursivelyCreateDirectory(v66, 0);
    if ( v18 < 0 )
      break;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::GetImpl'::`2'::impl) )
    {
      v19 = (const WCHAR *)*((_QWORD *)*v14 + 139);
      lpExistingFileName = v19;
      if ( v19 )
      {
        v20 = wcsrchr(v19, 0x2Eu);
        lpNewFileName[0] = 0;
        v21 = SczAllocFormatted(lpNewFileName, L"%ws\\metadatacontainer%ws", v17, v20);
        v18 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x15D,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
            (const char *)(unsigned int)v21,
            v55);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(lpNewFileName);
          goto LABEL_120;
        }
        v22 = CCbsSession::IsOfflineUnitTestMode(this);
        v23 = lpNewFileName[0];
        if ( v22 )
        {
          if ( !CopyFileW(lpExistingFileName, lpNewFileName[0], 0) )
          {
            LastError = GetLastError();
            if ( LogAdapter::g_Logger )
            {
              v59 = (LPCWSTR *)v23;
              LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to copy metadata container into sandbox. Source: {} Target: {}",
                (__int64)&lpExistingFileName,
                (__int64)&v59);
              if ( LastError > 0 )
                v25 = (unsigned __int16)LastError | 0x80070000;
              else
                v25 = LastError;
              LODWORD(v65) = v25;
              *(_QWORD *)v57 = &v65;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {0}",
                (__int64)v57);
            }
            if ( LastError )
            {
              v37 = 355;
LABEL_74:
              v38 = (unsigned int)LastError;
LABEL_75:
              v4 = wil::details::in1diag3::Return_Win32(
                     retaddr,
                     (void *)v37,
                     (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
                     (const char *)v38,
                     v55);
LABEL_76:
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(lpNewFileName);
LABEL_126:
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v66);
              goto LABEL_152;
            }
            goto LABEL_84;
          }
        }
        else if ( !MoveFileExW(lpExistingFileName, lpNewFileName[0], 8u) )
        {
          LastError = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v57 = v23;
            LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to move metadata container into sandbox. Source: {} Target: {}",
              (__int64)&lpExistingFileName,
              (__int64)v57);
            if ( LastError > 0 )
              v39 = (unsigned __int16)LastError | 0x80070000;
            else
              v39 = LastError;
            LODWORD(v65) = v39;
            v59 = (LPCWSTR *)&v65;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {0}",
              (__int64)&v59);
          }
          if ( LastError )
          {
            v37 = 362;
            goto LABEL_74;
          }
          goto LABEL_84;
        }
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(lpNewFileName);
      }
    }
    if ( *((_DWORD *)v14 + 2) )
    {
      if ( *((_DWORD *)v14 + 2) == 1 )
      {
        v32 = CCbsSession::IsOfflineUnitTestMode(this);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::GetImpl'::`2'::impl) )
        {
          if ( *((_BYTE *)this + 2254) && CCbsPackage::IsLCUPackage(*v14) )
          {
            if ( v1 )
            {
              v33 = SczAllocFromSz(&v62, v1);
              if ( v33 < 0 )
              {
                v42 = 400;
LABEL_99:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v42,
                  (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
                  (const char *)(unsigned int)v33,
                  v55);
                Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v66);
                v4 = v33;
                goto LABEL_152;
              }
            }
            v33 = SczAllocFromSz(&v61, v17);
            if ( v33 < 0 )
            {
              v42 = 403;
              goto LABEL_99;
            }
            v33 = CbsMoveDirectoryContents(v32, v14[3], v17);
            if ( v33 < 0 )
            {
              LODWORD(v65) = v33;
              if ( LogAdapter::g_Logger )
              {
                *(_QWORD *)v57 = v14[3];
                *(_QWORD *)v58 = v17;
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (__int64)"Failed to move directory. Source: {} Target: {}",
                  (__int64)v57,
                  (__int64)v58);
                v59 = (LPCWSTR *)&v65;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v59);
              }
              v42 = 408;
              goto LABEL_99;
            }
            v1 = v61;
          }
          else
          {
            v18 = CbsMoveDirectoryContents(v32, v14[3], v17);
            if ( v18 < 0 )
            {
              LODWORD(v65) = v18;
              if ( LogAdapter::g_Logger )
              {
                *(_QWORD *)v57 = v14[3];
                *(_QWORD *)v58 = v17;
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (__int64)"Failed to move directory. Source: {} Target: {}",
                  (__int64)v57,
                  (__int64)v58);
                v59 = (LPCWSTR *)&v65;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v59);
              }
              v36 = 415;
              goto LABEL_119;
            }
            v34 = CbsMoveDirectoryContents(v32, *((_QWORD *)*v14 + 138), v17);
            v18 = v34;
            if ( v34 < 0 )
            {
              LODWORD(v65) = v34;
              if ( LogAdapter::g_Logger )
              {
                v35 = *v14;
                *(_QWORD *)v58 = v17;
                *(_QWORD *)v57 = *((_QWORD *)v35 + 138);
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (__int64)"Failed to move directory. Source: {} Target: {}",
                  (__int64)v57,
                  (__int64)v58);
                v59 = (LPCWSTR *)&v65;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v59);
              }
              v36 = 421;
              goto LABEL_119;
            }
          }
        }
        else
        {
          v18 = CbsMoveDirectoryContents(v32, v14[3], v17);
          if ( v18 < 0 )
          {
            LODWORD(v65) = v18;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v57 = v14[3];
              *(_QWORD *)v58 = v17;
              LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to move directory. Source: {} Target: {}",
                (__int64)v57,
                (__int64)v58);
              v59 = (LPCWSTR *)&v65;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)&v59);
            }
            v36 = 429;
            goto LABEL_119;
          }
          v18 = CbsMoveDirectoryContents(v32, *((_QWORD *)*v14 + 138), v17);
          if ( v18 < 0 )
          {
            LODWORD(v65) = v18;
            if ( LogAdapter::g_Logger )
            {
              v43 = *v14;
              *(_QWORD *)v58 = v17;
              *(_QWORD *)v57 = *((_QWORD *)v43 + 138);
              LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to move directory. Source: {} Target: {}",
                (__int64)v57,
                (__int64)v58);
              v59 = (LPCWSTR *)&v65;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)&v59);
            }
            v36 = 435;
            goto LABEL_119;
          }
        }
        v12 = v65;
      }
    }
    else
    {
      lpNewFileName[0] = 0;
      v26 = SczAllocFormatted(lpNewFileName, L"%ws\\package.cab", v17);
      v4 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x172,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
          (const char *)(unsigned int)v26,
          v55);
        goto LABEL_76;
      }
      v27 = CCbsSession::IsOfflineUnitTestMode(this);
      v28 = lpNewFileName[0];
      v29 = (const WCHAR *)v14[5];
      if ( v27 )
      {
        if ( !CopyFileW(v29, lpNewFileName[0], 0) )
        {
          v30 = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            v59 = (LPCWSTR *)v14[5];
            *(_QWORD *)v57 = v28;
            LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to copy cab into sandbox. Source: {} Target: {}",
              (__int64)&v59,
              (__int64)v57);
            if ( v30 > 0 )
              v31 = (unsigned __int16)v30 | 0x80070000;
            else
              v31 = v30;
            LODWORD(v65) = v31;
            *(_QWORD *)v58 = &v65;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {0}",
              (__int64)v58);
          }
          if ( v30 )
          {
            v38 = (unsigned int)v30;
            v37 = 377;
            goto LABEL_75;
          }
          goto LABEL_84;
        }
      }
      else if ( !MoveFileExW(v29, lpNewFileName[0], 8u) )
      {
        v40 = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v57 = v14[5];
          *(_QWORD *)v58 = v28;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to move cab into sandbox. Source: {} Target: {}",
            (__int64)v57,
            (__int64)v58);
          if ( v40 > 0 )
            v41 = (unsigned __int16)v40 | 0x80070000;
          else
            v41 = v40;
          LODWORD(v65) = v41;
          v59 = (LPCWSTR *)&v65;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)&v59);
        }
        if ( v40 )
        {
          v38 = (unsigned int)v40;
          v37 = 382;
          goto LABEL_75;
        }
LABEL_84:
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(lpNewFileName);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v66);
        goto LABEL_151;
      }
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(lpNewFileName);
    }
    v4 = PackageTrackerRemove(*v14);
    if ( (v4 & 0x80000000) != 0 )
    {
      LODWORD(v65) = v4;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to remove postponed package from package tracker");
        *(_QWORD *)v58 = &v65;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v58);
      }
      v44 = v4;
      v45 = 442;
LABEL_125:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v45,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
        (const char *)v44,
        v55);
      goto LABEL_126;
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v66);
    v13 = v59;
    ++v12;
  }
  LODWORD(v65) = v18;
  if ( LogAdapter::g_Logger )
  {
    *(_QWORD *)v58 = v17;
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (__int64)"Failed creating {} directory.",
      (__int64)v58);
    *(_QWORD *)v57 = &v65;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)v57);
  }
  v36 = 340;
LABEL_119:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v36,
    (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
    (const char *)(unsigned int)v18,
    v55);
LABEL_120:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v66);
LABEL_121:
  v4 = v18;
LABEL_152:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v61);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v62);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v60);
  return v4;
}

```

## disassembly

```asm
0x1800caa88  push    rbp
0x1800caa8a  push    rbx
0x1800caa8b  push    rsi
0x1800caa8c  push    rdi
0x1800caa8d  push    r12
0x1800caa8f  push    r13
0x1800caa91  push    r14
0x1800caa93  push    r15
0x1800caa95  lea     rbp, [rsp-1Fh]
0x1800caa9a  sub     rsp, 0E8h
0x1800caaa1  mov     rax, cs:__security_cookie
0x1800caaa8  xor     rax, rsp
0x1800caaab  mov     [rbp+57h+var_50], rax
0x1800caaaf  bts     dword ptr [rcx+8A0h], 11h
0x1800caab7  lea     r8, [rsp+120h+var_D8]; wchar_t **
0x1800caabc  xor     esi, esi
0x1800caabe  mov     [rsp+120h+var_D8], 0
0x1800caac7  lea     rdx, aSandboxes; "Sandboxes\\"
0x1800caace  mov     [rbp+57h+var_D0], rsi
0x1800caad2  mov     r15, rcx
0x1800caad5  mov     [rbp+57h+var_C8], 0
0x1800caadd  call    ?GetServicingDirectory@CCbsSession@@QEAAJPEB_WPEAPEA_W@Z; CCbsSession::GetServicingDirectory(wchar_t const *,wchar_t * *)
0x1800caae2  mov     ebx, eax
0x1800caae4  test    eax, eax
0x1800caae6  jns     short loc_1800CAB3E
0x1800caae8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800caaef  mov     dword ptr [rbp+57h+var_B0], eax
0x1800caaf2  test    rcx, rcx
0x1800caaf5  jz      short loc_1800CAB34
0x1800caaf7  lea     edi, [rsi+3]
0x1800caafa  xor     edx, edx
0x1800caafc  mov     r8d, edi
0x1800caaff  lea     r9, aFailedToGetSer_4; "Failed to get servicing directory sandb"...
0x1800cab06  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cab0b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cab12  lea     rax, [rbp+57h+var_B0]
0x1800cab16  mov     [rbp+57h+lpExistingFileName], rax
0x1800cab1a  lea     r9, asc_1802EE7AC; ": {}"
0x1800cab21  lea     rax, [rbp+57h+lpExistingFileName]
0x1800cab25  mov     r8d, edi
0x1800cab28  mov     dl, 1
0x1800cab2a  mov     qword ptr [rsp+120h+var_100], rax
0x1800cab2f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cab34  mov     r9d, ebx
0x1800cab37  mov     edx, 135h
0x1800cab3c  jmp     short loc_1800CAB5D
0x1800cab3e  mov     rdx, [r15+280h]
0x1800cab45  lea     rcx, [rsp+120h+var_D8]
0x1800cab4a  call    SczAllocConcatSz
0x1800cab4f  mov     ebx, eax
0x1800cab51  test    eax, eax
0x1800cab53  jns     short loc_1800CAB72
0x1800cab55  mov     edx, 137h; void *
0x1800cab5a  mov     r9d, eax; char *
0x1800cab5d  mov     rcx, [rbp+5Fh]; this
0x1800cab61  lea     r8, aOnecoreBaseCbs_83; "onecore\\base\\cbs\\core\\cbssessionsto"...
0x1800cab68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cab6d  jmp     loc_1800CB96E
0x1800cab72  lea     rcx, [rsp+120h+var_D8]
0x1800cab77  call    SczEnsureBackslashTerminated
0x1800cab7c  mov     ebx, eax
0x1800cab7e  test    eax, eax
0x1800cab80  jns     short loc_1800CAB89
0x1800cab82  mov     edx, 139h
0x1800cab87  jmp     short loc_1800CAB5A
0x1800cab89  mov     rdi, [rsp+120h+var_D8]
0x1800cab8e  mov     rcx, r15; this
0x1800cab91  mov     rdx, rdi; wchar_t *
0x1800cab94  call    ?RemoveDirectoryViaCbsTemp@CCbsSession@@QEAAJQEB_W@Z; CCbsSession::RemoveDirectoryViaCbsTemp(wchar_t const * const)
0x1800cab99  mov     ebx, eax
0x1800cab9b  test    eax, eax
0x1800cab9d  jns     short loc_1800CAC07
0x1800cab9f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800caba6  mov     dword ptr [rbp+57h+var_B0], eax
0x1800caba9  test    rcx, rcx
0x1800cabac  jz      short loc_1800CABFA
0x1800cabae  mov     [rbp+57h+lpExistingFileName], rdi
0x1800cabb2  lea     rax, [rbp+57h+lpExistingFileName]
0x1800cabb6  mov     edi, 3
0x1800cabbb  mov     qword ptr [rsp+120h+var_100], rax
0x1800cabc0  mov     r8d, edi
0x1800cabc3  lea     r9, aFailedToRemove_0; "Failed to remove directory {}"
0x1800cabca  xor     edx, edx
0x1800cabcc  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800cabd1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cabd8  lea     rax, [rbp+57h+var_B0]
0x1800cabdc  mov     [rbp+57h+var_A8], rax
0x1800cabe0  lea     r9, asc_1802EE7AC; ": {}"
0x1800cabe7  lea     rax, [rbp+57h+var_A8]
0x1800cabeb  mov     r8d, edi
0x1800cabee  mov     dl, 1
0x1800cabf0  mov     qword ptr [rsp+120h+var_100], rax
0x1800cabf5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cabfa  mov     r9d, ebx
0x1800cabfd  mov     edx, 13Ch
0x1800cac02  jmp     loc_1800CAB5D
0x1800cac07  xor     edx, edx
0x1800cac09  mov     rcx, rdi
0x1800cac0c  call    RecursivelyCreateDirectory
0x1800cac11  mov     ebx, eax
0x1800cac13  test    eax, eax
0x1800cac15  jns     short loc_1800CAC7F
0x1800cac17  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cac1e  mov     dword ptr [rbp+57h+var_B0], eax
0x1800cac21  test    rcx, rcx
0x1800cac24  jz      short loc_1800CAC72
0x1800cac26  mov     [rbp+57h+lpExistingFileName], rdi
0x1800cac2a  lea     rax, [rbp+57h+lpExistingFileName]
0x1800cac2e  mov     edi, 3
0x1800cac33  mov     qword ptr [rsp+120h+var_100], rax
0x1800cac38  mov     r8d, edi
0x1800cac3b  lea     r9, aFailedCreating; "Failed creating {} directory."
0x1800cac42  xor     edx, edx
0x1800cac44  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800cac49  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cac50  lea     rax, [rbp+57h+var_B0]
0x1800cac54  mov     [rbp+57h+var_A8], rax
0x1800cac58  lea     r9, asc_1802EE7AC; ": {}"
0x1800cac5f  lea     rax, [rbp+57h+var_A8]
0x1800cac63  mov     r8d, edi
0x1800cac66  mov     dl, 1
0x1800cac68  mov     qword ptr [rsp+120h+var_100], rax
0x1800cac6d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cac72  mov     r9d, ebx
0x1800cac75  mov     edx, 13Fh
0x1800cac7a  jmp     loc_1800CAB5D
0x1800cac7f  mov     rdx, rdi
0x1800cac82  mov     rcx, r15
0x1800cac85  call    ?TagEmptyDirectory@CCbsSession@@QEAAJPEB_WW4ScenarioId@IUpdateReserveManager@@@Z; CCbsSession::TagEmptyDirectory(wchar_t const *,IUpdateReserveManager::ScenarioId)
0x1800cac8a  mov     ebx, eax
0x1800cac8c  test    eax, eax
0x1800cac8e  jns     short loc_1800CACEB
0x1800cac90  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cac97  mov     dword ptr [rbp+57h+var_B0], eax
0x1800cac9a  test    rcx, rcx
0x1800cac9d  jz      short loc_1800CACDE
0x1800cac9f  mov     edi, 3
0x1800caca4  lea     r9, aFailedToPutSer; "Failed to put servicing sandbox in rese"...
0x1800cacab  mov     r8d, edi
0x1800cacae  xor     edx, edx
0x1800cacb0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cacb5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cacbc  lea     rax, [rbp+57h+var_B0]
0x1800cacc0  mov     [rbp+57h+lpExistingFileName], rax
0x1800cacc4  lea     r9, asc_1802EE7AC; ": {}"
0x1800caccb  lea     rax, [rbp+57h+lpExistingFileName]
0x1800caccf  mov     r8d, edi
0x1800cacd2  mov     dl, 1
0x1800cacd4  mov     qword ptr [rsp+120h+var_100], rax
0x1800cacd9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cacde  mov     r9d, ebx
0x1800cace1  mov     edx, 142h
0x1800cace6  jmp     loc_1800CAB5D
0x1800caceb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::GetImpl(void)'::`2'::impl
0x1800cacf2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::__private_IsEnabled(void)
0x1800cacf7  test    al, al
0x1800cacf9  jz      short loc_1800CAD07
0x1800cacfb  lea     rcx, [r15+940h]
0x1800cad02  call    ?Close@?$AutoGenericHandleBase@PEAVIMultiSourceUpdateContainer@@$0A@V?$AutoReleasePtr@VIMultiSourceUpdateContainer@@@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<IMultiSourceUpdateContainer *,0,Windows::AutoReleasePtr<IMultiSourceUpdateContainer>>::Close(void)
0x1800cad07  mov     rax, [r15+320h]
0x1800cad0e  mov     r13, [r15+330h]
0x1800cad15  lea     rax, ds:0[rax*8]
0x1800cad1d  add     rax, r13
0x1800cad20  mov     [rsp+120h+var_E0], rax
0x1800cad25  mov     [rbp+57h+var_B0], r13
0x1800cad29  cmp     r13, rax
0x1800cad2c  jz      loc_1800CB6E4
0x1800cad32  mov     r12, [r13+0]
0x1800cad36  lea     rcx, [rbp+57h+var_A8]
0x1800cad3a  mov     rdx, rdi
0x1800cad3d  mov     [rbp+57h+var_A8], 0
0x1800cad45  call    SczAllocConcatSz
0x1800cad4a  mov     ebx, eax
0x1800cad4c  test    eax, eax
0x1800cad4e  js      loc_1800CB6BE
0x1800cad54  mov     rax, [r12]
0x1800cad58  lea     rdx, qword_1802EB518
0x1800cad5f  lea     rcx, [rbp+57h+var_A8]
0x1800cad63  cmp     qword ptr [rax+78h], 0
0x1800cad68  cmovnz  rdx, [rax+78h]
0x1800cad6d  call    SczAllocConcatSz
0x1800cad72  mov     ebx, eax
0x1800cad74  test    eax, eax
0x1800cad76  js      loc_1800CB6B7
0x1800cad7c  mov     rbx, [rbp+57h+var_A8]
0x1800cad80  xor     edx, edx
0x1800cad82  mov     rcx, rbx
0x1800cad85  call    RecursivelyCreateDirectory
0x1800cad8a  mov     r14d, eax
0x1800cad8d  test    eax, eax
0x1800cad8f  js      loc_1800CB62E
0x1800cad95  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::GetImpl(void)'::`2'::impl
0x1800cad9c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::__private_IsEnabled(void)
0x1800cada1  test    al, al
0x1800cada3  jz      loc_1800CAEA3
0x1800cada9  mov     rax, [r12]
0x1800cadad  mov     rcx, [rax+458h]; Str
0x1800cadb4  mov     [rbp+57h+lpExistingFileName], rcx
0x1800cadb8  test    rcx, rcx
0x1800cadbb  jz      loc_1800CAEA3
0x1800cadc1  mov     edx, 2Eh ; '.'; Ch
0x1800cadc6  call    cs:__imp_wcsrchr
0x1800cadcd  nop     dword ptr [rax+rax+00h]
0x1800cadd2  mov     r8, rbx
0x1800cadd5  mov     [rbp+57h+lpNewFileName], 0
0x1800caddd  mov     r9, rax
0x1800cade0  lea     rdx, aWsMetadatacont_0; "%ws\\metadatacontainer%ws"
0x1800cade7  lea     rcx, [rbp+57h+lpNewFileName]
0x1800cadeb  call    SczAllocFormatted
0x1800cadf0  mov     r14d, eax
0x1800cadf3  test    eax, eax
0x1800cadf5  js      loc_1800CB26C
0x1800cadfb  mov     rcx, r15; this
0x1800cadfe  call    ?IsOfflineUnitTestMode@CCbsSession@@QEBA_NXZ; CCbsSession::IsOfflineUnitTestMode(void)
0x1800cae03  mov     r14, [rbp+57h+lpNewFileName]
0x1800cae07  mov     rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x1800cae0b  mov     rdx, r14; lpNewFileName
0x1800cae0e  test    al, al
0x1800cae10  jz      short loc_1800CAE80
0x1800cae12  xor     r8d, r8d; bFailIfExists
0x1800cae15  call    cs:__imp_CopyFileW
0x1800cae1c  nop     dword ptr [rax+rax+00h]
0x1800cae21  test    eax, eax
0x1800cae23  jnz     short loc_1800CAE9A
0x1800cae25  call    cs:__imp_GetLastError
0x1800cae2c  nop     dword ptr [rax+rax+00h]
0x1800cae31  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cae38  mov     ebx, eax
0x1800cae3a  test    rcx, rcx
0x1800cae3d  jz      loc_1800CB191
0x1800cae43  lea     rax, [rsp+120h+var_E0]
0x1800cae48  mov     [rsp+120h+var_E0], r14
0x1800cae4d  mov     [rsp+120h+var_F8], rax
0x1800cae52  lea     r9, aFailedToCopyMe; "Failed to copy metadata container into "...
0x1800cae59  lea     rax, [rbp+57h+lpExistingFileName]
0x1800cae5d  mov     edi, 3
0x1800cae62  mov     r8d, edi
0x1800cae65  mov     qword ptr [rsp+120h+var_100], rax
0x1800cae6a  xor     edx, edx
0x1800cae6c  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1800cae71  test    ebx, ebx
0x1800cae73  jg      loc_1800CB15B
0x1800cae79  mov     eax, ebx
0x1800cae7b  jmp     loc_1800CB163
0x1800cae80  mov     r8d, 8; dwFlags
0x1800cae86  call    cs:__imp_MoveFileExW
0x1800cae8d  nop     dword ptr [rax+rax+00h]
0x1800cae92  test    eax, eax
0x1800cae94  jz      loc_1800CB1C1
0x1800cae9a  lea     rcx, [rbp+57h+lpNewFileName]
0x1800cae9e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800caea3  cmp     dword ptr [r12+8], 0
0x1800caea9  jnz     loc_1800CAF98
0x1800caeaf  mov     r8, rbx
0x1800caeb2  mov     [rbp+57h+lpNewFileName], 0
0x1800caeba  lea     rdx, aWsPackageCab; "%ws\\package.cab"
0x1800caec1  lea     rcx, [rbp+57h+lpNewFileName]
0x1800caec5  call    SczAllocFormatted
0x1800caeca  mov     ebx, eax
0x1800caecc  test    eax, eax
0x1800caece  js      loc_1800CB382
0x1800caed4  mov     rcx, r15; this
0x1800caed7  call    ?IsOfflineUnitTestMode@CCbsSession@@QEBA_NXZ; CCbsSession::IsOfflineUnitTestMode(void)
0x1800caedc  mov     rbx, [rbp+57h+lpNewFileName]
0x1800caee0  mov     rcx, [r12+28h]; lpExistingFileName
0x1800caee5  mov     rdx, rbx; lpNewFileName
0x1800caee8  test    al, al
0x1800caeea  jz      loc_1800CAF70
0x1800caef0  xor     r8d, r8d; bFailIfExists
0x1800caef3  call    cs:__imp_CopyFileW
0x1800caefa  nop     dword ptr [rax+rax+00h]
0x1800caeff  test    eax, eax
0x1800caf01  jnz     loc_1800CAF8A
0x1800caf07  call    cs:__imp_GetLastError
0x1800caf0e  nop     dword ptr [rax+rax+00h]
0x1800caf13  mov     esi, eax
0x1800caf15  mov     rax, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800caf1c  test    rax, rax
0x1800caf1f  jz      loc_1800CB2C8
0x1800caf25  mov     rcx, [r12+28h]
0x1800caf2a  lea     r9, aFailedToCopyCa; "Failed to copy cab into sandbox. Source"...
0x1800caf31  mov     [rsp+120h+var_E0], rcx
0x1800caf36  mov     edi, 3
0x1800caf3b  lea     rcx, [rsp+120h+var_F0]
0x1800caf40  mov     qword ptr [rsp+120h+var_F0], rbx
0x1800caf45  mov     [rsp+120h+var_F8], rcx
0x1800caf4a  mov     r8d, edi
0x1800caf4d  lea     rcx, [rsp+120h+var_E0]
0x1800caf52  xor     edx, edx
0x1800caf54  mov     qword ptr [rsp+120h+var_100], rcx
0x1800caf59  mov     rcx, rax
0x1800caf5c  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1800caf61  test    esi, esi
0x1800caf63  jg      loc_1800CB292
0x1800caf69  mov     eax, esi
0x1800caf6b  jmp     loc_1800CB29A
0x1800caf70  mov     r8d, 8; dwFlags
0x1800caf76  call    cs:__imp_MoveFileExW
0x1800caf7d  nop     dword ptr [rax+rax+00h]
0x1800caf82  test    eax, eax
  ... truncated ...
```
