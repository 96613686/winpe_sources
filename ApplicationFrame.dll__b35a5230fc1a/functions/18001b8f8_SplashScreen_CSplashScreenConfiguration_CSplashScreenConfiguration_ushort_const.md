# SplashScreen::CSplashScreenConfiguration::CSplashScreenConfiguration(ushort const *)

- ea: `0x18001b8f8`
- end: `0x18001bdf3`
- name: `??0CSplashScreenConfiguration@SplashScreen@@QEAA@PEBG@Z`
- size: `1275`
- prototype: `__int64 __fastcall(SplashScreen::CSplashScreenConfiguration *__hidden this, LPCWSTR lpSubKey)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000471c`
- `0x180016320`
- `0x18001b47c`
- `0x18004f4a4`

## callees

- `0x18001b8f8`
- `0x18001bdfc`
- `0x18001be20`
- `0x18001bfec`
- `0x18001c058`
- `0x180043c30`
- `0x1800446fc`
- `0x18004bb84`
- `0x18006ea08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001b9c2`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001b9c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bb78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bb78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bcd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bcd0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ba81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bad8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bb0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ba81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bad8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bb0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bb38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bb47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bb5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bdbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bb38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bb47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bb5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bdbd`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001ba17`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001ba17`

## string_xrefs

- `0x18001bd99`: `shellcommondesktopbase\splashscreen\splashscreenconfiguration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
SplashScreen::CSplashScreenConfiguration *__fastcall SplashScreen::CSplashScreenConfiguration::CSplashScreenConfiguration(
        SplashScreen::CSplashScreenConfiguration *this,
        LPCWSTR lpSubKey)
{
  SplashScreen::CSplashScreenConfiguration *v3; // r12
  unsigned __int64 v4; // r15
  unsigned __int16 *v5; // r14
  __int64 v6; // rsi
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rcx
  unsigned __int128 v10; // rax
  __int16 v11; // r9
  _WORD *v12; // rax
  signed int v13; // edi
  __int64 v14; // r9
  char IsStateSeparationEnabled; // al
  const unsigned __int16 *v16; // r8
  int v17; // eax
  const char *v18; // r9
  HKEY v19; // rsi
  HKEY v20; // rcx
  HKEY SystemAppDataKey; // rdi
  unsigned int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // eax
  unsigned int v25; // r8d
  HKEY v26; // rcx
  HKEY v27; // rcx
  __int64 v29; // rsi
  bool v30; // cf
  __int64 v31; // rax
  wchar_t *v32; // r10
  __int64 v33; // rcx
  wchar_t *v34; // r9
  wchar_t v35; // r11
  wchar_t *v36; // rax
  unsigned __int64 v37; // rsi
  unsigned __int16 *v38; // rcx
  __int64 v39; // r10
  __int16 v40; // r9
  int phkResult; // [rsp+20h] [rbp-328h]
  unsigned int phkResulta; // [rsp+20h] [rbp-328h]
  unsigned int phkResultb; // [rsp+20h] [rbp-328h]
  HKEY hKey; // [rsp+30h] [rbp-318h] BYREF
  HKEY v45; // [rsp+38h] [rbp-310h] BYREF
  unsigned __int16 *v46; // [rsp+40h] [rbp-308h]
  __int64 v47; // [rsp+48h] [rbp-300h]
  __int64 v48; // [rsp+50h] [rbp-2F8h]
  SplashScreen::CSplashScreenConfiguration *v49; // [rsp+58h] [rbp-2F0h]
  HKEY v50; // [rsp+60h] [rbp-2E8h]
  _WORD v51[72]; // [rsp+70h] [rbp-2D8h] BYREF
  wchar_t Str[264]; // [rsp+100h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+0h]

  v3 = this;
  v49 = this;
  *(_QWORD *)this = &SplashScreen::CSplashScreenConfiguration::`vftable';
  *((_WORD *)this + 4) = 0;
  std::wstring::wstring((char *)this + 16);
  std::wstring::wstring((char *)v3 + 48);
  *((_QWORD *)v3 + 11) = 0;
  *((_DWORD *)v3 + 24) = 0;
  v4 = -1;
  v47 = -1;
  v48 = -1;
  v5 = 0;
  v46 = 0;
  v51[0] = 0;
  v6 = 2147483646;
  *(_QWORD *)&v10 = 2147483646;
  v8 = v7;
  v9 = 130;
  *((_QWORD *)&v10 + 1) = Str;
  do
  {
    if ( !(_QWORD)v10 )
      break;
    v11 = *(_WORD *)v8;
    if ( !*(_WORD *)v8 )
      break;
    v8 += 2;
    **((_WORD **)&v10 + 1) = v11;
    *((_QWORD *)&v10 + 1) += 2LL;
    *(_QWORD *)&v10 = v10 - 1;
    --v9;
  }
  while ( v9 );
  v12 = (_WORD *)(*((_QWORD *)&v10 + 1) - 2LL);
  if ( v9 )
    v12 = (_WORD *)*((_QWORD *)&v10 + 1);
  *v12 = 0;
  if ( !v9
    || (*(_QWORD *)&v10 = wcsrchr(Str, 0x21u), Str[0] == 33)
    || !(_QWORD)v10
    || (*((_QWORD *)&v10 + 1) = v10 + 2, !*(_WORD *)(v10 + 2)) )
  {
    v13 = -2147024809;
    goto LABEL_16;
  }
  *(_WORD *)v10 = 0;
  v31 = 2147483646;
  v32 = Str;
  v33 = 65;
  v8 = 65;
  v34 = v51;
  do
  {
    if ( !v31 )
      break;
    v35 = *v32;
    if ( !*v32 )
      break;
    ++v32;
    *v34++ = v35;
    --v31;
    --v8;
  }
  while ( v8 );
  v13 = v8 == 0 ? 0x8007007A : 0;
  v36 = v34 - 1;
  if ( v8 )
    v36 = v34;
  *v36 = 0;
  if ( v8 )
  {
    do
    {
      if ( !v6 )
        break;
      if ( !**((_WORD **)&v10 + 1) )
        break;
      *((_QWORD *)&v10 + 1) += 2LL;
      --v6;
      --v33;
    }
    while ( v33 );
    v13 = v33 == 0 ? 0x8007007A : 0;
  }
  if ( v13 >= 0 )
  {
    do
      ++v4;
    while ( v51[v4] );
    v5 = 0;
    v46 = 0;
    v37 = v4 + 1;
    if ( v4 + 1 < v4 )
    {
      v13 = -2147024362;
    }
    else
    {
      v46 = 0;
      v45 = 0;
      v10 = v37 * (unsigned __int128)2uLL;
      if ( is_mul_ok(v37, 2u) )
      {
        v5 = (unsigned __int16 *)CoTaskMemAlloc(2 * v37);
        v46 = v5;
        v13 = v5 == 0 ? 0x8007000E : 0;
        v38 = v5;
      }
      else
      {
        v38 = 0;
        v13 = -2147024362;
      }
      if ( v13 >= 0 )
      {
        if ( !v38 && v4 != -1 || v37 > 0x7FFFFFFF )
        {
LABEL_60:
          *v38 = 0;
          goto LABEL_16;
        }
        if ( v4 >= 0x7FFFFFFF )
        {
          if ( v4 == -1 )
            goto LABEL_16;
          goto LABEL_60;
        }
        *(_QWORD *)&v10 = v51;
        *((_QWORD *)&v10 + 1) = v4 + 1;
        v8 = (__int64)v38;
        v39 = 0;
        do
        {
          if ( !v4 )
            break;
          v40 = *(_WORD *)v10;
          if ( !*(_WORD *)v10 )
            break;
          *(_QWORD *)&v10 = v10 + 2;
          *(_WORD *)v8 = v40;
          v8 += 2;
          --v4;
          ++v39;
          --*((_QWORD *)&v10 + 1);
        }
        while ( *((_QWORD *)&v10 + 1) );
        v14 = v39 - 1;
        if ( *((_QWORD *)&v10 + 1) )
          v14 = v39;
        *(_QWORD *)&v10 = v8 - 2;
        if ( *((_QWORD *)&v10 + 1) )
          *(_QWORD *)&v10 = v8;
        *(_WORD *)v10 = 0;
        if ( *((_QWORD *)&v10 + 1) )
        {
          v30 = v37 == v14;
          v29 = v37 - v14;
          if ( !v30 && v29 != 1 )
          {
            v8 = 2 * v29;
            if ( (unsigned __int64)(2 * v29) > 2 )
              memset_0(&v38[v14 + 1], 0, v8 - 2);
          }
        }
      }
    }
  }
LABEL_16:
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"shellcommondesktopbase\\splashscreen\\splashscreenconfiguration.cpp",
      (const char *)(unsigned int)v13,
      phkResult);
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(retaddr, *((_QWORD *)&v10 + 1), v8);
  v16 = L"OSDATA\\Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\SystemAppData"
         "\\%s\\SplashScreen\\%s";
  if ( !IsStateSeparationEnabled )
    v16 = L"Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\SystemAppData\\%s\\"
           "SplashScreen\\%s";
  v17 = StringCchPrintfW(Str, 0x104u, v16, v5, lpSubKey);
  try
  {
    v19 = 0;
    v20 = 0;
    hKey = 0;
    if ( v17 >= 0 )
    {
      hKey = 0;
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, Str, 0, 0x20019u, &hKey) )
      {
        v20 = hKey;
      }
      else
      {
        v19 = hKey;
        v20 = 0;
        hKey = 0;
      }
    }
    if ( v20 )
      RegCloseKey(v20);
    if ( !v19 )
    {
      SystemAppDataKey = SplashScreen::CSplashScreenConfiguration::_GetSystemAppDataKey(
                           (SplashScreen::CSplashScreenConfiguration *)v20,
                           v5);
      v50 = SystemAppDataKey;
      hKey = 0;
      v22 = RegOpenKeyExW(SystemAppDataKey, L"SplashScreen", 0, 0x20019u, &hKey);
      if ( v22 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0xB0, v23, (const char *)v22, phkResulta);
      v45 = 0;
      v24 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &v45);
      if ( v24 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0xB3, v25, (const char *)v24, phkResultb);
      v19 = v45;
      v26 = hKey;
      hKey = 0;
      if ( v26 )
        RegCloseKey(v26);
      if ( SystemAppDataKey )
        RegCloseKey(SystemAppDataKey);
    }
    v27 = (HKEY)*((_QWORD *)v3 + 11);
    *((_QWORD *)v3 + 11) = 0;
    if ( v27 )
      RegCloseKey(v27);
    *((_QWORD *)v3 + 11) = v19;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x59,
      (unsigned int)"shellcommondesktopbase\\splashscreen\\splashscreenconfiguration.cpp",
      v18);
    v5 = v46;
    v3 = v49;
  }
  SplashScreen::CSplashScreenConfiguration::_PopulateFastDataFromRegistryWithFallback(v3);
  if ( v5 )
    CoTaskMemFree(v5);
  return v3;
}

```

## disassembly

```asm
0x18001b8f8  mov     [rsp+arg_10], rbx
0x18001b8fd  mov     [rsp+arg_18], rsi
0x18001b902  push    rdi
0x18001b903  push    r12
0x18001b905  push    r13
0x18001b907  push    r14
0x18001b909  push    r15
0x18001b90b  sub     rsp, 320h
0x18001b912  mov     rax, cs:__security_cookie
0x18001b919  xor     rax, rsp
0x18001b91c  mov     [rsp+348h+var_38], rax
0x18001b924  mov     r13, rdx
0x18001b927  mov     r12, rcx
0x18001b92a  mov     [rsp+348h+var_2F0], rcx
0x18001b92f  lea     rax, ??_7CSplashScreenConfiguration@SplashScreen@@6B@; const SplashScreen::CSplashScreenConfiguration::`vftable'
0x18001b936  mov     [rcx], rax
0x18001b939  xor     ebx, ebx
0x18001b93b  mov     [rcx+8], bx
0x18001b93f  add     rcx, 10h
0x18001b943  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001b948  nop
0x18001b949  lea     rcx, [r12+30h]
0x18001b94e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001b953  nop
0x18001b954  mov     [r12+58h], rbx
0x18001b959  mov     [r12+60h], ebx
0x18001b95e  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001b962  mov     [rsp+348h+var_300], r15
0x18001b967  mov     [rsp+348h+var_2F8], r15
0x18001b96c  mov     r14d, ebx
0x18001b96f  mov     [rsp+348h+var_308], rbx
0x18001b974  mov     [rsp+348h+var_2D8], bx
0x18001b979  mov     esi, 7FFFFFFEh
0x18001b97e  mov     eax, esi
0x18001b980  mov     r8, rdx
0x18001b983  mov     ecx, 82h
0x18001b988  lea     rdx, [rsp+348h+Str]
0x18001b990  test    rax, rax
0x18001b993  jz      short loc_18001B9A3
0x18001b995  movzx   r9d, word ptr [r8]
0x18001b999  test    r9w, r9w
0x18001b99d  jnz     loc_18001BD0F
0x18001b9a3  lea     rax, [rdx-2]
0x18001b9a7  test    rcx, rcx
0x18001b9aa  cmovnz  rax, rdx
0x18001b9ae  mov     [rax], bx
0x18001b9b1  jz      short loc_18001B9E4
0x18001b9b3  mov     edi, 21h ; '!'
0x18001b9b8  mov     edx, edi; Ch
0x18001b9ba  lea     rcx, [rsp+348h+Str]; Str
0x18001b9c2  call    cs:__imp_wcsrchr
0x18001b9c8  cmp     di, [rsp+348h+Str]
0x18001b9d0  jz      short loc_18001B9E4
0x18001b9d2  test    rax, rax
0x18001b9d5  jz      short loc_18001B9E4
0x18001b9d7  lea     rdx, [rax+2]
0x18001b9db  cmp     bx, [rdx]
0x18001b9de  jnz     loc_18001BBE2
0x18001b9e4  mov     edi, 80070057h
0x18001b9e9  jmp     short loc_18001BA07
0x18001b9eb  lea     r9, [r10-1]
0x18001b9ef  test    rdx, rdx
0x18001b9f2  cmovnz  r9, r10
0x18001b9f6  lea     rax, [r8-2]
0x18001b9fa  cmovnz  rax, r8
0x18001b9fe  mov     [rax], bx
0x18001ba01  jnz     loc_18001BBAF
0x18001ba07  mov     rcx, [rsp+348h]; this
0x18001ba0f  test    edi, edi
0x18001ba11  js      loc_18001BD96
0x18001ba17  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001ba1d  lea     rcx, aSoftwareClasse; "Software\\Classes\\Local Settings\\Soft"...
0x18001ba24  lea     r8, aOsdataSoftware; "OSDATA\\Software\\Classes\\Local Settin"...
0x18001ba2b  test    al, al
0x18001ba2d  cmovz   r8, rcx; unsigned __int16 *
0x18001ba31  mov     qword ptr [rsp+348h+phkResult], r13
0x18001ba36  mov     r9, r14
0x18001ba39  mov     edx, 104h; unsigned __int64
0x18001ba3e  lea     rcx, [rsp+348h+Str]; unsigned __int16 *
0x18001ba46  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001ba4b  mov     rsi, rbx
0x18001ba4e  mov     rcx, rbx
0x18001ba51  mov     [rsp+348h+hKey], rbx
0x18001ba56  test    eax, eax
0x18001ba58  js      short loc_18001BA94
0x18001ba5a  mov     [rsp+348h+hKey], rbx
0x18001ba5f  lea     rax, [rsp+348h+hKey]
0x18001ba64  mov     qword ptr [rsp+348h+phkResult], rax; phkResult
0x18001ba69  mov     r9d, 20019h; samDesired
0x18001ba6f  xor     r8d, r8d; ulOptions
0x18001ba72  lea     rdx, [rsp+348h+Str]; lpSubKey
0x18001ba7a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ba81  call    cs:__imp_RegOpenKeyExW
0x18001ba87  test    eax, eax
0x18001ba89  jz      loc_18001BDAB
0x18001ba8f  mov     rcx, [rsp+348h+hKey]; this
0x18001ba94  test    rcx, rcx
0x18001ba97  jnz     loc_18001BDBD
0x18001ba9d  test    rsi, rsi
0x18001baa0  jnz     loc_18001BB4D
0x18001baa6  mov     rdx, r14; unsigned __int16 *
0x18001baa9  call    ?_GetSystemAppDataKey@CSplashScreenConfiguration@SplashScreen@@AEAAPEAUHKEY__@@PEBG@Z; SplashScreen::CSplashScreenConfiguration::_GetSystemAppDataKey(ushort const *)
0x18001baae  mov     rdi, rax
0x18001bab1  mov     [rsp+348h+var_2E8], rax
0x18001bab6  mov     [rsp+348h+hKey], rbx
0x18001babb  lea     rax, [rsp+348h+hKey]
0x18001bac0  mov     qword ptr [rsp+348h+phkResult], rax; unsigned int
0x18001bac5  mov     r9d, 20019h; samDesired
0x18001bacb  xor     r8d, r8d; ulOptions
0x18001bace  lea     rdx, aSplashscreen; "SplashScreen"
0x18001bad5  mov     rcx, rdi; hKey
0x18001bad8  call    cs:__imp_RegOpenKeyExW
0x18001bade  mov     rcx, [rsp+348h]; this
0x18001bae6  test    eax, eax
0x18001bae8  jnz     loc_18001BDC8
0x18001baee  mov     [rsp+348h+var_310], rbx
0x18001baf3  lea     rax, [rsp+348h+var_310]
0x18001baf8  mov     qword ptr [rsp+348h+phkResult], rax; unsigned int
0x18001bafd  mov     r9d, 20019h; samDesired
0x18001bb03  xor     r8d, r8d; ulOptions
0x18001bb06  mov     rdx, r13; lpSubKey
0x18001bb09  mov     rcx, [rsp+348h+hKey]; hKey
0x18001bb0e  call    cs:__imp_RegOpenKeyExW
0x18001bb14  mov     rcx, [rsp+348h]; this
0x18001bb1c  test    eax, eax
0x18001bb1e  jnz     loc_18001BDD5
0x18001bb24  mov     rsi, [rsp+348h+var_310]
0x18001bb29  mov     rcx, [rsp+348h+hKey]; hKey
0x18001bb2e  mov     [rsp+348h+hKey], rbx
0x18001bb33  test    rcx, rcx
0x18001bb36  jz      short loc_18001BB3F
0x18001bb38  call    cs:__imp_RegCloseKey
0x18001bb3e  nop
0x18001bb3f  test    rdi, rdi
0x18001bb42  jz      short loc_18001BB4D
0x18001bb44  mov     rcx, rdi; hKey
0x18001bb47  call    cs:__imp_RegCloseKey
0x18001bb4d  mov     rcx, [r12+58h]; hKey
0x18001bb52  mov     [r12+58h], rbx
0x18001bb57  test    rcx, rcx
0x18001bb5a  jz      short loc_18001BB62
0x18001bb5c  call    cs:__imp_RegCloseKey
0x18001bb62  mov     [r12+58h], rsi
0x18001bb67  mov     rcx, r12; this
0x18001bb6a  call    ?_PopulateFastDataFromRegistryWithFallback@CSplashScreenConfiguration@SplashScreen@@AEAAXXZ; SplashScreen::CSplashScreenConfiguration::_PopulateFastDataFromRegistryWithFallback(void)
0x18001bb6f  nop
0x18001bb70  test    r14, r14
0x18001bb73  jz      short loc_18001BB7F
0x18001bb75  mov     rcx, r14; pv
0x18001bb78  call    cs:__imp_CoTaskMemFree
0x18001bb7e  nop
0x18001bb7f  mov     rax, r12
0x18001bb82  mov     rcx, [rsp+348h+var_38]
0x18001bb8a  xor     rcx, rsp; StackCookie
0x18001bb8d  call    __security_check_cookie
0x18001bb92  lea     r11, [rsp+348h+var_28]
0x18001bb9a  mov     rbx, [r11+40h]
0x18001bb9e  mov     rsi, [r11+48h]
0x18001bba2  mov     rsp, r11
0x18001bba5  pop     r15
0x18001bba7  pop     r14
0x18001bba9  pop     r13
0x18001bbab  pop     r12
0x18001bbad  pop     rdi
0x18001bbae  retn
0x18001bbaf  sub     rsi, r9
0x18001bbb2  cmp     rsi, 1
0x18001bbb6  jbe     loc_18001BA07
0x18001bbbc  lea     r8, [rsi+rsi]
0x18001bbc0  cmp     r8, 2
0x18001bbc4  jbe     loc_18001BA07
0x18001bbca  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18001bbce  lea     rcx, [rcx+r9*2]
0x18001bbd2  add     rcx, 2; void *
0x18001bbd6  xor     edx, edx; Val
0x18001bbd8  call    memset_0
0x18001bbdd  jmp     loc_18001BA07
0x18001bbe2  mov     [rax], bx
0x18001bbe5  mov     rax, rsi
0x18001bbe8  lea     r10, [rsp+348h+Str]
0x18001bbf0  mov     ecx, 41h ; 'A'
0x18001bbf5  mov     r8d, ecx
0x18001bbf8  lea     r9, [rsp+348h+var_2D8]
0x18001bbfd  test    rax, rax
0x18001bc00  jz      short loc_18001BC10
0x18001bc02  movzx   r11d, word ptr [r10]
0x18001bc06  test    r11w, r11w
0x18001bc0a  jnz     loc_18001BD2D
0x18001bc10  mov     rax, r8
0x18001bc13  neg     rax
0x18001bc16  sbb     edi, edi
0x18001bc18  not     edi
0x18001bc1a  mov     r10d, 8007007Ah
0x18001bc20  and     edi, r10d
0x18001bc23  lea     rax, [r9-2]
0x18001bc27  test    r8, r8
0x18001bc2a  cmovnz  rax, r9
0x18001bc2e  mov     [rax], bx
0x18001bc31  jz      short loc_18001BC46
0x18001bc33  test    rsi, rsi
0x18001bc36  jnz     loc_18001BCF0
0x18001bc3c  neg     rcx
0x18001bc3f  sbb     edi, edi
0x18001bc41  not     edi
0x18001bc43  and     edi, r10d
0x18001bc46  test    edi, edi
0x18001bc48  js      loc_18001BA07
0x18001bc4e  lea     rax, [rsp+348h+var_2D8]
0x18001bc53  inc     r15
0x18001bc56  cmp     [rax+r15*2], bx
0x18001bc5b  jnz     short loc_18001BC53
0x18001bc5d  mov     r14, rbx
0x18001bc60  mov     [rsp+348h+var_308], rbx
0x18001bc65  lea     rsi, [r15+1]
0x18001bc69  cmp     rsi, r15
0x18001bc6c  jb      short loc_18001BCC3
0x18001bc6e  mov     [rsp+348h+var_308], rbx
0x18001bc73  mov     [rsp+348h+var_310], rbx
0x18001bc78  mov     eax, 2
0x18001bc7d  mul     rsi
0x18001bc80  test    rdx, rdx
0x18001bc83  jz      short loc_18001BCCD
0x18001bc85  mov     rcx, rbx
0x18001bc88  mov     edi, 80070216h
0x18001bc8d  test    edi, edi
0x18001bc8f  js      loc_18001BA07
0x18001bc95  test    rcx, rcx
0x18001bc98  jnz     short loc_18001BC9F
0x18001bc9a  test    rsi, rsi
0x18001bc9d  jnz     short loc_18001BCBB
0x18001bc9f  mov     eax, 7FFFFFFFh
0x18001bca4  cmp     rsi, rax
0x18001bca7  ja      short loc_18001BCBB
0x18001bca9  cmp     r15, rax
0x18001bcac  jb      loc_18001BD4B
0x18001bcb2  test    rsi, rsi
0x18001bcb5  jz      loc_18001BA07
0x18001bcbb  mov     [rcx], bx
0x18001bcbe  jmp     loc_18001BA07
0x18001bcc3  mov     edi, 80070216h
0x18001bcc8  jmp     loc_18001BA07
0x18001bccd  mov     rcx, rax; cb
0x18001bcd0  call    cs:__imp_CoTaskMemAlloc
0x18001bcd6  mov     r14, rax
0x18001bcd9  mov     [rsp+348h+var_308], rax
0x18001bcde  neg     rax
0x18001bce1  sbb     edi, edi
0x18001bce3  not     edi
0x18001bce5  and     edi, 8007000Eh
0x18001bceb  mov     rcx, r14
0x18001bcee  jmp     short loc_18001BC8D
0x18001bcf0  cmp     [rdx], bx
0x18001bcf3  jz      loc_18001BC3C
0x18001bcf9  add     rdx, 2
0x18001bcfd  dec     rsi
0x18001bd00  sub     rcx, 1
0x18001bd04  jnz     loc_18001BC33
0x18001bd0a  jmp     loc_18001BC3C
0x18001bd0f  add     r8, 2
0x18001bd13  mov     [rdx], r9w
0x18001bd17  add     rdx, 2
0x18001bd1b  dec     rax
0x18001bd1e  sub     rcx, 1
0x18001bd22  jnz     loc_18001B990
0x18001bd28  jmp     loc_18001B9A3
0x18001bd2d  add     r10, 2
0x18001bd31  mov     [r9], r11w
0x18001bd35  add     r9, 2
0x18001bd39  dec     rax
0x18001bd3c  sub     r8, 1
0x18001bd40  jnz     loc_18001BBFD
0x18001bd46  jmp     loc_18001BC10
0x18001bd4b  test    rsi, rsi
0x18001bd4e  jz      loc_18001BA07
0x18001bd54  lea     rax, [rsp+348h+var_2D8]
0x18001bd59  mov     rdx, rsi
0x18001bd5c  mov     r8, rcx
0x18001bd5f  mov     r10, rbx
0x18001bd62  test    r15, r15
0x18001bd65  jz      loc_18001B9EB
0x18001bd6b  movzx   r9d, word ptr [rax]
0x18001bd6f  test    r9w, r9w
0x18001bd73  jz      loc_18001B9EB
0x18001bd79  add     rax, 2
0x18001bd7d  mov     [r8], r9w
0x18001bd81  add     r8, 2
0x18001bd85  dec     r15
0x18001bd88  inc     r10
0x18001bd8b  sub     rdx, 1
0x18001bd8f  jnz     short loc_18001BD62
0x18001bd91  jmp     loc_18001B9EB
0x18001bd96  mov     r9d, edi; char *
0x18001bd99  lea     r8, aShellcommondes; "shellcommondesktopbase\\splashscreen\\s"...
0x18001bda0  mov     edx, 52h ; 'R'; void *
0x18001bda5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001bdab  mov     rsi, [rsp+348h+hKey]
0x18001bdb0  mov     rcx, rbx
0x18001bdb3  mov     [rsp+348h+hKey], rbx
0x18001bdb8  jmp     loc_18001BA94
0x18001bdbd  call    cs:__imp_RegCloseKey
  ... truncated ...
```
