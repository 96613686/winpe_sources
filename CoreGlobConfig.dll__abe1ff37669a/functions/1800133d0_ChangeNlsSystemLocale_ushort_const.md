# ChangeNlsSystemLocale(ushort const *)

- ea: `0x1800133d0`
- end: `0x1800136bf`
- name: `?ChangeNlsSystemLocale@@YAJPEBG@Z`
- size: `751`
- prototype: `__int64 __fastcall(LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x1800190bc`

## callees

- `0x180002380`
- `0x180008294`
- `0x1800088b4`
- `0x180011428`
- `0x1800133d0`
- `0x180015680`
- `0x180018c10`
- `0x18001b044`
- `0x18001d408`
- `0x18001d564`
- `0x18001de84`
- `0x18001ebcc`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18001341f`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180013451`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18001341f`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180013451`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x18001340c`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x18001340c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001354f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800135e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001354f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800135e2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800135a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001361b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800135a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001361b`
- `api-ms-win-core-localization-private-l1-1-0!NlsUpdateSystemLocale` at `0x18001365a`
- `api-ms-win-core-localization-private-l1-1-0!NlsUpdateSystemLocale` at `0x18001365a`

## string_xrefs

- `0x1800134aa`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18001368d`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
__int64 __fastcall ChangeNlsSystemLocale(LPCWSTR lpName)
{
  LCID v2; // eax
  LCID v3; // esi
  const WCHAR *v4; // rax
  unsigned int v5; // ebx
  HRESULT v6; // eax
  __int64 v7; // rdx
  unsigned int v8; // eax
  unsigned int v9; // r8d
  __int64 v10; // rdx
  int v11; // eax
  void *p_hKey; // rcx
  unsigned int v13; // eax
  unsigned int v14; // r8d
  __int64 v15; // rdx
  unsigned int updated; // eax
  void *v17; // rdx
  unsigned int v18; // r8d
  __int64 v20; // rdx
  int phkResult; // [rsp+20h] [rbp-59h]
  unsigned int phkResulta; // [rsp+20h] [rbp-59h]
  unsigned int phkResultb; // [rsp+20h] [rbp-59h]
  size_t pcchLength; // [rsp+30h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-41h] BYREF
  size_t v26; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v27[32]; // [rsp+48h] [rbp-31h] BYREF
  wchar_t psz[8]; // [rsp+68h] [rbp-11h] BYREF
  int v29; // [rsp+78h] [rbp-1h]
  wchar_t v30[8]; // [rsp+80h] [rbp+7h] BYREF
  int v31; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( !lpName || !*lpName || !IsValidLocaleName(lpName) )
  {
    v20 = 612;
    goto LABEL_34;
  }
  v2 = LocaleNameToLCID(lpName, 0);
  v3 = v2;
  if ( !v2 || (v2 & 0x3FF) == 0 )
  {
    v20 = 619;
LABEL_34:
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)0x80070057LL,
      phkResult);
    return v5;
  }
  GetNlsSystemLocale(v27);
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  if ( v3 == LocaleNameToLCID(v4, 0) )
  {
    v5 = 0;
LABEL_28:
    std::wstring::_Tidy_deallocate(v27);
    return v5;
  }
  pcchLength = 0;
  v29 = 0;
  v31 = 0;
  v26 = 0;
  *(_OWORD *)psz = 0;
  *(_OWORD *)v30 = 0;
  v6 = StringCchPrintfW(psz, 0xAu, L"%.4x", v3);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = 647;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)(unsigned int)v6,
      phkResult);
    goto LABEL_28;
  }
  v6 = StringLengthWorkerW(psz, 0xAu, &pcchLength);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = 648;
    goto LABEL_10;
  }
  v6 = StringCchPrintfW(v30, 0xAu, L"%.8x", v3);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = 650;
    goto LABEL_10;
  }
  v6 = StringLengthWorkerW(v30, 0xAu, &v26);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = 651;
    goto LABEL_10;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\NLS\\Language", 0, 2u, &hKey);
  if ( v8 )
  {
    v10 = 663;
LABEL_19:
    v11 = wil::details::in1diag3::Return_Win32(retaddr, (void *)v10, v9, (const char *)v8, phkResulta);
    p_hKey = &hKey;
LABEL_27:
    v5 = v11;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(p_hKey);
    goto LABEL_28;
  }
  v8 = RegSetValueExW(hKey, L"Default", 0, 1u, (const BYTE *)psz, 2 * pcchLength + 2);
  if ( v8 )
  {
    v10 = 670;
    goto LABEL_19;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  pcchLength = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &pcchLength,
    0);
  v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\NLS\\Locale", 0, 2u, (PHKEY)&pcchLength);
  if ( v13 )
  {
    v15 = 679;
LABEL_26:
    v11 = wil::details::in1diag3::Return_Win32(retaddr, (void *)v15, v14, (const char *)v13, phkResultb);
    p_hKey = &pcchLength;
    goto LABEL_27;
  }
  v13 = RegSetValueExW((HKEY)pcchLength, L"(Default)", 0, 1u, (const BYTE *)v30, 2 * v26 + 2);
  if ( v13 )
  {
    v15 = 687;
    goto LABEL_26;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&pcchLength);
  updated = NlsUpdateSystemLocale(lpName, 1);
  if ( updated )
    wil::details::in1diag3::_Log_Win32(retaddr, v17, v18, (const char *)updated, phkResultb);
  std::wstring::_Tidy_deallocate(v27);
  return 0;
}

```

