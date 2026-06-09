# CCopyTree::InitializeFromPaths(HWND__ *,uint,ulong,ushort const *,ushort const *,CDPA<CPendingOperation,CTContainer_PolicyUnOwned<CPendingOperation>> *,bool)

- ea: `0x1800b5b34`
- end: `0x1800b663c`
- name: `?InitializeFromPaths@CCopyTree@@QEAAJPEAUHWND__@@IKPEBG1PEAV?$CDPA@VCPendingOperation@@V?$CTContainer_PolicyUnOwned@VCPendingOperation@@@@@@_N@Z`
- size: `2824`
- prototype: `__int64 __usercall@<rax>(CCopyTree *this@<rcx>, LPCWSTR lpsz, LPCWSTR, __int64, char)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1802b0a94`

## callees

- `0x18001b390`
- `0x18001e41c`
- `0x1800432f0`
- `0x180048fb0`
- `0x1800a3080`
- `0x1800ae570`
- `0x1800b3bfc`
- `0x1800b4cdc`
- `0x1800b5124`
- `0x1800b5b34`
- `0x1800b6650`
- `0x1800b67d0`
- `0x1800b68fc`
- `0x1800e68c0`
- `0x1800ee064`
- `0x18011c67c`
- `0x18011c6e8`
- `0x18014be50`
- `0x18014d4e0`
- `0x1801d90dc`
- `0x1802a9bb0`
- `0x1802a9c10`
- `0x18030fe20`
- `0x1803a4cb0`
- `0x1803a518c`
- `0x1803a57e0`
- `0x180521cb4`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800b62ad`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800b62ad`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800b5c4d`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800b5f2e`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800b5ffb`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800b5c4d`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800b5f2e`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800b5ffb`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800b6141`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800b6141`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1800b607e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1800b607e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1800b5dce`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1800b5dce`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800b5e7e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800b60ed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800b6129`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800b5e7e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800b60ed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800b6129`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5c28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5c88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5cea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5d3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5dfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5f70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5fd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b6030`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b6066`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b6267`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b6280`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b64c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b64dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b64f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b6522`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b654c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b65ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b65c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b65f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5c28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5c88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5cea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5d3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5dfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5f70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5fd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b6030`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b6066`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b6267`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b6280`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b64c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b64dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b64f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b6522`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b654c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b65ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b65c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b65f2`
- `SHCORE!__imp__CreateDirectoryHelper` at `0x1800b61ff`
- `SHCORE!__imp__CreateDirectoryHelper` at `0x1800b61ff`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x1800b5dde`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x1800b5dde`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x1800b636b`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x1800b636b`

## string_xrefs

- `0x1800b5bb5`: `onecoreuap\shell\windows.storage\copy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CCopyTree::InitializeFromPaths(
        CFileOperation **this,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned __int16 *lpsz,
        LPCWSTR a6,
        __int64 a7,
        char a8)
{
  unsigned int v8; // r14d
  CFileOperation **v10; // r15
  unsigned __int16 *v11; // rsi
  LPCWSTR v12; // r12
  int v13; // eax
  unsigned int v14; // ebx
  int v16; // edi
  unsigned __int16 *v17; // rbx
  __int64 v18; // rdx
  int ProgressCancelled; // r14d
  __int64 v20; // rdi
  WCHAR *v21; // rbx
  LPWSTR FileNameW; // rax
  __int64 v23; // rdx
  WCHAR *v24; // r8
  WCHAR v25; // cx
  WCHAR *v26; // rcx
  int v27; // r13d
  unsigned int v28; // edi
  int IsWild; // eax
  CFileOperation *v30; // rcx
  WCHAR *v31; // rdi
  __int64 v32; // rdx
  HRESULT v33; // esi
  unsigned __int16 *v34; // r15
  unsigned int v35; // r14d
  PWSTR v36; // rsi
  size_t v37; // rdx
  bool v38; // zf
  PWSTR v39; // rdx
  const unsigned __int16 *v40; // rax
  __int64 v41; // r14
  LPWSTR v42; // rax
  CFileOperation *v43; // rcx
  int DirectoryHelper; // eax
  HRESULT v45; // r14d
  int v46; // esi
  WCHAR *i; // rax
  unsigned int v48; // r13d
  CPendingOperation *v49; // rax
  CPendingOperation *v50; // rsi
  CPendingOperation *v51; // rsi
  void *v52; // rcx
  struct IShellItem *v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rax
  PWSTR v56; // rcx
  void *v57; // rcx
  void *v58; // rcx
  struct IShellItem *v59; // rcx
  int v60; // [rsp+20h] [rbp-E0h]
  struct CONFIRM_CONSTANTS *v61; // [rsp+30h] [rbp-D0h]
  int v62; // [rsp+40h] [rbp-C0h]
  PWSTR pszPath; // [rsp+68h] [rbp-98h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  BOOL v66; // [rsp+78h] [rbp-88h]
  unsigned int v67; // [rsp+7Ch] [rbp-84h]
  CCopyTree *v68; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v69; // [rsp+88h] [rbp-78h]
  int v70; // [rsp+90h] [rbp-70h]
  LPVOID v71; // [rsp+98h] [rbp-68h] BYREF
  LPVOID v72; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v73; // [rsp+A8h] [rbp-58h] BYREF
  PWSTR v74; // [rsp+B0h] [rbp-50h] BYREF
  struct IShellItem *v75; // [rsp+B8h] [rbp-48h] BYREF
  void *ppv; // [rsp+C0h] [rbp-40h] BYREF
  struct IShellItem *v77; // [rsp+C8h] [rbp-38h] BYREF
  LPCITEMIDLIST v78; // [rsp+D0h] [rbp-30h]
  LPCITEMIDLIST pidl; // [rsp+D8h] [rbp-28h]
  WCHAR sz[256]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v81[256]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  v8 = a4;
  v67 = a4;
  v10 = this;
  v68 = (CCopyTree *)this;
  v11 = lpsz;
  v69 = lpsz;
  v12 = a6;
  v60 = a4;
  LOBYTE(a4) = a8;
  v13 = CCopyTree::PromptDangerousOperation(this, a2, a7, a4);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2996,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\copy.cpp",
      (const char *)(unsigned int)v13,
      v60);
    return v14;
  }
  v66 = 0;
  v16 = CountFiles(lpsz);
  if ( a3 == 3 )
  {
    v8 &= ~1u;
    v67 = v8;
    goto LABEL_34;
  }
  pszPath = 0;
  if ( !a6 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pv,
      lpsz,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pszPath,
      &pv);
    if ( pv )
      CoTaskMemFree(pv);
    v17 = pszPath;
    if ( pszPath )
    {
      v18 = -1;
      do
        ++v18;
      while ( pszPath[v18] );
      PathCchRemoveFileSpec(pszPath, v18 + 1);
      goto LABEL_20;
    }
