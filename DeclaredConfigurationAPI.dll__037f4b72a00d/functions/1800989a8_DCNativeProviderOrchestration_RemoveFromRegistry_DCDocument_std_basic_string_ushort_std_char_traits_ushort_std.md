# DCNativeProviderOrchestration::RemoveFromRegistry(DCDocument *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800989a8`
- end: `0x180098d7e`
- name: `?RemoveFromRegistry@DCNativeProviderOrchestration@@QEAAJPEAVDCDocument@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `982`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18007ee20`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180011fe0`
- `0x180013b44`
- `0x180014348`
- `0x180018ac0`
- `0x18001ce5c`
- `0x18001d03c`
- `0x18001d0b0`
- `0x1800989a8`
- `0x180100ad8`
- `0x18012d590`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180098b1e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180098b1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180098a85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180098c33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180098a85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180098c33`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180098caa`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180098caa`

## string_xrefs

- `0x180098b4c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180098ba4`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180098c6a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180098cd4`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DCNativeProviderOrchestration::RemoveFromRegistry(_QWORD *a1, const wchar_t *a2, _QWORD *a3)
{
  _QWORD *v5; // rdx
  _QWORD *v6; // r15
  _QWORD *v7; // rax
  _QWORD *v8; // r9
  int v9; // eax
  int v10; // ebx
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  _QWORD *v14; // r9
  int v15; // eax
  int v16; // ebx
  int v17; // esi
  const WCHAR *v18; // rdx
  int v19; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY v23; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *String1; // [rsp+40h] [rbp-C0h] BYREF
  HKEY *p_hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v27; // [rsp+50h] [rbp-B0h] BYREF
  char v28; // [rsp+58h] [rbp-A8h]
  _QWORD *v29; // [rsp+60h] [rbp-A0h]
  LPCWSTR lpSubKey[5]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR v32[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4E8h] [rbp+3E8h]

  v29 = a3;
  hKey = 0;
  if ( a1[9] <= 7u )
    v5 = a1 + 6;
  else
    v5 = (_QWORD *)a1[6];
  v6 = a1 + 2;
  if ( a1[5] <= 7u )
    v7 = a1 + 2;
  else
    v7 = (_QWORD *)*v6;
  if ( a3[3] <= 7u )
    v8 = a3;
  else
    v8 = (_QWORD *)*a3;
  v9 = StringCchPrintfW(SubKey, 0x104u, qword_18018A580, v8, v7, v5);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = (unsigned int)v9;
    v12 = 24371;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)v11,
      phkResult);
    goto LABEL_50;
  }
  p_hKey = &hKey;
  v27 = 0;
  v28 = 1;
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2011Fu, &v27);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v10 )
  {
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    goto LABEL_50;
  }
  String1 = 0;
  if ( DCCDNUtil_GetRegistryString(hKey, 0, L"OriginatingDocument", &String1) < 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(a3);
    return 2147942487LL;
  }
  else
  {
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(const wchar_t **)a2;
    if ( wcsncmp_0(String1, a2, 0x104u) )
    {
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&String1);
      v10 = -2147024891;
LABEL_50:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::_Tidy_deallocate(a3);
      return (unsigned int)v10;
    }
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&String1);
    v13 = RegDeleteTreeW(hKey, 0);
    if ( v13 )
    {
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      v10 = 0;
      if ( v13 != -2147024894 )
        v10 = v13;
      if ( v10 < 0 )
      {
        v11 = (unsigned int)v10;
        v12 = 24411;
        goto LABEL_27;
      }
    }
    v23 = 0;
    if ( a3[3] <= 7u )
      v14 = a3;
    else
      v14 = (_QWORD *)*a3;
    v15 = StringCchPrintfW(v32, 0x104u, qword_18018A588, v14);
    v10 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F62,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v15,
        phkResult);
LABEL_49:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
      goto LABEL_50;
    }
    std::wstring::wstring((__int64)lpSubKey, v6);
    std::wstring::_Append<unsigned short>(lpSubKey);
    std::wstring::_Append<unsigned short>(lpSubKey);
    p_hKey = &v23;
    v27 = 0;
    v28 = 1;
    v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v32, 0, 0xF003Fu, &v27);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( v16 )
    {
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      v17 = 0;
      if ( v16 != -2147024894 )
        v17 = v16;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5F76,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)v17,
          phkResulta);
        std::wstring::_Tidy_deallocate(lpSubKey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
        v10 = v17;
        goto LABEL_50;
      }
    }
    v18 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v18 = lpSubKey[0];
    v19 = RegDeleteKeyW(v23, v18);
    if ( v19 )
    {
      if ( v19 > 0 )
        v19 = (unsigned __int16)v19 | 0x80070000;
      v10 = 0;
      if ( v19 != -2147024894 )
        v10 = v19;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5F81,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)v10,
          phkResulta);
        std::wstring::_Tidy_deallocate(lpSubKey);
        goto LABEL_49;
      }
    }
    std::wstring::_Tidy_deallocate(lpSubKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(a3);
    return 0;
  }
}

```

