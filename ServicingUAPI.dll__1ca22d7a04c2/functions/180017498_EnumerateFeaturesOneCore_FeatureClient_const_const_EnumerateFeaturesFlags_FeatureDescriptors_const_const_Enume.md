# EnumerateFeaturesOneCore(FeatureClient const * const,EnumerateFeaturesFlags,FeatureDescriptors const * const,EnumerateFeaturesResult * const)

- ea: `0x180017498`
- end: `0x180017eef`
- name: `?EnumerateFeaturesOneCore@@YAXQEBUFeatureClient@@W4EnumerateFeaturesFlags@@QEBUFeatureDescriptors@@QEAUEnumerateFeaturesResult@@@Z`
- size: `2647`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d090`

## callees

- `0x1800031d0`
- `0x180006198`
- `0x1800062b8`
- `0x180009750`
- `0x18000aedc`
- `0x18000c468`
- `0x18000ca2c`
- `0x18000cc98`
- `0x18000ccb8`
- `0x18000f614`
- `0x18000f874`
- `0x1800126b8`
- `0x180012b9c`
- `0x180013908`
- `0x18001662c`
- `0x18001675c`
- `0x180016fcc`
- `0x180017498`
- `0x180017ef8`
- `0x1800190dc`
- `0x18002bc54`
- `0x18002c0d0`
- `0x18002c298`
- `0x18002c7e8`
- `0x18002d49c`
- `0x18002dd20`
- `0x18002dfe0`
- `0x18002ea4c`
- `0x18002fee4`
- `0x180071cf0`
- `0x1801b31e0`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180017b77`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180017bbe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180017b77`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180017bbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017db2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180017693`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800176bd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180017693`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800176bd`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180017da2`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180017da2`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18001797d`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18001797d`

## string_xrefs