LABEL_16:
    CFileOperation::PromptUserOrQueue(
      v10[2],
      0,
      0,
      a3,
      0,
      0,
      (const struct CONFIRM_CONSTANTS *)&off_1806698B0,
      -2144927716,
      0,
      0,
      0);
  }
  if ( *a6 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pv,
      a6,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pszPath,
      &pv);
    if ( pv )
      CoTaskMemFree(pv);
    v17 = pszPath;
    if ( !pszPath )
      goto LABEL_16;
  }
  else
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pv,
      L".",
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pszPath,
      &pv);
    if ( pv )
      CoTaskMemFree(pv);
    v17 = pszPath;
    if ( !pszPath )
      goto LABEL_16;
  }
LABEL_20:
  if ( (unsigned int)PathIsInvalidW(v17) )
    goto LABEL_16;
  if ( a3 == 4 )
  {
    if ( v16 != 1 && !(unsigned int)PathIsWild(v17) )
      CFileOperation::PromptUserOrQueue(
        v10[2],
        0,
        0,
        4u,
        0,
        0,
        (const struct CONFIRM_CONSTANTS *)&off_180669920,
        -2144927739,
        0,
        0,
        0);
  }
  else if ( (v8 & 1) == 0 || !a6 || (unsigned int)CountFiles(a6) != v16 )
  {
    if ( v16 == 1 && !PathIsRootW(v17) )
      v66 = !PathIsDirectoryW(v17);
    goto LABEL_32;
  }
  v66 = 1;
LABEL_32:
  if ( v17 )
    CoTaskMemFree(v17);