## disassembly

```asm
0x1800133d0  push    rbp
0x1800133d2  push    rbx
0x1800133d3  push    rsi
0x1800133d4  push    rdi
0x1800133d5  push    r14
0x1800133d7  push    r15
0x1800133d9  lea     rbp, [rsp-2Fh]
0x1800133de  sub     rsp, 0A8h
0x1800133e5  mov     rax, cs:__security_cookie
0x1800133ec  xor     rax, rsp
0x1800133ef  mov     [rbp+57h+var_38], rax
0x1800133f3  xor     r14d, r14d
0x1800133f6  mov     rdi, rcx
0x1800133f9  test    rcx, rcx
0x1800133fc  jz      loc_180013684
0x180013402  cmp     [rcx], r14w
0x180013406  jz      loc_180013684
0x18001340c  call    cs:__imp_IsValidLocaleName
0x180013412  test    eax, eax
0x180013414  jz      loc_180013684
0x18001341a  xor     edx, edx; dwFlags
0x18001341c  mov     rcx, rdi; lpName
0x18001341f  call    cs:__imp_LocaleNameToLCID
0x180013425  mov     esi, eax
0x180013427  test    eax, eax
0x180013429  jz      loc_18001367D
0x18001342f  test    eax, 3FFh
0x180013434  jz      loc_18001367D
0x18001343a  lea     rcx, [rbp+57h+var_88]
0x18001343e  call    ?GetNlsSystemLocale@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetNlsSystemLocale(void)
0x180013443  lea     rcx, [rbp+57h+var_88]
0x180013447  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001344c  mov     rcx, rax; lpName
0x18001344f  xor     edx, edx; dwFlags
0x180013451  call    cs:__imp_LocaleNameToLCID
0x180013457  cmp     esi, eax
0x180013459  jnz     short loc_180013463
0x18001345b  mov     ebx, r14d
0x18001345e  jmp     loc_180013641
0x180013463  xor     eax, eax
0x180013465  mov     [rbp+57h+pcchLength], r14
0x180013469  xorps   xmm0, xmm0
0x18001346c  mov     [rbp+57h+var_58], eax
0x18001346f  xorps   xmm1, xmm1
0x180013472  mov     [rbp+57h+var_40], eax
0x180013475  mov     r9d, esi
0x180013478  mov     [rbp+57h+var_90], r14
0x18001347c  lea     r15d, [rax+0Ah]
0x180013480  mov     edx, r15d; unsigned __int64
0x180013483  lea     r8, a4x; "%.4x"
0x18001348a  lea     rcx, [rbp+57h+psz]; unsigned __int16 *
0x18001348e  movups  xmmword ptr [rbp+57h+psz], xmm0
0x180013492  movups  xmmword ptr [rbp+57h+var_50], xmm1
0x180013496  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001349b  mov     ebx, eax
0x18001349d  test    eax, eax
0x18001349f  jns     short loc_1800134BE
0x1800134a1  mov     edx, 287h; void *
0x1800134a6  mov     rcx, [rbp+5Fh]; this
0x1800134aa  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x1800134b1  mov     r9d, eax; char *
0x1800134b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800134b9  jmp     loc_180013641
0x1800134be  lea     r8, [rbp+57h+pcchLength]; pcchLength
0x1800134c2  mov     rdx, r15; cchMax
0x1800134c5  lea     rcx, [rbp+57h+psz]; psz
0x1800134c9  call    StringLengthWorkerW
0x1800134ce  mov     ebx, eax
0x1800134d0  test    eax, eax
0x1800134d2  jns     short loc_1800134DB
0x1800134d4  mov     edx, 288h
0x1800134d9  jmp     short loc_1800134A6
0x1800134db  mov     r9d, esi
0x1800134de  lea     r8, a8x; "%.8x"
0x1800134e5  mov     rdx, r15; unsigned __int64
0x1800134e8  lea     rcx, [rbp+57h+var_50]; unsigned __int16 *
0x1800134ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800134f1  mov     ebx, eax
0x1800134f3  test    eax, eax
0x1800134f5  jns     short loc_1800134FE
0x1800134f7  mov     edx, 28Ah
0x1800134fc  jmp     short loc_1800134A6
0x1800134fe  lea     r8, [rbp+57h+var_90]; pcchLength
0x180013502  mov     rdx, r15; cchMax
0x180013505  lea     rcx, [rbp+57h+var_50]; psz
0x180013509  call    StringLengthWorkerW
0x18001350e  mov     ebx, eax
0x180013510  test    eax, eax
0x180013512  jns     short loc_18001351B
0x180013514  mov     edx, 28Bh
0x180013519  jmp     short loc_1800134A6
0x18001351b  xor     edx, edx
0x18001351d  mov     [rbp+57h+hKey], r14
0x180013521  lea     rcx, [rbp+57h+hKey]
0x180013525  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001352a  lea     rax, [rbp+57h+hKey]
0x18001352e  mov     esi, 2
0x180013533  mov     r15, 0FFFFFFFF80000002h
0x18001353a  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x18001353f  mov     r9d, esi; samDesired
0x180013542  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\NLS"...
0x180013549  mov     rcx, r15; hKey
0x18001354c  xor     r8d, r8d; ulOptions
0x18001354f  call    cs:__imp_RegOpenKeyExW
0x180013555  test    eax, eax
0x180013557  jz      short loc_180013573
0x180013559  mov     edx, 297h; void *
0x18001355e  mov     rcx, [rbp+5Fh]; this
0x180013562  mov     r9d, eax; char *
0x180013565  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001356a  lea     rcx, [rbp+57h+hKey]
0x18001356e  jmp     loc_18001363A
0x180013573  mov     eax, dword ptr [rbp+57h+pcchLength]
0x180013576  lea     rdx, ValueName; "Default"
0x18001357d  mov     rcx, [rbp+57h+hKey]; hKey
0x180013581  mov     ebx, 1
0x180013586  mov     r9d, ebx; dwType
0x180013589  xor     r8d, r8d; Reserved
0x18001358c  lea     eax, ds:2[rax*2]
0x180013593  mov     [rsp+0D0h+cbData], eax; cbData
0x180013597  lea     rax, [rbp+57h+psz]
0x18001359b  mov     [rsp+0D0h+phkResult], rax; lpData
0x1800135a0  call    cs:__imp_RegSetValueExW
0x1800135a6  test    eax, eax
0x1800135a8  jz      short loc_1800135B1
0x1800135aa  mov     edx, 29Eh
0x1800135af  jmp     short loc_18001355E
0x1800135b1  lea     rcx, [rbp+57h+hKey]
0x1800135b5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800135ba  xor     edx, edx
0x1800135bc  mov     [rbp+57h+pcchLength], r14
0x1800135c0  lea     rcx, [rbp+57h+pcchLength]
0x1800135c4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800135c9  lea     rax, [rbp+57h+pcchLength]
0x1800135cd  mov     r9d, esi; samDesired
0x1800135d0  xor     r8d, r8d; ulOptions
0x1800135d3  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800135d8  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\NLS"...
0x1800135df  mov     rcx, r15; hKey
0x1800135e2  call    cs:__imp_RegOpenKeyExW
0x1800135e8  test    eax, eax
0x1800135ea  jz      short loc_1800135F3
0x1800135ec  mov     edx, 2A7h
0x1800135f1  jmp     short loc_18001362A
0x1800135f3  mov     eax, dword ptr [rbp+57h+var_90]
0x1800135f6  lea     rdx, aDefault_0; "(Default)"
0x1800135fd  mov     rcx, [rbp+57h+pcchLength]; hKey
0x180013601  mov     r9d, ebx; dwType
0x180013604  xor     r8d, r8d; Reserved
0x180013607  lea     eax, ds:2[rax*2]
0x18001360e  mov     [rsp+0D0h+cbData], eax; cbData
0x180013612  lea     rax, [rbp+57h+var_50]
0x180013616  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x18001361b  call    cs:__imp_RegSetValueExW
0x180013621  test    eax, eax
0x180013623  jz      short loc_18001364C
0x180013625  mov     edx, 2AFh; void *
0x18001362a  mov     rcx, [rbp+5Fh]; this
0x18001362e  mov     r9d, eax; char *
0x180013631  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180013636  lea     rcx, [rbp+57h+pcchLength]
0x18001363a  mov     ebx, eax
0x18001363c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013641  lea     rcx, [rbp+57h+var_88]
0x180013645  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001364a  jmp     short loc_1800136A1
0x18001364c  lea     rcx, [rbp+57h+pcchLength]
0x180013650  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013655  mov     edx, ebx
0x180013657  mov     rcx, rdi
0x18001365a  call    cs:__imp_NlsUpdateSystemLocale
0x180013660  test    eax, eax
0x180013662  jz      short loc_180013670
0x180013664  mov     rcx, [rbp+5Fh]; this
0x180013668  mov     r9d, eax; char *
0x18001366b  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180013670  lea     rcx, [rbp+57h+var_88]
0x180013674  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013679  xor     eax, eax
0x18001367b  jmp     short loc_1800136A3
0x18001367d  mov     edx, 26Bh
0x180013682  jmp     short loc_180013689
0x180013684  mov     edx, 264h; void *
0x180013689  mov     rcx, [rbp+5Fh]; this
0x18001368d  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180013694  mov     ebx, 80070057h
0x180013699  mov     r9d, ebx; char *
0x18001369c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800136a1  mov     eax, ebx
0x1800136a3  mov     rcx, [rbp+57h+var_38]
0x1800136a7  xor     rcx, rsp; StackCookie
0x1800136aa  call    __security_check_cookie
0x1800136af  add     rsp, 0A8h
0x1800136b6  pop     r15
0x1800136b8  pop     r14
0x1800136ba  pop     rdi
0x1800136bb  pop     rsi
0x1800136bc  pop     rbx
0x1800136bd  pop     rbp
0x1800136be  retn
```
