# MsiApplication::GetMsiApplication(ConfigSettings const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003b364`
- end: `0x18003bfa9`
- name: `?GetMsiApplication@MsiApplication@@QEAAXAEBVConfigSettings@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `3141`
- prototype: `INSTALLUILEVEL __fastcall(Application *this, struct ConfigSettings *, const WCHAR *szProduct)`
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001405c`

## callees

- `0x18000e06c`
- `0x18000eb5c`
- `0x1800118d0`
- `0x1800150ac`
- `0x1800175b0`
- `0x180018450`
- `0x180018a60`
- `0x1800197d4`
- `0x1800289a4`
- `0x18002b584`
- `0x18002ed54`
- `0x18002f4f0`
- `0x180034908`
- `0x18003b364`
- `0x18003bfb0`
- `0x1800403ac`
- `0x1800404c4`
- `0x180042ed4`
- `0x180044c88`
- `0x1800461c4`
- `0x1800493b8`
- `0x180052f28`
- `0x180059920`
- `0x180067aa0`
- `0x1800ffa08`
- `0x180100418`
- `0x18010f720`
- `0x18012546c`
- `0x180130010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18003b8a5`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18003b92f`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18003b8a5`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18003b92f`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18003b56b`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18003b56b`
- `msi!__imp_MsiOpenDatabaseW` at `0x18003b510`
- `msi!__imp_MsiOpenDatabaseW` at `0x18003b510`
- `msi!__imp_MsiQueryProductStateW` at `0x18003b3d7`
- `msi!__imp_MsiQueryProductStateW` at `0x18003b3d7`
- `msi!__imp_MsiRecordGetFieldCount` at `0x18003b5c6`
- `msi!__imp_MsiRecordGetFieldCount` at `0x18003b5c6`
- `msi!__imp_MsiRecordGetStringW` at `0x18003b5ef`
- `msi!__imp_MsiRecordGetStringW` at `0x18003b5ef`
- `msi!__imp_MsiSetInternalUI` at `0x18003b3b0`
- `msi!__imp_MsiSetInternalUI` at `0x18003be4a`
- `msi!__imp_MsiSetInternalUI` at `0x18003b3b0`
- `msi!__imp_MsiSetInternalUI` at `0x18003be4a`
- `msi!__imp_MsiViewExecute` at `0x18003b581`
- `msi!__imp_MsiViewExecute` at `0x18003b581`
- `msi!__imp_MsiViewGetColumnInfo` at `0x18003b5ad`
- `msi!__imp_MsiViewGetColumnInfo` at `0x18003b5ad`

## string_xrefs

- `0x18003b8bb`: `InstallDate`
- `0x18003be79`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18003bec3`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18003bf09`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18003bf6d`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18003bf82`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18003bf97`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18003b518`: `MsiApplication::GetMsiApplication`
- `0x18003bd22`: `MsiApplication::GetMsiApplication`
- `0x18003bf52`: `MsiApplication::GetMsiApplication`
- `0x18003bee8`: `Failed to open MsiPackage %ws`
- `0x18003b560`: `SELECT * from Component`
- `0x18003b53a`: `Opened MSI Database: %ws`
- `0x18003bf3c`: `MsiDatabaseOpenView failed for MsiPackage %ws`
- `0x18003bf2d`: `MsiPackage has no components: %ws`
- `0x18003b62d`: `InstalledProductName`
- `0x18003b60b`: `ComponentId`
- `0x18003b7da`: `InstalledLanguage`

## pseudocode

```c
INSTALLUILEVEL __fastcall MsiApplication::GetMsiApplication(
        Application *this,
        struct ConfigSettings *a2,
        const WCHAR *szProduct)
{
  const WCHAR *v6; // rcx
  INSTALLUILEVEL result; // eax
  LPCWSTR *v8; // rcx
  __int64 *v9; // rdx
  unsigned int v10; // ebx
  __int64 FirstUserSid; // rax
  MSIHANDLE *v12; // rax
  const WCHAR *v13; // rcx
  UINT v14; // ebx
  LPCWSTR *v15; // rax
  MSIHANDLE *v16; // rax
  UINT v17; // ebx
  UINT v18; // eax
  MSIHANDLE *v19; // rax
  UINT ColumnInfo; // eax
  UINT FieldCount; // r15d
  UINT StringW; // eax
  unsigned int v23; // ebx
  __int64 v24; // rax
  __int64 v25; // rax
  unsigned int v26; // ebx
  __int64 v27; // rax
  __int64 v28; // rax
  unsigned int v29; // ebx
  __int64 v30; // rax
  __int64 v31; // rax
  unsigned int v32; // ebx
  __int64 v33; // rax
  unsigned int v34; // ebx
  __int64 v35; // rax
  _QWORD *v36; // rcx
  unsigned int v37; // ebx
  __int64 v38; // rax
  _QWORD *v39; // rcx
  unsigned int v40; // ebx
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rax
  _BYTE *i; // rbx
  char *v45; // rcx
  char *v46; // rdx
  __int64 v47; // rax
  LPCWSTR *v48; // rcx
  LPCWSTR *v49; // rcx
  int v50; // r8d
  const char *v51; // r9
  unsigned int v52; // [rsp+28h] [rbp-E0h]
  unsigned int v53; // [rsp+28h] [rbp-E0h]
  unsigned int v54; // [rsp+28h] [rbp-E0h]
  MSIHANDLE hRecord; // [rsp+48h] [rbp-C0h] BYREF
  MSIHANDLE hView; // [rsp+4Ch] [rbp-BCh] BYREF
  INSTALLUILEVEL hDatabase; // [rsp+50h] [rbp-B8h] BYREF
  MSIHANDLE hDatabase_4; // [rsp+54h] [rbp-B4h] BYREF
  MSIHANDLE hDatabase_8[4]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v60; // [rsp+68h] [rbp-A0h]
  DWORD pcchValueBuf[2]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v62; // [rsp+78h] [rbp-90h]
  INSTALLUILEVEL *p_hDatabase; // [rsp+80h] [rbp-88h]
  char v64; // [rsp+88h] [rbp-80h]
  char v65; // [rsp+90h] [rbp-78h] BYREF
  char v66; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD Src[4]; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v68; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v69; // [rsp+E0h] [rbp-28h]
  LPCWSTR szDatabasePath[3]; // [rsp+F0h] [rbp-18h] BYREF
  unsigned __int64 v71; // [rsp+108h] [rbp+0h]
  _QWORD v72[4]; // [rsp+110h] [rbp+8h] BYREF
  _QWORD v73[4]; // [rsp+130h] [rbp+28h] BYREF
  _BYTE v74[32]; // [rsp+150h] [rbp+48h] BYREF
  _BYTE v75[32]; // [rsp+170h] [rbp+68h] BYREF
  _BYTE v76[32]; // [rsp+190h] [rbp+88h] BYREF
  _BYTE v77[40]; // [rsp+1B0h] [rbp+A8h] BYREF
  WCHAR szValueBuf[264]; // [rsp+1D8h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+420h] [rbp+318h]

  v62 = -2;
  hDatabase = MsiSetInternalUI(INSTALLUILEVEL_NONE, 0);
  p_hDatabase = &hDatabase;
  v64 = 1;
  if ( *((_QWORD *)szProduct + 3) <= 7u )
    v6 = szProduct;
  else
    v6 = *(const WCHAR **)szProduct;
  result = MsiQueryProductStateW(v6);
  if ( (unsigned int)(result - 1) <= 2 || result == INSTALLUILEVEL_FULL )
  {
    v9 = Application::ApplicationTypePlaceholder;
    if ( result != INSTALLUILEVEL_DEFAULT )
      v9 = Application::ApplicationTypeApplication;
    std::wstring::operator=((char *)this + 368, v9);
    *((_DWORD *)this + 174) = 4;
    std::wstring::wstring(szDatabasePath);
    std::wstring::wstring(Src, L"LocalPackage");
    v10 = *((_DWORD *)this + 174);
    FirstUserSid = MsiApplication::GetFirstUserSid(this, &v68);
    MsiApplication::GetMsiProductInfo(this, szProduct, FirstUserSid, v10);
    std::wstring::~wstring(&v68);
    std::wstring::~wstring(Src);
    if ( !szDatabasePath[2] )
    {
      std::wstring::wstring(Src, &byte_1801389F0);
      std::wstring::operator=((char *)this + 600, Src);
      std::wstring::~wstring(Src);
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xB4,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
        (const char *)2,
        (unsigned int)Src);
    }
    std::wstring::operator=((char *)this + 664, szDatabasePath);
    std::wstring::operator=((char *)this + 600, szProduct);
    std::wstring::operator=((char *)this + 336, &Application::ApplicationSourceMsi);
    hDatabase_4 = 0;
    v12 = (MSIHANDLE *)PMSIHANDLE::operator&(&hDatabase_4);
    v13 = (const WCHAR *)szDatabasePath;
    if ( v71 > 7 )
      v13 = szDatabasePath[0];
    v14 = MsiOpenDatabaseW(v13, 0, v12);
    if ( v14 )
    {
      v48 = szDatabasePath;
      if ( v71 > 7 )
        LODWORD(v48) = szDatabasePath[0];
      v53 = (unsigned int)v48;
      AslLogCallPrintf(
        1,
        (unsigned int)"MsiApplication::GetMsiApplication",
        194,
        (unsigned int)"Failed to open MsiPackage %ws");
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xC3,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
        (const char *)v14,
        v53);
    }
    v15 = szDatabasePath;
    if ( v71 > 7 )
      LODWORD(v15) = szDatabasePath[0];
    v52 = (unsigned int)v15;
    AslLogCallPrintf(
      3,
      (unsigned int)"MsiApplication::GetMsiApplication",
      198,
      (unsigned int)"Opened MSI Database: %ws");
    hView = 0;
    v16 = (MSIHANDLE *)PMSIHANDLE::operator&(&hView);
    v17 = MsiDatabaseOpenViewW(hDatabase_4, L"SELECT * from Component", v16);
    if ( v17 )
    {
      v49 = szDatabasePath;
      if ( v17 == 1615 )
      {
        v50 = 207;
        v51 = "MsiPackage has no components: %ws";
      }
      else
      {
        v50 = 211;
        v51 = "MsiDatabaseOpenView failed for MsiPackage %ws";
      }
      if ( v71 > 7 )
        LODWORD(v49) = szDatabasePath[0];
      v54 = (unsigned int)v49;
      AslLogCallPrintf(1, (unsigned int)"MsiApplication::GetMsiApplication", v50, (_DWORD)v51);
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xD5,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
        (const char *)v17,
        v54);
    }
    v18 = MsiViewExecute(hView, 0);
    if ( v18 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xD8,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
        (const char *)v18,
        v52);
    hRecord = 0;
    v19 = (MSIHANDLE *)PMSIHANDLE::operator&(&hRecord);
    ColumnInfo = MsiViewGetColumnInfo(hView, MSICOLINFO_NAMES, v19);
    if ( ColumnInfo )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xDD,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
        (const char *)ColumnInfo,
        v52);
    FieldCount = MsiRecordGetFieldCount(hRecord);
    if ( FieldCount )
    {
      do
      {
        pcchValueBuf[0] = 260;
        StringW = MsiRecordGetStringW(hRecord, ++v17, szValueBuf, pcchValueBuf);
        if ( StringW )
          wil::details::in1diag3::_Throw_Win32(
            retaddr,
            (void *)0xE9,
            (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
            (const char *)StringW,
            v52);
      }
      while ( wcscmp_0(L"ComponentId", szValueBuf) && v17 < FieldCount );
    }
    std::wstring::wstring(v77);
    std::wstring::wstring(Src, L"InstalledProductName");
    v23 = *((_DWORD *)this + 174);
    v24 = MsiApplication::GetFirstUserSid(this, &v68);
    MsiApplication::GetMsiProductInfo(this, szProduct, v24, v23);
    std::wstring::~wstring(&v68);
    std::wstring::~wstring(Src);
    v25 = Utility::TrimSpace2(Src, v77);
    std::wstring::operator=((char *)this + 472, v25);
    std::wstring::~wstring(Src);
    std::wstring::wstring(v76);
    std::wstring::wstring(Src, L"Publisher");
    v26 = *((_DWORD *)this + 174);
    v27 = MsiApplication::GetFirstUserSid(this, &v68);
    MsiApplication::GetMsiProductInfo(this, szProduct, v27, v26);
    std::wstring::~wstring(&v68);
    std::wstring::~wstring(Src);
    v28 = Utility::TrimSpace2(Src, v76);
    std::wstring::operator=((char *)this + 504, v28);
    std::wstring::~wstring(Src);
    std::wstring::wstring(v75);
    std::wstring::wstring(Src, L"VersionString");
    v29 = *((_DWORD *)this + 174);
    v30 = MsiApplication::GetFirstUserSid(this, &v68);
    MsiApplication::GetMsiProductInfo(this, szProduct, v30, v29);
    std::wstring::~wstring(&v68);
    std::wstring::~wstring(Src);
    v31 = Utility::TrimSpace2(Src, v75);
    std::wstring::operator=((char *)this + 536, v31);
    std::wstring::~wstring(Src);
    std::wstring::wstring(v73);
    std::wstring::wstring(Src, L"InstalledLanguage");
    v32 = *((_DWORD *)this + 174);
    v33 = MsiApplication::GetFirstUserSid(this, &v68);
    MsiApplication::GetMsiProductInfo(this, szProduct, v33, v32);
    std::wstring::~wstring(&v68);
    std::wstring::~wstring(Src);
    if ( !v73[2] )
    {
      std::wstring::wstring(Src, L"Language");
      v34 = *((_DWORD *)this + 174);
      v35 = MsiApplication::GetFirstUserSid(this, &v68);
      MsiApplication::GetMsiProductInfo(this, szProduct, v35, v34);
      std::wstring::~wstring(&v68);
      std::wstring::~wstring(Src);
    }
    v36 = v73;
    if ( v73[3] > 7u )
      v36 = (_QWORD *)v73[0];
    *((_DWORD *)this + 176) = _o__wtoi(v36);
    std::wstring::wstring(v72);
    std::wstring::wstring(Src, L"InstallDate");
    v37 = *((_DWORD *)this + 174);
    v38 = MsiApplication::GetFirstUserSid(this, &v68);
    MsiApplication::GetMsiProductInfo(this, szProduct, v38, v37);
    std::wstring::~wstring(&v68);
    std::wstring::~wstring(Src);
    if ( v72[2] == 8 )
    {
      v39 = v72;
      if ( v72[3] > 7u )
        v39 = (_QWORD *)v72[0];
      if ( (unsigned int)_o__wtoi(v39) )
      {
        std::wstring::substr(v72, Src, 4, 2);
        std::wstring::_Append<unsigned short>(Src);
        std::wstring::substr(v72, &v68, 6, 2);
        std::wstring::_Append<unsigned short>(Src);
        std::wstring::~wstring(&v68);
        std::wstring::_Append<unsigned short>(Src);
        std::wstring::substr(v72, &v68, 0, 4);
        std::wstring::_Append<unsigned short>(Src);
        std::wstring::~wstring(&v68);
        std::wstring::_Append<unsigned short>(Src);
        std::wstring::operator=(v72, Src);
        std::wstring::operator=((char *)this + 568, v72);
        std::wstring::~wstring(Src);
      }
    }
    MsiApplication::GetMsiInstallLocation(this);
    std::wstring::wstring(v74);
    std::wstring::wstring(Src, L"PackageCode");
    v40 = *((_DWORD *)this + 174);
    v41 = MsiApplication::GetFirstUserSid(this, &v68);
    MsiApplication::GetMsiProductInfo(this, szProduct, v41, v40);
    std::wstring::~wstring(&v68);
    std::wstring::~wstring(Src);
    std::wstring::operator=((char *)this + 632, v74);
    if ( *((_DWORD *)a2 + 2) == 5 )
      goto LABEL_49;
    *(_OWORD *)hDatabase_8 = 0;
    v60 = 0;
    if ( *((_DWORD *)a2 + 2) != 2 )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl) )
      {
        std::wstring::wstring(Src, L".exe");
        std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(hDatabase_8, Src);
        std::wstring::~wstring(Src);
        std::wstring::wstring(Src, L".dll");
        std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(hDatabase_8, Src);
        std::wstring::~wstring(Src);
        std::wstring::wstring(Src, L".cpl");
        std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(hDatabase_8, Src);
        std::wstring::~wstring(Src);
        std::wstring::wstring(Src, L".sys");
        std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(hDatabase_8, Src);
        goto LABEL_38;
      }
      std::wstring::wstring(Src, L".exe");
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(hDatabase_8, Src);
      std::wstring::~wstring(Src);
      std::wstring::wstring(Src, L".cpl");
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(hDatabase_8, Src);
      std::wstring::~wstring(Src);
      std::wstring::wstring(Src, L".sys");
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(hDatabase_8, Src);
      std::wstring::~wstring(Src);
      if ( *((_BYTE *)a2 + 219) )
      {
        std::wstring::wstring(Src, L".dll");
        std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(hDatabase_8, Src);
LABEL_38:
        std::wstring::~wstring(Src);
      }
    }
    v68 = 0;
    v69 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl) )
      MsiApplication::QueryMsiDatabaseForFiles2(
        v42,
        (__int64)szProduct,
        (const WCHAR *)szDatabasePath,
        (__int64)hDatabase_8,
        (__int64)&v68);
    else
      MsiApplication::QueryMsiDatabaseForFiles(v42, szProduct, (const WCHAR *)szDatabasePath, (__int64)&v68);
    v43 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 2) + 16LL))((char *)this + 16);
    File::GetFilesFromPaths(Src, a2, v43, 0, hDatabase_8, &v68);
    for ( i = (_BYTE *)Src[0]; i != (_BYTE *)Src[1]; i += 816 )
    {
      (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)i + 112LL))(i);
      (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)i + 24LL))(i);
      (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)i + 32LL))(i);
      AslLogCallPrintf(3, (unsigned int)"MsiApplication::GetMsiApplication", 345, (unsigned int)"File %ws : %ws : %ws");
      if ( i[806] )
      {
        v45 = (char *)this + 40;
        v46 = &v65;
      }
      else
      {
        v45 = (char *)this + 24;
        v46 = &v66;
      }
      std::_Tree<std::_Tset_traits<File,std::less<File>,std::allocator<File>,0>>::emplace<File &>(v45, v46, i);
    }
    std::vector<File>::_Tidy(Src);
    std::vector<std::wstring>::_Tidy(&v68);
    std::vector<std::wstring>::_Tidy(hDatabase_8);