- `0x180017604`: `UpdateAPI.dll`
- `0x1800175b2`: `Failed to get current running path`
- `0x18001765b`: `GetRootPath`
- `0x180017685`: `GetTokenInfo`
- `0x1800176b3`: `FreeGetTokenInfoResults`
- `0x180017756`: `\Windows\ImageUpdate\CompDBs`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall EnumerateFeaturesOneCore(__int64 a1, unsigned int a2, _QWORD **a3, _OWORD *a4)
{
  _QWORD **v4; // r13
  unsigned int v5; // esi
  int v7; // r12d
  __int64 v8; // rdx
  __int64 *v9; // r15
  __int64 *v10; // rbx
  __int64 v11; // rdx
  int RunningDllPath; // eax
  HMODULE v13; // rbx
  __int64 v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  __int128 *v16; // rax
  __int64 v17; // rax
  int v18; // eax
  const char *v19; // r9
  const char *v20; // r9
  __int64 v21; // rax
  __int64 v22; // rax
  int TemporaryFileName; // eax
  const wchar_t *v24; // rax
  const wchar_t *v25; // rax
  int AllFilesAndDirectories; // eax
  LPCWSTR v27; // rdi
  LPCWSTR v28; // r14
  const wchar_t *v29; // rcx
  const wchar_t *FileName; // rax
  __int64 v31; // rcx
  __int128 *v32; // rax
  const WCHAR *v33; // rdx
  const WCHAR *v34; // rcx
  const char *v35; // r9
  _QWORD *v36; // rdx
  _QWORD *v37; // rcx
  __int128 *v38; // rax
  int ActionList; // eax
  const wchar_t *v40; // rax
  _QWORD *v41; // rax
  int v42; // eax
  __int64 *v43; // rsi
  __int64 v44; // r12
  void *v45; // r14
  void (__fastcall *v46)(char *); // rdi
  _BYTE *v47; // r13
  _QWORD *v48; // rax
  __int128 *v49; // r14
  void **v50; // r12
  _QWORD *v51; // rdi
  __int64 v52; // rsi
  unsigned int v53; // r15d
  _QWORD *v54; // rdi
  void *v55; // rcx
  _OWORD *v56; // rbx
  int *v58; // [rsp+20h] [rbp-E0h]
  int v59; // [rsp+20h] [rbp-E0h]
  const wchar_t *v60; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v61; // [rsp+78h] [rbp-88h]
  unsigned int v62; // [rsp+80h] [rbp-80h]
  __int128 *v63; // [rsp+88h] [rbp-78h] BYREF
  __int64 v64; // [rsp+90h] [rbp-70h]
  int v65[2]; // [rsp+98h] [rbp-68h] BYREF
  void **p_Block; // [rsp+A0h] [rbp-60h] BYREF
  __int128 *v67; // [rsp+A8h] [rbp-58h]
  HMODULE hModule; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v69; // [rsp+B8h] [rbp-48h]
  _QWORD **v70; // [rsp+C0h] [rbp-40h]
  _OWORD *v71; // [rsp+C8h] [rbp-38h]
  __int64 v72; // [rsp+D0h] [rbp-30h]
  FARPROC ProcAddress; // [rsp+D8h] [rbp-28h] BYREF
  void *Block; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v75; // [rsp+E8h] [rbp-18h]
  __int64 v76; // [rsp+F0h] [rbp-10h]
  __int64 (*v77)(void); // [rsp+F8h] [rbp-8h] BYREF
  __int128 v78; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v79; // [rsp+110h] [rbp+10h]
  unsigned __int64 v80; // [rsp+118h] [rbp+18h]
  __int128 v81; // [rsp+120h] [rbp+20h] BYREF
  __int64 v82; // [rsp+130h] [rbp+30h]
  unsigned __int64 v83; // [rsp+138h] [rbp+38h]
  __int128 v84; // [rsp+140h] [rbp+40h] BYREF
  __int64 v85; // [rsp+150h] [rbp+50h]
  __int128 v86; // [rsp+158h] [rbp+58h] BYREF
  __int64 v87; // [rsp+168h] [rbp+68h]
  LPCWSTR lpTargetFileName[2]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v89; // [rsp+180h] [rbp+80h]
  __int128 v90; // [rsp+188h] [rbp+88h] BYREF
  __int64 v91; // [rsp+198h] [rbp+98h]
  char v92[8]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v93; // [rsp+1A8h] [rbp+A8h]
  __int64 v94; // [rsp+1B0h] [rbp+B0h]
  __int64 *v95; // [rsp+1B8h] [rbp+B8h]
  __int64 v96; // [rsp+1C0h] [rbp+C0h]
  void (__fastcall *v97)(char *); // [rsp+1C8h] [rbp+C8h]
  _QWORD v98[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD v99[4]; // [rsp+1F0h] [rbp+F0h] BYREF
  LPCWSTR lpSymlinkFileName[4]; // [rsp+210h] [rbp+110h] BYREF
  _QWORD v101[4]; // [rsp+230h] [rbp+130h] BYREF
  _QWORD v102[2]; // [rsp+250h] [rbp+150h] BYREF
  __int128 v103; // [rsp+260h] [rbp+160h]
  __int64 v104; // [rsp+270h] [rbp+170h]
  __int64 v105; // [rsp+278h] [rbp+178h]
  __int64 v106; // [rsp+280h] [rbp+180h]
  __int64 v107; // [rsp+288h] [rbp+188h]
  __int128 v108; // [rsp+290h] [rbp+190h]
  __int64 v109; // [rsp+2A0h] [rbp+1A0h]
  __int64 v110; // [rsp+2A8h] [rbp+1A8h]
  _WORD v111[2048]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1308h] [rbp+1208h]

  v72 = -2;
  v71 = a4;
  v4 = a3;
  v70 = a3;
  v5 = a2;
  v62 = a2;
  if ( a4 )
  {
    *a4 = 0;
    a4[1] = 0;
  }
  v90 = 0;
  v91 = 0;
  GetClientPreferredUILanguages(a1, &v90);
  v7 = *(_DWORD *)(a1 + 160);
  v86 = 0;
  v87 = 0;
  v8 = 1024;
  v9 = (__int64 *)(v4 + 1);
  v10 = (__int64 *)(v4 + 1);
  if ( v4 && (unsigned __int64)*v9 > 0x400 )
    v8 = *v9;
  std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>>::reserve(
    &v86,
    v8);
  v84 = 0;
  v85 = 0;
  if ( v4 && (unsigned __int64)*v10 > 1 )
    v11 = *v10;
  else
    v11 = 1;
  std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>>::reserve(
    &v84,
    v11);
  hModule = 0;
  v77 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 7;
  LOWORD(v81) = 0;
  RunningDllPath = GetRunningDllPath(&v81);
  LODWORD(v13) = RunningDllPath;
  if ( RunningDllPath < 0 )
  {
    LODWORD(ProcAddress) = RunningDllPath;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get current running path");
      *(_QWORD *)v65 = &ProcAddress;
      v58 = v65;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v14,
        3,
        ": {}");
    }
  }
  v15 = retaddr;
  if ( (int)v13 < 0 )
