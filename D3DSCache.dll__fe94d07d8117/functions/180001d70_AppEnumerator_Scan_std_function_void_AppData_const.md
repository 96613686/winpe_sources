# AppEnumerator::Scan(std::function<void (AppData &)> const &)

- ea: `0x180001d70`
- end: `0x180002839`
- name: `?Scan@AppEnumerator@@UEAAJAEBV?$function@$$A6AXAEAUAppData@@@Z@std@@@Z`
- size: `2761`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001ad4`
- `0x180001bd0`
- `0x180001ce0`
- `0x180001d70`
- `0x180002840`
- `0x180002acc`
- `0x180002b68`
- `0x180002bd0`
- `0x180002c40`
- `0x180002f40`
- `0x180003710`
- `0x180003794`
- `0x18001a700`
- `0x18001fa30`
- `0x180021a70`
- `0x180029170`
- `0x18002a1e0`
- `0x180033940`
- `0x18003b704`
- `0x18003ed98`
- `0x18003fec0`
- `0x1800449f0`
- `0x180045374`
- `0x18004591c`
- `0x180051190`
- `0x18005151c`
- `0x1800a6cd8`
- `0x1800a6cfc`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x1800021be`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x1800021c8`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x1800021be`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x1800021c8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180001eb2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180001eb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002127`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002127`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000248d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800026e9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000248d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800026e9`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180002504`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180002763`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180002504`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180002763`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000227e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800024ee`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000274a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000227e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800024ee`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000274a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180002241`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000242c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180002682`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180002241`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000242c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180002682`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180001ed3`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180001ed3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180001e9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180001e9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180002570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180002570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000205c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000205c`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800020f4`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800020f4`

## string_xrefs

- `0x180002107`: `%s\D3DSCache`
- `0x1800023c4`: `*.dxcache`
- `0x180002617`: `*.dxcache`

## pseudocode

```c
__int64 __fastcall AppEnumerator::Scan(__int64 a1, void *a2)
{
  AppData *v4; // rdx
  AppData *v5; // rcx
  __int64 v6; // rax
  int v7; // ebx
  WCHAR *v8; // rsi
  WCHAR *v9; // rax
  HRESULT v10; // eax
  int v11; // ebx
  int v12; // eax
  PWSTR v13; // rcx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  char nFileSizeLow; // dl
  int v18; // ebx
  __int64 v19; // rax
  __int64 v20; // rdx
  WCHAR *v21; // r12
  __int64 v22; // rax
  WCHAR *v23; // r8
  __int64 v24; // rcx
  unsigned __int16 *v25; // rsi
  unsigned __int16 *v26; // r13
  unsigned __int16 *v27; // r15
  WCHAR *j; // r14
  int v29; // ebx
  int v30; // edi
  __int64 v31; // rsi
  int v32; // r14d
  HANDLE v33; // r15
  __int64 result; // rax
  unsigned int v35; // r8d
  const wchar_t **k; // rdi
  HANDLE v37; // rax
  void *v38; // rbx
  unsigned int v39; // r8d
  __int64 v40; // r8
  PCWSTR StringRawBuffer; // rdx
  unsigned int v42; // r8d
  const wchar_t **i; // rdi
  HANDLE FirstFileW; // rax
  void *v45; // rbx
  unsigned int v46; // r8d
  __int64 v47; // r8
  unsigned int v48; // ecx
  int v49; // [rsp+30h] [rbp-F28h]
  PWSTR ppszPath; // [rsp+38h] [rbp-F20h] BYREF
  HANDLE v51; // [rsp+40h] [rbp-F18h]
  char v52; // [rsp+48h] [rbp-F10h]
  __int64 v53; // [rsp+50h] [rbp-F08h]
  const wchar_t *v54; // [rsp+60h] [rbp-EF8h] BYREF
  char v55; // [rsp+68h] [rbp-EF0h]
  const wchar_t *v56; // [rsp+70h] [rbp-EE8h]
  char v57; // [rsp+78h] [rbp-EE0h]
  const wchar_t *v58; // [rsp+80h] [rbp-ED8h]
  char v59; // [rsp+88h] [rbp-ED0h]
  const wchar_t *v60; // [rsp+90h] [rbp-EC8h]
  char v61; // [rsp+98h] [rbp-EC0h]
  const wchar_t *v62; // [rsp+A0h] [rbp-EB8h] BYREF
  char v63; // [rsp+A8h] [rbp-EB0h]
  const wchar_t *v64; // [rsp+B0h] [rbp-EA8h]
  char v65; // [rsp+B8h] [rbp-EA0h]
  const wchar_t *v66; // [rsp+C0h] [rbp-E98h]
  char v67; // [rsp+C8h] [rbp-E90h]
  const wchar_t *v68; // [rsp+D0h] [rbp-E88h]
  char v69; // [rsp+D8h] [rbp-E80h]
  _com_error *v70; // [rsp+E0h] [rbp-E78h] BYREF
  void **pExceptionObject; // [rsp+E8h] [rbp-E70h] BYREF
  int v72; // [rsp+F0h] [rbp-E68h]
  __int128 v73; // [rsp+F8h] [rbp-E60h]
  void **v74; // [rsp+108h] [rbp-E50h] BYREF
  int v75; // [rsp+110h] [rbp-E48h]
  __int128 v76; // [rsp+118h] [rbp-E40h]
  void **v77; // [rsp+128h] [rbp-E30h] BYREF
  int v78; // [rsp+130h] [rbp-E28h]
  __int128 v79; // [rsp+138h] [rbp-E20h]
  HSTRING_HEADER hstringHeader; // [rsp+148h] [rbp-E10h] BYREF
  HSTRING string; // [rsp+160h] [rbp-DF8h] BYREF
  _BYTE v82[32]; // [rsp+168h] [rbp-DF0h] BYREF
  __int128 v83; // [rsp+188h] [rbp-DD0h]
  _BYTE v84[32]; // [rsp+1A0h] [rbp-DB8h] BYREF
  _BYTE v85[32]; // [rsp+1C0h] [rbp-D98h] BYREF
  _QWORD v86[3]; // [rsp+1E0h] [rbp-D78h] BYREF
  int v87; // [rsp+1F8h] [rbp-D60h]
  struct _WIN32_FIND_DATAW v88; // [rsp+200h] [rbp-D58h] BYREF
  WCHAR *v89; // [rsp+450h] [rbp-B08h] BYREF
  HANDLE hFindFile; // [rsp+458h] [rbp-B00h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+460h] [rbp-AF8h] BYREF
  unsigned __int16 v92[260]; // [rsp+6B0h] [rbp-8A8h] BYREF
  unsigned __int16 v93[260]; // [rsp+8B8h] [rbp-6A0h] BYREF
  struct _WIN32_FIND_DATAW v94; // [rsp+AC0h] [rbp-498h] BYREF
  WCHAR FileName[264]; // [rsp+D10h] [rbp-248h] BYREF

  v51 = a2;
  v53 = a1;
  v49 = 0;
  v4 = *(AppData **)(a1 + 16);
  v5 = *(AppData **)(a1 + 8);
  if ( v5 != v4 )
  {
    std::_Destroy_range<std::allocator<AppData>>(v5);
    v6 = *(_QWORD *)(a1 + 8);
    *(_QWORD *)(a1 + 16) = v6;
  }
  try
  {
    hstringHeader.Reserved.Reserved1 = (PVOID)a1;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = FileName;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = a2;
    if ( *(_BYTE *)(a1 + 64) )
    {
      v7 = IsAppContainerPresent();
      CurrentAppEnumeratorImpl::CurrentAppEnumeratorImpl((CurrentAppEnumeratorImpl *)&v88, v7);
      lambda_847a5091599a0d35931edee757dff544_::operator()_CurrentAppEnumeratorImpl_(&hstringHeader, &v88, v7 == 0);
    }
    v8 = (WCHAR *)(a1 + 32);
    if ( *(_QWORD *)(a1 + 56) <= 7u )
      v9 = (WCHAR *)(a1 + 32);
    else
      v9 = *(WCHAR **)v8;
    *(_QWORD *)&v88.dwFileAttributes = v9;
    memset(&v88.ftCreationTime.dwHighDateTime, 0, 24);
    LOBYTE(v88.nFileSizeLow) = 1;
    *(_QWORD *)&v88.dwReserved1 = 0;
    *(_QWORD *)&v88.cFileName[2] = 0;
    string = 0;
    v10 = WindowsCreateStringReference(L"Windows.Management.Deployment.PackageManager", 0x2Cu, &hstringHeader, &string);
    if ( v10 < 0 )
      RaiseException(v10, 1u, 0, 0);
    *(_QWORD *)&v88.ftCreationTime.dwHighDateTime = 0;
    ppszPath = 0;
    v11 = RoActivateInstance(string, &ppszPath);
    if ( v11 < 0
      || ((v12 = memcmp_0(&GUID_9a7d4b65_5e8f_4fc7_a2e5_7f6925cb8b53, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u),
           v13 = ppszPath,
           v12)
        ? (v11 = (**(__int64 (__fastcall ***)(PWSTR, GUID *, DWORD *))ppszPath)(
                   ppszPath,
                   &GUID_9a7d4b65_5e8f_4fc7_a2e5_7f6925cb8b53,
                   &v88.ftCreationTime.dwHighDateTime),
           (*(void (__fastcall **)(PWSTR))(*(_QWORD *)ppszPath + 16LL))(ppszPath),
           v13 = *(PWSTR *)&v88.ftCreationTime.dwHighDateTime)
        : (PWSTR)(*(_QWORD *)&v88.ftCreationTime.dwHighDateTime = ppszPath),
          v11 < 0) )
    {
      v77 = &_com_error::`vftable';
      v78 = v11;
      v79 = 0;
      throw (_com_error *)&v77;
    }
    v14 = (*(__int64 (__fastcall **)(PWSTR, _QWORD, DWORD *))(*(_QWORD *)v13 + 96LL))(
            v13,
            0,
            &v88.ftLastAccessTime.dwHighDateTime);
    if ( v14 < 0 )
    {
      pExceptionObject = &_com_error::`vftable';
      v72 = v14;
      v73 = 0;
      throw (_com_error *)&pExceptionObject;
    }
    v15 = (*(__int64 (__fastcall **)(_QWORD, DWORD *))(**(_QWORD **)&v88.ftLastAccessTime.dwHighDateTime + 48LL))(
            *(_QWORD *)&v88.ftLastAccessTime.dwHighDateTime,
            &v88.ftLastWriteTime.dwHighDateTime);
    if ( v15 < 0 )
    {
      v74 = &_com_error::`vftable';
      v75 = v15;
      v76 = 0;
      throw (_com_error *)&v74;
    }
    v16 = (*(__int64 (__fastcall **)(_QWORD, DWORD *))(**(_QWORD **)&v88.ftLastWriteTime.dwHighDateTime + 56LL))(
            *(_QWORD *)&v88.ftLastWriteTime.dwHighDateTime,
            &v88.nFileSizeLow);
    nFileSizeLow = v88.nFileSizeLow;
    if ( v16 < 0 )
      nFileSizeLow = 0;
    LOBYTE(v88.nFileSizeLow) = nFileSizeLow;
    AppEnumeratorImpl::ScanForPackagesOnVolume((AppEnumeratorImpl *)&v88);
    while ( LOBYTE(v88.nFileSizeLow) )
    {
      AppData::AppData((AppData *)v84);
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)&v88.cFileName[2], 0);
      std::wstring::wstring(v82, StringRawBuffer);
      std::wstring::operator=(v84, v82);
      std::wstring::~wstring(v82);
      v87 = 0;
      std::wstring::wstring(v82, &v88.cFileName[6]);
      std::wstring::operator=(v85, v82);
      std::wstring::~wstring(v82);
      v62 = L"*.idx";
      v63 = 0;
      v64 = L"*.lock";
      v65 = 0;
      v66 = L"*.val";
      v67 = 0;
      v68 = L"*.dxcache";
      v69 = 1;
      for ( i = &v62; i != (const wchar_t **)&v70; i += 2 )
      {
        AppEnumeratorImpl::GetCurrentPackagePathCached((AppEnumeratorImpl *)&v88, FileName, v42, *i);
        memset_0(&v94, 0, sizeof(v94));
        FirstFileW = FindFirstFileW(FileName, &v94);
        v45 = FirstFileW;
        if ( FirstFileW != (HANDLE)-1LL )
        {
          hstringHeader.Reserved.Reserved1 = FirstFileW;
          hstringHeader.Reserved.Reserved2[8] = 1;
          do
          {
            std::wstring::wstring(v82);
            v83 = 0;
            AppEnumeratorImpl::GetCurrentPackagePathCached((AppEnumeratorImpl *)&v88, FileName, v46, v94.cFileName);
            if ( *((_BYTE *)i + 8) )
            {
              v47 = -1;
              do
                ++v47;
              while ( FileName[v47] );
              std::wstring::_Assign<unsigned short>(v82, FileName);
              std::vector<AppCacheData>::push_back(v86, v82);
            }
            else
            {
              DeleteFileW(FileName);
            }
            std::wstring::~wstring(v82);
          }
          while ( FindNextFileW(v45, &v94) );
          hstringHeader.Reserved.Reserved2[8] = 0;
          FindClose(v45);
        }
      }
      std::_Func_class<void,AppData &>::operator()(a2, v84);
      if ( v86[0] != v86[1] )
        std::vector<AppData>::push_back(a1 + 8, v84);
      v49 |= 3u;
      AppEnumeratorImpl::MoveNext((AppEnumeratorImpl *)&v88);
      AppData::~AppData((AppData *)v84);
    }
    WindowsDeleteString(*(HSTRING *)&v88.cFileName[2]);
    *(_QWORD *)&v88.cFileName[2] = 0;
    ATL::CComPtrBase<ABI::Windows::ApplicationModel::IPackage>::~CComPtrBase<ABI::Windows::ApplicationModel::IPackage>(&v88.dwReserved1);
    ATL::CComPtrBase<ABI::Windows::ApplicationModel::IPackage>::~CComPtrBase<ABI::Windows::ApplicationModel::IPackage>(&v88.ftLastWriteTime.dwHighDateTime);
    ATL::CComPtrBase<ABI::Windows::ApplicationModel::IPackage>::~CComPtrBase<ABI::Windows::ApplicationModel::IPackage>(&v88.ftLastAccessTime.dwHighDateTime);
    ATL::CComPtrBase<ABI::Windows::ApplicationModel::IPackage>::~CComPtrBase<ABI::Windows::ApplicationModel::IPackage>(&v88.ftCreationTime.dwHighDateTime);
    if ( *(_QWORD *)(a1 + 56) > 7u )
      v8 = *(WCHAR **)v8;
    v89 = v8;
    hFindFile = (HANDLE)-1LL;
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    if ( (unsigned __int8)IsSHGetKnownFolderPathPresent() )
    {
      ppszPath = 0;
      if ( SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0, 0, &ppszPath) >= 0 )
      {
        v18 = StringCchPrintfW(v92, 0x104u, L"%s\\D3DSCache", ppszPath);
        CoTaskMemFree(ppszPath);
        if ( v18 >= 0 )
        {
          v19 = -1;
          do
            ++v19;
          while ( v92[v19] );
          v20 = v19;
          v21 = v89;
          v22 = -1;
          do
            ++v22;
          while ( v89[v22] );
          v23 = &v89[v22];
          ppszPath = v23;
          v24 = (2 * v22) >> 1;
          if ( (v20 * 2) >> 1 >= v24 )
          {
            hstringHeader.Reserved.Reserved1 = &v92[v20];
            v25 = v92;
            v26 = &v92[v20 - v24];
LABEL_34:
            v27 = v25;
            for ( j = v21; j != v23; ++j )
            {
              v29 = *v27;
              v30 = toupper(*j);
              if ( toupper(v29) != v30 )
              {
                if ( v25 == v26 )
                  goto LABEL_51;
                ++v25;
                v23 = ppszPath;
                goto LABEL_34;
              }
              ++v27;
              v23 = ppszPath;
            }
            if ( v25 != hstringHeader.Reserved.Reserved1
              && (int)StringCchPrintfW(FindFileData.cFileName, 0x104u, L"%s\\*", v92) >= 0 )
            {
              hFindFile = FindFirstFileW(FindFileData.cFileName, &FindFileData);
              if ( hFindFile != (HANDLE)-1LL )
              {
                while ( (FindFileData.dwFileAttributes & 0x10) == 0 || FindFileData.cFileName[0] == 46 )
                {
                  if ( !FindNextFileW(hFindFile, &FindFileData) )
                    AppDataEnumeratorImpl::Close((AppDataEnumeratorImpl *)&v89);
                  if ( hFindFile == (HANDLE)-1LL )
                    goto LABEL_51;
                }
                if ( (int)StringCchPrintfW(v93, 0x104u, L"%s\\%s\\", v92, FindFileData.cFileName) < 0 )
                  AppDataEnumeratorImpl::Close((AppDataEnumeratorImpl *)&v89);
              }
            }
          }
        }
      }
    }
LABEL_51:
    v31 = v53;
    v32 = v49;
    v33 = v51;
    while ( hFindFile != (HANDLE)-1LL )
    {
      AppData::AppData((AppData *)v84);
      std::wstring::wstring(&hstringHeader, &qword_1800ACF70);
      std::wstring::operator=(v84, &hstringHeader);
      std::wstring::~wstring(&hstringHeader);
      v87 = 1;
      std::wstring::wstring(&hstringHeader, v93);
      std::wstring::operator=(v85, &hstringHeader);
      std::wstring::~wstring(&hstringHeader);
      v54 = L"*.idx";
      v55 = 0;
      v56 = L"*.lock";
      v57 = 0;
      v58 = L"*.val";
      v59 = 0;
      v60 = L"*.dxcache";
      v61 = 1;
      for ( k = &v54; k != &v62; k += 2 )
      {
        AppDataEnumeratorImpl::GetCurrentPackagePathCached((AppDataEnumeratorImpl *)&v89, FileName, v35, *k);
        memset_0(&v88, 0, sizeof(v88));
        v37 = FindFirstFileW(FileName, &v88);
        v38 = v37;
        if ( v37 != (HANDLE)-1LL )
        {
          v51 = v37;
          v52 = 1;
          do
          {
            std::wstring::wstring(v82);
            v83 = 0;
            AppDataEnumeratorImpl::GetCurrentPackagePathCached(
              (AppDataEnumeratorImpl *)&v89,
              FileName,
              v39,
              v88.cFileName);
            if ( *((_BYTE *)k + 8) )
            {
              v40 = -1;
              do
                ++v40;
              while ( FileName[v40] );
              std::wstring::_Assign<unsigned short>(v82, FileName);
              std::vector<AppCacheData>::push_back(v86, v82);
            }
            else
            {
              DeleteFileW(FileName);
            }
            std::wstring::~wstring(v82);
          }
          while ( FindNextFileW(v38, &v88) );
          v52 = 0;
          FindClose(v38);
        }
      }
      std::_Func_class<void,AppData &>::operator()(v33, v84);
      std::vector<AppData>::push_back(v31 + 8, v84);
      v32 |= 0xCu;
      AppDataEnumeratorImpl::MoveNext((AppDataEnumeratorImpl *)&v89);
      AppData::~AppData((AppData *)v84);
    }
    result = 0;
  }
  catch ( _com_error *v70 )
  {
    v48 = 1;
    if ( *((_DWORD *)v70 + 2) == -2147467260 )
      return (unsigned int)-2147467260;
    return v48;
  }
  catch ( std::bad_alloc )
  {
    return 1;
  }
  hstringHeader.Reserved.Reserved1 = (PVOID)a1;
}

```

## disassembly

```asm
0x180001d70  mov     [rsp+arg_8], rbx
0x180001d75  mov     [rsp+arg_10], rsi
0x180001d7a  push    rdi
0x180001d7b  push    r12
0x180001d7d  push    r13
0x180001d7f  push    r14
0x180001d81  push    r15
0x180001d83  sub     rsp, 0F30h
0x180001d8a  mov     rax, cs:__security_cookie
0x180001d91  xor     rax, rsp
0x180001d94  mov     [rsp+0F58h+var_38], rax
0x180001d9c  mov     r15, rdx
0x180001d9f  mov     [rsp+0F58h+var_F18], rdx
0x180001da4  mov     r14, rcx
0x180001da7  mov     [rsp+0F58h+var_F08], rcx
0x180001dac  xor     r13d, r13d
0x180001daf  mov     [rsp+0F58h+var_F28], r13d
0x180001db4  mov     rdx, [rcx+10h]
0x180001db8  mov     rcx, [rcx+8]; this
0x180001dbc  cmp     rcx, rdx
0x180001dbf  jz      short loc_180001DCE
0x180001dc1  call    ??$_Destroy_range@V?$allocator@UAppData@@@std@@@std@@YAXPEAUAppData@@QEAU1@AEAV?$allocator@UAppData@@@0@@Z; std::_Destroy_range<std::allocator<AppData>>(AppData *,AppData * const,std::allocator<AppData> &)
0x180001dc6  mov     rax, [r14+8]
0x180001dca  mov     [r14+10h], rax
0x180001dce  mov     qword ptr [rsp+0F58h+hstringHeader.Reserved], r14
0x180001dd6  lea     rax, [rsp+0F58h+FileName]
0x180001dde  mov     qword ptr [rsp+0F58h+hstringHeader.Reserved+8], rax
0x180001de6  mov     qword ptr [rsp+0F58h+hstringHeader.Reserved+10h], r15
0x180001dee  cmp     [r14+40h], r13b
0x180001df2  jz      short loc_180001E2D
0x180001df4  call    ?IsAppContainerPresent@@YAHXZ; IsAppContainerPresent(void)
0x180001df9  mov     ebx, eax
0x180001dfb  mov     edx, eax; int
0x180001dfd  lea     rcx, [rsp+0F58h+var_D58]; this
0x180001e05  call    ??0CurrentAppEnumeratorImpl@@QEAA@H@Z; CurrentAppEnumeratorImpl::CurrentAppEnumeratorImpl(int)
0x180001e0a  mov     r8d, r13d
0x180001e0d  test    ebx, ebx
0x180001e0f  setz    r8b
0x180001e13  lea     rdx, [rsp+0F58h+var_D58]
0x180001e1b  lea     rcx, [rsp+0F58h+hstringHeader]
0x180001e23  call    _lambda_847a5091599a0d35931edee757dff544___operator___CurrentAppEnumeratorImpl_
0x180001e28  jmp     loc_1800022FE
0x180001e2d  lea     rsi, [r14+20h]
0x180001e31  cmp     qword ptr [rsi+18h], 7
0x180001e36  jbe     short loc_180001E3D
0x180001e38  mov     rax, [rsi]
0x180001e3b  jmp     short loc_180001E40
0x180001e3d  mov     rax, rsi
0x180001e40  mov     qword ptr [rsp+0F58h+var_D58.dwFileAttributes], rax
0x180001e48  mov     qword ptr [rsp+0F58h+var_D58.ftCreationTime.dwHighDateTime], r13
0x180001e50  mov     qword ptr [rsp+0F58h+var_D58.ftLastAccessTime.dwHighDateTime], r13
0x180001e58  mov     qword ptr [rsp+0F58h+var_D58.ftLastWriteTime.dwHighDateTime], r13
0x180001e60  mov     byte ptr [rsp+0F58h+var_D58.nFileSizeLow], 1
0x180001e68  mov     qword ptr [rsp+0F58h+var_D58.dwReserved1], r13
0x180001e70  mov     qword ptr [rsp+0F58h+var_D58.cFileName+4], r13
0x180001e78  mov     [rsp+0F58h+string], r13
0x180001e80  lea     r9, [rsp+0F58h+string]; string
0x180001e88  lea     r8, [rsp+0F58h+hstringHeader]; hstringHeader
0x180001e90  mov     edx, 2Ch ; ','; length
0x180001e95  lea     rcx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x180001e9c  call    cs:__imp_WindowsCreateStringReference
0x180001ea2  test    eax, eax
0x180001ea4  jns     short loc_180001EB9
0x180001ea6  xor     r9d, r9d; lpArguments
0x180001ea9  xor     r8d, r8d; nNumberOfArguments
0x180001eac  lea     edx, [r9+1]; dwExceptionFlags
0x180001eb0  mov     ecx, eax; dwExceptionCode
0x180001eb2  call    cs:__imp_RaiseException
0x180001eb8  nop
0x180001eb9  mov     qword ptr [rsp+0F58h+var_D58.ftCreationTime.dwHighDateTime], r13
0x180001ec1  mov     [rsp+0F58h+ppszPath], r13
0x180001ec6  lea     rdx, [rsp+0F58h+ppszPath]
0x180001ecb  mov     rcx, [rsp+0F58h+string]
0x180001ed3  call    cs:__imp_RoActivateInstance
0x180001ed9  mov     ebx, eax
0x180001edb  test    eax, eax
0x180001edd  js      loc_1800027CA
0x180001ee3  mov     r8d, 10h; Size
0x180001ee9  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180001ef0  lea     rcx, _GUID_9a7d4b65_5e8f_4fc7_a2e5_7f6925cb8b53; Buf1
0x180001ef7  call    memcmp_0
0x180001efc  mov     rcx, [rsp+0F58h+ppszPath]
0x180001f01  test    eax, eax
0x180001f03  jnz     short loc_180001F0F
0x180001f05  mov     qword ptr [rsp+0F58h+var_D58.ftCreationTime.dwHighDateTime], rcx
0x180001f0d  jmp     short loc_180001F44
0x180001f0f  mov     rax, [rcx]
0x180001f12  lea     r8, [rsp+0F58h+var_D58.ftCreationTime.dwHighDateTime]
0x180001f1a  lea     rdx, _GUID_9a7d4b65_5e8f_4fc7_a2e5_7f6925cb8b53
0x180001f21  mov     rax, [rax]
0x180001f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f29  mov     ebx, eax
0x180001f2b  mov     rcx, [rsp+0F58h+ppszPath]
0x180001f30  mov     rax, [rcx]
0x180001f33  mov     rax, [rax+10h]
0x180001f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f3c  mov     rcx, qword ptr [rsp+0F58h+var_D58.ftCreationTime.dwHighDateTime]
0x180001f44  test    ebx, ebx
0x180001f46  js      loc_1800027CA
0x180001f4c  mov     rax, [rcx]
0x180001f4f  lea     r8, [rsp+0F58h+var_D58.ftLastAccessTime.dwHighDateTime]
0x180001f57  xor     edx, edx
0x180001f59  mov     rax, [rax+60h]
0x180001f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f62  test    eax, eax
0x180001f64  jns     short loc_180001F9C
0x180001f66  lea     rcx, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180001f6d  mov     [rsp+0F58h+pExceptionObject], rcx
0x180001f75  mov     [rsp+0F58h+var_E68], eax
0x180001f7c  xorps   xmm0, xmm0
0x180001f7f  movdqu  [rsp+0F58h+var_E60], xmm0
0x180001f88  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180001f8f  lea     rcx, [rsp+0F58h+pExceptionObject]; pExceptionObject
0x180001f97  call    _CxxThrowException_0
0x180001f9c  mov     rcx, qword ptr [rsp+0F58h+var_D58.ftLastAccessTime.dwHighDateTime]
0x180001fa4  mov     rax, [rcx]
0x180001fa7  lea     rdx, [rsp+0F58h+var_D58.ftLastWriteTime.dwHighDateTime]
0x180001faf  mov     rax, [rax+30h]
0x180001fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fb8  test    eax, eax
0x180001fba  jns     short loc_180001FF2
0x180001fbc  lea     rcx, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180001fc3  mov     [rsp+0F58h+var_E50], rcx
0x180001fcb  mov     [rsp+0F58h+var_E48], eax
0x180001fd2  xorps   xmm0, xmm0
0x180001fd5  movdqu  [rsp+0F58h+var_E40], xmm0
0x180001fde  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180001fe5  lea     rcx, [rsp+0F58h+var_E50]; pExceptionObject
0x180001fed  call    _CxxThrowException_0
0x180001ff2  mov     rcx, qword ptr [rsp+0F58h+var_D58.ftLastWriteTime.dwHighDateTime]
0x180001ffa  mov     rax, [rcx]
0x180001ffd  lea     rdx, [rsp+0F58h+var_D58.nFileSizeLow]
0x180002005  mov     rax, [rax+38h]
0x180002009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000200e  movzx   edx, byte ptr [rsp+0F58h+var_D58.nFileSizeLow]
0x180002016  test    eax, eax
0x180002018  cmovs   edx, r13d
0x18000201c  mov     byte ptr [rsp+0F58h+var_D58.nFileSizeLow], dl
0x180002023  lea     rcx, [rsp+0F58h+var_D58]; this
0x18000202b  call    ?ScanForPackagesOnVolume@AppEnumeratorImpl@@AEAAXXZ; AppEnumeratorImpl::ScanForPackagesOnVolume(void)
0x180002030  nop
0x180002031  lea     r12, aVal; "*.val"
0x180002038  lea     rdi, aLock; "*.lock"
0x18000203f  lea     rbx, aIdx; "*.idx"
0x180002046  cmp     byte ptr [rsp+0F58h+var_D58.nFileSizeLow], r13b
0x18000204e  jnz     loc_180002558
0x180002054  mov     rcx, qword ptr [rsp+0F58h+var_D58.cFileName+4]; string
0x18000205c  call    cs:__imp_WindowsDeleteString
0x180002062  mov     qword ptr [rsp+0F58h+var_D58.cFileName+4], r13
0x18000206a  lea     rcx, [rsp+0F58h+var_D58.dwReserved1]
0x180002072  call    ??1?$CComPtrBase@UIPackage@ApplicationModel@Windows@ABI@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ABI::Windows::ApplicationModel::IPackage>::~CComPtrBase<ABI::Windows::ApplicationModel::IPackage>(void)
0x180002077  lea     rcx, [rsp+0F58h+var_D58.ftLastWriteTime.dwHighDateTime]
0x18000207f  call    ??1?$CComPtrBase@UIPackage@ApplicationModel@Windows@ABI@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ABI::Windows::ApplicationModel::IPackage>::~CComPtrBase<ABI::Windows::ApplicationModel::IPackage>(void)
0x180002084  lea     rcx, [rsp+0F58h+var_D58.ftLastAccessTime.dwHighDateTime]
0x18000208c  call    ??1?$CComPtrBase@UIPackage@ApplicationModel@Windows@ABI@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ABI::Windows::ApplicationModel::IPackage>::~CComPtrBase<ABI::Windows::ApplicationModel::IPackage>(void)
0x180002091  lea     rcx, [rsp+0F58h+var_D58.ftCreationTime.dwHighDateTime]
0x180002099  call    ??1?$CComPtrBase@UIPackage@ApplicationModel@Windows@ABI@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ABI::Windows::ApplicationModel::IPackage>::~CComPtrBase<ABI::Windows::ApplicationModel::IPackage>(void)
0x18000209e  cmp     qword ptr [rsi+18h], 7
0x1800020a3  jbe     short loc_1800020A8
0x1800020a5  mov     rsi, [rsi]
0x1800020a8  mov     [rsp+0F58h+var_B08], rsi
0x1800020b0  mov     [rsp+0F58h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x1800020bc  xor     edx, edx; Val
0x1800020be  mov     r8d, 250h; Size
0x1800020c4  lea     rcx, [rsp+0F58h+FindFileData]; void *
0x1800020cc  call    memset_0
0x1800020d1  call    IsSHGetKnownFolderPathPresent
0x1800020d6  test    al, al
0x1800020d8  jz      loc_1800022E4
0x1800020de  mov     [rsp+0F58h+ppszPath], r13
0x1800020e3  lea     r9, [rsp+0F58h+ppszPath]; ppszPath
0x1800020e8  xor     r8d, r8d; hToken
0x1800020eb  xor     edx, edx; dwFlags
0x1800020ed  lea     rcx, FOLDERID_LocalAppData; rfid
0x1800020f4  call    cs:__imp_SHGetKnownFolderPath
0x1800020fa  test    eax, eax
0x1800020fc  js      loc_1800022E4
0x180002102  mov     r9, [rsp+0F58h+ppszPath]
0x180002107  lea     r8, aSD3dscache; "%s\\D3DSCache"
0x18000210e  mov     edx, 104h; unsigned __int64
0x180002113  lea     rcx, [rsp+0F58h+var_8A8]; unsigned __int16 *
0x18000211b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002120  mov     ebx, eax
0x180002122  mov     rcx, [rsp+0F58h+ppszPath]; pv
0x180002127  call    cs:__imp_CoTaskMemFree
0x18000212d  test    ebx, ebx
0x18000212f  js      loc_1800022E4
0x180002135  lea     rcx, [rsp+0F58h+var_8A8]
0x18000213d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002141  inc     rax
0x180002144  cmp     [rcx+rax*2], r13w
0x180002149  jnz     short loc_180002141
0x18000214b  lea     rdx, [rax+rax]
0x18000214f  mov     r12, [rsp+0F58h+var_B08]
0x180002157  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000215b  inc     rax
0x18000215e  cmp     [r12+rax*2], r13w
0x180002163  jnz     short loc_18000215B
0x180002165  lea     r8, [r12+rax*2]
0x180002169  mov     [rsp+0F58h+ppszPath], r8
0x18000216e  mov     rcx, r8
0x180002171  sub     rcx, r12
0x180002174  sar     rcx, 1
0x180002177  mov     rax, rdx
0x18000217a  sar     rax, 1
0x18000217d  cmp     rax, rcx
0x180002180  jl      loc_1800022E4
0x180002186  lea     rax, [rsp+0F58h+var_8A8]
0x18000218e  add     rdx, rax
0x180002191  mov     qword ptr [rsp+0F58h+hstringHeader.Reserved], rdx
0x180002199  lea     rsi, [rsp+0F58h+var_8A8]
0x1800021a1  lea     rax, [rcx+rcx]
0x1800021a5  mov     r13, rdx
0x1800021a8  sub     r13, rax
0x1800021ab  mov     r15, rsi
0x1800021ae  mov     r14, r12
0x1800021b1  cmp     r14, r8
0x1800021b4  jz      short loc_1800021F5
0x1800021b6  movzx   ecx, word ptr [r14]; C
0x1800021ba  movzx   ebx, word ptr [r15]
0x1800021be  call    cs:__imp_toupper
0x1800021c4  mov     edi, eax
0x1800021c6  mov     ecx, ebx; C
0x1800021c8  call    cs:__imp_toupper
0x1800021ce  cmp     eax, edi
0x1800021d0  jnz     short loc_1800021E1
0x1800021d2  add     r15, 2
0x1800021d6  add     r14, 2
0x1800021da  mov     r8, [rsp+0F58h+ppszPath]
0x1800021df  jmp     short loc_1800021B1
0x1800021e1  cmp     rsi, r13
0x1800021e4  jz      loc_1800022E1
0x1800021ea  add     rsi, 2
0x1800021ee  mov     r8, [rsp+0F58h+ppszPath]
0x1800021f3  jmp     short loc_1800021AB
0x1800021f5  cmp     rsi, qword ptr [rsp+0F58h+hstringHeader.Reserved]
0x1800021fd  jz      loc_1800022E1
0x180002203  lea     r9, [rsp+0F58h+var_8A8]
0x18000220b  lea     r8, aS_2; "%s\\*"
0x180002212  mov     edi, 104h
0x180002217  mov     edx, edi; unsigned __int64
0x180002219  lea     rcx, [rsp+0F58h+FindFileData.cFileName]; unsigned __int16 *
0x180002221  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002226  xor     r13d, r13d
0x180002229  test    eax, eax
0x18000222b  js      loc_1800022E4
0x180002231  lea     rdx, [rsp+0F58h+FindFileData]; lpFindFileData
0x180002239  lea     rcx, [rsp+0F58h+FindFileData.cFileName]; lpFileName
0x180002241  call    cs:__imp_FindFirstFileW
0x180002247  mov     [rsp+0F58h+hFindFile], rax
0x18000224f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002253  jz      loc_1800022E4
0x180002259  test    byte ptr [rsp+0F58h+FindFileData.dwFileAttributes], 10h
0x180002261  jz      short loc_18000226E
0x180002263  cmp     [rsp+0F58h+FindFileData.cFileName], 2Eh ; '.'
0x18000226c  jnz     short loc_1800022A2
0x18000226e  lea     rdx, [rsp+0F58h+FindFileData]; lpFindFileData
0x180002276  mov     rcx, [rsp+0F58h+hFindFile]; hFindFile
0x18000227e  call    cs:__imp_FindNextFileW
0x180002284  test    eax, eax
0x180002286  jnz     short loc_180002295
0x180002288  lea     rcx, [rsp+0F58h+var_B08]; this
0x180002290  call    ?Close@AppDataEnumeratorImpl@@AEAAXXZ; AppDataEnumeratorImpl::Close(void)
0x180002295  cmp     [rsp+0F58h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18000229e  jnz     short loc_180002259
0x1800022a0  jmp     short loc_1800022E4
0x1800022a2  lea     rax, [rsp+0F58h+FindFileData.cFileName]
0x1800022aa  mov     [rsp+0F58h+var_F38], rax
0x1800022af  lea     r9, [rsp+0F58h+var_8A8]
0x1800022b7  lea     r8, aSS; "%s\\%s\\"
0x1800022be  mov     rdx, rdi; unsigned __int64
0x1800022c1  lea     rcx, [rsp+0F58h+var_6A0]; unsigned __int16 *
0x1800022c9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800022ce  test    eax, eax
0x1800022d0  jns     short loc_1800022E4
0x1800022d2  lea     rcx, [rsp+0F58h+var_B08]; this
0x1800022da  call    ?Close@AppDataEnumeratorImpl@@AEAAXXZ; AppDataEnumeratorImpl::Close(void)
0x1800022df  jmp     short loc_1800022E4
0x1800022e1  xor     r13d, r13d
0x1800022e4  mov     rsi, [rsp+0F58h+var_F08]
0x1800022e9  mov     r14d, [rsp+0F58h+var_F28]
0x1800022ee  mov     r15, [rsp+0F58h+var_F18]
0x1800022f3  cmp     [rsp+0F58h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x1800022fc  jnz     short loc_180002305
0x1800022fe  xor     eax, eax
0x180002300  jmp     loc_18000280C
0x180002305  lea     rcx, [rsp+0F58h+var_DB8]; this
0x18000230d  call    ??0AppData@@QEAA@XZ; AppData::AppData(void)
0x180002312  nop
0x180002313  lea     rdx, qword_1800ACF70
0x18000231a  lea     rcx, [rsp+0F58h+hstringHeader]
0x180002322  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180002327  lea     rdx, [rsp+0F58h+hstringHeader]
0x18000232f  lea     rcx, [rsp+0F58h+var_DB8]
0x180002337  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000233c  lea     rcx, [rsp+0F58h+hstringHeader]
0x180002344  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180002349  mov     [rsp+0F58h+var_D60], 1
0x180002354  lea     rdx, [rsp+0F58h+var_6A0]
0x18000235c  lea     rcx, [rsp+0F58h+hstringHeader]
  ... truncated ...
```
