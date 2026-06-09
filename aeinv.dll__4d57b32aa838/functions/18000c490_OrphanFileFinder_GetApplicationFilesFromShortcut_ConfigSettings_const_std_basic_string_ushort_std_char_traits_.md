# OrphanFileFinder::GetApplicationFilesFromShortcut(ConfigSettings const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>)

- ea: `0x18000c490`
- end: `0x18000d82c`
- name: `?GetApplicationFilesFromShortcut@OrphanFileFinder@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBVConfigSettings@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@V23@@Z`
- size: `5020`
- prototype: `__int64 __fastcall(__int64, struct ConfigSettings *, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `43`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800388dc`

## callees

- `0x18000c490`
- `0x18000d834`
- `0x18000e458`
- `0x18000ea1c`
- `0x1800112bc`
- `0x1800118d0`
- `0x180013640`
- `0x1800161e8`
- `0x1800172bc`
- `0x180018450`
- `0x1800188f4`
- `0x180018a60`
- `0x1800197d4`
- `0x1800260f4`
- `0x18003fb20`
- `0x1800404c4`
- `0x180040500`
- `0x180043598`
- `0x180043ebc`
- `0x180044694`
- `0x180045468`
- `0x180045480`
- `0x1800454e8`
- `0x18004e6b4`
- `0x18004f380`
- `0x18004f820`
- `0x1800503c8`
- `0x180050de8`
- `0x180052f28`
- `0x180053020`
- `0x180053c94`
- `0x180059920`
- `0x180059cd0`
- `0x180059f2c`
- `0x180059f94`
- `0x18005a8bc`
- `0x1800679f8`
- `0x1800f8ca8`
- `0x1800f9c18`
- `0x180106b54`
- `0x180106e48`
- `0x180125400`
- `0x180130010`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x18000cc32`
- `ADVAPI32!RegGetValueW` at `0x18000cc32`
- `KERNEL32!GetFileAttributesW` at `0x18000ca7a`
- `KERNEL32!GetFileAttributesW` at `0x18000ca7a`
- `KERNEL32!LocalFree` at `0x18000ca4b`
- `KERNEL32!LocalFree` at `0x18000ca4b`
- `SHLWAPI!PathIsNetworkPathW` at `0x18000c95a`
- `SHLWAPI!PathIsNetworkPathW` at `0x18000c95a`
- `ole32!PropVariantClear` at `0x18000d384`
- `ole32!PropVariantClear` at `0x18000d384`
- `ole32!CoCreateInstance` at `0x18000c5a9`
- `ole32!CoCreateInstance` at `0x18000c5a9`
- `SHELL32!SHCreateItemFromParsingName` at `0x18000c81c`
- `SHELL32!SHCreateItemFromParsingName` at `0x18000c81c`

## string_xrefs

- `0x18000c7e0`: `   Shortcut path: %ws`
- `0x18000cb05`: `   Shortcut target path (Translated): %ws`
- `0x18000c8ff`: `   Shortcut target path: %ws`
- `0x18000c5be`: `base\appcompat\inventory\software\inv2\lib\orphanfilefinder.cpp`
- `0x18000c605`: `base\appcompat\inventory\software\inv2\lib\orphanfilefinder.cpp`
- `0x18000c6e6`: `base\appcompat\inventory\software\inv2\lib\orphanfilefinder.cpp`
- `0x18000c720`: `base\appcompat\inventory\software\inv2\lib\orphanfilefinder.cpp`
- `0x18000c831`: `base\appcompat\inventory\software\inv2\lib\orphanfilefinder.cpp`
- `0x18000c886`: `base\appcompat\inventory\software\inv2\lib\orphanfilefinder.cpp`
- `0x18000c8e1`: `base\appcompat\inventory\software\inv2\lib\orphanfilefinder.cpp`
- `0x18000cf29`: `base\appcompat\inventory\software\inv2\lib\orphanfilefinder.cpp`
- `0x18000cfc5`: `base\appcompat\inventory\software\inv2\lib\orphanfilefinder.cpp`
- `0x18000d082`: `base\appcompat\inventory\software\inv2\lib\orphanfilefinder.cpp`
- `0x18000cbaf`: `   Darwin Shortcut Target File Path %ws`
- `0x18000cc24`: `Software\Policies\Microsoft\Windows\AppCompat`

## pseudocode

```c
__int64 __fastcall OrphanFileFinder::GetApplicationFilesFromShortcut(
        __int64 a1,
        struct ConfigSettings *a2,
        const WCHAR *a3,
        __int64 a4)
{
  const WCHAR *v4; // r12
  __int64 v5; // rbx
  char v6; // r14
  HRESULT v7; // eax
  __int64 (__fastcall **v8)(LPVOID, GUID *, __int64 *); // rax
  int v9; // eax
  const WCHAR *v10; // rdx
  __int64 (__fastcall **v11)(LPVOID, GUID *, __int64 *); // rax
  int v12; // eax
  int v13; // eax
  __int128 v14; // xmm0
  const WCHAR *v15; // rax
  const WCHAR *v16; // rcx
  HRESULT v17; // eax
  __int64 v18; // rax
  int v19; // eax
  int v20; // eax
  __int64 v21; // r8
  const WCHAR *v22; // rcx
  LPCWSTR *v23; // rax
  char v24; // di
  __int64 *v25; // rcx
  __int64 v26; // rax
  int v27; // ebx
  HLOCAL v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  LPCWSTR *v31; // rax
  __int64 MsiDatabaseForShortcutTargetFile; // rax
  LPCWSTR *v33; // rax
  __int64 v34; // r8
  int *v35; // rax
  __int64 v36; // r8
  int *v37; // rax
  __int64 *v38; // rdi
  int (__fastcall *v39)(__int64 *, _QWORD, void *, HLOCAL *, WCHAR *); // rbx
  __int64 v40; // r8
  int *v41; // rax
  void *v42; // rdi
  __int64 (__fastcall *v43)(void *, __int64, __int64 **); // rbx
  int v44; // eax
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, LPCWSTR *, int *, __int64 *); // rbx
  int *v47; // r8
  LPCWSTR *v48; // rdx
  int v49; // eax
  __int64 v50; // r8
  int *v51; // rax
  int v52; // eax
  __int64 v53; // r8
  struct ConfigSettings *v54; // rdi
  _QWORD *v55; // rdx
  WCHAR *v56; // rax
  char found; // bl
  __int64 v58; // rdi
  __int64 v59; // r14
  __int64 v60; // rbx
  __int64 v61; // rax
  __int64 v62; // rax
  __int128 *v63; // rcx
  WCHAR *v64; // rax
  int v65; // edi
  __int64 v66; // r14
  __int64 v67; // r15
  __int64 v68; // rbx
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 DirectoryFromPath; // rdi
  __int64 v72; // rax
  char v73; // al
  char v74; // di
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rax
  const struct wil::FailureInfo *v83; // r9
  int ppv; // [rsp+20h] [rbp-1938h]
  int ppva; // [rsp+20h] [rbp-1938h]
  WCHAR *ppvb; // [rsp+20h] [rbp-1938h]
  int v87; // [rsp+40h] [rbp-1918h]
  HLOCAL hMem; // [rsp+48h] [rbp-1910h] BYREF
  __int64 *pvData; // [rsp+50h] [rbp-1908h] BYREF
  int v90[2]; // [rsp+58h] [rbp-1900h] BYREF
  int v91; // [rsp+60h] [rbp-18F8h] BYREF
  void *v92; // [rsp+68h] [rbp-18F0h] BYREF
  __int64 v93; // [rsp+70h] [rbp-18E8h] BYREF
  LPVOID v94; // [rsp+78h] [rbp-18E0h] BYREF
  __int64 v95; // [rsp+80h] [rbp-18D8h] BYREF
  PROPVARIANT pvar[2]; // [rsp+88h] [rbp-18D0h] BYREF
  __int64 v97; // [rsp+98h] [rbp-18C0h]
  __int64 v98; // [rsp+A0h] [rbp-18B8h]
  struct ConfigSettings *v99; // [rsp+B0h] [rbp-18A8h]
  const WCHAR *v100; // [rsp+C0h] [rbp-1898h]
  __int64 v101; // [rsp+C8h] [rbp-1890h] BYREF
  __int64 v102; // [rsp+D0h] [rbp-1888h] BYREF
  struct ConfigSettings *v103; // [rsp+D8h] [rbp-1880h]
  __int64 v104; // [rsp+E0h] [rbp-1878h]
  __int64 v105; // [rsp+E8h] [rbp-1870h] BYREF
  char v106; // [rsp+F0h] [rbp-1868h]
  __int64 v107; // [rsp+100h] [rbp-1858h]
  __int64 v108; // [rsp+108h] [rbp-1850h]
  void **v109; // [rsp+110h] [rbp-1848h] BYREF
  __int64 v110; // [rsp+118h] [rbp-1840h] BYREF
  _BYTE v111[40]; // [rsp+130h] [rbp-1828h] BYREF
  __int128 v112; // [rsp+158h] [rbp-1800h]
  __int128 v113; // [rsp+168h] [rbp-17F0h]
  __int128 v114; // [rsp+178h] [rbp-17E0h]
  __int128 v115; // [rsp+188h] [rbp-17D0h]
  __int128 v116; // [rsp+198h] [rbp-17C0h]
  __int128 v117; // [rsp+1A8h] [rbp-17B0h]
  __int128 v118; // [rsp+1B8h] [rbp-17A0h]
  __int128 v119; // [rsp+1C8h] [rbp-1790h]
  __int64 v120; // [rsp+1D8h] [rbp-1780h]
  LPCWSTR pszPath[2]; // [rsp+200h] [rbp-1758h] BYREF
  __int64 v122; // [rsp+210h] [rbp-1748h]
  unsigned __int64 v123; // [rsp+218h] [rbp-1740h]
  __int128 v124; // [rsp+220h] [rbp-1738h] BYREF
  __int128 v125; // [rsp+230h] [rbp-1728h]
  int v126[4]; // [rsp+240h] [rbp-1718h] BYREF
  __int64 v127; // [rsp+250h] [rbp-1708h]
  unsigned __int64 v128; // [rsp+258h] [rbp-1700h]
  __int128 v129; // [rsp+260h] [rbp-16F8h] BYREF
  __int64 v130; // [rsp+270h] [rbp-16E8h]
  unsigned __int64 v131; // [rsp+278h] [rbp-16E0h]
  int v132[4]; // [rsp+280h] [rbp-16D8h] BYREF
  __int64 v133; // [rsp+290h] [rbp-16C8h]
  unsigned __int64 v134; // [rsp+298h] [rbp-16C0h]
  _QWORD v135[4]; // [rsp+2A0h] [rbp-16B8h] BYREF
  _OWORD v136[2]; // [rsp+2C0h] [rbp-1698h] BYREF
  WCHAR FileName[8]; // [rsp+2E0h] [rbp-1678h] BYREF
  __int128 v138; // [rsp+2F0h] [rbp-1668h]
  __int128 v139; // [rsp+300h] [rbp-1658h]
  __int128 v140; // [rsp+310h] [rbp-1648h]
  __int128 v141; // [rsp+320h] [rbp-1638h]
  __int128 v142; // [rsp+330h] [rbp-1628h]
  __int128 v143; // [rsp+340h] [rbp-1618h]
  __int128 v144; // [rsp+350h] [rbp-1608h]
  __int128 v145; // [rsp+360h] [rbp-15F8h]
  __int64 v146; // [rsp+370h] [rbp-15E8h]
  _WORD v147[264]; // [rsp+4F0h] [rbp-1468h] BYREF
  _WORD v148[264]; // [rsp+700h] [rbp-1258h] BYREF
  _BYTE v149[88]; // [rsp+910h] [rbp-1048h] BYREF
  _QWORD v150[89]; // [rsp+968h] [rbp-FF0h] BYREF
  char v151; // [rsp+C35h] [rbp-D23h]
  wil::details::in1diag3 *retaddr; // [rsp+1958h] [rbp+0h]

  v108 = -2;
  v4 = a3;
  v103 = a2;
  v5 = a1;
  v105 = a1;
  v98 = a1;
  v99 = a2;
  v100 = a3;
  v104 = a4;
  v6 = 1;
  v107 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_1801842E0 > *(_DWORD *)(v107 + 4) )
  {
    Init_thread_header(&dword_1801842E0);
    if ( dword_1801842E0 == -1 )
    {
      std::set<std::wstring>::set<std::wstring>(&qword_1801842E8);
      atexit(OrphanFileFinder::GetApplicationFilesFromShortcut_::_2_::_dynamic_atexit_destructor_for__searchedDirectories__);
      Init_thread_footer(&dword_1801842E0);
    }
  }
  std::vector<enum tagMSIINSTALLCONTEXT>::vector<enum tagMSIINSTALLCONTEXT>(v5);
  v87 = 1;
  v94 = 0;
  v7 = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &GUID_000214f9_0000_0000_c000_000000000046, &v94);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\orphanfilefinder.cpp",
      (const char *)(unsigned int)v7,
      ppv);
  v93 = 0;
  v8 = *(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v94;
  v93 = 0;
  v9 = (*v8)(v94, &GUID_0000010b_0000_0000_c000_000000000046, &v93);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\orphanfilefinder.cpp",
      (const char *)(unsigned int)v9,
      ppv);
  if ( *((_QWORD *)v4 + 3) <= 7u )
    v10 = v4;
  else
    v10 = *(const WCHAR **)v4;
  if ( (*(int (__fastcall **)(__int64, const WCHAR *, _QWORD))(*(_QWORD *)v93 + 40LL))(v93, v10, 0) >= 0 )
  {
    v91 = 0;
    v95 = 0;
    v11 = *(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v94;
    v95 = 0;
    v12 = (*v11)(v94, &GUID_45e2b4ae_b1c3_11d0_b92f_00a0c90312e1, &v95);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xD3,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\orphanfilefinder.cpp",
        (const char *)(unsigned int)v12,
        ppv);
    v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v95 + 48LL))(v95, &v91);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xD4,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\orphanfilefinder.cpp",
        (const char *)(unsigned int)v13,
        ppv);
    v14 = 0;
    *(_OWORD *)v126 = 0;
    v127 = 0;
    v128 = 0;
    *(double *)&v14 = std::wstring::_Construct_empty(v126);
    v129 = v14;
    v130 = 0;
    v131 = 0;
    *(double *)&v14 = std::wstring::_Construct_empty(&v129);
    *(_OWORD *)pszPath = v14;
    v122 = 0;
    v123 = 0;
    std::wstring::_Construct_empty(pszPath);
    try
    {
      AslLogCallPrintf(
        3,
        (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
        220,
        (unsigned int)"-------------------------------------------");
      if ( *((_QWORD *)v4 + 3) <= 7u )
        LODWORD(v15) = (_DWORD)v4;
      else
        v15 = *(const WCHAR **)v4;
      ppva = (int)v15;
      AslLogCallPrintf(
        3,
        (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
        221,
        (unsigned int)"   Shortcut path: %ws");
      v92 = 0;
      if ( *((_QWORD *)v4 + 3) <= 7u )
        v16 = v4;
      else
        v16 = *(const WCHAR **)v4;
      v17 = SHCreateItemFromParsingName(v16, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &v92);
      if ( v17 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xE0,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\orphanfilefinder.cpp",
          (const char *)(unsigned int)v17,
          ppva);
      *(_QWORD *)v90 = 0;
      v18 = *(_QWORD *)v92;
      *(_QWORD *)v90 = 0;
      v19 = (*(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *))(v18 + 24))(
              v92,
              0,
              &BHID_SFUIObject,
              &GUID_000214f9_0000_0000_c000_000000000046);
      if ( v19 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xE3,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\orphanfilefinder.cpp",
          (const char *)(unsigned int)v19,
          (int)v90);
      memset_0(FileName, 0, 0x208u);
      v20 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, __int64, _QWORD))(**(_QWORD **)v90 + 24LL))(
              *(_QWORD *)v90,
              FileName,
              260,
              0);
      if ( v20 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xE7,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\orphanfilefinder.cpp",
          (const char *)(unsigned int)v20,
          0);
      ppvb = FileName;
      AslLogCallPrintf(
        3,
        (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
        232,
        (unsigned int)"   Shortcut target path: %ws");
      v21 = -1;
      do
        ++v21;
      while ( FileName[v21] );
      std::wstring::_Assign<unsigned short>(pszPath, FileName);
      v22 = (const WCHAR *)pszPath;
      if ( v123 > 7 )
        v22 = pszPath[0];
      if ( PathIsNetworkPathW(v22) )
      {
        v122 = 0;
        v23 = pszPath;
        if ( v123 > 7 )
          v23 = (LPCWSTR *)pszPath[0];
        *(_WORD *)v23 = 0;
      }
      if ( v122 )
      {
        v24 = 0;
        pvData = 0;
        (***(void (__fastcall ****)(_QWORD, GUID *, __int64 **))v90)(
          *(_QWORD *)v90,
          &GUID_45e2b4ae_b1c3_11d0_b92f_00a0c90312e1,
          &pvData);
        v25 = pvData;
        if ( pvData )
        {
          hMem = 0;
          v26 = *pvData;
          pvar[0] = &hMem;
          pvar[1] = 0;
          LOBYTE(v97) = 1;
          v27 = (*(__int64 (__fastcall **)(__int64 *, __int64, PROPVARIANT *))(v26 + 32))(
                  pvData,
                  2684354571LL,
                  &pvar[1]);
          wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(pvar);
          v28 = hMem;
          if ( v27 >= 0 )
          {
            v29 = *(_QWORD *)&FOLDERID_UsersFiles.Data1 - *((_QWORD *)hMem + 1);
            if ( *(_QWORD *)&FOLDERID_UsersFiles.Data1 == *((_QWORD *)hMem + 1) )
              v29 = *(_QWORD *)FOLDERID_UsersFiles.Data4 - *((_QWORD *)hMem + 2);
            if ( !v29 )
              v24 = 1;
          }
          hMem = 0;
          if ( v28 )
            LocalFree(v28);
          v25 = pvData;
        }
        if ( v25 )
          (*(void (__fastcall **)(__int64 *))(*v25 + 16))(v25);
        if ( v24 || GetFileAttributesW(FileName) == -1 )
        {
          std::wstring::wstring(v135, FileName);
          v30 = Utility::TranslateSystemProfilePathToShortcutsProfile(v136, v135, v4);
          std::wstring::operator=(pszPath, v30);
          std::wstring::~wstring(v136);
          std::wstring::~wstring(v135);
          v31 = pszPath;
          if ( v123 > 7 )
            v31 = (LPCWSTR *)pszPath[0];
          ppvb = (WCHAR *)v31;
          AslLogCallPrintf(
            3,
            (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
            263,
            (unsigned int)"   Shortcut target path (Translated): %ws");
        }
        else
        {
          v6 = 0;
        }
        if ( (v91 & 0x1000) != 0 )
        {
          Utility::GetGuidFromPath(v136, pszPath);
          Utility::GetFileNameFromPath(v135, pszPath);
          MsiDatabaseForShortcutTargetFile = MsiApplication::QueryMsiDatabaseForShortcutTargetFile(
                                               (__int64)&v124,
                                               (__int64)v136,
                                               v135);
          std::wstring::operator=(pszPath, MsiDatabaseForShortcutTargetFile);
          std::wstring::~wstring(&v124);
          v33 = pszPath;
          if ( v123 > 7 )
            v33 = (LPCWSTR *)pszPath[0];
          ppvb = (WCHAR *)v33;
          AslLogCallPrintf(
            3,
            (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
            279,
            (unsigned int)"   Darwin Shortcut Target File Path %ws");
          std::wstring::~wstring(v135);
          std::wstring::~wstring(v136);
        }
        if ( !byte_180183EE0 )
        {
          byte_180183EE0 = 1;
          LODWORD(pvData) = 0;
          LODWORD(hMem) = 4;
          RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Policies\\Microsoft\\Windows\\AppCompat",
            L"DisableWin32AppBackup",
            0x20000018u,
            0,
            &pvData,
            (LPDWORD)&hMem);
          if ( (_DWORD)pvData == 1 )
          {
            byte_1801817F0 = 0;
            AslLogCallPrintf(
              3,
              (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
              303,
              (unsigned int)"Aumid collection disabled by policy");
          }
        }
        if ( byte_1801817F0 )
        {
          wil::com_query<IPropertyStore,wil::com_ptr_t<IShellLinkW,wil::err_exception_policy> &>(&v102, v90);
          *(_OWORD *)pvar = 0;
          v97 = 0;
          if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v102 + 40LL))(
                 v102,
                 &PKEY_AppUserModel_ID,
                 pvar) >= 0
            && (LOWORD(pvar[0]) == 31 || LOWORD(pvar[0]) == 8) )
          {
            v34 = -1;
            do
              ++v34;
            while ( *((_WORD *)pvar[1] + v34) );
            std::wstring::_Assign<unsigned short>(v126, pvar[1]);
            v35 = v126;
            if ( v128 > 7 )
              LODWORD(v35) = v126[0];
            LODWORD(ppvb) = (_DWORD)v35;
            AslLogCallPrintf(
              3,
              (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
              316,
              (unsigned int)"   Shortcut Aumid: %ws");
          }
          *(_OWORD *)v132 = 0;
          v133 = 0;
          v134 = 0;
          std::wstring::_Construct_empty(v132);
          if ( !v127 )
          {
            memset_0(v147, 0, 0x208u);
            (*(void (__fastcall **)(_QWORD, _WORD *, __int64))(**(_QWORD **)v90 + 80LL))(*(_QWORD *)v90, v147, 260);
            v36 = -1;
            do
              ++v36;
            while ( v147[v36] );
            std::wstring::_Assign<unsigned short>(v132, v147);
            v37 = v132;
            if ( v134 > 7 )
              v37 = *(int **)v132;
            ppvb = (WCHAR *)v37;
            AslLogCallPrintf(
              3,
              (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
              326,
              (unsigned int)"   Shortcut target file args: %ws");
            if ( v133 )
              goto LABEL_91;
            if ( !v6 )
            {
              wil::CoCreateInstance<IApplicationResolver,wil::err_exception_policy>(&pvData);
              hMem = 0;
              v38 = pvData;
              v39 = *(int (__fastcall **)(__int64 *, _QWORD, void *, HLOCAL *, WCHAR *))(*pvData + 32);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &hMem,
                0);
              if ( v39(v38, *(_QWORD *)v90, v92, &hMem, ppvb) >= 0 )
              {
                v40 = -1;
                do
                  ++v40;
                while ( *((_WORD *)hMem + v40) );
                std::wstring::_Assign<unsigned short>(v126, hMem);
                v41 = v126;
                if ( v128 > 7 )
                  LODWORD(v41) = v126[0];
                LODWORD(ppvb) = (_DWORD)v41;
                AslLogCallPrintf(
                  3,
                  (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
                  335,
                  (unsigned int)"   Shortcut Aumid (no args): %ws");
              }
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hMem);
              wil::com_ptr_t<IShellLinkDataList,wil::err_exception_policy>::~com_ptr_t<IShellLinkDataList,wil::err_exception_policy>(&pvData);
              if ( v133 )
                goto LABEL_91;
            }
            if ( !v127 || v6 )
            {
LABEL_91:
              pvData = 0;
              v42 = v92;
              v43 = *(__int64 (__fastcall **)(void *, __int64, __int64 **))(*(_QWORD *)v92 + 40LL);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &pvData,
                0);
              v44 = v43(v42, 2147684353LL, &pvData);
              if ( v44 < 0 )
                wil::details::in1diag3::_Throw_Hr(
                  retaddr,
                  (void *)0x155,
                  (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\orphanfilefinder.cpp",
                  (const char *)(unsigned int)v44,
                  (int)ppvb);
              wil::CoCreateInstance<IAppResolverHelpers,wil::err_exception_policy>(&v101);
              hMem = 0;
              v45 = v101;
              v46 = *(__int64 (__fastcall **)(__int64, LPCWSTR *, int *, __int64 *))(*(_QWORD *)v101 + 24LL);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &hMem,
                0);
              v47 = v132;
              if ( v134 > 7 )
                v47 = *(int **)v132;
              v48 = pszPath;
              if ( v123 > 7 )
                v48 = (LPCWSTR *)pszPath[0];
              v49 = v46(v45, v48, v47, pvData);
              if ( v49 < 0 )
                wil::details::in1diag3::_Throw_Hr(
                  retaddr,
                  (void *)0x158,
                  (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\orphanfilefinder.cpp",
                  (const char *)(unsigned int)v49,
                  (int)&hMem);
              v50 = -1;
              do
                ++v50;
              while ( *((_WORD *)hMem + v50) );
              std::wstring::_Assign<unsigned short>(v126, hMem);
              v51 = v126;
              if ( v128 > 7 )
                LODWORD(v51) = v126[0];
              LODWORD(ppvb) = (_DWORD)v51;
              AslLogCallPrintf(
                3,
                (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
                346,
                (unsigned int)"   Shortcut Aumid: %ws");
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hMem);
              wil::com_ptr_t<IShellLinkDataList,wil::err_exception_policy>::~com_ptr_t<IShellLinkDataList,wil::err_exception_policy>(&v101);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pvData);
            }
          }
          v52 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, __int64))(**(_QWORD **)v90 + 64LL))(
                  *(_QWORD *)v90,
                  v148,
                  260);
          if ( v52 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x160,
              (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\orphanfilefinder.cpp",
              (const char *)(unsigned int)v52,
              (int)ppvb);
          memset(v136, 0, sizeof(v136));
          v53 = -1;
          do
            ++v53;
          while ( v148[v53] );
          std::wstring::_Construct<1,unsigned short const *>(v136);
          v54 = v103;
          File::File((File *)v149, v103);
          v55 = v150;
          if ( v150[3] > 7u )
            v55 = (_QWORD *)v150[0];
          std::wstring::assign(&v129, v55, v150[2]);
          if ( !v130 || v151 )
          {
            if ( dword_1801842F8 > *(_DWORD *)(v107 + 4) )
            {
              Init_thread_header(&dword_1801842F8);
              if ( dword_1801842F8 == -1 )
              {
                Application::GetApplicationsFromCache(&qword_180184300, v54);
                atexit(OrphanFileFinder::GetApplicationFilesFromShortcut_::_54_::_dynamic_atexit_destructor_for__cachedApplications__);
                Init_thread_footer(&dword_1801842F8);
              }
            }
            v124 = 0;
            v125 = 0;
            std::wstring::_Construct<1,unsigned short const *>(&v124);
            found = Utility::FoundSubstring(&v124, pszPath);
            std::wstring::~wstring(&v124);
            if ( found )
            {
              Utility::GetFileNameFromPath(&v124, v4);
              AslLogCallPrintf(
                3,
                (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
                364,
                (unsigned int)"   Android shortcut file name: %ws");
              v58 = qword_180184300;
              v59 = qword_180184308;
              while ( v58 != v59 )
              {
                v60 = v58 + 16;
                v61 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v58 + 16) + 8LL))(v58 + 16);
                if ( (unsigned __int8)Utility::FoundSubstring(v61, &v124) )
                {
                  v62 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v58 + 16);
                  std::wstring::operator=(&v129, v62);
                  (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 8LL))(v58 + 16);
                  AslLogCallPrintf(
                    3,
                    (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
                    371,
                    (unsigned int)"   Shortcut Mapped Program Name: %ws");
                  break;
                }
                v58 += 1008;
              }
              v63 = &v124;