LABEL_96:
    wil::details::in1diag3::Throw_Hr(
      v15,
      (void *)0x2B2,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
      (const char *)(unsigned int)v13,
      (int)v58);
  v60 = L"UpdateAPI.dll";
  v61 = 13;
  v16 = &v81;
  if ( v83 > 7 )
    v16 = (__int128 *)v81;
  v63 = v16;
  v64 = v82;
  v17 = CreatePath(v98, &v63, &v60);
  if ( *(_QWORD *)(v17 + 24) > 7u )
    v17 = *(_QWORD *)v17;
  v18 = LoadLibraryAndFunction((const wchar_t *const)v17, "GetRootPath", &hModule, &v77);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B9,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
      (const char *)(unsigned int)v18,
      (int)v58);
  std::wstring::~wstring(v98);
  v13 = hModule;
  ProcAddress = GetProcAddress(hModule, "GetTokenInfo");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2BD,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
      v19);
  *(_QWORD *)v65 = GetProcAddress(v13, "FreeGetTokenInfoResults");
  if ( !*(_QWORD *)v65 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2C1,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
      v20);
  v76 = 0;
  v102[1] = 17;
  v104 = 0;
  v107 = 0;
  v109 = 0;
  v102[0] = &SessionData::`vftable';
  v103 = 0;
  v105 = 0;
  v106 = 0;
  v108 = 0;
  v110 = 0;
  ((void (__fastcall *)(const wchar_t *, _WORD *, __int64))v77)(L"MAINOS", v111, 2048);
  v60 = L"\\Windows\\ImageUpdate\\CompDBs";
  v61 = 28;
  v63 = (__int128 *)v111;
  v21 = -1;
  do
    ++v21;
  while ( v111[v21] );
  v64 = v21;
  CreatePath(v99, &v63, &v60);
  v60 = L"\\Windows";
  v61 = 8;
  v63 = (__int128 *)v111;
  v22 = -1;
  do
    ++v22;
  while ( v111[v22] );
  v64 = v22;
  CreatePath(v98, &v63, &v60);
  to_wstring(v101, a1 + 8);
  v78 = 0;
  v79 = 0;
  v80 = 7;
  LOWORD(v78) = 0;
  v60 = 0;
  v61 = 0;
  TemporaryFileName = GetTemporaryFileName(&v60, &v78);
  if ( TemporaryFileName < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D4,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
      (const char *)(unsigned int)TemporaryFileName,
      (int)v58);
  v24 = (const wchar_t *)&v78;
  if ( v80 > 7 )
    v24 = (const wchar_t *)v78;
  v60 = v24;
  v61 = v79;
  EnsureDirectoryExistsHr((__int64)&v60);
  LOBYTE(p_Block) = 1;
  v67 = &v78;
  *(_OWORD *)lpTargetFileName = 0;
  v89 = 0;
  wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&v63);
  v25 = (const wchar_t *)v99;
  if ( v99[3] > 7u )
    v25 = (const wchar_t *)v99[0];
  v60 = v25;
  v61 = v99[2];
  AllFilesAndDirectories = GetAllFilesAndDirectories(
                             (unsigned int)&v60,
                             (unsigned int)&v63,
                             0,
                             (unsigned int)lpTargetFileName,
                             0);
  if ( AllFilesAndDirectories < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2DD,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
      (const char *)(unsigned int)AllFilesAndDirectories,
      (int)v58);
  v27 = lpTargetFileName[0];
  v28 = lpTargetFileName[1];
  if ( lpTargetFileName[0] != lpTargetFileName[1] )
  {
    do
    {
      if ( *((_QWORD *)v27 + 3) <= 7u )
        v29 = v27;
      else
        v29 = *(const wchar_t **)v27;
      FileName = GetFileName(v29);
      v60 = FileName;
      v31 = -1;
      do
        ++v31;
      while ( FileName[v31] );
      v61 = v31;
      v32 = &v78;
      if ( v80 > 7 )
        v32 = (__int128 *)v78;
      v63 = v32;
      v64 = v79;
      CreatePath(lpSymlinkFileName, &v63, &v60);
      if ( *((_QWORD *)v27 + 3) <= 7u )
        v33 = v27;
      else
        v33 = *(const WCHAR **)v27;
      v34 = (const WCHAR *)lpSymlinkFileName;
      if ( lpSymlinkFileName[3] > (LPCWSTR)7 )
        v34 = lpSymlinkFileName[0];
      if ( !CreateSymbolicLinkW(v34, v33, 0) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x2E7,
          (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
          v35);
      std::wstring::~wstring(lpSymlinkFileName);
      v27 += 16;
    }
    while ( v27 != v28 );
    v5 = v62;
  }
  if ( v76 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    goto LABEL_96;
  }
  v36 = v101;
  if ( v101[3] > 7u )
    LODWORD(v36) = v101[0];
  if ( (v7 & 1) != 0 )
  {
    v37 = v98;
    if ( v98[3] > 7u )
      LODWORD(v37) = v98[0];
  }
  else
  {
    LODWORD(v37) = 0;
  }
  v38 = &v78;
  if ( v80 > 7 )
    v38 = (__int128 *)v78;
  ActionList = CreateActionList((_DWORD)v37, (_DWORD)v36, 0, (unsigned int)v102, (_DWORD)v58, (__int64)v38);
  if ( ActionList < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2FB,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
      (const char *)(unsigned int)ActionList,
      v59);
  std::vector<std::wstring>::_Tidy(lpTargetFileName);
  v40 = (const wchar_t *)&v78;
  if ( v80 > 7 )
    v40 = (const wchar_t *)v78;
  v60 = v40;
  v61 = v79;
  DestroyDirectory(&v60);
  std::wstring::~wstring(&v78);
  std::wstring::~wstring(v101);
  std::wstring::~wstring(v98);
  std::wstring::~wstring(v99);
  v92[0] = 1;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  v97 = *(void (__fastcall **)(char *))v65;
  Block = 0;
  v75 = 0;
  v41 = operator new(0x30u);
  *v41 = v41;
  v41[1] = v41;
  v41[2] = v41;
  *((_WORD *)v41 + 12) = 257;
  Block = v41;
  if ( (v5 & 2) != 0 )
  {
    LOBYTE(v77) = 0;
    HIDWORD(v77) = 1;
    v42 = ((__int64 (__fastcall *)(__int64 (**)(void), char *))ProcAddress)(&v77, v92);
    if ( v42 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30A,
        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
        (const char *)(unsigned int)v42,
        v59);
    v43 = v95;
    v63 = (__int128 *)&v95[v96];
    if ( v95 != (__int64 *)v63 )
    {
      while ( 1 )
      {
        v44 = *v43;
        v45 = Block;
        v46 = (void (__fastcall *)(char *))*((_QWORD *)Block + 1);
        LODWORD(ProcAddress) = 0;
        v69 = 0;
        v47 = Block;
        if ( !*((_BYTE *)v46 + 25) )
        {
          do
          {
            *(_QWORD *)v65 = v46;
            if ( (int)_o__wcsicmp(*((_QWORD *)v46 + 4), *(_QWORD *)(v44 + 16)) >= 0 )
            {
              LODWORD(ProcAddress) = 1;
              v47 = v46;
              v46 = *(void (__fastcall **)(char *))v46;
            }
            else
            {
              LODWORD(ProcAddress) = 0;
              v46 = (void (__fastcall *)(char *))*((_QWORD *)v46 + 2);
            }
          }
          while ( !*((_BYTE *)v46 + 25) );
          v13 = hModule;
          v45 = Block;
          v46 = *(void (__fastcall **)(char *))v65;
        }
        if ( v47[25] )
          goto LABEL_72;
        if ( (int)_o__wcsicmp(*(_QWORD *)(v44 + 16), *((_QWORD *)v47 + 4)) < 0 )
          break;
LABEL_74:
        if ( ++v43 == (__int64 *)v63 )
        {
          v4 = v70;
          goto LABEL_76;
        }
      }
      v45 = Block;
LABEL_72:
      if ( v75 == 0x555555555555555LL )
        std::_Throw_tree_length_error();
      p_Block = &Block;
      v67 = 0;
      v48 = operator new(0x30u);
      v48[4] = *(_QWORD *)(v44 + 16);
      v48[5] = *v43;
      *v48 = v45;
      v48[1] = v45;
      v48[2] = v45;
      *((_WORD *)v48 + 12) = 0;
      v67 = 0;
      v60 = (const wchar_t *)v46;
      v61 = __PAIR64__(v69, (unsigned int)ProcAddress);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ActionList::FeatureAction>>>::_Insert_node(
        &Block,
        &v60,
        v48);
      goto LABEL_74;
    }
LABEL_76:
    v5 = v62;
    if ( !v75 )
    {
      v5 = v62 & 0xFFFFFFFD;
      v62 &= ~2u;
    }
  }
  v49 = (__int128 *)*(unsigned int *)(v76 + 208);
  v50 = *(void ***)(v76 + 200);
  if ( v4 && *v9 )
  {
    v51 = *v4;
    v52 = (__int64)&(*v4)[*v9];
    if ( *v4 != (_QWORD *)v52 )
    {
      v53 = v62;
      do
      {
        p_Block = v50;
        v67 = v49;
        EnumerateMatchingFeatures(
          v53,
          *v51++,
          (unsigned int)&v90,
          (unsigned int)&p_Block,
          (__int64)&Block,
          (__int64)&v86,
          (__int64)&v84);
      }
      while ( v51 != (_QWORD *)v52 );
    }
  }
  else
  {
    p_Block = *(void ***)(v76 + 200);
    v67 = v49;
    EnumerateMatchingFeatures(
      v5,
      0,
      (unsigned int)&v90,
      (unsigned int)&p_Block,
      (__int64)&Block,
      (__int64)&v86,
      (__int64)&v84);
  }
  v54 = (_QWORD *)*((_QWORD *)Block + 1);
  while ( !*((_BYTE *)v54 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<STORE_ID>>::_Erase_tree<std::allocator<std::_Tree_node<STORE_ID,void *>>>(
      &Block,
      &Block,
      v54[2]);
    v55 = v54;
    v54 = (_QWORD *)*v54;
    operator delete(v55);
  }
  operator delete(Block);
  v97(v92);
  if ( v76 )
  {
    (**(void (__fastcall ***)(__int64))v76)(v76);
    v76 = 0;
  }
  std::wstring::~wstring(&v81);
  if ( v13 && !FreeLibrary(v13) )
  {
    GetLastError();
    __fastfail(7u);
  }
  v56 = v71;
  DisownResults<Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>,FeatureResults>(
    &v86,
    v71);
  DisownResults<Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>,FeatureResults>(
    &v84,
    v56 + 1);
  std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>>::~vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>>(&v84);
  std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>>::~vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>>(&v86);
  return std::vector<std::wstring>::_Tidy(&v90);
}

```