LABEL_34:
  *((_DWORD *)v10[2] + 50) = v16;
  v70 = v8 & 0x2000;
  ppv = 0;
  v75 = 0;
  ProgressCancelled = 0;
  while ( 1 )
  {
    if ( !*v11 )
      goto LABEL_160;
    ProgressCancelled = CFileOperation::QueryProgressCancelled(v10[2]);
    if ( ProgressCancelled < 0 )
      goto LABEL_160;
    if ( (unsigned int)PathIsInvalidW(v11) )
      break;
    pv = 0;
    if ( (int)wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
                v11,
                &pv) < 0 )
    {
      ProgressCancelled = -2144927717;
      v57 = pv;
      if ( !pv )
        goto LABEL_160;
      goto LABEL_158;
    }
    v20 = 2147483646;
    v21 = (WCHAR *)pv;
    FileNameW = PathFindFileNameW((LPCWSTR)pv);
    v23 = 255;
    v24 = sz;
    do
    {
      if ( !v20 )
        break;
      v25 = *FileNameW;
      if ( !*FileNameW )
        break;
      ++FileNameW;
      *v24++ = v25;
      --v20;
      --v23;
    }
    while ( v23 );
    v26 = v24 - 1;
    if ( v23 )
      v26 = v24;
    *v26 = 0;
    if ( !v23 )
    {
      ProgressCancelled = -2144927717;
      goto LABEL_155;
    }
    v27 = 3;
    v28 = v67;
    if ( (v67 & 0x80u) != 0 )
    {
      IsWild = PathIsWild(sz);
      v30 = v10[2];
      if ( IsWild )
      {
        CFileOperation::SetOperationFlagsWithoutValidation(v30, v28);
        v27 = 1;
      }
      else
      {
        CFileOperation::SetOperationFlagsWithoutValidation(v30, v28 & 0xFFFFFF7F);
      }
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pszPath,
      v21,
      -1);
    v31 = pszPath;
    if ( !pszPath )
    {
      ProgressCancelled = -2147024882;
      goto LABEL_155;
    }
    v32 = -1;
    do
      ++v32;
    while ( pszPath[v32] );
    PathCchRemoveFileSpec(pszPath, v32 + 1);
    pidl = 0;
    if ( (int)ILCreateFromPathEx(v31, 0) < 0 )
    {
      ProgressCancelled = -2144927717;
      goto LABEL_151;
    }
    v33 = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    CoTaskMemFree((LPVOID)pidl);
    if ( v33 < 0 )
    {
      ProgressCancelled = -2147024888;
LABEL_149:
      CoTaskMemFree(v31);
      goto LABEL_155;
    }
    if ( CCopyTree::DiskCheck((CCopyTree *)v10, v31) < 0 )
    {
      ProgressCancelled = -2147023673;
      goto LABEL_151;
    }
    v34 = 0;
    v35 = a3;
    if ( a3 != 3 )
    {
      v74 = 0;
      if ( v12 )
      {
        if ( *v12 )
        {
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v73,
            v12,
            -1);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v74,
            &v73);
          if ( v73 )
            CoTaskMemFree(v73);
          v36 = v74;
          v38 = v74 == 0;
        }
        else
        {
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v72,
            L".",
            -1);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v74,
            &v72);
          if ( v72 )
            CoTaskMemFree(v72);
          v36 = v74;
          v38 = v74 == 0;
        }
        if ( v38 )
        {
LABEL_143:
          ProgressCancelled = -2144927716;
          if ( v36 )
            CoTaskMemFree(v36);
          goto LABEL_149;
        }
      }
      else
      {
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v71,
          v69,
          -1);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &v74,
          &v71);
        if ( v71 )
          CoTaskMemFree(v71);
        v36 = v74;
        if ( !v74 )
          goto LABEL_143;
        v37 = -1;
        do
          ++v37;
        while ( v74[v37 + 1] );
        PathCchRemoveFileSpec(v74, v37);
      }
      if ( PathIsRelativeW(v36) || (unsigned int)PathContainsDotOrDotDot(v36) )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pszPath,
          0);
        if ( (int)wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
                    v36,
                    &pszPath) < 0 )
        {
          ProgressCancelled = -2144927716;
          if ( v36 )
            CoTaskMemFree(v36);
          v56 = pszPath;
          if ( !pszPath )
            goto LABEL_155;
          goto LABEL_152;
        }
        v31 = pszPath;
      }
      else
      {
        v39 = v36;
        v36 = 0;
        v74 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pszPath,
          v39);
        v31 = pszPath;
        if ( !pszPath )
        {
          ProgressCancelled = -2144927716;
          goto LABEL_155;
        }
      }
      if ( v66 )
      {
        v40 = PathFindFileNameW(v31);
        if ( (int)StringCchCopyW(v81, 0xFFu, v40) < 0 )
          goto LABEL_133;
        v34 = v81;
        v41 = -1;
        do
          ++v41;
        while ( v31[v41] );
        v42 = PathFindFileNameW(v31);
        if ( v42 > v31 )
        {
          *(v42 - 1) = 0;
          PathCchAddBackslash(v31, v41 + 1);
        }
        v35 = a3;
      }
      v78 = 0;
      if ( (int)ILCreateFromPathEx(v31, 0) < 0 )
      {
        v43 = (CFileOperation *)*((_QWORD *)v68 + 2);
        if ( (*((_DWORD *)v43 + 21) & 0x200) == 0 && (*((_DWORD *)v43 + 21) & 0x400) == 0 )
          CFileOperation::PromptUserOrQueue(
            v43,
            0,
            0,
            v35,
            1,
            v31,
            (const struct CONFIRM_CONSTANTS *)&off_1806D0438,
            0,
            0,
            0,
            0);
        DirectoryHelper = _CreateDirectoryHelper(
                            *(_QWORD *)(*((_QWORD *)v68 + 2) + 208LL),
                            v31,
                            0,
                            (*(_DWORD *)(*((_QWORD *)v68 + 2) + 84LL) & 0x400) == 0);
        ProgressCancelled = 0;
        if ( DirectoryHelper > 0 )
        {
          ProgressCancelled = (unsigned __int16)DirectoryHelper | 0x80070000;
        }
        else if ( DirectoryHelper )
        {
          ProgressCancelled = DirectoryHelper;
        }
        if ( ProgressCancelled < 0 )
          goto LABEL_134;
        if ( (int)ILCreateFromPathEx(v31, 0) < 0 )
        {
LABEL_133:
          ProgressCancelled = -2144927716;
          goto LABEL_134;
        }
      }
      v45 = SHCreateItemFromIDList(v78, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)&v75);
      CoTaskMemFree((LPVOID)v78);
      if ( v45 < 0 )
      {
        ProgressCancelled = -2147024888;
LABEL_134:
        if ( v36 )
          CoTaskMemFree(v36);
LABEL_136:
        if ( !v31 )
        {
LABEL_155:
          if ( !v21 )
            goto LABEL_160;
          v57 = v21;
LABEL_158:
          CoTaskMemFree(v57);
          goto LABEL_160;
        }
LABEL_151:
        v56 = v31;
LABEL_152:
        CoTaskMemFree(v56);
        goto LABEL_155;
      }
      if ( v36 )
        CoTaskMemFree(v36);
    }
    v46 = v70 != 0 ? 1 : 9;
    for ( i = sz; *i; i = CharNextW(i) )
    {
      if ( *i == 63 || *i == 42 )
      {
        v77 = 0;
        v62 = v27;
        v61 = (struct CONFIRM_CONSTANTS *)v34;
        v48 = a3;
        v10 = (CFileOperation **)v68;
        ProgressCancelled = CCopyTree::EnumerateRootMatches(v68, a3, ppv, v75, sz, 0, v61, v46, v62, &v77);
        if ( v77 )
          CRecursiveFolderOperation::Release((CRecursiveFolderOperation *)v77);
        goto LABEL_116;
      }
    }
    ProgressCancelled = -2147024882;
    v49 = (CPendingOperation *)operator new(0x428u, (const struct std::nothrow_t *)&std::nothrow);
    v50 = v49;
    if ( v49 )
    {
      memset_0(v49, 0, 0x428u);
      v51 = CPendingOperation::CPendingOperation(v50);
      if ( v51 )
      {
        v74 = 0;
        ProgressCancelled = CreateBindCtx(0, (LPBC *)&v74);
        if ( ProgressCancelled >= 0 )
        {
          ProgressCancelled = SHAddSkipBindCtx((struct IBindCtx *)v74, 0);
          if ( ProgressCancelled >= 0 )
          {
            v77 = 0;
            ProgressCancelled = SHCreateItemFromParsingName(
                                  v21,
                                  (IBindCtx *)v74,
                                  &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                  (void **)&v77);
            if ( ProgressCancelled >= 0 )
            {
              ProgressCancelled = CPendingOperation::InitPendingOperation(v51, a3, v77, v75, v34, 0);
              if ( ProgressCancelled >= 0 )
                ProgressCancelled = (*(__int64 (__fastcall **)(CPendingOperation *, _QWORD, _QWORD))(*(_QWORD *)v51 + 8LL))(
                                      v51,
                                      *((_QWORD *)v68 + 2),
                                      0);
              ((void (__fastcall *)(struct IShellItem *))v77->lpVtbl->Release)(v77);
            }
            (*(void (__fastcall **)(PWSTR))(*(_QWORD *)v74 + 16LL))(v74);
          }
        }
        (**(void (__fastcall ***)(CPendingOperation *, __int64))v51)(v51, 1);
      }
    }
    v10 = (CFileOperation **)v68;
    v48 = a3;