LABEL_49:
    v47 = Application::ComputeProgramInstanceId(this, Src);
    std::wstring::operator=((char *)this + 400, v47);
    std::wstring::~wstring(Src);
    if ( *((_BYTE *)a2 + 219) )
      (*(void (__fastcall **)(Application *, struct ConfigSettings *))(*(_QWORD *)this + 96LL))(this, a2);
    Application::SaveApplicationToCache(this, a2);
    std::wstring::~wstring(v74);
    std::wstring::~wstring(v72);
    std::wstring::~wstring(v73);
    std::wstring::~wstring(v75);
    std::wstring::~wstring(v76);
    std::wstring::~wstring(v77);
    PMSIHANDLE::~PMSIHANDLE((PMSIHANDLE *)&hRecord);
    PMSIHANDLE::~PMSIHANDLE((PMSIHANDLE *)&hView);
    PMSIHANDLE::~PMSIHANDLE((PMSIHANDLE *)&hDatabase_4);
    v8 = szDatabasePath;
    goto LABEL_52;
  }
  if ( result != -1 )
    goto LABEL_53;
  std::wstring::wstring(Src, &byte_1801389F0);
  std::wstring::operator=((char *)this + 600, Src);
  v8 = (LPCWSTR *)Src;
LABEL_52:
  result = (unsigned int)std::wstring::~wstring(v8);