LABEL_124:
              std::wstring::~wstring(v63);
            }
            else
            {
              v66 = qword_180184300;
              v67 = qword_180184308;
              while ( v66 != v67 )
              {
                v68 = v66 + 16;
                if ( *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v66 + 16) + 40LL))(v66 + 16) + 16) )
                {
                  v69 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 40LL))(v66 + 16);
                  if ( (unsigned __int8)Utility::FoundSubstring(v69, v136)
                    || (v70 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 40LL))(v66 + 16),
                        (unsigned __int8)Utility::FoundSubstring(v70, v132))
                    || (DirectoryFromPath = Utility::GetDirectoryFromPath(v135, pszPath),
                        v87 |= 2u,
                        v72 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 40LL))(v66 + 16),
                        v73 = Utility::FoundSubstring(v72, DirectoryFromPath),
                        v74 = 0,
                        v73) )
                  {
                    v74 = 1;
                  }
                  if ( (v87 & 2) != 0 )
                  {
                    v87 &= ~2u;
                    std::wstring::~wstring(v135);
                  }
                  if ( v74 )
                  {
                    v75 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 40LL))(v66 + 16);
                    if ( (unsigned __int8)Utility::ShouldScanInstallDirectoryForFiles(v75) )
                    {
                      v76 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v66 + 16);
                      std::wstring::operator=(&v129, v76);
                      (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 8LL))(v66 + 16);
                      AslLogCallPrintf(
                        3,
                        (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
                        391,
                        (unsigned int)"   Shortcut Mapped Program Name: %ws");
                      break;
                    }
                  }
                }
                if ( *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 96LL))(v66 + 16) + 16) )
                {
                  Utility::GetGuidFromPath(v135, pszPath);
                  Utility::GetGuidFromPath(&v124, v132);
                  v77 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 96LL))(v66 + 16);
                  if ( (unsigned __int8)Utility::FoundSubstring(v77, v135)
                    || (v78 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 96LL))(v66 + 16),
                        (unsigned __int8)Utility::FoundSubstring(v78, &v124)) )
                  {
                    v79 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v66 + 16);
                    std::wstring::operator=(&v129, v79);
                    (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 8LL))(v66 + 16);
                    AslLogCallPrintf(
                      3,
                      (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
                      407,
                      (unsigned int)"   Shortcut Mapped Program Name: %ws");
                    std::wstring::~wstring(&v124);
                    v63 = (__int128 *)v135;
                    goto LABEL_124;
                  }
                  std::wstring::~wstring(&v124);
                  std::wstring::~wstring(v135);
                }
                v66 += 1008;
              }
            }
            v64 = (WCHAR *)&v129;
            if ( v131 > 7 )
              v64 = (WCHAR *)v129;
            ppvb = v64;
            AslLogCallPrintf(
              3,
              (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
              414,
              (unsigned int)"   Shortcut Mapped ProgramId: %ws");
          }
          else
          {
            v56 = (WCHAR *)&v129;
            if ( v131 > 7 )
              v56 = (WCHAR *)v129;
            ppvb = v56;
            AslLogCallPrintf(
              3,
              (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
              418,
              (unsigned int)"   Shortcut ProgramId: %ws");
          }
          File::~File((File *)v149);
          std::wstring::~wstring(v136);
          std::wstring::~wstring(v132);
          PropVariantClear(pvar);
          if ( v102 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v102 + 16LL))(v102);
        }
      }
      if ( *(_QWORD *)v90 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v90 + 16LL))(*(_QWORD *)v90);
      if ( v92 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v92 + 16LL))(v92);
      v5 = v105;
      v65 = (int)v103;
    }
    catch ( wil::ResultException v111 )
    {
      memset_0(v149, 0, 0x1000u);
      *(_OWORD *)FileName = *(_OWORD *)&v111[24];
      v138 = v112;
      v139 = v113;
      v140 = v114;
      v141 = v115;
      v142 = v116;
      v143 = v117;
      v144 = v118;
      v145 = v119;
      v146 = v120;
      wil::GetFailureLogString((wil *)v149, (unsigned __int16 *)0x800, (unsigned __int64)FileName, v83);
      AslLogCallPrintf(1, (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut", 428, (unsigned int)"%ws");
      wil::ResultException::~ResultException((wil::ResultException *)v111);
      v5 = v98;
      v65 = (int)v99;
      LODWORD(v4) = (_DWORD)v100;
    }
    catch ( std::exception v109 )
    {
      GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
        433,
        (unsigned int)"Exception: 0x%08x %s");
      v109 = &std::exception::`vftable';
      o___std_exception_destroy_0(&v110);
      v5 = v98;
      v65 = (int)v99;
      LODWORD(v4) = (_DWORD)v100;
    }
    catch ( ... )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
        438,
        (unsigned int)"Exception: [0x%08x]");
      v5 = v98;
      v65 = (int)v99;
      LODWORD(v4) = (_DWORD)v100;
    }
    if ( (v91 & 0x1000) == 0 && v122 )
    {
      Utility::GetDirectoryFromPath(&v124, pszPath);
      if ( (_QWORD)v125 )
      {
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
          &qword_1801842E8,
          &v105,
          &v124);
        if ( v106 )
        {
          if ( (unsigned __int8)Utility::ShouldScanInstallDirectoryForFiles(&v124) )
          {
            v80 = std::vector<std::wstring>::vector<std::wstring>(pvar, v104);
            v81 = OrphanFileFinder::SearchForLooseAppFiles(&v105, &v124, v80, 7, ppvb);
            std::vector<std::wstring>::operator=(v5, v81);
            std::vector<std::wstring>::_Tidy(&v105);
          }
        }
      }
      std::wstring::~wstring(&v124);
    }
    OrphanFileFinder::SaveShortcutToCache(v65, (_DWORD)v4, (unsigned int)pszPath, (unsigned int)v126, (__int64)&v129);
    std::wstring::~wstring(pszPath);
    std::wstring::~wstring(&v129);
    std::wstring::~wstring(v126);
    if ( v95 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
    if ( v93 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
    if ( v94 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v94 + 16LL))(v94);
  }
  else
  {
    AslLogCallPrintf(
      3,
      (unsigned int)"OrphanFileFinder::GetApplicationFilesFromShortcut",
      204,
      (unsigned int)"Failed to load shortcut: %ws");
    if ( v93 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
    if ( v94 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v94 + 16LL))(v94);
  }
  std::vector<std::wstring>::_Tidy(v104);
  return v5;
}

```

## disassembly

```asm
0x18000c490  push    rbx
0x18000c492  push    rsi
0x18000c493  push    rdi
0x18000c494  push    r12
0x18000c496  push    r13
0x18000c498  push    r14
0x18000c49a  push    r15
0x18000c49c  mov     eax, 1920h
0x18000c4a1  call    _alloca_probe
0x18000c4a6  sub     rsp, rax
0x18000c4a9  mov     [rsp+1958h+var_1850], 0FFFFFFFFFFFFFFFEh
0x18000c4b5  mov     rax, cs:__security_cookie
0x18000c4bc  xor     rax, rsp
0x18000c4bf  mov     [rsp+1958h+var_48], rax
0x18000c4c7  mov     r12, r8
0x18000c4ca  mov     [rsp+1958h+var_1880], rdx
0x18000c4d2  mov     rbx, rcx
0x18000c4d5  mov     [rsp+1958h+var_1870], rcx
0x18000c4dd  mov     [rsp+1958h+var_18B8], rcx
0x18000c4e5  mov     [rsp+1958h+var_18A8], rdx
0x18000c4ed  mov     [rsp+1958h+var_1898], r8
0x18000c4f5  mov     [rsp+1958h+var_1878], r9
0x18000c4fd  mov     r14d, 1
0x18000c503  mov     [rsp+1958h+var_1918], r14d
0x18000c508  mov     ecx, cs:_tls_index
0x18000c50e  mov     rax, gs:58h
0x18000c517  mov     edx, 4
0x18000c51c  mov     rax, [rax+rcx*8]
0x18000c520  mov     [rsp+1958h+var_1858], rax
0x18000c528  mov     eax, [rax+rdx]
0x18000c52b  cmp     cs:dword_1801842E0, eax
0x18000c531  jle     short loc_18000C573
0x18000c533  lea     rcx, dword_1801842E0
0x18000c53a  call    _Init_thread_header
0x18000c53f  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000c543  cmp     cs:dword_1801842E0, r15d
0x18000c54a  jnz     short loc_18000C577
0x18000c54c  lea     rcx, qword_1801842E8
0x18000c553  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x18000c558  lea     rcx, _OrphanFileFinder__GetApplicationFilesFromShortcut____2____dynamic_atexit_destructor_for__searchedDirectories__; void (__cdecl *)()
0x18000c55f  call    atexit
0x18000c564  nop
0x18000c565  lea     rcx, dword_1801842E0
0x18000c56c  call    _Init_thread_footer
0x18000c571  jmp     short loc_18000C577
0x18000c573  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000c577  mov     rcx, rbx
0x18000c57a  call    ??0?$vector@W4tagMSIINSTALLCONTEXT@@V?$allocator@W4tagMSIINSTALLCONTEXT@@@std@@@std@@QEAA@XZ; std::vector<tagMSIINSTALLCONTEXT>::vector<tagMSIINSTALLCONTEXT>(void)
0x18000c57f  nop
0x18000c580  mov     [rsp+1958h+var_1918], r14d
0x18000c585  xor     esi, esi
0x18000c587  mov     [rsp+1958h+var_18E0], rsi
0x18000c58c  lea     rax, [rsp+1958h+var_18E0]
0x18000c591  mov     [rsp+1958h+ppv], rax; int
0x18000c596  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046; riid
0x18000c59d  mov     r8d, r14d; dwClsContext
0x18000c5a0  xor     edx, edx; pUnkOuter
0x18000c5a2  lea     rcx, CLSID_ShellLink; rclsid
0x18000c5a9  call    cs:__imp_CoCreateInstance
0x18000c5af  mov     rcx, [rsp+1958h]; this
0x18000c5b7  test    eax, eax
0x18000c5b9  jns     short loc_18000C5D0
0x18000c5bb  mov     r9d, eax; char *
0x18000c5be  lea     r8, aBaseAppcompatI_2; "base\\appcompat\\inventory\\software\\i"...
0x18000c5c5  mov     edx, 0C4h; void *
0x18000c5ca  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c5d0  mov     [rsp+1958h+var_18E8], rsi
0x18000c5d5  mov     rcx, [rsp+1958h+var_18E0]
0x18000c5da  mov     rax, [rcx]
0x18000c5dd  mov     [rsp+1958h+var_18E8], rsi
0x18000c5e2  lea     r8, [rsp+1958h+var_18E8]
0x18000c5e7  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x18000c5ee  mov     rax, [rax]
0x18000c5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5f6  mov     rcx, [rsp+1958h]; this
0x18000c5fe  test    eax, eax
0x18000c600  jns     short loc_18000C617
0x18000c602  mov     r9d, eax; char *
0x18000c605  lea     r8, aBaseAppcompatI_2; "base\\appcompat\\inventory\\software\\i"...
0x18000c60c  mov     edx, 0C8h; void *
0x18000c611  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c617  mov     rcx, [rsp+1958h+var_18E8]
0x18000c61c  mov     rax, [rcx]
0x18000c61f  cmp     qword ptr [r12+18h], 7
0x18000c625  jbe     short loc_18000C62D
0x18000c627  mov     rdx, [r12]
0x18000c62b  jmp     short loc_18000C630
0x18000c62d  mov     rdx, r12
0x18000c630  xor     r8d, r8d
0x18000c633  mov     rax, [rax+28h]
0x18000c637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c63c  test    eax, eax
0x18000c63e  jns     short loc_18000C6A4
0x18000c640  cmp     qword ptr [r12+18h], 7
0x18000c646  jbe     short loc_18000C64C
0x18000c648  mov     r12, [r12]
0x18000c64c  mov     [rsp+1958h+ppv], r12
0x18000c651  lea     r9, aFailedToLoadSh; "Failed to load shortcut: %ws"
0x18000c658  mov     r8d, 0CCh
0x18000c65e  lea     rdx, aOrphanfilefind_3; "OrphanFileFinder::GetApplicationFilesFr"...
0x18000c665  mov     ecx, 3
0x18000c66a  call    AslLogCallPrintf
0x18000c66f  mov     [rsp+1958h+var_1918], esi
0x18000c673  mov     rcx, [rsp+1958h+var_18E8]
0x18000c678  test    rcx, rcx
0x18000c67b  jz      short loc_18000C68A
0x18000c67d  mov     rax, [rcx]
0x18000c680  mov     rax, [rax+10h]
0x18000c684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c689  nop
0x18000c68a  mov     rcx, [rsp+1958h+var_18E0]
0x18000c68f  test    rcx, rcx
0x18000c692  jz      loc_18000D7F9
0x18000c698  mov     rax, [rcx]
0x18000c69b  mov     rax, [rax+10h]
0x18000c69f  jmp     loc_18000D7F3
0x18000c6a4  mov     [rsp+1958h+var_18F8], esi
0x18000c6a8  mov     [rsp+1958h+var_18D8], rsi
0x18000c6b0  mov     rcx, [rsp+1958h+var_18E0]
0x18000c6b5  mov     rax, [rcx]
0x18000c6b8  mov     [rsp+1958h+var_18D8], rsi
0x18000c6c0  lea     r8, [rsp+1958h+var_18D8]
0x18000c6c8  lea     rdx, _GUID_45e2b4ae_b1c3_11d0_b92f_00a0c90312e1
0x18000c6cf  mov     rax, [rax]
0x18000c6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6d7  mov     rcx, [rsp+1958h]; this
0x18000c6df  test    eax, eax
0x18000c6e1  jns     short loc_18000C6F8
0x18000c6e3  mov     r9d, eax; char *
0x18000c6e6  lea     r8, aBaseAppcompatI_2; "base\\appcompat\\inventory\\software\\i"...
0x18000c6ed  mov     edx, 0D3h; void *
0x18000c6f2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c6f8  mov     rcx, [rsp+1958h+var_18D8]
0x18000c700  mov     rax, [rcx]
0x18000c703  lea     rdx, [rsp+1958h+var_18F8]
0x18000c708  mov     rax, [rax+30h]
0x18000c70c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c711  mov     rcx, [rsp+1958h]; this
0x18000c719  test    eax, eax
0x18000c71b  jns     short loc_18000C732
0x18000c71d  mov     r9d, eax; char *
0x18000c720  lea     r8, aBaseAppcompatI_2; "base\\appcompat\\inventory\\software\\i"...
0x18000c727  mov     edx, 0D4h; void *
0x18000c72c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c732  xorps   xmm0, xmm0
0x18000c735  movups  xmmword ptr [rsp+1958h+var_1718], xmm0
0x18000c73d  mov     [rsp+1958h+var_1708], rsi
0x18000c745  mov     [rsp+1958h+var_1700], rsi
0x18000c74d  lea     rcx, [rsp+1958h+var_1718]
0x18000c755  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000c75a  nop
0x18000c75b  movups  [rsp+1958h+var_16F8], xmm0
0x18000c763  mov     [rsp+1958h+var_16E8], rsi
0x18000c76b  mov     [rsp+1958h+var_16E0], rsi
0x18000c773  lea     rcx, [rsp+1958h+var_16F8]
0x18000c77b  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000c780  nop
0x18000c781  movups  xmmword ptr [rsp+1958h+pszPath], xmm0
0x18000c789  mov     [rsp+1958h+var_1748], rsi
0x18000c791  mov     [rsp+1958h+var_1740], rsi
0x18000c799  lea     rcx, [rsp+1958h+pszPath]
0x18000c7a1  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000c7a6  nop
0x18000c7a7  lea     r9, asc_180139D48; "---------------------------------------"...
0x18000c7ae  mov     r8d, 0DCh
0x18000c7b4  lea     r13, aOrphanfilefind_3; "OrphanFileFinder::GetApplicationFilesFr"...
0x18000c7bb  mov     rdx, r13
0x18000c7be  mov     ebx, 3
0x18000c7c3  mov     ecx, ebx
0x18000c7c5  call    AslLogCallPrintf
0x18000c7ca  cmp     qword ptr [r12+18h], 7
0x18000c7d0  jbe     short loc_18000C7D8
0x18000c7d2  mov     rax, [r12]
0x18000c7d6  jmp     short loc_18000C7DB
0x18000c7d8  mov     rax, r12
0x18000c7db  mov     [rsp+1958h+ppv], rax; int
0x18000c7e0  lea     r9, aShortcutPathWs; "   Shortcut path: %ws"
0x18000c7e7  mov     r8d, 0DDh
0x18000c7ed  mov     rdx, r13
0x18000c7f0  mov     ecx, ebx
0x18000c7f2  call    AslLogCallPrintf
0x18000c7f7  nop
0x18000c7f8  mov     [rsp+1958h+var_18F0], rsi
0x18000c7fd  cmp     qword ptr [r12+18h], 7
0x18000c803  jbe     short loc_18000C80B
0x18000c805  mov     rcx, [r12]
0x18000c809  jmp     short loc_18000C80E
0x18000c80b  mov     rcx, r12; pszPath
0x18000c80e  lea     r9, [rsp+1958h+var_18F0]; ppv
0x18000c813  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x18000c81a  xor     edx, edx; pbc
0x18000c81c  call    cs:__imp_SHCreateItemFromParsingName
0x18000c822  mov     rcx, [rsp+1958h]; this
0x18000c82a  test    eax, eax
0x18000c82c  jns     short loc_18000C842
0x18000c82e  mov     r9d, eax; char *
0x18000c831  lea     r8, aBaseAppcompatI_2; "base\\appcompat\\inventory\\software\\i"...
0x18000c838  mov     edx, 0E0h; void *
0x18000c83d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c842  mov     qword ptr [rsp+1958h+var_1900], rsi
0x18000c847  mov     rcx, [rsp+1958h+var_18F0]
0x18000c84c  mov     rax, [rcx]
0x18000c84f  mov     qword ptr [rsp+1958h+var_1900], rsi
0x18000c854  lea     rdx, [rsp+1958h+var_1900]
0x18000c859  mov     [rsp+1958h+ppv], rdx; int
0x18000c85e  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046
0x18000c865  lea     r8, BHID_SFUIObject
0x18000c86c  xor     edx, edx
0x18000c86e  mov     rax, [rax+18h]
0x18000c872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c877  mov     rcx, [rsp+1958h]; this
0x18000c87f  test    eax, eax
0x18000c881  jns     short loc_18000C897
0x18000c883  mov     r9d, eax; char *
0x18000c886  lea     r8, aBaseAppcompatI_2; "base\\appcompat\\inventory\\software\\i"...
0x18000c88d  mov     edx, 0E3h; void *
0x18000c892  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c897  xor     edx, edx; Val
0x18000c899  mov     r8d, 208h; Size
0x18000c89f  lea     rcx, [rsp+1958h+FileName]; void *
0x18000c8a7  call    memset_0
0x18000c8ac  mov     rcx, qword ptr [rsp+1958h+var_1900]
0x18000c8b1  mov     rax, [rcx]
0x18000c8b4  mov     dword ptr [rsp+1958h+ppv], esi; int
0x18000c8b8  xor     r9d, r9d
0x18000c8bb  mov     r8d, 104h
0x18000c8c1  lea     rdx, [rsp+1958h+FileName]
0x18000c8c9  mov     rax, [rax+18h]
0x18000c8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8d2  mov     rcx, [rsp+1958h]; this
0x18000c8da  test    eax, eax
0x18000c8dc  jns     short loc_18000C8F2
0x18000c8de  mov     r9d, eax; char *
0x18000c8e1  lea     r8, aBaseAppcompatI_2; "base\\appcompat\\inventory\\software\\i"...
0x18000c8e8  mov     edx, 0E7h; void *
0x18000c8ed  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000c8f2  lea     rax, [rsp+1958h+FileName]
0x18000c8fa  mov     [rsp+1958h+ppv], rax
0x18000c8ff  lea     r9, aShortcutTarget_1; "   Shortcut target path: %ws"
0x18000c906  mov     r8d, 0E8h
0x18000c90c  mov     rdx, r13
0x18000c90f  mov     ecx, ebx
0x18000c911  call    AslLogCallPrintf
0x18000c916  lea     rax, [rsp+1958h+FileName]
0x18000c91e  mov     r8, r15
0x18000c921  inc     r8
0x18000c924  cmp     [rax+r8*2], si
0x18000c929  jnz     short loc_18000C921
0x18000c92b  lea     rdx, [rsp+1958h+FileName]
0x18000c933  lea     rcx, [rsp+1958h+pszPath]
0x18000c93b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000c940  lea     rcx, [rsp+1958h+pszPath]
0x18000c948  cmp     [rsp+1958h+var_1740], 7
0x18000c951  cmova   rcx, [rsp+1958h+pszPath]; pszPath
0x18000c95a  call    cs:__imp_PathIsNetworkPathW
0x18000c960  test    eax, eax
0x18000c962  jz      short loc_18000C989
0x18000c964  mov     [rsp+1958h+var_1748], rsi
0x18000c96c  lea     rax, [rsp+1958h+pszPath]
0x18000c974  cmp     [rsp+1958h+var_1740], 7
0x18000c97d  cmova   rax, [rsp+1958h+pszPath]
0x18000c986  mov     [rax], si
0x18000c989  cmp     [rsp+1958h+var_1748], rsi
0x18000c991  jz      loc_18000D3A5
0x18000c997  movzx   edi, sil
0x18000c99b  mov     rcx, qword ptr [rsp+1958h+var_1900]
0x18000c9a0  mov     [rsp+1958h+var_1908], rsi
0x18000c9a5  mov     rax, [rcx]
0x18000c9a8  lea     r8, [rsp+1958h+var_1908]
0x18000c9ad  lea     rdx, _GUID_45e2b4ae_b1c3_11d0_b92f_00a0c90312e1
0x18000c9b4  mov     rax, [rax]
0x18000c9b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9bc  nop
0x18000c9bd  mov     rcx, [rsp+1958h+var_1908]
0x18000c9c2  test    rcx, rcx
0x18000c9c5  jz      loc_18000CA5B
0x18000c9cb  mov     [rsp+1958h+hMem], rsi
0x18000c9d0  mov     rax, [rcx]
0x18000c9d3  lea     rdx, [rsp+1958h+hMem]
0x18000c9d8  mov     [rsp+1958h+pvar], rdx
0x18000c9e0  mov     [rsp+1958h+pvar+8], rsi
0x18000c9e8  mov     byte ptr [rsp+1958h+var_18C0], r14b
0x18000c9f0  lea     r8, [rsp+1958h+pvar+8]
0x18000c9f8  mov     edx, 0A000000Bh
0x18000c9fd  mov     rax, [rax+20h]
0x18000ca01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca06  mov     ebx, eax
0x18000ca08  lea     rcx, [rsp+1958h+pvar]
0x18000ca10  call    ??1?$out_param_t@V?$unique_ptr@XU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18000ca15  shr     ebx, 1Fh
0x18000ca18  xor     bl, r14b
0x18000ca1b  mov     rcx, [rsp+1958h+hMem]; hMem
0x18000ca20  jz      short loc_18000CA41
0x18000ca22  mov     rax, qword ptr cs:FOLDERID_UsersFiles.Data1
0x18000ca29  sub     rax, [rcx+8]
0x18000ca2d  jnz     short loc_18000CA3A
0x18000ca2f  mov     rax, qword ptr cs:FOLDERID_UsersFiles.Data4
0x18000ca36  sub     rax, [rcx+10h]
0x18000ca3a  test    rax, rax
0x18000ca3d  cmovz   edi, r14d
  ... truncated ...
```
