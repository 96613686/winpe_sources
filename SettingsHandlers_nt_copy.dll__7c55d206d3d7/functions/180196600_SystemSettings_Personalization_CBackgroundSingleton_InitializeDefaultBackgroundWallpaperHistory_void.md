# SystemSettings::Personalization::CBackgroundSingleton::InitializeDefaultBackgroundWallpaperHistory(void)

- ea: `0x180196600`
- end: `0x180196cd6`
- name: `?InitializeDefaultBackgroundWallpaperHistory@CBackgroundSingleton@Personalization@SystemSettings@@AEAAJXZ`
- size: `1750`
- prototype: `__int64 __fastcall(SystemSettings::Personalization::CBackgroundSingleton *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180196eb0`

## callees

- `0x18000c840`
- `0x180019a20`
- `0x18001a64c`
- `0x18001ecfc`
- `0x1800234f8`
- `0x18002373c`
- `0x18002395c`
- `0x180027dd8`
- `0x180027e08`
- `0x180027f98`
- `0x18004528c`
- `0x180045a90`
- `0x18004e624`
- `0x18004e954`
- `0x18005016c`
- `0x18005019c`
- `0x18007eb74`
- `0x1801963b4`
- `0x180196600`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180196900`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180196900`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18019699f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18019699f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180196b64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180196c06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180196b64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180196c06`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1801968e0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1801968e0`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180196957`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180196957`
- `SHELL32!SHGetKnownFolderPath` at `0x1801966c3`
- `SHELL32!SHGetKnownFolderPath` at `0x1801966c3`

## string_xrefs

