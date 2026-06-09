# xgc::GDIFonts::GDIFonts(void)

- ea: `0x18001d1ec`
- end: `0x18001d617`
- name: `??0GDIFonts@xgc@@QEAA@XZ`
- size: `1067`
- prototype: `__int64 __fastcall(xgc::GDIFonts *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800166d8`

## callees

- `0x180008420`
- `0x180008430`
- `0x180008830`
- `0x180008854`
- `0x1800093b8`
- `0x18000d900`
- `0x18000e0f4`
- `0x180011e88`
- `0x18001bcb4`
- `0x18001c3f8`
- `0x18001cf50`
- `0x18001d1ec`
- `0x18001d8c4`
- `0x180022748`
- `0x1800227f0`
- `0x180023034`
- `0x180023060`
- `0x180037278`
- `0x1800372e4`

## import_xrefs

- `SHLWAPI!PathIsRelativeW` at `0x18001d47d`
- `SHLWAPI!PathIsRelativeW` at `0x18001d47d`
- `SHELL32!SHGetKnownFolderPath` at `0x18001d2ec`
- `SHELL32!SHGetKnownFolderPath` at `0x18001d2ec`
- `ADVAPI32!RegEnumValueW` at `0x18001d451`
- `ADVAPI32!RegEnumValueW` at `0x18001d451`
- `ADVAPI32!RegOpenKeyExW` at `0x18001d353`
- `ADVAPI32!RegOpenKeyExW` at `0x18001d353`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001d3c8`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001d3c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
BYTE *__fastcall xgc::GDIFonts::GDIFonts(BYTE *this)
{
  _QWORD *v2; // rax
  WCHAR *v3; // rbx
  __int64 v4; // rax
  WCHAR *v5; // rax
  HRESULT v6; // esi
  _QWORD *v7; // rdi
  PWSTR v8; // rbx
  int v9; // edx
  const char *v10; // r8
  int v11; // r9d
  LSTATUS v12; // esi
  _QWORD *v13; // rdi
  PWSTR v14; // rbx
  const char *v15; // rdx
  xpsrdr *v16; // rcx
  int v17; // r8d
  const char *v18; // rdx
  xpsrdr *v19; // rcx
  int v20; // r8d
  DWORD i; // r15d
  LSTATUS v22; // eax
  const char *v23; // rdx
  xpsrdr *v24; // rcx
  int v25; // r8d
  void **v26; // rdx
  char *v27; // r8
  void **v28; // rdx
  WCHAR *trivial_2; // rax
  const char *v30; // rdx
  xpsrdr *v31; // rcx
  int v32; // r8d
  WCHAR *v33; // rbx
  LPWSTR v34; // rdi
  __int64 v35; // rsi
  __int64 v36; // r14
  __int64 v37; // rax
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-98h] BYREF
  DWORD cValues; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD Type; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchValueName[2]; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  LPWSTR lpValueName; // [rsp+90h] [rbp-70h] BYREF
  WCHAR *v48; // [rsp+98h] [rbp-68h]
  LPBYTE lpData[4]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v50[16]; // [rsp+C8h] [rbp-38h] BYREF
  void *Src[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v52; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v53; // [rsp+F0h] [rbp-10h]
  _BYTE v54[32]; // [rsp+F8h] [rbp-8h] BYREF
  PWSTR ppszPath; // [rsp+118h] [rbp+18h] BYREF
  HKEY *p_hKey; // [rsp+120h] [rbp+20h]

  lpData[3] = this;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  v2 = operator new(0x50u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  *(_QWORD *)this = v2;
  v3 = (WCHAR *)operator new(0x10u);
  ppszPath = v3;
  *(_QWORD *)v3 = 0;
  *((_QWORD *)v3 + 1) = 0;
  v4 = std::_Allocate<16,std::_Default_allocate_traits>(64);
  *(_QWORD *)v4 = v4;
  *(_QWORD *)(v4 + 8) = v4;
  *(_QWORD *)(v4 + 16) = v4;
  *(_WORD *)(v4 + 24) = 257;
  *(_QWORD *)v3 = v4;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  v5 = (WCHAR *)operator new(0x18u);
  ppszPath = v5;
  *(_OWORD *)v5 = 0;
  *((_DWORD *)v5 + 2) = 1;
  *((_DWORD *)v5 + 3) = 1;
  *(_QWORD *)v5 = &std::_Ref_count<std::set<std::wstring>>::`vftable';
  *((_QWORD *)v5 + 2) = v3;
  *((_QWORD *)this + 2) = v3;
  *((_QWORD *)this + 3) = v5;
  *(_QWORD *)cchValueName = 0;
  std::_Temporary_owner<std::set<std::wstring>>::~_Temporary_owner<std::set<std::wstring>>(cchValueName);
  v46 = 0;
  ppszPath = 0;
  p_hKey = (HKEY *)&v46;
  v6 = SHGetKnownFolderPath(&FOLDERID_Fonts, 0, 0, &ppszPath);
  v7 = p_hKey;
  v8 = ppszPath;
  Holder<void *,close_funct<void (*)(void *),&void CoTaskMemFree(void *)>,invalid_const<void *,0>>::reset(p_hKey);
  *v7 = v8;
  if ( v6 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v6, v9, v10, v11);
  std::wstring::wstring(Src, v46);
  std::wstring::append(Src);
  hKey = 0;
  ppszPath = 0;
  p_hKey = &hKey;
  v12 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Fonts",
          0,
          1u,
          (PHKEY)&ppszPath);
  v13 = p_hKey;
  v14 = ppszPath;
  Holder<HKEY__ *,close_funct<long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *)>,invalid_const<HKEY__ *,0>>::reset(p_hKey);
  *v13 = v14;
  if ( v12 )
    xpsrdr::ThrowLogicException(v16, v15, v17);
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  if ( RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0) )
    xpsrdr::ThrowLogicException(v19, v18, v20);
  cbMaxValueLen >>= 1;
  std::vector<unsigned short>::vector<unsigned short>(&lpValueName, cbMaxValueNameLen);
  std::vector<unsigned short>::vector<unsigned short>(lpData, v52 + cbMaxValueLen);
  Type = 0;
  for ( i = 0; i < cValues; ++i )
  {
    cchValueName[0] = cbMaxValueNameLen;
    cbData = 2 * cbMaxValueLen;
    v22 = RegEnumValueW(hKey, i, lpValueName, cchValueName, 0, &Type, lpData[0], &cbData);
    if ( v22 != 234 )
    {
      if ( v22 )
        xpsrdr::ThrowLogicException(v24, v23, v25);
      if ( Type != 1 )
        xpsrdr::ThrowLogicException(v24, v23, v25);
      cbData >>= 1;
      if ( PathIsRelativeW((LPCWSTR)lpData[0]) )
      {
        memmove_0(&lpData[0][2 * (v52 + cbData) - 2LL * cbData], lpData[0], 2LL * cbData);
        v26 = Src;
        if ( v53 > 7 )
          v26 = (void **)Src[0];
        v27 = (char *)v26 + 2 * v52;
        v28 = Src;
        if ( v53 > 7 )
          v28 = (void **)Src[0];
        memmove_0(lpData[0], v28, v27 - (char *)v28);
      }
      trivial_2 = (WCHAR *)_std_find_trivial_2(lpValueName, v48, 0);
      v33 = trivial_2;
      if ( trivial_2 == v48 )
        xpsrdr::ThrowLogicException(v31, v30, v32);
      v34 = lpValueName;
      while ( trivial_2 != lpValueName )
      {
        if ( *(trivial_2 - 1) == 40 )
        {
          v33 = trivial_2 - 2;
          break;
        }
        --trivial_2;
      }
      ppszPath = (PWSTR)0x2000260020LL;
      while ( v34 != v33 )
      {
        if ( (__int64)(((char *)v33 - (char *)v34) & 0xFFFFFFFFFFFFFFFEuLL) < 6 )
          v35 = (__int64)v33;
        else
          v35 = _std_search_2(v34, v33, &ppszPath, 3);
        v36 = *((_QWORD *)this + 2);
        v37 = std::wstring::wstring(v54, v34, v35);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
          v36,
          v50,
          v37);
        std::wstring::_Tidy_deallocate(v54);
        v34 = (LPWSTR)(v35 + 6);
        if ( (WCHAR *)v35 == v33 )
          v34 = (LPWSTR)v35;
      }
    }
  }
  std::vector<unsigned short>::_Tidy(lpData);
  std::vector<unsigned short>::_Tidy(&lpValueName);
  Holder<HKEY__ *,close_funct<long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *)>,invalid_const<HKEY__ *,0>>::reset(&hKey);
  std::wstring::_Tidy_deallocate(Src);
  Holder<void *,close_funct<void (*)(void *),&void CoTaskMemFree(void *)>,invalid_const<void *,0>>::reset(&v46);
  return this;
}