LABEL_53:
  if ( hDatabase )
    return MsiSetInternalUI(hDatabase, 0);
  return result;
}

```

## disassembly

```asm
0x18003b364  mov     rax, rsp
0x18003b367  push    rbp
0x18003b368  push    rsi
0x18003b369  push    rdi
0x18003b36a  push    r14
0x18003b36c  push    r15
0x18003b36e  lea     rbp, [rax-318h]
0x18003b375  sub     rsp, 3F0h
0x18003b37c  mov     [rsp+410h+var_3A0], 0FFFFFFFFFFFFFFFEh
0x18003b385  mov     [rax+20h], rbx
0x18003b389  mov     rax, cs:__security_cookie
0x18003b390  xor     rax, rsp
0x18003b393  mov     [rbp+310h+var_30], rax
0x18003b39a  mov     rsi, r8
0x18003b39d  mov     r14, rdx
0x18003b3a0  mov     rdi, rcx
0x18003b3a3  mov     [rsp+410h+hDatabase], 0
0x18003b3ab  xor     edx, edx; phWnd
0x18003b3ad  lea     ecx, [rdx+2]; dwUILevel
0x18003b3b0  call    cs:__imp_MsiSetInternalUI
0x18003b3b6  mov     [rsp+410h+hDatabase], eax
0x18003b3ba  lea     rax, [rsp+410h+hDatabase]
0x18003b3bf  mov     [rsp+410h+var_398], rax
0x18003b3c4  mov     [rbp+310h+var_390], 1
0x18003b3c8  cmp     qword ptr [rsi+18h], 7
0x18003b3cd  jbe     short loc_18003B3D4
0x18003b3cf  mov     rcx, [rsi]
0x18003b3d2  jmp     short loc_18003B3D7
0x18003b3d4  mov     rcx, rsi; szProduct
0x18003b3d7  call    cs:__imp_MsiQueryProductStateW
0x18003b3dd  lea     ecx, [rax-1]
0x18003b3e0  cmp     ecx, 2
0x18003b3e3  jbe     short loc_18003B41E
0x18003b3e5  cmp     eax, 5
0x18003b3e8  jz      short loc_18003B41E
0x18003b3ea  cmp     eax, 0FFFFFFFFh
0x18003b3ed  jnz     loc_18003BE40
0x18003b3f3  lea     rdx, byte_1801389F0
0x18003b3fa  lea     rcx, [rbp+310h+Src]
0x18003b3fe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003b403  nop
0x18003b404  lea     rcx, [rdi+258h]
0x18003b40b  lea     rdx, [rbp+310h+Src]
0x18003b40f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003b414  nop
0x18003b415  lea     rcx, [rbp+310h+Src]
0x18003b419  jmp     loc_18003BE3A
0x18003b41e  lea     rcx, ?ApplicationTypeApplication@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationTypeApplication
0x18003b425  lea     rdx, ?ApplicationTypePlaceholder@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationTypePlaceholder
0x18003b42c  cmp     eax, 1
0x18003b42f  cmovnz  rdx, rcx
0x18003b433  lea     rcx, [rdi+170h]
0x18003b43a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003b43f  mov     dword ptr [rdi+2B8h], 4
0x18003b449  lea     rcx, [rbp+310h+szDatabasePath]
0x18003b44d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003b452  nop
0x18003b453  lea     rdx, szProperty; "LocalPackage"
0x18003b45a  lea     rcx, [rbp+310h+Src]
0x18003b45e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003b463  nop
0x18003b464  mov     ebx, [rdi+2B8h]
0x18003b46a  lea     rdx, [rbp+310h+var_348]
0x18003b46e  mov     rcx, rdi
0x18003b471  call    ?GetFirstUserSid@MsiApplication@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; MsiApplication::GetFirstUserSid(void)
0x18003b476  nop
0x18003b477  lea     rcx, [rbp+310h+szDatabasePath]
0x18003b47b  mov     [rsp+410h+var_3E8], rcx
0x18003b480  lea     rcx, [rbp+310h+Src]
0x18003b484  mov     qword ptr [rsp+410h+var_3F0], rcx; unsigned int
0x18003b489  mov     r9d, ebx
0x18003b48c  mov     r8, rax
0x18003b48f  mov     rdx, rsi
0x18003b492  mov     rcx, rdi
0x18003b495  call    ?GetMsiProductInfo@MsiApplication@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4tagMSIINSTALLCONTEXT@@0AEAV23@@Z; MsiApplication::GetMsiProductInfo(std::wstring const &,std::wstring const &,tagMSIINSTALLCONTEXT,std::wstring const &,std::wstring &)
0x18003b49a  nop
0x18003b49b  lea     rcx, [rbp+310h+var_348]
0x18003b49f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b4a4  nop
0x18003b4a5  lea     rcx, [rbp+310h+Src]
0x18003b4a9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b4ae  cmp     [rbp+310h+var_318], 0
0x18003b4b3  jz      loc_18003BE8B
0x18003b4b9  lea     rcx, [rdi+298h]
0x18003b4c0  lea     rdx, [rbp+310h+szDatabasePath]
0x18003b4c4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003b4c9  lea     rcx, [rdi+258h]
0x18003b4d0  mov     rdx, rsi
0x18003b4d3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003b4d8  lea     rcx, [rdi+150h]
0x18003b4df  lea     rdx, ?ApplicationSourceMsi@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationSourceMsi
0x18003b4e6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003b4eb  mov     [rsp+410h+hDatabase+4], 0
0x18003b4f3  lea     rcx, [rsp+410h+hDatabase+4]
0x18003b4f8  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x18003b4fd  lea     rcx, [rbp+310h+szDatabasePath]
0x18003b501  cmp     [rbp+310h+var_310], 7
0x18003b506  cmova   rcx, [rbp+310h+szDatabasePath]; szDatabasePath
0x18003b50b  mov     r8, rax; phDatabase
0x18003b50e  xor     edx, edx; szPersist
0x18003b510  call    cs:__imp_MsiOpenDatabaseW
0x18003b516  mov     ebx, eax
0x18003b518  lea     rdx, aMsiapplication_3; "MsiApplication::GetMsiApplication"
0x18003b51f  test    eax, eax
0x18003b521  jnz     loc_18003BED5
0x18003b527  lea     rax, [rbp+310h+szDatabasePath]
0x18003b52b  cmp     [rbp+310h+var_310], 7
0x18003b530  cmova   rax, [rbp+310h+szDatabasePath]
0x18003b535  mov     qword ptr [rsp+410h+var_3F0], rax; unsigned int
0x18003b53a  lea     r9, aOpenedMsiDatab; "Opened MSI Database: %ws"
0x18003b541  mov     r8d, 0C6h
0x18003b547  lea     ecx, [rbx+3]
0x18003b54a  call    AslLogCallPrintf
0x18003b54f  mov     [rsp+410h+hView], ebx
0x18003b553  lea     rcx, [rsp+410h+hView]
0x18003b558  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x18003b55d  mov     r8, rax; phView
0x18003b560  lea     rdx, szQuery; "SELECT * from Component"
0x18003b567  mov     ecx, [rsp+410h+hDatabase+4]; hDatabase
0x18003b56b  call    cs:__imp_MsiDatabaseOpenViewW
0x18003b571  mov     ebx, eax
0x18003b573  test    eax, eax
0x18003b575  jnz     loc_18003BF1B
0x18003b57b  xor     edx, edx; hRecord
0x18003b57d  mov     ecx, [rsp+410h+hView]; hView
0x18003b581  call    cs:__imp_MsiViewExecute
0x18003b587  mov     rcx, [rbp+318h]; this
0x18003b58e  test    eax, eax
0x18003b590  jnz     loc_18003BF7F
0x18003b596  mov     [rsp+410h+hRecord], eax
0x18003b59a  lea     rcx, [rsp+410h+hRecord]
0x18003b59f  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x18003b5a4  mov     r8, rax; phRecord
0x18003b5a7  xor     edx, edx; eColumnInfo
0x18003b5a9  mov     ecx, [rsp+410h+hView]; hView
0x18003b5ad  call    cs:__imp_MsiViewGetColumnInfo
0x18003b5b3  mov     rcx, [rbp+318h]; this
0x18003b5ba  test    eax, eax
0x18003b5bc  jnz     loc_18003BF94
0x18003b5c2  mov     ecx, [rsp+410h+hRecord]; hRecord
0x18003b5c6  call    cs:__imp_MsiRecordGetFieldCount
0x18003b5cc  mov     r15d, eax
0x18003b5cf  test    eax, eax
0x18003b5d1  jz      short loc_18003B620
0x18003b5d3  mov     [rsp+410h+pcchValueBuf], 104h
0x18003b5db  inc     ebx
0x18003b5dd  lea     r9, [rsp+410h+pcchValueBuf]; pcchValueBuf
0x18003b5e2  lea     r8, [rbp+310h+szValueBuf]; szValueBuf
0x18003b5e9  mov     edx, ebx; iField
0x18003b5eb  mov     ecx, [rsp+410h+hRecord]; hRecord
0x18003b5ef  call    cs:__imp_MsiRecordGetStringW
0x18003b5f5  mov     rcx, [rbp+318h]; this
0x18003b5fc  test    eax, eax
0x18003b5fe  jnz     loc_18003BE76
0x18003b604  lea     rdx, [rbp+310h+szValueBuf]; String2
0x18003b60b  lea     rcx, aComponentid; "ComponentId"
0x18003b612  call    wcscmp_0
0x18003b617  test    eax, eax
0x18003b619  jz      short loc_18003B620
0x18003b61b  cmp     ebx, r15d
0x18003b61e  jb      short loc_18003B5D3
0x18003b620  lea     rcx, [rbp+310h+var_268]
0x18003b627  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003b62c  nop
0x18003b62d  lea     rdx, aInstalledprodu; "InstalledProductName"
0x18003b634  lea     rcx, [rbp+310h+Src]
0x18003b638  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003b63d  nop
0x18003b63e  mov     ebx, [rdi+2B8h]
0x18003b644  lea     rdx, [rbp+310h+var_348]
0x18003b648  mov     rcx, rdi
0x18003b64b  call    ?GetFirstUserSid@MsiApplication@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; MsiApplication::GetFirstUserSid(void)
0x18003b650  nop
0x18003b651  lea     rcx, [rbp+310h+var_268]
0x18003b658  mov     [rsp+410h+var_3E8], rcx
0x18003b65d  lea     rcx, [rbp+310h+Src]
0x18003b661  mov     qword ptr [rsp+410h+var_3F0], rcx
0x18003b666  mov     r9d, ebx
0x18003b669  mov     r8, rax
0x18003b66c  mov     rdx, rsi
0x18003b66f  mov     rcx, rdi
0x18003b672  call    ?GetMsiProductInfo@MsiApplication@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4tagMSIINSTALLCONTEXT@@0AEAV23@@Z; MsiApplication::GetMsiProductInfo(std::wstring const &,std::wstring const &,tagMSIINSTALLCONTEXT,std::wstring const &,std::wstring &)
0x18003b677  nop
0x18003b678  lea     rcx, [rbp+310h+var_348]
0x18003b67c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b681  nop
0x18003b682  lea     rcx, [rbp+310h+Src]
0x18003b686  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b68b  lea     rdx, [rbp+310h+var_268]
0x18003b692  lea     rcx, [rbp+310h+Src]
0x18003b696  call    ?TrimSpace2@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::TrimSpace2(std::wstring const &)
0x18003b69b  lea     rcx, [rdi+1D8h]
0x18003b6a2  mov     rdx, rax
0x18003b6a5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003b6aa  lea     rcx, [rbp+310h+Src]
0x18003b6ae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b6b3  lea     rcx, [rbp+310h+var_288]
0x18003b6ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003b6bf  nop
0x18003b6c0  lea     rdx, aPublisher; "Publisher"
0x18003b6c7  lea     rcx, [rbp+310h+Src]
0x18003b6cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003b6d0  nop
0x18003b6d1  mov     ebx, [rdi+2B8h]
0x18003b6d7  lea     rdx, [rbp+310h+var_348]
0x18003b6db  mov     rcx, rdi
0x18003b6de  call    ?GetFirstUserSid@MsiApplication@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; MsiApplication::GetFirstUserSid(void)
0x18003b6e3  nop
0x18003b6e4  lea     rcx, [rbp+310h+var_288]
0x18003b6eb  mov     [rsp+410h+var_3E8], rcx
0x18003b6f0  lea     rcx, [rbp+310h+Src]
0x18003b6f4  mov     qword ptr [rsp+410h+var_3F0], rcx
0x18003b6f9  mov     r9d, ebx
0x18003b6fc  mov     r8, rax
0x18003b6ff  mov     rdx, rsi
0x18003b702  mov     rcx, rdi
0x18003b705  call    ?GetMsiProductInfo@MsiApplication@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4tagMSIINSTALLCONTEXT@@0AEAV23@@Z; MsiApplication::GetMsiProductInfo(std::wstring const &,std::wstring const &,tagMSIINSTALLCONTEXT,std::wstring const &,std::wstring &)
0x18003b70a  nop
0x18003b70b  lea     rcx, [rbp+310h+var_348]
0x18003b70f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b714  nop
0x18003b715  lea     rcx, [rbp+310h+Src]
0x18003b719  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b71e  lea     rdx, [rbp+310h+var_288]
0x18003b725  lea     rcx, [rbp+310h+Src]
0x18003b729  call    ?TrimSpace2@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::TrimSpace2(std::wstring const &)
0x18003b72e  lea     rcx, [rdi+1F8h]
0x18003b735  mov     rdx, rax
0x18003b738  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003b73d  lea     rcx, [rbp+310h+Src]
0x18003b741  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b746  lea     rcx, [rbp+310h+var_2A8]
0x18003b74a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003b74f  nop
0x18003b750  lea     rdx, aVersionstring; "VersionString"
0x18003b757  lea     rcx, [rbp+310h+Src]
0x18003b75b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003b760  nop
0x18003b761  mov     ebx, [rdi+2B8h]
0x18003b767  lea     rdx, [rbp+310h+var_348]
0x18003b76b  mov     rcx, rdi
0x18003b76e  call    ?GetFirstUserSid@MsiApplication@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; MsiApplication::GetFirstUserSid(void)
0x18003b773  nop
0x18003b774  lea     rcx, [rbp+310h+var_2A8]
0x18003b778  mov     [rsp+410h+var_3E8], rcx
0x18003b77d  lea     rcx, [rbp+310h+Src]
0x18003b781  mov     qword ptr [rsp+410h+var_3F0], rcx
0x18003b786  mov     r9d, ebx
0x18003b789  mov     r8, rax
0x18003b78c  mov     rdx, rsi
0x18003b78f  mov     rcx, rdi
0x18003b792  call    ?GetMsiProductInfo@MsiApplication@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4tagMSIINSTALLCONTEXT@@0AEAV23@@Z; MsiApplication::GetMsiProductInfo(std::wstring const &,std::wstring const &,tagMSIINSTALLCONTEXT,std::wstring const &,std::wstring &)
0x18003b797  nop
0x18003b798  lea     rcx, [rbp+310h+var_348]
0x18003b79c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b7a1  nop
0x18003b7a2  lea     rcx, [rbp+310h+Src]
0x18003b7a6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b7ab  lea     rdx, [rbp+310h+var_2A8]
0x18003b7af  lea     rcx, [rbp+310h+Src]
0x18003b7b3  call    ?TrimSpace2@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::TrimSpace2(std::wstring const &)
0x18003b7b8  lea     rcx, [rdi+218h]
0x18003b7bf  mov     rdx, rax
0x18003b7c2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003b7c7  lea     rcx, [rbp+310h+Src]
0x18003b7cb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b7d0  lea     rcx, [rbp+310h+var_2E8]
0x18003b7d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003b7d9  nop
0x18003b7da  lea     rdx, aInstalledlangu; "InstalledLanguage"
0x18003b7e1  lea     rcx, [rbp+310h+Src]
0x18003b7e5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003b7ea  nop
0x18003b7eb  mov     ebx, [rdi+2B8h]
0x18003b7f1  lea     rdx, [rbp+310h+var_348]
0x18003b7f5  mov     rcx, rdi
0x18003b7f8  call    ?GetFirstUserSid@MsiApplication@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; MsiApplication::GetFirstUserSid(void)
0x18003b7fd  nop
0x18003b7fe  lea     rcx, [rbp+310h+var_2E8]
0x18003b802  mov     [rsp+410h+var_3E8], rcx
0x18003b807  lea     rcx, [rbp+310h+Src]
0x18003b80b  mov     qword ptr [rsp+410h+var_3F0], rcx
0x18003b810  mov     r9d, ebx
0x18003b813  mov     r8, rax
0x18003b816  mov     rdx, rsi
0x18003b819  mov     rcx, rdi
0x18003b81c  call    ?GetMsiProductInfo@MsiApplication@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4tagMSIINSTALLCONTEXT@@0AEAV23@@Z; MsiApplication::GetMsiProductInfo(std::wstring const &,std::wstring const &,tagMSIINSTALLCONTEXT,std::wstring const &,std::wstring &)
0x18003b821  nop
0x18003b822  lea     rcx, [rbp+310h+var_348]
0x18003b826  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b82b  nop
0x18003b82c  lea     rcx, [rbp+310h+Src]
0x18003b830  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b835  cmp     [rbp+310h+var_2D8], 0
0x18003b83a  jnz     short loc_18003B897
0x18003b83c  lea     rdx, aLanguage; "Language"
0x18003b843  lea     rcx, [rbp+310h+Src]
0x18003b847  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003b84c  nop
0x18003b84d  mov     ebx, [rdi+2B8h]
  ... truncated ...
```