- `0x180196868`: `BackgroundHistoryPath`
- `0x180196a41`: `BackgroundHistoryPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SystemSettings::Personalization::CBackgroundSingleton::InitializeDefaultBackgroundWallpaperHistory(
        SystemSettings::Personalization::CBackgroundSingleton *this)
{
  unsigned __int64 i; // rbx
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // r8
  unsigned int j; // ebx
  int v6; // eax
  unsigned int v7; // edi
  int v8; // r9d
  int v9; // ebx
  int v10; // edi
  unsigned int v11; // ebx
  const unsigned __int16 *v12; // rax
  unsigned __int64 v13; // rbx
  unsigned int k; // esi
  int v15; // r9d
  __int64 v16; // rcx
  __int64 v17; // rdx
  _QWORD *v18; // rax
  __int64 v19; // rdx
  const unsigned __int16 *v20; // rax
  int v21; // eax
  HKEY v22; // rcx
  HKEY v24; // rcx
  void **v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+20h] [rbp-E0h]
  unsigned int *v27; // [rsp+28h] [rbp-D8h]
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v29; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h]
  __int128 v31; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h]
  PWSTR ppszPath; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+78h] [rbp-88h]
  __int128 v36; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+90h] [rbp-70h]
  __int128 v38; // [rsp+98h] [rbp-68h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-58h]
  _BYTE v40[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v41[32]; // [rsp+B8h] [rbp-48h] BYREF
  LPCWSTR pszPath; // [rsp+D8h] [rbp-28h] BYREF
  DWORD cchLength[2]; // [rsp+E0h] [rbp-20h]
  __int64 v44; // [rsp+E8h] [rbp-18h]
  _BYTE v45[40]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 v46[264]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR ValueName[264]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v48[264]; // [rsp+540h] [rbp+440h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7A8h] [rbp+6A8h]

  v29 = 0;
  v30 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  for ( i = 0; i < 0x17; ++i )
  {
    std::wstring::wstring(&pszPath, off_1802C1670[i]);
    std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&v38, &pszPath);
    std::wstring::_Tidy_deallocate(&pszPath);
  }
  ppszPath = 0;
  v34 = 0;
  v35 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
  v34 = -1;
  v35 = -1;
  v2 = SHGetKnownFolderPath(&FOLDERID_Windows, 0x4000u, 0, &ppszPath);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\backgroundsingleton.cpp",
      (const char *)(unsigned int)v2,
      (int)v25);
LABEL_57:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
    std::vector<std::wstring>::_Tidy(&v38);
    std::vector<std::wstring>::_Tidy(&v36);
    std::vector<std::wstring>::_Tidy(&v29);
    return v3;
  }
  std::wstring::wstring(v41, ppszPath);
  std::wstring::append(v41, L"\\Web\\Wallpaper\\Windows");
  if ( *((_QWORD *)&v29 + 1) == v30 )
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v29, *((_QWORD *)&v29 + 1), v41);
  else
    std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(&v29, v41);
  std::wstring::assign(v41, ppszPath);
  std::wstring::append(v41, L"\\Web\\Wallpaper\\ThemeA");
  if ( *((_QWORD *)&v29 + 1) == v30 )
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v29, *((_QWORD *)&v29 + 1), v41);
  else
    std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(&v29, v41);
  std::wstring::assign(v41, ppszPath);
  std::wstring::append(v41, L"\\Web\\Wallpaper\\ThemeB");
  if ( *((_QWORD *)&v29 + 1) == v30 )
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v29, *((_QWORD *)&v29 + 1), v41);
  else
    std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(&v29, v41);
  std::wstring::assign(v41, ppszPath);
  std::wstring::append(v41, L"\\Web\\Wallpaper\\ThemeC");
  if ( *((_QWORD *)&v29 + 1) == v30 )
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v29, *((_QWORD *)&v29 + 1), v41);
  else
    std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(&v29, v41);
  std::wstring::assign(v41, ppszPath);
  std::wstring::append(v41, L"\\Web\\Wallpaper\\ThemeD");
  if ( *((_QWORD *)&v29 + 1) == v30 )
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v29, *((_QWORD *)&v29 + 1), v41);
  else
    std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(&v29, v41);
  SystemSettings::Personalization::GetNumOfImagesFromDirectories(&v29, &v38, v4, &v36);
  v31 = 0;
  v32 = 0;
  for ( j = 0; j < 5; ++j )
  {
    LODWORD(v25) = j;
    v6 = StringCchPrintfW(v46, 0x104u, L"%s%u", L"BackgroundHistoryPath", v25);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B6,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\backgroundsingleton.cpp",
        (const char *)(unsigned int)v6,
        v26);
      std::vector<std::wstring>::_Tidy(&v31);
      std::wstring::_Tidy_deallocate(v41);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
      std::vector<std::wstring>::_Tidy(&v38);
      std::vector<std::wstring>::_Tidy(&v36);
      std::vector<std::wstring>::_Tidy(&v29);
      return v7;
    }
    pszPath = 0;
    *(_QWORD *)cchLength = 0;
    v44 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
    *(_QWORD *)cchLength = -1;
    v44 = -1;
    if ( SHRegAllocData(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers",
           v46,
           v8,
           (void **)&pszPath,
           v27) >= 0
      && PathFileExistsW(pszPath) )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&pszPath);
      CharLowerBuffW((LPWSTR)pszPath, cchLength[0]);
      std::wstring::wstring(v45, pszPath);
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&v31, v45);
      std::wstring::_Tidy_deallocate(v45);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
  }
  phkResult = 0;
  if ( !RegOpenKeyW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers",
          &phkResult) )
  {
    v9 = 0;
    while ( 1 )
    {
      LODWORD(v25) = v9;
      v10 = StringCchPrintfW(ValueName, 0x104u, L"%s%u", L"BackgroundHistoryPath", v25);
      if ( v10 < 0 )
        break;
      RegDeleteValueW(phkResult, ValueName);
      if ( (unsigned int)++v9 >= 5 )
        goto LABEL_30;
    }
    v19 = 459;
    goto LABEL_53;
  }
LABEL_30:
  v11 = 0;
  if ( (__int64)(*((_QWORD *)&v31 + 1) - v31) >> 5 )
  {
    while ( 1 )
    {
      LODWORD(v25) = v11;
      v10 = StringCchPrintfW(v48, 0x104u, L"%s%u", L"BackgroundHistoryPath", v25);
      if ( v10 < 0 )
        break;
      v12 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v31 + 32LL * v11);
      v10 = SHRegSetString(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers",
              v48,
              v12);
      if ( v10 < 0 )
      {
        v19 = 468;
        goto LABEL_53;
      }
      if ( ++v11 >= (unsigned __int64)((__int64)(*((_QWORD *)&v31 + 1) - v31) >> 5) )
        goto LABEL_34;
    }
    v19 = 467;
LABEL_53:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\backgroundsingleton.cpp",
      (const char *)(unsigned int)v10,
      (int)v25);
LABEL_54:
    v24 = phkResult;
    phkResult = 0;
    if ( v24 )
      RegCloseKey(v24);
    std::vector<std::wstring>::_Tidy(&v31);
    std::wstring::_Tidy_deallocate(v41);
    v3 = v10;
    goto LABEL_57;
  }
LABEL_34:
  v13 = 0;
  for ( k = 0; k < 5; ++k )
  {
    LODWORD(v25) = k;
    v10 = StringCchPrintfW(v46, 0x104u, L"%s%u", L"BackgroundHistoryPath", v25);
    if ( v10 < 0 )
    {
      v19 = 476;
      goto LABEL_53;
    }
    pszPath = 0;
    *(_QWORD *)cchLength = 0;
    v44 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
    *(_QWORD *)cchLength = -1;
    v44 = -1;
    if ( SHRegAllocData(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers",
           v46,
           v15,
           (void **)&pszPath,
           v27) < 0 )
    {
      v16 = v36;
      if ( v13 < (__int64)(*((_QWORD *)&v36 + 1) - v36) >> 5 )
      {
        v17 = *((_QWORD *)&v31 + 1);
        while ( 1 )
        {
          v18 = (_QWORD *)std::find<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring>(
                            v40,
                            v31,
                            v17,
                            v16 + 32 * v13);
          v17 = *((_QWORD *)&v31 + 1);
          v16 = v36;
          if ( *v18 == *((_QWORD *)&v31 + 1) )
            break;
          if ( ++v13 >= (__int64)(*((_QWORD *)&v36 + 1) - v36) >> 5 )
            goto LABEL_47;
        }
        v20 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(32 * v13 + v36);
        v21 = SHRegSetString(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers",
                v46,
                v20);
        v10 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1E5,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\backgroundsingleton.cpp",
            (const char *)(unsigned int)v21,
            (int)v25);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
          goto LABEL_54;
        }
        ++v13;
      }
    }
LABEL_47:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
  }
  v22 = phkResult;
  phkResult = 0;
  if ( v22 )
    RegCloseKey(v22);
  std::vector<std::wstring>::_Tidy(&v31);
  std::wstring::_Tidy_deallocate(v41);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
  std::vector<std::wstring>::_Tidy(&v38);
  std::vector<std::wstring>::_Tidy(&v36);
  std::vector<std::wstring>::_Tidy(&v29);
  return 0;
}

```