```

## disassembly

```asm
0x18001d1ec  push    rbp
0x18001d1ee  push    rbx
0x18001d1ef  push    rsi
0x18001d1f0  push    rdi
0x18001d1f1  push    r12
0x18001d1f3  push    r13
0x18001d1f5  push    r14
0x18001d1f7  push    r15
0x18001d1f9  lea     rbp, [rsp-38h]
0x18001d1fe  sub     rsp, 138h
0x18001d205  mov     rax, cs:__security_cookie
0x18001d20c  xor     rax, rsp
0x18001d20f  mov     [rbp+70h+var_48], rax
0x18001d213  mov     r12, rcx
0x18001d216  mov     [rbp+70h+var_B0], rcx
0x18001d21a  xor     r13d, r13d
0x18001d21d  mov     [rcx], r13
0x18001d220  mov     [rcx+8], r13
0x18001d224  lea     ecx, [r13+50h]; Size
0x18001d228  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d22d  mov     [rax], rax
0x18001d230  mov     [rax+8], rax
0x18001d234  mov     [rax+10h], rax
0x18001d238  lea     r14d, [r13+1]
0x18001d23c  mov     word ptr [rax+18h], 101h
0x18001d242  mov     [r12], rax
0x18001d246  lea     ecx, [r13+10h]; Size
0x18001d24a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d24f  mov     rbx, rax
0x18001d252  mov     [rbp+70h+ppszPath], rax
0x18001d256  mov     [rax], r13
0x18001d259  mov     [rax+8], r13
0x18001d25d  lea     ecx, [r13+40h]
0x18001d261  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001d266  mov     [rax], rax
0x18001d269  mov     [rax+8], rax
0x18001d26d  mov     [rax+10h], rax
0x18001d271  mov     word ptr [rax+18h], 101h
0x18001d277  mov     [rbx], rax
0x18001d27a  mov     [r12+10h], r13
0x18001d27f  mov     [r12+18h], r13
0x18001d284  mov     qword ptr [rsp+170h+cchValueName], rbx
0x18001d289  lea     ecx, [r13+18h]; Size
0x18001d28d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d292  mov     [rbp+70h+ppszPath], rax
0x18001d296  xorps   xmm0, xmm0
0x18001d299  movups  xmmword ptr [rax], xmm0
0x18001d29c  mov     [rax+8], r14d
0x18001d2a0  mov     [rax+0Ch], r14d
0x18001d2a4  lea     rcx, ??_7?$_Ref_count@V?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@std@@6B@; const std::_Ref_count<std::set<std::wstring>>::`vftable'
0x18001d2ab  mov     [rax], rcx
0x18001d2ae  mov     [rax+10h], rbx
0x18001d2b2  mov     [r12+10h], rbx
0x18001d2b7  mov     [r12+18h], rax
0x18001d2bc  mov     qword ptr [rsp+170h+cchValueName], r13
0x18001d2c1  lea     rcx, [rsp+170h+cchValueName]
0x18001d2c6  call    ??1?$_Temporary_owner@V?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@std@@QEAA@XZ; std::_Temporary_owner<std::set<std::wstring>>::~_Temporary_owner<std::set<std::wstring>>(void)
0x18001d2cb  nop
0x18001d2cc  mov     [rbp+70h+var_E8], r13
0x18001d2d0  mov     [rbp+70h+ppszPath], r13
0x18001d2d4  lea     rax, [rbp+70h+var_E8]
0x18001d2d8  mov     [rbp+70h+var_50], rax
0x18001d2dc  lea     r9, [rbp+70h+ppszPath]; ppszPath
0x18001d2e0  xor     r8d, r8d; hToken
0x18001d2e3  xor     edx, edx; dwFlags
0x18001d2e5  lea     rcx, FOLDERID_Fonts; rfid
0x18001d2ec  call    cs:__imp_SHGetKnownFolderPath
0x18001d2f2  mov     esi, eax
0x18001d2f4  mov     rdi, [rbp+70h+var_50]
0x18001d2f8  mov     rbx, [rbp+70h+ppszPath]
0x18001d2fc  mov     rcx, rdi
0x18001d2ff  call    ?reset@?$Holder@PEAXU?$close_funct@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@@U?$invalid_const@PEAX$0A@@@@@QEAAXXZ; Holder<void *,close_funct<void (*)(void *),&CoTaskMemFree(void *)>,invalid_const<void *,0>>::reset(void)
0x18001d304  mov     [rdi], rbx
0x18001d307  test    esi, esi
0x18001d309  js      loc_18001D5FD
0x18001d30f  mov     rdx, [rbp+70h+var_E8]
0x18001d313  lea     rcx, [rbp+70h+Src]
0x18001d317  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001d31c  nop
0x18001d31d  lea     rcx, [rbp+70h+Src]
0x18001d321  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18001d326  mov     [rbp+70h+hKey], r13
0x18001d32a  mov     [rbp+70h+ppszPath], r13
0x18001d32e  lea     rax, [rbp+70h+hKey]
0x18001d332  mov     [rbp+70h+var_50], rax
0x18001d336  lea     rax, [rbp+70h+ppszPath]
0x18001d33a  mov     [rsp+170h+phkResult], rax; phkResult
0x18001d33f  mov     r9d, r14d; samDesired
0x18001d342  xor     r8d, r8d; ulOptions
0x18001d345  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001d34c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d353  call    cs:__imp_RegOpenKeyExW
0x18001d359  mov     esi, eax
0x18001d35b  mov     rdi, [rbp+70h+var_50]
0x18001d35f  mov     rbx, [rbp+70h+ppszPath]
0x18001d363  mov     rcx, rdi
0x18001d366  call    ?reset@?$Holder@PEAUHKEY__@@U?$close_funct@P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@Z@@U?$invalid_const@PEAUHKEY__@@$0A@@@@@QEAAXXZ; Holder<HKEY__ *,close_funct<long (*)(HKEY__ *),&RegCloseKey(HKEY__ *)>,invalid_const<HKEY__ *,0>>::reset(void)
0x18001d36b  mov     [rdi], rbx
0x18001d36e  test    esi, esi
0x18001d370  jnz     loc_18001D605
0x18001d376  mov     [rsp+170h+cValues], r13d
0x18001d37b  mov     [rsp+170h+cbMaxValueNameLen], r13d
0x18001d380  mov     [rsp+170h+cbMaxValueLen], r13d
0x18001d385  mov     [rsp+170h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18001d38a  mov     [rsp+170h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18001d38f  lea     rax, [rsp+170h+cbMaxValueLen]
0x18001d394  mov     [rsp+170h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18001d399  lea     rax, [rsp+170h+cbMaxValueNameLen]
0x18001d39e  mov     [rsp+170h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18001d3a3  lea     rax, [rsp+170h+cValues]
0x18001d3a8  mov     [rsp+170h+lpcValues], rax; lpcValues
0x18001d3ad  mov     [rsp+170h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18001d3b2  mov     [rsp+170h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18001d3b7  mov     [rsp+170h+phkResult], r13; lpcSubKeys
0x18001d3bc  xor     r9d, r9d; lpReserved
0x18001d3bf  xor     r8d, r8d; lpcchClass
0x18001d3c2  xor     edx, edx; lpClass
0x18001d3c4  mov     rcx, [rbp+70h+hKey]; hKey
0x18001d3c8  call    cs:__imp_RegQueryInfoKeyW
0x18001d3ce  test    eax, eax
0x18001d3d0  jnz     loc_18001D60B
0x18001d3d6  shr     [rsp+170h+cbMaxValueLen], 1
0x18001d3da  mov     edx, [rsp+170h+cbMaxValueNameLen]
0x18001d3de  lea     rcx, [rbp+70h+lpValueName]
0x18001d3e2  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18001d3e7  nop
0x18001d3e8  mov     edx, [rsp+170h+cbMaxValueLen]
0x18001d3ec  add     rdx, [rbp+70h+var_88]
0x18001d3f0  lea     rcx, [rbp+70h+lpData]
0x18001d3f4  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18001d3f9  nop
0x18001d3fa  mov     [rsp+170h+Type], r13d
0x18001d3ff  mov     r15d, r13d
0x18001d402  cmp     [rsp+170h+cValues], r13d
0x18001d407  jbe     loc_18001D59C
0x18001d40d  mov     eax, [rsp+170h+cbMaxValueNameLen]
0x18001d411  mov     [rsp+170h+cchValueName], eax
0x18001d415  mov     eax, [rsp+170h+cbMaxValueLen]
0x18001d419  add     eax, eax
0x18001d41b  mov     [rsp+170h+cbData], eax
0x18001d41f  mov     rax, [rbp+70h+lpData]
0x18001d423  lea     rcx, [rsp+170h+cbData]
0x18001d428  mov     [rsp+170h+lpcValues], rcx; lpcbData
0x18001d42d  mov     [rsp+170h+lpcbMaxClassLen], rax; lpData
0x18001d432  lea     rax, [rsp+170h+Type]
0x18001d437  mov     [rsp+170h+lpcbMaxSubKeyLen], rax; lpType
0x18001d43c  mov     [rsp+170h+phkResult], r13; lpReserved
0x18001d441  lea     r9, [rsp+170h+cchValueName]; lpcchValueName
0x18001d446  mov     r8, [rbp+70h+lpValueName]; lpValueName
0x18001d44a  mov     edx, r15d; dwIndex
0x18001d44d  mov     rcx, [rbp+70h+hKey]; hKey
0x18001d451  call    cs:__imp_RegEnumValueW
0x18001d457  cmp     eax, 0EAh
0x18001d45c  jz      loc_18001D58E
0x18001d462  test    eax, eax
0x18001d464  jnz     loc_18001D5F7
0x18001d46a  cmp     [rsp+170h+Type], r14d
0x18001d46f  jnz     loc_18001D5F1
0x18001d475  shr     [rsp+170h+cbData], 1
0x18001d479  mov     rcx, [rbp+70h+lpData]; pszPath
0x18001d47d  call    cs:__imp_PathIsRelativeW
0x18001d483  test    eax, eax
0x18001d485  jz      short loc_18001D4D6
0x18001d487  mov     ecx, [rsp+170h+cbData]
0x18001d48b  mov     rdx, [rbp+70h+lpData]; Src
0x18001d48f  lea     r8, [rcx+rcx]
0x18001d493  sub     r8, rdx
0x18001d496  add     r8, rdx; Size
0x18001d499  add     rcx, [rbp+70h+var_88]
0x18001d49d  add     rcx, rcx
0x18001d4a0  sub     rcx, r8
0x18001d4a3  add     rcx, rdx; void *
0x18001d4a6  call    memmove_0
0x18001d4ab  lea     rdx, [rbp+70h+Src]
0x18001d4af  cmp     [rbp+70h+var_80], 7
0x18001d4b4  cmova   rdx, [rbp+70h+Src]
0x18001d4b9  mov     rax, [rbp+70h+var_88]
0x18001d4bd  lea     r8, [rdx+rax*2]
0x18001d4c1  lea     rdx, [rbp+70h+Src]
0x18001d4c5  cmova   rdx, [rbp+70h+Src]; Src
0x18001d4ca  sub     r8, rdx; Size
0x18001d4cd  mov     rcx, [rbp+70h+lpData]; void *
0x18001d4d1  call    memmove_0
0x18001d4d6  xor     r8d, r8d
0x18001d4d9  mov     rdx, [rbp+70h+var_D8]
0x18001d4dd  mov     rcx, [rbp+70h+lpValueName]
0x18001d4e1  call    __std_find_trivial_2
0x18001d4e6  mov     rbx, rax
0x18001d4e9  cmp     rax, [rbp+70h+var_D8]
0x18001d4ed  jz      loc_18001D611
0x18001d4f3  mov     rdi, [rbp+70h+lpValueName]
0x18001d4f7  cmp     rax, rdi
0x18001d4fa  jz      short loc_18001D50D
0x18001d4fc  cmp     word ptr [rax-2], 28h ; '('
0x18001d501  jz      short loc_18001D509
0x18001d503  add     rax, 0FFFFFFFFFFFFFFFEh
0x18001d507  jmp     short loc_18001D4F7
0x18001d509  lea     rbx, [rax-4]
0x18001d50d  mov     rax, 2000260020h
0x18001d517  mov     [rbp+70h+ppszPath], rax
0x18001d51b  cmp     rdi, rbx
0x18001d51e  jz      short loc_18001D588
0x18001d520  mov     rax, rbx
0x18001d523  sub     rax, rdi
0x18001d526  and     rax, 0FFFFFFFFFFFFFFFEh
0x18001d52a  cmp     rax, 6
0x18001d52e  jl      short loc_18001D54A
0x18001d530  mov     r9d, 3
0x18001d536  lea     r8, [rbp+70h+ppszPath]
0x18001d53a  mov     rdx, rbx
0x18001d53d  mov     rcx, rdi
0x18001d540  call    __std_search_2
0x18001d545  mov     rsi, rax
0x18001d548  jmp     short loc_18001D54D
0x18001d54a  mov     rsi, rbx
0x18001d54d  mov     r14, [r12+10h]
0x18001d552  mov     r8, rsi
0x18001d555  mov     rdx, rdi
0x18001d558  lea     rcx, [rbp+70h+var_78]
0x18001d55c  call    ??$?0V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@_W@std@@@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@_W@std@@@std@@@1@0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<wchar_t>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<wchar_t>>>,std::allocator<wchar_t> const &)
0x18001d561  nop
0x18001d562  mov     r8, rax
0x18001d565  lea     rdx, [rbp+70h+var_A8]
0x18001d569  mov     rcx, r14
0x18001d56c  call    ??$_Emplace@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(std::wstring &&)
0x18001d571  nop
0x18001d572  lea     rcx, [rbp+70h+var_78]
0x18001d576  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d57b  lea     rdi, [rsi+6]
0x18001d57f  cmp     rsi, rbx
0x18001d582  cmovz   rdi, rsi
0x18001d586  jmp     short loc_18001D51B
0x18001d588  mov     r14d, 1
0x18001d58e  add     r15d, r14d
0x18001d591  cmp     r15d, [rsp+170h+cValues]
0x18001d596  jb      loc_18001D40D
0x18001d59c  lea     rcx, [rbp+70h+lpData]
0x18001d5a0  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18001d5a5  nop
0x18001d5a6  lea     rcx, [rbp+70h+lpValueName]
0x18001d5aa  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18001d5af  nop
0x18001d5b0  lea     rcx, [rbp+70h+hKey]
0x18001d5b4  call    ?reset@?$Holder@PEAUHKEY__@@U?$close_funct@P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@Z@@U?$invalid_const@PEAUHKEY__@@$0A@@@@@QEAAXXZ; Holder<HKEY__ *,close_funct<long (*)(HKEY__ *),&RegCloseKey(HKEY__ *)>,invalid_const<HKEY__ *,0>>::reset(void)
0x18001d5b9  nop
0x18001d5ba  lea     rcx, [rbp+70h+Src]
0x18001d5be  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d5c3  nop
0x18001d5c4  lea     rcx, [rbp+70h+var_E8]
0x18001d5c8  call    ?reset@?$Holder@PEAXU?$close_funct@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@@U?$invalid_const@PEAX$0A@@@@@QEAAXXZ; Holder<void *,close_funct<void (*)(void *),&CoTaskMemFree(void *)>,invalid_const<void *,0>>::reset(void)
0x18001d5cd  nop
0x18001d5ce  mov     rax, r12
0x18001d5d1  mov     rcx, [rbp+70h+var_48]
0x18001d5d5  xor     rcx, rsp; StackCookie
0x18001d5d8  call    __security_check_cookie
0x18001d5dd  add     rsp, 138h
0x18001d5e4  pop     r15
0x18001d5e6  pop     r14
0x18001d5e8  pop     r13
0x18001d5ea  pop     r12
0x18001d5ec  pop     rdi
0x18001d5ed  pop     rsi
0x18001d5ee  pop     rbx
0x18001d5ef  pop     rbp
0x18001d5f0  retn
0x18001d5f1  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18001d5f7  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18001d5fd  mov     ecx, esi; this
0x18001d5ff  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18001d605  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18001d60b  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18001d611  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
```