LABEL_116:
    v52 = ppv;
    ppv = 0;
    if ( v52 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v52 + 16LL))(v52);
    v53 = v75;
    v75 = 0;
    if ( v53 )
      ((void (__fastcall *)(struct IShellItem *))v53->lpVtbl->Release)(v53);
    if ( ProgressCancelled < 0 )
      goto LABEL_136;
    if ( ProgressCancelled == 1 )
      CFileOperation::PromptUserOrQueue(
        v10[2],
        0,
        0,
        v48,
        0,
        v69,
        (const struct CONFIRM_CONSTANTS *)&off_1806698E8,
        -2147024894,
        0,
        0,
        0);
    v54 = -1;
    do
      ++v54;
    while ( v69[v54] );
    v11 = &v69[v54 + 1];
    v69 = v11;
    if ( (v67 & 1) != 0 && v12 )
    {
      v55 = -1;
      do
        ++v55;
      while ( v12[v55] );
      v12 += v55 + 1;
    }
    if ( v31 )
      CoTaskMemFree(v31);
    if ( v21 )
      CoTaskMemFree(v21);
  }
  ProgressCancelled = -2144927717;
LABEL_160:
  v58 = ppv;
  ppv = 0;
  if ( v58 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v58 + 16LL))(v58);
  v59 = v75;
  v75 = 0;
  if ( v59 )
    ((void (__fastcall *)(struct IShellItem *))v59->lpVtbl->Release)(v59);
  return (unsigned int)ProgressCancelled;
}