## disassembly

```asm
0x1800989a8  mov     [rsp-8+arg_8], rbx
0x1800989ad  push    rbp
0x1800989ae  push    rsi
0x1800989af  push    rdi
0x1800989b0  push    r14
0x1800989b2  push    r15
0x1800989b4  lea     rbp, [rsp-3C0h]
0x1800989bc  sub     rsp, 4C0h
0x1800989c3  mov     rax, cs:__security_cookie
0x1800989ca  xor     rax, rsp
0x1800989cd  mov     [rbp+3E0h+var_30], rax
0x1800989d4  mov     rdi, r8
0x1800989d7  mov     r14, rdx
0x1800989da  mov     [rsp+4E0h+var_480], r8
0x1800989df  mov     [rsp+4E0h+hKey], 0
0x1800989e8  lea     rsi, [rcx+30h]
0x1800989ec  cmp     qword ptr [rsi+18h], 7
0x1800989f1  jbe     short loc_1800989F8
0x1800989f3  mov     rdx, [rsi]
0x1800989f6  jmp     short loc_1800989FB
0x1800989f8  mov     rdx, rsi
0x1800989fb  lea     r15, [rcx+10h]
0x1800989ff  cmp     qword ptr [r15+18h], 7
0x180098a04  jbe     short loc_180098A0B
0x180098a06  mov     rax, [r15]
0x180098a09  jmp     short loc_180098A0E
0x180098a0b  mov     rax, r15
0x180098a0e  cmp     qword ptr [r8+18h], 7
0x180098a13  jbe     short loc_180098A1A
0x180098a15  mov     r9, [r8]
0x180098a18  jmp     short loc_180098A1D
0x180098a1a  mov     r9, rdi
0x180098a1d  mov     [rsp+4E0h+var_4B8], rdx
0x180098a22  mov     [rsp+4E0h+phkResult], rax
0x180098a27  mov     r8, cs:qword_18018A580; unsigned __int16 *
0x180098a2e  mov     edx, 104h; unsigned __int64
0x180098a33  lea     rcx, [rbp+3E0h+SubKey]; unsigned __int16 *
0x180098a37  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180098a3c  mov     ebx, eax
0x180098a3e  test    eax, eax
0x180098a40  jns     short loc_180098A4F
0x180098a42  mov     r9d, eax
0x180098a45  mov     edx, 5F33h
0x180098a4a  jmp     loc_180098B4C
0x180098a4f  lea     rax, [rsp+4E0h+hKey]
0x180098a54  mov     [rsp+4E0h+var_498], rax
0x180098a59  mov     [rsp+4E0h+var_490], 0
0x180098a62  mov     [rsp+4E0h+var_488], 1
0x180098a67  lea     rax, [rsp+4E0h+var_490]
0x180098a6c  mov     [rsp+4E0h+phkResult], rax; int
0x180098a71  mov     r9d, 2011Fh; samDesired
0x180098a77  xor     r8d, r8d; ulOptions
0x180098a7a  lea     rdx, [rbp+3E0h+SubKey]; lpSubKey
0x180098a7e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180098a85  call    cs:__imp_RegOpenKeyExW
0x180098a8b  mov     ebx, eax
0x180098a8d  lea     rcx, [rsp+4E0h+var_498]
0x180098a92  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180098a97  test    ebx, ebx
0x180098a99  jz      short loc_180098AAF
0x180098a9b  jle     loc_180098CFC
0x180098aa1  movzx   ebx, bx
0x180098aa4  or      ebx, 80070000h
0x180098aaa  jmp     loc_180098CFC
0x180098aaf  mov     [rsp+4E0h+String1], 0
0x180098ab8  lea     r9, [rsp+4E0h+String1]; unsigned __int16 **
0x180098abd  lea     r8, aOriginatingdoc; "OriginatingDocument"
0x180098ac4  xor     edx, edx; unsigned __int16 *
0x180098ac6  mov     rcx, [rsp+4E0h+hKey]; HKEY
0x180098acb  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180098ad0  test    eax, eax
0x180098ad2  js      loc_180098D40
0x180098ad8  mov     rcx, [rsp+4E0h+String1]; String1
0x180098add  mov     [rsp+4E0h+String1], rcx
0x180098ae2  cmp     qword ptr [r14+18h], 7
0x180098ae7  jbe     short loc_180098AEC
0x180098ae9  mov     r14, [r14]
0x180098aec  mov     r8d, 104h; MaxCount
0x180098af2  mov     rdx, r14; String2
0x180098af5  call    wcsncmp_0
0x180098afa  lea     rcx, [rsp+4E0h+String1]
0x180098aff  test    eax, eax
0x180098b01  jz      short loc_180098B12
0x180098b03  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180098b08  mov     ebx, 80070005h
0x180098b0d  jmp     loc_180098CFC
0x180098b12  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180098b17  xor     edx, edx; lpSubKey
0x180098b19  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180098b1e  call    cs:__imp_RegDeleteTreeW
0x180098b24  mov     r14d, 80070000h
0x180098b2a  test    eax, eax
0x180098b2c  jz      short loc_180098B64
0x180098b2e  jle     short loc_180098B36
0x180098b30  movzx   eax, ax
0x180098b33  or      eax, r14d
0x180098b36  xor     ebx, ebx
0x180098b38  cmp     eax, 80070002h
0x180098b3d  cmovnz  ebx, eax
0x180098b40  test    ebx, ebx
0x180098b42  jns     short loc_180098B64
0x180098b44  mov     r9d, ebx; char *
0x180098b47  mov     edx, 5F5Bh; void *
0x180098b4c  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180098b53  mov     rcx, [rbp+3E8h]; this
0x180098b5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098b5f  jmp     loc_180098CFC
0x180098b64  mov     [rsp+4E0h+var_4B0], 0
0x180098b6d  cmp     qword ptr [rdi+18h], 7
0x180098b72  jbe     short loc_180098B79
0x180098b74  mov     r9, [rdi]
0x180098b77  jmp     short loc_180098B7C
0x180098b79  mov     r9, rdi
0x180098b7c  mov     r8, cs:qword_18018A588; unsigned __int16 *
0x180098b83  mov     edx, 104h; unsigned __int64
0x180098b88  lea     rcx, [rbp+3E0h+var_240]; unsigned __int16 *
0x180098b8f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180098b94  mov     ebx, eax
0x180098b96  test    eax, eax
0x180098b98  jns     short loc_180098BBA
0x180098b9a  mov     rcx, [rbp+3E8h]; this
0x180098ba1  mov     r9d, eax; char *
0x180098ba4  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180098bab  mov     edx, 5F62h; void *
0x180098bb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098bb5  jmp     loc_180098CF1
0x180098bba  mov     rdx, r15
0x180098bbd  lea     rcx, [rsp+4E0h+lpSubKey]
0x180098bc2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180098bc7  nop
0x180098bc8  mov     r8d, 1
0x180098bce  lea     rdx, asc_18014D3A0; ":"
0x180098bd5  lea     rcx, [rsp+4E0h+lpSubKey]; Src
0x180098bda  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180098bdf  mov     r8, [rsi+10h]
0x180098be3  cmp     qword ptr [rsi+18h], 7
0x180098be8  jbe     short loc_180098BED
0x180098bea  mov     rsi, [rsi]
0x180098bed  mov     rdx, rsi
0x180098bf0  lea     rcx, [rsp+4E0h+lpSubKey]; Src
0x180098bf5  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180098bfa  lea     rax, [rsp+4E0h+var_4B0]
0x180098bff  mov     [rsp+4E0h+var_498], rax
0x180098c04  mov     [rsp+4E0h+var_490], 0
0x180098c0d  mov     [rsp+4E0h+var_488], 1
0x180098c12  lea     rax, [rsp+4E0h+var_490]
0x180098c17  mov     [rsp+4E0h+phkResult], rax; int
0x180098c1c  mov     r9d, 0F003Fh; samDesired
0x180098c22  xor     r8d, r8d; ulOptions
0x180098c25  lea     rdx, [rbp+3E0h+var_240]; lpSubKey
0x180098c2c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180098c33  call    cs:__imp_RegOpenKeyExW
0x180098c39  mov     ebx, eax
0x180098c3b  lea     rcx, [rsp+4E0h+var_498]
0x180098c40  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180098c45  test    ebx, ebx
0x180098c47  jz      short loc_180098C95
0x180098c49  jle     short loc_180098C51
0x180098c4b  movzx   ebx, bx
0x180098c4e  or      ebx, r14d
0x180098c51  xor     esi, esi
0x180098c53  cmp     ebx, 80070002h
0x180098c59  cmovnz  esi, ebx
0x180098c5c  test    esi, esi
0x180098c5e  jns     short loc_180098C95
0x180098c60  mov     rcx, [rbp+3E8h]; this
0x180098c67  mov     r9d, esi; char *
0x180098c6a  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180098c71  mov     edx, 5F76h; void *
0x180098c76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098c7b  nop
0x180098c7c  lea     rcx, [rsp+4E0h+lpSubKey]
0x180098c81  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180098c86  nop
0x180098c87  lea     rcx, [rsp+4E0h+var_4B0]
0x180098c8c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180098c91  mov     ebx, esi
0x180098c93  jmp     short loc_180098CFC
0x180098c95  lea     rdx, [rsp+4E0h+lpSubKey]
0x180098c9a  cmp     [rbp+3E0h+var_460], 7
0x180098c9f  cmova   rdx, [rsp+4E0h+lpSubKey]; lpSubKey
0x180098ca5  mov     rcx, [rsp+4E0h+var_4B0]; hKey
0x180098caa  call    cs:__imp_RegDeleteKeyW
0x180098cb0  test    eax, eax
0x180098cb2  jz      short loc_180098D13
0x180098cb4  jle     short loc_180098CBC
0x180098cb6  movzx   eax, ax
0x180098cb9  or      eax, r14d
0x180098cbc  xor     ebx, ebx
0x180098cbe  cmp     eax, 80070002h
0x180098cc3  cmovnz  ebx, eax
0x180098cc6  test    ebx, ebx
0x180098cc8  jns     short loc_180098D13
0x180098cca  mov     rcx, [rbp+3E8h]; this
0x180098cd1  mov     r9d, ebx; char *
0x180098cd4  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180098cdb  mov     edx, 5F81h; void *
0x180098ce0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098ce5  nop
0x180098ce6  lea     rcx, [rsp+4E0h+lpSubKey]
0x180098ceb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180098cf0  nop
0x180098cf1  lea     rcx, [rsp+4E0h+var_4B0]
0x180098cf6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180098cfb  nop
0x180098cfc  lea     rcx, [rsp+4E0h+hKey]
0x180098d01  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180098d06  nop
0x180098d07  mov     rcx, rdi
0x180098d0a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180098d0f  mov     eax, ebx
0x180098d11  jmp     short loc_180098D58
0x180098d13  lea     rcx, [rsp+4E0h+lpSubKey]
0x180098d18  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180098d1d  nop
0x180098d1e  lea     rcx, [rsp+4E0h+var_4B0]
0x180098d23  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180098d28  nop
0x180098d29  lea     rcx, [rsp+4E0h+hKey]
0x180098d2e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180098d33  nop
0x180098d34  mov     rcx, rdi
0x180098d37  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180098d3c  xor     eax, eax
0x180098d3e  jmp     short loc_180098D58
0x180098d40  lea     rcx, [rsp+4E0h+hKey]
0x180098d45  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180098d4a  nop
0x180098d4b  mov     rcx, rdi
0x180098d4e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180098d53  mov     eax, 80070057h
0x180098d58  mov     rcx, [rbp+3E0h+var_30]
0x180098d5f  xor     rcx, rsp; StackCookie
0x180098d62  call    __security_check_cookie
0x180098d67  mov     rbx, [rsp+4E0h+arg_8]
0x180098d6f  add     rsp, 4C0h
0x180098d76  pop     r15
0x180098d78  pop     r14
0x180098d7a  pop     rdi
0x180098d7b  pop     rsi
0x180098d7c  pop     rbp
0x180098d7d  retn
```