## disassembly

```asm
0x180196600  push    rbp
0x180196602  push    rbx
0x180196603  push    rsi
0x180196604  push    rdi
0x180196605  push    r12
0x180196607  push    r13
0x180196609  push    r14
0x18019660b  push    r15
0x18019660d  lea     rbp, [rsp-668h]
0x180196615  sub     rsp, 768h
0x18019661c  mov     rax, cs:__security_cookie
0x180196623  xor     rax, rsp
0x180196626  mov     [rbp+6A0h+var_50], rax
0x18019662d  xorps   xmm0, xmm0
0x180196630  movdqu  [rsp+7A0h+var_768], xmm0
0x180196636  xor     r14d, r14d
0x180196639  mov     [rsp+7A0h+var_758], r14
0x18019663e  movdqu  [rbp+6A0h+var_720], xmm0
0x180196643  mov     [rbp+6A0h+var_710], r14
0x180196647  movdqu  [rbp+6A0h+var_708], xmm0
0x18019664c  mov     [rbp+6A0h+var_6F8], r14
0x180196650  mov     ebx, r14d
0x180196653  lea     rdx, off_1802C1670; ".jpg"
0x18019665a  mov     rdx, [rdx+rbx*8]
0x18019665e  lea     rcx, [rbp+6A0h+pszPath]
0x180196662  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180196667  nop
0x180196668  lea     rdx, [rbp+6A0h+pszPath]
0x18019666c  lea     rcx, [rbp+6A0h+var_708]
0x180196670  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x180196675  nop
0x180196676  lea     rcx, [rbp+6A0h+pszPath]
0x18019667a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019667f  inc     rbx
0x180196682  cmp     rbx, 17h
0x180196686  jb      short loc_180196653
0x180196688  mov     [rsp+7A0h+ppszPath], r14
0x18019668d  mov     [rsp+7A0h+var_730], r14
0x180196692  mov     [rsp+7A0h+var_728], r14
0x180196697  lea     rcx, [rsp+7A0h+ppszPath]
0x18019669c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801966a1  or      r15, 0FFFFFFFFFFFFFFFFh
0x1801966a5  mov     [rsp+7A0h+var_730], r15
0x1801966aa  mov     [rsp+7A0h+var_728], r15
0x1801966af  lea     r9, [rsp+7A0h+ppszPath]; ppszPath
0x1801966b4  xor     r8d, r8d; hToken
0x1801966b7  mov     edx, 4000h; dwFlags
0x1801966bc  lea     rcx, FOLDERID_Windows; rfid
0x1801966c3  call    cs:__imp_SHGetKnownFolderPath
0x1801966ca  nop     dword ptr [rax+rax+00h]
0x1801966cf  mov     ebx, eax
0x1801966d1  test    eax, eax
0x1801966d3  jns     short loc_1801966F5
0x1801966d5  mov     rcx, [rbp+6A8h]; this
0x1801966dc  mov     r9d, eax; char *
0x1801966df  lea     r8, aShellSystemset_80; "shell\\systemsettingsthreshold\\handler"...
0x1801966e6  mov     edx, 19Bh; void *
0x1801966eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801966f0  jmp     loc_180196C29
0x1801966f5  mov     rdx, [rsp+7A0h+ppszPath]
0x1801966fa  lea     rcx, [rbp+6A0h+var_6E8]
0x1801966fe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180196703  nop
0x180196704  lea     rdx, aWebWallpaperWi; "\\Web\\Wallpaper\\Windows"
0x18019670b  lea     rcx, [rbp+6A0h+var_6E8]
0x18019670f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180196714  mov     rdx, qword ptr [rsp+7A0h+var_768+8]
0x180196719  lea     rcx, [rsp+7A0h+var_768]
0x18019671e  cmp     rdx, [rsp+7A0h+var_758]
0x180196723  jz      short loc_180196730
0x180196725  lea     rdx, [rbp+6A0h+var_6E8]
0x180196729  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x18019672e  jmp     short loc_180196739
0x180196730  lea     r8, [rbp+6A0h+var_6E8]
0x180196734  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180196739  mov     rdx, [rsp+7A0h+ppszPath]
0x18019673e  lea     rcx, [rbp+6A0h+var_6E8]
0x180196742  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180196747  lea     rdx, aWebWallpaperTh_2; "\\Web\\Wallpaper\\ThemeA"
0x18019674e  lea     rcx, [rbp+6A0h+var_6E8]
0x180196752  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180196757  mov     rdx, qword ptr [rsp+7A0h+var_768+8]
0x18019675c  lea     rcx, [rsp+7A0h+var_768]
0x180196761  cmp     rdx, [rsp+7A0h+var_758]
0x180196766  jz      short loc_180196773
0x180196768  lea     rdx, [rbp+6A0h+var_6E8]
0x18019676c  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x180196771  jmp     short loc_18019677C
0x180196773  lea     r8, [rbp+6A0h+var_6E8]
0x180196777  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18019677c  mov     rdx, [rsp+7A0h+ppszPath]
0x180196781  lea     rcx, [rbp+6A0h+var_6E8]
0x180196785  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18019678a  lea     rdx, aWebWallpaperTh_0; "\\Web\\Wallpaper\\ThemeB"
0x180196791  lea     rcx, [rbp+6A0h+var_6E8]
0x180196795  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18019679a  mov     rdx, qword ptr [rsp+7A0h+var_768+8]
0x18019679f  lea     rcx, [rsp+7A0h+var_768]
0x1801967a4  cmp     rdx, [rsp+7A0h+var_758]
0x1801967a9  jz      short loc_1801967B6
0x1801967ab  lea     rdx, [rbp+6A0h+var_6E8]
0x1801967af  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x1801967b4  jmp     short loc_1801967BF
0x1801967b6  lea     r8, [rbp+6A0h+var_6E8]
0x1801967ba  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x1801967bf  mov     rdx, [rsp+7A0h+ppszPath]
0x1801967c4  lea     rcx, [rbp+6A0h+var_6E8]
0x1801967c8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801967cd  lea     rdx, aWebWallpaperTh_1; "\\Web\\Wallpaper\\ThemeC"
0x1801967d4  lea     rcx, [rbp+6A0h+var_6E8]
0x1801967d8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1801967dd  mov     rdx, qword ptr [rsp+7A0h+var_768+8]
0x1801967e2  lea     rcx, [rsp+7A0h+var_768]
0x1801967e7  cmp     rdx, [rsp+7A0h+var_758]
0x1801967ec  jz      short loc_1801967F9
0x1801967ee  lea     rdx, [rbp+6A0h+var_6E8]
0x1801967f2  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x1801967f7  jmp     short loc_180196802
0x1801967f9  lea     r8, [rbp+6A0h+var_6E8]
0x1801967fd  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180196802  mov     rdx, [rsp+7A0h+ppszPath]
0x180196807  lea     rcx, [rbp+6A0h+var_6E8]
0x18019680b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180196810  lea     rdx, aWebWallpaperTh; "\\Web\\Wallpaper\\ThemeD"
0x180196817  lea     rcx, [rbp+6A0h+var_6E8]
0x18019681b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180196820  mov     rdx, qword ptr [rsp+7A0h+var_768+8]
0x180196825  lea     rcx, [rsp+7A0h+var_768]
0x18019682a  cmp     rdx, [rsp+7A0h+var_758]
0x18019682f  jz      short loc_18019683C
0x180196831  lea     rdx, [rbp+6A0h+var_6E8]
0x180196835  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x18019683a  jmp     short loc_180196845
0x18019683c  lea     r8, [rbp+6A0h+var_6E8]
0x180196840  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180196845  lea     r9, [rbp+6A0h+var_720]
0x180196849  lea     rdx, [rbp+6A0h+var_708]
0x18019684d  lea     rcx, [rsp+7A0h+var_768]
0x180196852  call    ?GetNumOfImagesFromDirectories@Personalization@SystemSettings@@YAXAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0HAEAV34@@Z; SystemSettings::Personalization::GetNumOfImagesFromDirectories(std::vector<std::wstring> const &,std::vector<std::wstring> const &,int,std::vector<std::wstring> &)
0x180196857  xorps   xmm0, xmm0
0x18019685a  movdqu  [rsp+7A0h+var_750], xmm0
0x180196860  mov     [rsp+7A0h+var_740], r14
0x180196865  mov     ebx, r14d
0x180196868  lea     rsi, aBackgroundhist_0; "BackgroundHistoryPath"
0x18019686f  lea     r12, aSoftwareMicros_65; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180196876  mov     r13, 0FFFFFFFF80000001h
0x18019687d  mov     dword ptr [rsp+7A0h+var_780], ebx; int
0x180196881  mov     r9, rsi
0x180196884  lea     r8, aSU_0; "%s%u"
0x18019688b  mov     edx, 104h; unsigned __int64
0x180196890  lea     rcx, [rbp+6A0h+var_680]; unsigned __int16 *
0x180196894  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180196899  mov     edi, eax
0x18019689b  test    eax, eax
0x18019689d  js      loc_180196C56
0x1801968a3  mov     [rbp+6A0h+pszPath], r14
0x1801968a7  mov     qword ptr [rbp+6A0h+cchLength], r14
0x1801968ab  mov     [rbp+6A0h+var_6B8], r14
0x1801968af  lea     rcx, [rbp+6A0h+pszPath]
0x1801968b3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801968b8  mov     qword ptr [rbp+6A0h+cchLength], r15
0x1801968bc  mov     [rbp+6A0h+var_6B8], r15
0x1801968c0  lea     rax, [rbp+6A0h+pszPath]
0x1801968c4  mov     [rsp+7A0h+var_780], rax; void **
0x1801968c9  lea     r8, [rbp+6A0h+var_680]; unsigned __int16 *
0x1801968cd  mov     rdx, r12; unsigned __int16 *
0x1801968d0  mov     rcx, r13; HKEY
0x1801968d3  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1801968d8  test    eax, eax
0x1801968da  js      short loc_180196933
0x1801968dc  mov     rcx, [rbp+6A0h+pszPath]; pszPath
0x1801968e0  call    cs:__imp_PathFileExistsW
0x1801968e7  nop     dword ptr [rax+rax+00h]
0x1801968ec  test    eax, eax
0x1801968ee  jz      short loc_180196933
0x1801968f0  lea     rcx, [rbp+6A0h+pszPath]
0x1801968f4  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1801968f9  mov     edx, [rbp+6A0h+cchLength]; cchLength
0x1801968fc  mov     rcx, [rbp+6A0h+pszPath]; lpsz
0x180196900  call    cs:__imp_CharLowerBuffW
0x180196907  nop     dword ptr [rax+rax+00h]
0x18019690c  mov     rdx, [rbp+6A0h+pszPath]
0x180196910  lea     rcx, [rbp+6A0h+var_6A8]
0x180196914  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180196919  nop
0x18019691a  lea     rdx, [rbp+6A0h+var_6A8]
0x18019691e  lea     rcx, [rsp+7A0h+var_750]
0x180196923  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x180196928  nop
0x180196929  lea     rcx, [rbp+6A0h+var_6A8]
0x18019692d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180196932  nop
0x180196933  lea     rcx, [rbp+6A0h+pszPath]
0x180196937  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18019693c  inc     ebx
0x18019693e  cmp     ebx, 5
0x180196941  jb      loc_18019687D
0x180196947  mov     [rsp+7A0h+phkResult], r14
0x18019694c  lea     r8, [rsp+7A0h+phkResult]; phkResult
0x180196951  mov     rdx, r12; lpSubKey
0x180196954  mov     rcx, r13; hKey
0x180196957  call    cs:__imp_RegOpenKeyW
0x18019695e  nop     dword ptr [rax+rax+00h]
0x180196963  test    eax, eax
0x180196965  jnz     short loc_1801969B2
0x180196967  mov     ebx, r14d
0x18019696a  mov     dword ptr [rsp+7A0h+var_780], ebx
0x18019696e  mov     r9, rsi
0x180196971  lea     r8, aSU_0; "%s%u"
0x180196978  mov     edx, 104h; unsigned __int64
0x18019697d  lea     rcx, [rbp+6A0h+ValueName]; unsigned __int16 *
0x180196984  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180196989  mov     edi, eax
0x18019698b  test    eax, eax
0x18019698d  js      loc_180196B00
0x180196993  lea     rdx, [rbp+6A0h+ValueName]; lpValueName
0x18019699a  mov     rcx, [rsp+7A0h+phkResult]; hKey
0x18019699f  call    cs:__imp_RegDeleteValueW
0x1801969a6  nop     dword ptr [rax+rax+00h]
0x1801969ab  inc     ebx
0x1801969ad  cmp     ebx, 5
0x1801969b0  jb      short loc_18019696A
0x1801969b2  mov     ebx, r14d
0x1801969b5  mov     rax, qword ptr [rsp+7A0h+var_750+8]
0x1801969ba  sub     rax, qword ptr [rsp+7A0h+var_750]
0x1801969bf  sar     rax, 5
0x1801969c3  test    rax, rax
0x1801969c6  jz      short loc_180196A37
0x1801969c8  mov     dword ptr [rsp+7A0h+var_780], ebx
0x1801969cc  mov     r9, rsi
0x1801969cf  lea     r8, aSU_0; "%s%u"
0x1801969d6  mov     edx, 104h; unsigned __int64
0x1801969db  lea     rcx, [rbp+6A0h+var_260]; unsigned __int16 *
0x1801969e2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801969e7  mov     edi, eax
0x1801969e9  test    eax, eax
0x1801969eb  js      loc_180196B14
0x1801969f1  mov     ecx, ebx
0x1801969f3  shl     rcx, 5
0x1801969f7  add     rcx, qword ptr [rsp+7A0h+var_750]
0x1801969fc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180196a01  mov     r9, rax; unsigned __int16 *
0x180196a04  lea     r8, [rbp+6A0h+var_260]; unsigned __int16 *
0x180196a0b  mov     rdx, r12; unsigned __int16 *
0x180196a0e  mov     rcx, r13; HKEY
0x180196a11  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180196a16  mov     edi, eax
0x180196a18  test    eax, eax
0x180196a1a  js      loc_180196B0A
0x180196a20  inc     ebx
0x180196a22  mov     rcx, qword ptr [rsp+7A0h+var_750+8]
0x180196a27  sub     rcx, qword ptr [rsp+7A0h+var_750]
0x180196a2c  sar     rcx, 5
0x180196a30  mov     eax, ebx
0x180196a32  cmp     rax, rcx
0x180196a35  jb      short loc_1801969C8
0x180196a37  mov     rbx, r14
0x180196a3a  mov     esi, r14d
0x180196a3d  mov     dword ptr [rsp+7A0h+var_780], esi; int
0x180196a41  lea     r9, aBackgroundhist_0; "BackgroundHistoryPath"
0x180196a48  lea     r8, aSU_0; "%s%u"
0x180196a4f  mov     edx, 104h; unsigned __int64
0x180196a54  lea     rcx, [rbp+6A0h+var_680]; unsigned __int16 *
0x180196a58  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180196a5d  mov     edi, eax
0x180196a5f  test    eax, eax
0x180196a61  js      loc_180196BDC
0x180196a67  mov     [rbp+6A0h+pszPath], r14
0x180196a6b  mov     qword ptr [rbp+6A0h+cchLength], r14
0x180196a6f  mov     [rbp+6A0h+var_6B8], r14
0x180196a73  lea     rcx, [rbp+6A0h+pszPath]
0x180196a77  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180196a7c  mov     qword ptr [rbp+6A0h+cchLength], r15
0x180196a80  mov     [rbp+6A0h+var_6B8], r15
0x180196a84  lea     rax, [rbp+6A0h+pszPath]
0x180196a88  mov     [rsp+7A0h+var_780], rax; int
0x180196a8d  lea     r8, [rbp+6A0h+var_680]; unsigned __int16 *
0x180196a91  mov     rdx, r12; unsigned __int16 *
0x180196a94  mov     rcx, r13; HKEY
0x180196a97  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x180196a9c  test    eax, eax
0x180196a9e  jns     loc_180196B41
0x180196aa4  mov     rax, qword ptr [rbp+6A0h+var_720+8]
0x180196aa8  mov     rcx, qword ptr [rbp+6A0h+var_720]
0x180196aac  sub     rax, rcx
0x180196aaf  sar     rax, 5
0x180196ab3  cmp     rbx, rax
0x180196ab6  jnb     loc_180196B41
0x180196abc  mov     rdx, qword ptr [rsp+7A0h+var_750+8]
0x180196ac1  mov     rdi, rbx
0x180196ac4  shl     rdi, 5
0x180196ac8  lea     r9, [rcx+rdi]
0x180196acc  mov     r8, rdx
0x180196acf  mov     rdx, qword ptr [rsp+7A0h+var_750]
0x180196ad4  lea     rcx, [rbp+6A0h+var_6F0]
0x180196ad8  call    ??$find@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@std@@YA?AV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@0@V10@V10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::find<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring const &)
0x180196add  mov     rdx, qword ptr [rsp+7A0h+var_750+8]
0x180196ae2  mov     rcx, qword ptr [rbp+6A0h+var_720]
0x180196ae6  cmp     [rax], rdx
0x180196ae9  jz      short loc_180196B1E
  ... truncated ...
```