## disassembly

```asm
0x180017498  push    rbp
0x18001749a  push    rbx
0x18001749b  push    rsi
0x18001749c  push    rdi
0x18001749d  push    r12
0x18001749f  push    r13
0x1800174a1  push    r14
0x1800174a3  push    r15
0x1800174a5  lea     rbp, [rsp-11C8h]
0x1800174ad  mov     eax, 12C8h
0x1800174b2  call    _alloca_probe
0x1800174b7  sub     rsp, rax
0x1800174ba  mov     [rbp+1200h+var_1230], 0FFFFFFFFFFFFFFFEh
0x1800174c2  mov     rax, cs:__security_cookie
0x1800174c9  xor     rax, rsp
0x1800174cc  mov     [rbp+1200h+var_50], rax
0x1800174d3  mov     [rbp+1200h+var_1238], r9
0x1800174d7  mov     r13, r8
0x1800174da  mov     [rbp+1200h+var_1240], r8
0x1800174de  mov     esi, edx
0x1800174e0  mov     [rbp+1200h+var_1280], edx
0x1800174e3  mov     rdi, rcx
0x1800174e6  xorps   xmm0, xmm0
0x1800174e9  xor     r14d, r14d
0x1800174ec  test    r9, r9
0x1800174ef  jz      short loc_1800174FA
0x1800174f1  movups  xmmword ptr [r9], xmm0
0x1800174f5  movups  xmmword ptr [r9+10h], xmm0
0x1800174fa  movdqu  [rbp+1200h+var_1178], xmm0
0x180017502  mov     [rbp+1200h+var_1168], r14
0x180017509  lea     rdx, [rbp+1200h+var_1178]
0x180017510  call    GetClientPreferredUILanguages
0x180017515  mov     r12d, [rdi+0A0h]
0x18001751c  xorps   xmm0, xmm0
0x18001751f  movdqu  [rbp+1200h+var_11A8], xmm0
0x180017524  mov     [rbp+1200h+var_1198], r14
0x180017528  mov     edx, 400h
0x18001752d  lea     r15, [r13+8]
0x180017531  mov     rbx, r15
0x180017534  test    r13, r13
0x180017537  jz      short loc_180017541
0x180017539  cmp     [r15], rdx
0x18001753c  jbe     short loc_180017541
0x18001753e  mov     rdx, [r15]
0x180017541  lea     rcx, [rbp+1200h+var_11A8]
0x180017545  call    ?reserve@?$vector@V?$AutoNewPtr@V?$AutoGenericHandle@UFeatureResult@@$03$1?CloseWithFreeFeatureResult@@YAXU1@@Z@Windows@@@Windows@@V?$allocator@V?$AutoNewPtr@V?$AutoGenericHandle@UFeatureResult@@$03$1?CloseWithFreeFeatureResult@@YAXU1@@Z@Windows@@@Windows@@@std@@@std@@QEAAX_K@Z; std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResult,4,&CloseWithFreeFeatureResult(FeatureResult)>>>::reserve(unsigned __int64)
0x18001754a  xorps   xmm0, xmm0
0x18001754d  movdqu  [rbp+1200h+var_11C0], xmm0
0x180017552  mov     [rbp+1200h+var_11B0], r14
0x180017556  test    r13, r13
0x180017559  jz      short loc_180017566
0x18001755b  cmp     qword ptr [rbx], 1
0x18001755f  jbe     short loc_180017566
0x180017561  mov     rdx, [rbx]
0x180017564  jmp     short loc_18001756B
0x180017566  mov     edx, 1
0x18001756b  lea     rcx, [rbp+1200h+var_11C0]
0x18001756f  call    ?reserve@?$vector@V?$AutoNewPtr@V?$AutoGenericHandle@UFeatureResult@@$03$1?CloseWithFreeFeatureResult@@YAXU1@@Z@Windows@@@Windows@@V?$allocator@V?$AutoNewPtr@V?$AutoGenericHandle@UFeatureResult@@$03$1?CloseWithFreeFeatureResult@@YAXU1@@Z@Windows@@@Windows@@@std@@@std@@QEAAX_K@Z; std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResult,4,&CloseWithFreeFeatureResult(FeatureResult)>>>::reserve(unsigned __int64)
0x180017574  mov     [rbp+1200h+hModule], r14
0x180017578  mov     [rbp+1200h+var_1208], r14
0x18001757c  xorps   xmm0, xmm0
0x18001757f  movups  [rbp+1200h+var_11E0], xmm0
0x180017583  mov     [rbp+1200h+var_11D0], r14
0x180017587  mov     [rbp+1200h+var_11C8], 7
0x18001758f  mov     word ptr [rbp+1200h+var_11E0], r14w
0x180017594  lea     rcx, [rbp+1200h+var_11E0]
0x180017598  call    ?GetRunningDllPath@@YAJPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; GetRunningDllPath(std::wstring *)
0x18001759d  mov     ebx, eax
0x18001759f  test    eax, eax
0x1800175a1  jns     short loc_1800175F5
0x1800175a3  mov     dword ptr [rbp+1200h+var_1228], eax
0x1800175a6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800175ad  test    rcx, rcx
0x1800175b0  jz      short loc_1800175F5
0x1800175b2  lea     r9, aFailedToGetCur_1; "Failed to get current running path"
0x1800175b9  mov     r14d, 3
0x1800175bf  mov     r8d, r14d
0x1800175c2  xor     edx, edx
0x1800175c4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800175c9  lea     rax, [rbp+1200h+var_1228]
0x1800175cd  mov     qword ptr [rbp+1200h+var_1268], rax
0x1800175d1  lea     rax, [rbp+1200h+var_1268]
0x1800175d5  mov     qword ptr [rsp+1300h+var_12E0], rax; int
0x1800175da  lea     r9, asc_1801CAFB4; ": {}"
0x1800175e1  mov     r8d, r14d
0x1800175e4  mov     dl, 1
0x1800175e6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800175ed  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800175f2  xor     r14d, r14d
0x1800175f5  mov     rcx, [rbp+1208h]
0x1800175fc  test    ebx, ebx
0x1800175fe  js      loc_180017E38
0x180017604  lea     rax, aUpdateapiDll_0; "UpdateAPI.dll"
0x18001760b  mov     [rsp+1300h+var_1290], rax
0x180017610  mov     [rsp+1300h+var_1288], 0Dh
0x180017619  lea     rax, [rbp+1200h+var_11E0]
0x18001761d  cmp     [rbp+1200h+var_11C8], 7
0x180017622  cmova   rax, qword ptr [rbp+1200h+var_11E0]
0x180017627  mov     [rbp+1200h+var_1278], rax
0x18001762b  mov     rax, [rbp+1200h+var_11D0]
0x18001762f  mov     [rbp+1200h+var_1270], rax
0x180017633  lea     r8, [rsp+1300h+var_1290]
0x180017638  lea     rdx, [rbp+1200h+var_1278]
0x18001763c  lea     rcx, [rbp+1200h+var_1130]
0x180017643  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x180017648  nop
0x180017649  cmp     qword ptr [rax+18h], 7
0x18001764e  jbe     short loc_180017653
0x180017650  mov     rax, [rax]
0x180017653  lea     r9, [rbp+1200h+var_1208]; __int64 (**)(void)
0x180017657  lea     r8, [rbp+1200h+hModule]; HINSTANCE *
0x18001765b  lea     rdx, aGetrootpath; "GetRootPath"
0x180017662  mov     rcx, rax; wchar_t *
0x180017665  call    ?LoadLibraryAndFunction@@YAJQEB_WQEBDPEAPEAUHINSTANCE__@@PEAP6A_JXZ@Z; LoadLibraryAndFunction(wchar_t const * const,char const * const,HINSTANCE__ * *,__int64 (**)(void))
0x18001766a  mov     rcx, [rbp+1208h]; this
0x180017671  test    eax, eax
0x180017673  js      loc_180017E4D
0x180017679  lea     rcx, [rbp+1200h+var_1130]; void *
0x180017680  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017685  lea     rdx, aGettokeninfo; "GetTokenInfo"
0x18001768c  mov     rbx, [rbp+1200h+hModule]
0x180017690  mov     rcx, rbx; hModule
0x180017693  call    cs:__imp_GetProcAddress
0x18001769a  nop     dword ptr [rax+rax+00h]
0x18001769f  mov     [rbp+1200h+var_1228], rax
0x1800176a3  mov     rcx, [rbp+1208h]; this
0x1800176aa  test    rax, rax
0x1800176ad  jz      loc_180017E62
0x1800176b3  lea     rdx, aFreegettokenin; "FreeGetTokenInfoResults"
0x1800176ba  mov     rcx, rbx; hModule
0x1800176bd  call    cs:__imp_GetProcAddress
0x1800176c4  nop     dword ptr [rax+rax+00h]
0x1800176c9  mov     qword ptr [rbp+1200h+var_1268], rax
0x1800176cd  mov     rcx, [rbp+1208h]; this
0x1800176d4  test    rax, rax
0x1800176d7  jz      loc_180017E74
0x1800176dd  mov     [rbp+1200h+var_1210], r14
0x1800176e1  mov     [rbp+1200h+var_10A8], 11h
0x1800176ec  xor     eax, eax
0x1800176ee  mov     [rbp+1200h+var_1090], rax
0x1800176f5  mov     [rbp+1200h+var_1078], rax
0x1800176fc  mov     [rbp+1200h+var_1060], rax
0x180017703  lea     rax, ??_7SessionData@@6B@; const SessionData::`vftable'
0x18001770a  mov     [rbp+1200h+var_10B0], rax
0x180017711  xorps   xmm0, xmm0
0x180017714  movdqa  [rbp+1200h+var_10A0], xmm0
0x18001771c  mov     [rbp+1200h+var_1088], r14
0x180017723  mov     [rbp+1200h+var_1080], r14
0x18001772a  movdqa  [rbp+1200h+var_1070], xmm0
0x180017732  mov     [rbp+1200h+var_1058], r14
0x180017739  mov     r8d, 800h
0x18001773f  lea     rdx, [rbp+1200h+var_1050]
0x180017746  lea     rcx, aMainos_1; "MAINOS"
0x18001774d  mov     rax, [rbp+1200h+var_1208]
0x180017751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017756  lea     rax, aWindowsImageup; "\\Windows\\ImageUpdate\\CompDBs"
0x18001775d  mov     [rsp+1300h+var_1290], rax
0x180017762  mov     [rsp+1300h+var_1288], 1Ch
0x18001776b  lea     rax, [rbp+1200h+var_1050]
0x180017772  mov     [rbp+1200h+var_1278], rax
0x180017776  lea     rcx, [rbp+1200h+var_1050]
0x18001777d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017781  inc     rax
0x180017784  cmp     [rcx+rax*2], r14w
0x180017789  jnz     short loc_180017781
0x18001778b  mov     [rbp+1200h+var_1270], rax
0x18001778f  lea     r8, [rsp+1300h+var_1290]
0x180017794  lea     rdx, [rbp+1200h+var_1278]
0x180017798  lea     rcx, [rbp+1200h+var_1110]
0x18001779f  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x1800177a4  nop
0x1800177a5  lea     rax, aWindows; "\\Windows"
0x1800177ac  mov     [rsp+1300h+var_1290], rax
0x1800177b1  mov     [rsp+1300h+var_1288], 8
0x1800177ba  lea     rax, [rbp+1200h+var_1050]
0x1800177c1  mov     [rbp+1200h+var_1278], rax
0x1800177c5  lea     rcx, [rbp+1200h+var_1050]
0x1800177cc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800177d0  inc     rax
0x1800177d3  cmp     [rcx+rax*2], r14w
0x1800177d8  jnz     short loc_1800177D0
0x1800177da  mov     [rbp+1200h+var_1270], rax
0x1800177de  lea     r8, [rsp+1300h+var_1290]
0x1800177e3  lea     rdx, [rbp+1200h+var_1278]
0x1800177e7  lea     rcx, [rbp+1200h+var_1130]
0x1800177ee  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x1800177f3  nop
0x1800177f4  lea     rdx, [rdi+8]
0x1800177f8  lea     rcx, [rbp+1200h+var_10D0]
0x1800177ff  call    ?to_wstring@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBD@Z; to_wstring(char const * const)
0x180017804  nop
0x180017805  xorps   xmm0, xmm0
0x180017808  movups  [rbp+1200h+var_1200], xmm0
0x18001780c  mov     [rbp+1200h+var_11F0], r14
0x180017810  mov     [rbp+1200h+var_11E8], 7
0x180017818  mov     word ptr [rbp+1200h+var_1200], r14w
0x18001781d  mov     [rsp+1300h+var_1290], r14
0x180017822  mov     [rsp+1300h+var_1288], r14
0x180017827  lea     rdx, [rbp+1200h+var_1200]
0x18001782b  lea     rcx, [rsp+1300h+var_1290]
0x180017830  call    ?GetTemporaryFileName@@YAJAEBV?$basic_zstring_view@_W@wil@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; GetTemporaryFileName(wil::basic_zstring_view<wchar_t> const &,std::wstring *)
0x180017835  mov     rcx, [rbp+1208h]; this
0x18001783c  test    eax, eax
0x18001783e  js      loc_180017E86
0x180017844  mov     rcx, [rbp+1200h+var_11F0]
0x180017848  lea     rax, [rbp+1200h+var_1200]
0x18001784c  cmp     [rbp+1200h+var_11E8], 7
0x180017851  cmova   rax, qword ptr [rbp+1200h+var_1200]
0x180017856  mov     [rsp+1300h+var_1290], rax
0x18001785b  mov     [rsp+1300h+var_1288], rcx
0x180017860  lea     rcx, [rsp+1300h+var_1290]
0x180017865  call    ?EnsureDirectoryExistsHr@@YAJAEBV?$basic_zstring_view@_W@wil@@@Z; EnsureDirectoryExistsHr(wil::basic_zstring_view<wchar_t> const &)
0x18001786a  mov     byte ptr [rbp+1200h+var_1260], 1
0x18001786e  lea     rax, [rbp+1200h+var_1200]
0x180017872  mov     [rbp+1200h+var_1258], rax
0x180017876  xorps   xmm0, xmm0
0x180017879  movdqu  xmmword ptr [rbp+1200h+lpTargetFileName], xmm0
0x18001787e  mov     [rbp+1200h+var_1180], r14
0x180017885  lea     rcx, [rbp+1200h+var_1278]
0x180017889  call    ??$?0$01@?$basic_zstring_view@_W@wil@@QEAA@AEAY01$$CB_W@Z; wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(wchar_t const (&)[2])
0x18001788e  mov     rcx, [rbp+1200h+var_1100]
0x180017895  lea     rax, [rbp+1200h+var_1110]
0x18001789c  cmp     [rbp+1200h+var_10F8], 7
0x1800178a4  cmova   rax, [rbp+1200h+var_1110]
0x1800178ac  mov     [rsp+1300h+var_1290], rax
0x1800178b1  mov     [rsp+1300h+var_1288], rcx
0x1800178b6  mov     qword ptr [rsp+1300h+var_12E0], r14; int
0x1800178bb  lea     r9, [rbp+1200h+lpTargetFileName]
0x1800178bf  xor     r8d, r8d
0x1800178c2  lea     rdx, [rbp+1200h+var_1278]
0x1800178c6  lea     rcx, [rsp+1300h+var_1290]
0x1800178cb  call    ?GetAllFilesAndDirectories@@YAJAEBV?$basic_zstring_view@_W@wil@@0HPEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@1@Z; GetAllFilesAndDirectories(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,int,std::vector<std::wstring> *,std::vector<std::wstring> *)
0x1800178d0  mov     rcx, [rbp+1208h]; this
0x1800178d7  test    eax, eax
0x1800178d9  js      loc_180017E9B
0x1800178df  mov     rdi, [rbp+1200h+lpTargetFileName]
0x1800178e3  mov     r14, [rbp+1200h+lpTargetFileName+8]
0x1800178e7  cmp     rdi, r14
0x1800178ea  jz      loc_1800179AD
0x1800178f0  cmp     qword ptr [rdi+18h], 7
0x1800178f5  jbe     short loc_1800178FC
0x1800178f7  mov     rcx, [rdi]
0x1800178fa  jmp     short loc_1800178FF
0x1800178fc  mov     rcx, rdi; FullPath
0x1800178ff  call    ?GetFileName@@YAPEB_WQEB_W@Z; GetFileName(wchar_t const * const)
0x180017904  mov     [rsp+1300h+var_1290], rax
0x180017909  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001790d  xor     edx, edx
0x18001790f  inc     rcx
0x180017912  cmp     [rax+rcx*2], dx
0x180017916  jnz     short loc_18001790F
0x180017918  mov     [rsp+1300h+var_1288], rcx
0x18001791d  lea     rax, [rbp+1200h+var_1200]
0x180017921  cmp     [rbp+1200h+var_11E8], 7
0x180017926  cmova   rax, qword ptr [rbp+1200h+var_1200]
0x18001792b  mov     [rbp+1200h+var_1278], rax
0x18001792f  mov     rax, [rbp+1200h+var_11F0]
0x180017933  mov     [rbp+1200h+var_1270], rax
0x180017937  lea     r8, [rsp+1300h+var_1290]
0x18001793c  lea     rdx, [rbp+1200h+var_1278]
0x180017940  lea     rcx, [rbp+1200h+lpSymlinkFileName]
0x180017947  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x18001794c  nop
0x18001794d  cmp     qword ptr [rdi+18h], 7
0x180017952  jbe     short loc_180017959
0x180017954  mov     rdx, [rdi]
0x180017957  jmp     short loc_18001795C
0x180017959  mov     rdx, rdi; lpTargetFileName
0x18001795c  lea     rcx, [rbp+1200h+lpSymlinkFileName]
0x180017963  cmp     [rbp+1200h+var_10D8], 7
0x18001796b  cmova   rcx, [rbp+1200h+lpSymlinkFileName]; lpSymlinkFileName
0x180017973  mov     rsi, [rbp+1208h]
0x18001797a  xor     r8d, r8d; dwFlags
0x18001797d  call    cs:__imp_CreateSymbolicLinkW
0x180017984  nop     dword ptr [rax+rax+00h]
0x180017989  test    al, al
0x18001798b  jz      loc_180017EB0
0x180017991  lea     rcx, [rbp+1200h+lpSymlinkFileName]; void *
0x180017998  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001799d  add     rdi, 20h ; ' '
0x1800179a1  cmp     rdi, r14
0x1800179a4  jnz     loc_1800178F0
0x1800179aa  mov     esi, [rbp+1200h+var_1280]
0x1800179ad  xor     edi, edi
0x1800179af  cmp     [rbp+1200h+var_1210], rdi
0x1800179b3  jnz     loc_180017E2D
0x1800179b9  lea     rdx, [rbp+1200h+var_10D0]
0x1800179c0  cmp     [rbp+1200h+var_10B8], 7
0x1800179c8  cmova   rdx, [rbp+1200h+var_10D0]
0x1800179d0  test    r12b, 1
0x1800179d4  jz      short loc_1800179EF
0x1800179d6  lea     rcx, [rbp+1200h+var_1130]
0x1800179dd  cmp     [rbp+1200h+var_1118], 7
0x1800179e5  cmova   rcx, [rbp+1200h+var_1130]
0x1800179ed  jmp     short loc_1800179F2
0x1800179ef  mov     rcx, rdi
0x1800179f2  lea     rax, [rbp+1200h+var_1200]
0x1800179f6  cmp     [rbp+1200h+var_11E8], 7
0x1800179fb  cmova   rax, qword ptr [rbp+1200h+var_1200]
0x180017a00  lea     r8, [rbp+1200h+var_1210]
  ... truncated ...
```