```

## disassembly

```asm
0x1800b5b34  mov     [rsp-8+arg_10], rbx
0x1800b5b39  push    rbp
0x1800b5b3a  push    rsi
0x1800b5b3b  push    rdi
0x1800b5b3c  push    r12
0x1800b5b3e  push    r13
0x1800b5b40  push    r14
0x1800b5b42  push    r15
0x1800b5b44  lea     rbp, [rsp-3F0h]
0x1800b5b4c  sub     rsp, 4F0h
0x1800b5b53  mov     rax, cs:__security_cookie
0x1800b5b5a  xor     rax, rsp
0x1800b5b5d  mov     [rbp+420h+var_40], rax
0x1800b5b64  mov     r14d, r9d
0x1800b5b67  mov     [rsp+520h+var_4A4], r9d
0x1800b5b6c  mov     r13d, r8d
0x1800b5b6f  mov     [rsp+520h+var_4C0], r8d
0x1800b5b74  mov     r15, rcx
0x1800b5b77  mov     [rbp+420h+var_4A0], rcx
0x1800b5b7b  mov     rsi, [rbp+420h+lpsz]
0x1800b5b82  mov     [rbp+420h+var_498], rsi
0x1800b5b86  mov     r12, [rbp+420h+arg_28]
0x1800b5b8d  mov     r8, [rbp+420h+arg_30]
0x1800b5b94  mov     dword ptr [rsp+520h+var_500], r9d; int
0x1800b5b99  mov     r9b, [rbp+420h+arg_38]
0x1800b5ba0  call    ?PromptDangerousOperation@CCopyTree@@AEAAJPEAUHWND__@@PEBV?$CDPA@VCPendingOperation@@V?$CTContainer_PolicyUnOwned@VCPendingOperation@@@@@@_NK@Z; CCopyTree::PromptDangerousOperation(HWND__ *,CDPA<CPendingOperation,CTContainer_PolicyUnOwned<CPendingOperation>> const *,bool,ulong)
0x1800b5ba5  mov     ebx, eax
0x1800b5ba7  test    eax, eax
0x1800b5ba9  jns     short loc_1800B5BCD
0x1800b5bab  mov     rcx, [rbp+428h]; this
0x1800b5bb2  mov     r9d, eax; char *
0x1800b5bb5  lea     r8, aOnecoreuapShel_87; "onecoreuap\\shell\\windows.storage\\cop"...
0x1800b5bbc  mov     edx, 2996h; void *
0x1800b5bc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5bc6  mov     eax, ebx
0x1800b5bc8  jmp     loc_1800B5CF2
0x1800b5bcd  xor     ebx, ebx
0x1800b5bcf  mov     [rsp+520h+var_4A8], ebx
0x1800b5bd3  mov     rcx, rsi; lpsz
0x1800b5bd6  call    CountFiles
0x1800b5bdb  mov     edi, eax
0x1800b5bdd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800b5be1  cmp     r13d, 3
0x1800b5be5  jnz     short loc_1800B5BF5
0x1800b5be7  and     r14d, 0FFFFFFFEh
0x1800b5beb  mov     [rsp+520h+var_4A4], r14d
0x1800b5bf0  jmp     loc_1800B5E04
0x1800b5bf5  mov     [rsp+520h+pszPath], rbx
0x1800b5bfa  mov     r8, rdx
0x1800b5bfd  lea     rcx, [rsp+520h+pv]
0x1800b5c02  test    r12, r12
0x1800b5c05  jnz     short loc_1800B5C58
0x1800b5c07  mov     rdx, rsi
0x1800b5c0a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800b5c0f  lea     rdx, [rsp+520h+pv]
0x1800b5c14  lea     rcx, [rsp+520h+pszPath]
0x1800b5c19  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800b5c1e  mov     rcx, [rsp+520h+pv]; pv
0x1800b5c23  test    rcx, rcx
0x1800b5c26  jz      short loc_1800B5C2E
0x1800b5c28  call    cs:__imp_CoTaskMemFree
0x1800b5c2e  mov     rbx, [rsp+520h+pszPath]
0x1800b5c33  xor     ecx, ecx
0x1800b5c35  test    rbx, rbx
0x1800b5c38  jz      short loc_1800B5CA3
0x1800b5c3a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800b5c3e  inc     rdx
0x1800b5c41  cmp     [rbx+rdx*2], cx
0x1800b5c45  jnz     short loc_1800B5C3E
0x1800b5c47  inc     rdx; cchPath
0x1800b5c4a  mov     rcx, rbx; pszPath
0x1800b5c4d  call    cs:__imp_PathCchRemoveFileSpec
0x1800b5c53  jmp     loc_1800B5D53
0x1800b5c58  cmp     [r12], bx
0x1800b5c5d  jnz     loc_1800B5D1C
0x1800b5c63  lea     rdx, S2; "."
0x1800b5c6a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800b5c6f  lea     rdx, [rsp+520h+pv]
0x1800b5c74  lea     rcx, [rsp+520h+pszPath]
0x1800b5c79  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800b5c7e  mov     rcx, [rsp+520h+pv]; pv
0x1800b5c83  test    rcx, rcx
0x1800b5c86  jz      short loc_1800B5C8E
0x1800b5c88  call    cs:__imp_CoTaskMemFree
0x1800b5c8e  mov     rbx, [rsp+520h+pszPath]
0x1800b5c93  xor     ecx, ecx
0x1800b5c95  test    rbx, rbx
0x1800b5c98  setnz   al
0x1800b5c9b  test    al, al
0x1800b5c9d  jnz     loc_1800B5D53
0x1800b5ca3  mov     [rsp+520h+var_4D0], rcx; struct IAutoRetry *
0x1800b5ca8  mov     [rsp+520h+var_4D8], rcx; struct CCopyWorkItem *
0x1800b5cad  mov     [rsp+520h+var_4E0], rcx; struct CRecursiveFolderOperation *
0x1800b5cb2  mov     [rsp+520h+var_4E8], 8027001Ch; int
0x1800b5cba  lea     rax, off_1806698B0
0x1800b5cc1  mov     r9d, r13d; unsigned int
0x1800b5cc4  mov     [rsp+520h+var_4F0], rax; struct CONFIRM_CONSTANTS *
0x1800b5cc9  mov     [rsp+520h+var_4F8], rcx; unsigned __int16 *
0x1800b5cce  mov     dword ptr [rsp+520h+var_500], ecx; int
0x1800b5cd2  xor     r8d, r8d; struct IShellItem *
0x1800b5cd5  xor     edx, edx; struct IShellItem *
0x1800b5cd7  mov     rcx, [r15+10h]; this
0x1800b5cdb  call    ?PromptUserOrQueue@CFileOperation@@QEAAJPEAUIShellItem@@0IHPEBGPEBUCONFIRM_CONSTANTS@@JPEAVCRecursiveFolderOperation@@PEAVCCopyWorkItem@@PEAUIAutoRetry@@@Z; CFileOperation::PromptUserOrQueue(IShellItem *,IShellItem *,uint,int,ushort const *,CONFIRM_CONSTANTS const *,long,CRecursiveFolderOperation *,CCopyWorkItem *,IAutoRetry *)
0x1800b5ce0  mov     edi, eax
0x1800b5ce2  test    rbx, rbx
0x1800b5ce5  jz      short loc_1800B5CF0
0x1800b5ce7  mov     rcx, rbx; pv
0x1800b5cea  call    cs:__imp_CoTaskMemFree
0x1800b5cf0  mov     eax, edi
0x1800b5cf2  mov     rcx, [rbp+420h+var_40]
0x1800b5cf9  xor     rcx, rsp; StackCookie
0x1800b5cfc  call    __security_check_cookie
0x1800b5d01  mov     rbx, [rsp+520h+arg_10]
0x1800b5d09  add     rsp, 4F0h
0x1800b5d10  pop     r15
0x1800b5d12  pop     r14
0x1800b5d14  pop     r13
0x1800b5d16  pop     r12
0x1800b5d18  pop     rdi
0x1800b5d19  pop     rsi
0x1800b5d1a  pop     rbp
0x1800b5d1b  retn
0x1800b5d1c  mov     rdx, r12
0x1800b5d1f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800b5d24  lea     rdx, [rsp+520h+pv]
0x1800b5d29  lea     rcx, [rsp+520h+pszPath]
0x1800b5d2e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800b5d33  mov     rcx, [rsp+520h+pv]; pv
0x1800b5d38  test    rcx, rcx
0x1800b5d3b  jz      short loc_1800B5D43
0x1800b5d3d  call    cs:__imp_CoTaskMemFree
0x1800b5d43  mov     rbx, [rsp+520h+pszPath]
0x1800b5d48  xor     ecx, ecx
0x1800b5d4a  test    rbx, rbx
0x1800b5d4d  jz      loc_1800B5CA3
0x1800b5d53  mov     rcx, rbx; unsigned __int16 *
0x1800b5d56  call    PathIsInvalidW
0x1800b5d5b  xor     ecx, ecx
0x1800b5d5d  test    eax, eax
0x1800b5d5f  jnz     loc_1800B5CA3
0x1800b5d65  cmp     r13d, 4
0x1800b5d69  lea     r13d, [rcx+1]
0x1800b5d6d  jnz     short loc_1800B5DA9
0x1800b5d6f  cmp     edi, r13d
0x1800b5d72  jz      short loc_1800B5DBF
0x1800b5d74  mov     rcx, rbx; lpsz
0x1800b5d77  call    PathIsWild
0x1800b5d7c  xor     ecx, ecx
0x1800b5d7e  test    eax, eax
0x1800b5d80  jnz     short loc_1800B5DBF
0x1800b5d82  mov     [rsp+520h+var_4D0], rcx
0x1800b5d87  mov     [rsp+520h+var_4D8], rcx
0x1800b5d8c  mov     [rsp+520h+var_4E0], rcx
0x1800b5d91  mov     [rsp+520h+var_4E8], 80270005h
0x1800b5d99  lea     rax, off_180669920
0x1800b5da0  lea     r9d, [r13+3]
0x1800b5da4  jmp     loc_1800B5CC4
0x1800b5da9  test    r13b, r14b
0x1800b5dac  jz      short loc_1800B5DC6
0x1800b5dae  test    r12, r12
0x1800b5db1  jz      short loc_1800B5DC6
0x1800b5db3  mov     rcx, r12; lpsz
0x1800b5db6  call    CountFiles
0x1800b5dbb  cmp     eax, edi
0x1800b5dbd  jnz     short loc_1800B5DC6
0x1800b5dbf  mov     [rsp+520h+var_4A8], r13d
0x1800b5dc4  jmp     short loc_1800B5DF4
0x1800b5dc6  cmp     edi, r13d
0x1800b5dc9  jnz     short loc_1800B5DF4
0x1800b5dcb  mov     rcx, rbx; pszPath
0x1800b5dce  call    cs:__imp_PathIsRootW
0x1800b5dd4  xor     r13d, r13d
0x1800b5dd7  test    eax, eax
0x1800b5dd9  jnz     short loc_1800B5DF4
0x1800b5ddb  mov     rcx, rbx; pszPath
0x1800b5dde  call    cs:__imp_PathIsDirectoryW
0x1800b5de4  mov     ecx, r13d
0x1800b5de7  test    eax, eax
0x1800b5de9  lea     edx, [r13+1]
0x1800b5ded  cmovz   ecx, edx
0x1800b5df0  mov     [rsp+520h+var_4A8], ecx
0x1800b5df4  test    rbx, rbx
0x1800b5df7  jz      short loc_1800B5E02
0x1800b5df9  mov     rcx, rbx; pv
0x1800b5dfc  call    cs:__imp_CoTaskMemFree
0x1800b5e02  xor     ebx, ebx
0x1800b5e04  mov     rax, [r15+10h]
0x1800b5e08  mov     [rax+0C8h], edi
0x1800b5e0e  and     r14d, 2000h
0x1800b5e15  mov     [rbp+420h+var_490], r14d
0x1800b5e19  mov     [rbp+420h+ppv], rbx
0x1800b5e1d  mov     [rbp+420h+var_468], rbx
0x1800b5e21  mov     r14d, ebx
0x1800b5e24  jmp     short loc_1800B5E28
0x1800b5e26  xor     ebx, ebx
0x1800b5e28  cmp     [rsi], bx
0x1800b5e2b  jz      loc_1800B6600
0x1800b5e31  mov     rcx, [r15+10h]; this
0x1800b5e35  call    ?QueryProgressCancelled@CFileOperation@@QEAAJXZ; CFileOperation::QueryProgressCancelled(void)
0x1800b5e3a  mov     r14d, eax
0x1800b5e3d  test    eax, eax
0x1800b5e3f  js      loc_1800B6600
0x1800b5e45  mov     rcx, rsi; unsigned __int16 *
0x1800b5e48  call    PathIsInvalidW
0x1800b5e4d  test    eax, eax
0x1800b5e4f  jnz     loc_1800B65FA
0x1800b5e55  mov     [rsp+520h+pv], rbx
0x1800b5e5a  lea     rdx, [rsp+520h+pv]
0x1800b5e5f  mov     rcx, rsi
0x1800b5e62  call    ??$GetFullPathNameW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAPEBG@Z; wil::GetFullPathNameW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)
0x1800b5e67  xor     esi, esi
0x1800b5e69  test    eax, eax
0x1800b5e6b  js      loc_1800B65E2
0x1800b5e71  mov     edi, 7FFFFFFEh
0x1800b5e76  mov     rbx, [rsp+520h+pv]
0x1800b5e7b  mov     rcx, rbx; pszPath
0x1800b5e7e  call    cs:__imp_PathFindFileNameW
0x1800b5e84  mov     edx, 0FFh
0x1800b5e89  lea     r8, [rbp+420h+sz]
0x1800b5e8d  lea     r14d, [rsi+1]
0x1800b5e91  test    rdi, rdi
0x1800b5e94  jz      short loc_1800B5EB2
0x1800b5e96  movzx   ecx, word ptr [rax]
0x1800b5e99  test    cx, cx
0x1800b5e9c  jz      short loc_1800B5EB2
0x1800b5e9e  add     rax, 2
0x1800b5ea2  mov     [r8], cx
0x1800b5ea6  add     r8, 2
0x1800b5eaa  sub     rdi, r14
0x1800b5ead  sub     rdx, r14
0x1800b5eb0  jnz     short loc_1800B5E91
0x1800b5eb2  lea     rcx, [r8-2]
0x1800b5eb6  test    rdx, rdx
0x1800b5eb9  cmovnz  rcx, r8
0x1800b5ebd  mov     [rcx], si
0x1800b5ec0  jz      loc_1800B65D2
0x1800b5ec6  mov     r13d, 3
0x1800b5ecc  mov     edi, [rsp+520h+var_4A4]
0x1800b5ed0  test    dil, dil
0x1800b5ed3  jns     short loc_1800B5EFB
0x1800b5ed5  lea     rcx, [rbp+420h+sz]; lpsz
0x1800b5ed9  call    PathIsWild
0x1800b5ede  mov     rcx, [r15+10h]; this
0x1800b5ee2  mov     edx, edi; unsigned int
0x1800b5ee4  test    eax, eax
0x1800b5ee6  jz      short loc_1800B5EF2
0x1800b5ee8  call    ?SetOperationFlagsWithoutValidation@CFileOperation@@QEAAJK@Z; CFileOperation::SetOperationFlagsWithoutValidation(ulong)
0x1800b5eed  mov     r13d, r14d
0x1800b5ef0  jmp     short loc_1800B5EFB
0x1800b5ef2  btr     edx, 7; unsigned int
0x1800b5ef6  call    ?SetOperationFlagsWithoutValidation@CFileOperation@@QEAAJK@Z; CFileOperation::SetOperationFlagsWithoutValidation(ulong)
0x1800b5efb  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b5eff  mov     rdx, rbx
0x1800b5f02  lea     rcx, [rsp+520h+pszPath]
0x1800b5f07  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800b5f0c  nop
0x1800b5f0d  mov     rdi, [rsp+520h+pszPath]
0x1800b5f12  test    rdi, rdi
0x1800b5f15  jz      loc_1800B65CA
0x1800b5f1b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800b5f1f  inc     rdx
0x1800b5f22  cmp     [rdi+rdx*2], si
0x1800b5f26  jnz     short loc_1800B5F1F
0x1800b5f28  inc     rdx; cchPath
0x1800b5f2b  mov     rcx, rdi; pszPath
0x1800b5f2e  call    cs:__imp_PathCchRemoveFileSpec
0x1800b5f34  mov     [rbp+420h+pidl], rsi
0x1800b5f38  mov     [rsp+520h+var_500], rsi; SFGAOF *
0x1800b5f3d  lea     r9, [rbp+420h+pidl]
0x1800b5f41  mov     r8d, r14d
0x1800b5f44  xor     edx, edx
0x1800b5f46  mov     rcx, rdi; pszName
0x1800b5f49  call    ILCreateFromPathEx
0x1800b5f4e  test    eax, eax
0x1800b5f50  js      loc_1800B65B9
0x1800b5f56  lea     r8, [rbp+420h+ppv]; ppv
0x1800b5f5a  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800b5f61  mov     rcx, [rbp+420h+pidl]; pidl
0x1800b5f65  call    SHCreateItemFromIDList
0x1800b5f6a  mov     esi, eax
0x1800b5f6c  mov     rcx, [rbp+420h+pidl]; pv
0x1800b5f70  call    cs:__imp_CoTaskMemFree
0x1800b5f76  test    esi, esi
0x1800b5f78  js      loc_1800B65A5
0x1800b5f7e  mov     rdx, rdi; unsigned __int16 *
0x1800b5f81  mov     rcx, r15; this
0x1800b5f84  call    ?DiskCheck@CCopyTree@@QEAAJPEBG@Z; CCopyTree::DiskCheck(ushort const *)
0x1800b5f89  xor     esi, esi
0x1800b5f8b  test    eax, eax
0x1800b5f8d  js      loc_1800B659D
0x1800b5f93  mov     r15d, esi
0x1800b5f96  mov     r14d, [rsp+520h+var_4C0]
0x1800b5f9b  cmp     r14d, 3
0x1800b5f9f  jz      loc_1800B6286
0x1800b5fa5  mov     [rbp+420h+var_470], rsi
0x1800b5fa9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b5fad  test    r12, r12
0x1800b5fb0  jnz     short loc_1800B6003
0x1800b5fb2  mov     rdx, [rbp+420h+var_498]
0x1800b5fb6  lea     rcx, [rbp+420h+var_488]
  ... truncated ...
```
