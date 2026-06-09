# DecodeBase64ToBinaryAndSaveToRegistry

- ea: `0x18010ca28`
- end: `0x18010cdfd`
- name: `DecodeBase64ToBinaryAndSaveToRegistry`
- size: `981`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010f334`
- `0x18011a3cc`

## callees

- `0x180021878`
- `0x18003164c`
- `0x1800328b8`
- `0x180036da4`
- `0x180037f6c`
- `0x1800467e0`
- `0x1800472cc`
- `0x18004d8f4`
- `0x1800b4e44`
- `0x180103f98`
- `0x18010ca28`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010cb70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010cbae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010cc1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010cc73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010cb70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010cbae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010cc1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010cc73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010cc68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010cd13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010cd30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010cd87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010cc68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010cd13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010cd30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010cd87`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010caa8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010cccb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010caa8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010cccb`
- `CRYPT32!CryptStringToBinaryA` at `0x18010cb56`
- `CRYPT32!CryptStringToBinaryA` at `0x18010cc05`
- `CRYPT32!CryptStringToBinaryA` at `0x18010cb56`
- `CRYPT32!CryptStringToBinaryA` at `0x18010cc05`

## string_xrefs

- `0x18010cabd`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010cb98`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010cc43`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010cce0`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010cd66`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010cdc4`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DecodeBase64ToBinaryAndSaveToRegistry(HKEY hKey, const BYTE **a2, _DWORD *a3, DWORD *a4, void **a5)
{
  const WCHAR *v9; // rdx
  const BYTE *v10; // rdi
  __int64 v11; // rax
  unsigned int v12; // eax
  __int64 v14; // rax
  const CHAR *v15; // rcx
  BOOL v16; // eax
  signed int LastError; // eax
  signed int v18; // ebx
  signed int v19; // eax
  const CHAR *v20; // rcx
  signed int v21; // eax
  BYTE *v22; // rcx
  signed int v23; // eax
  const WCHAR *v24; // rdx
  BYTE *v25; // r8
  unsigned int v26; // eax
  BYTE *v27; // rcx
  void *v28; // rax
  BYTE *v29; // rcx
  bool v30; // zf
  wil *v31; // rcx
  int v32; // eax
  int lpData; // [rsp+20h] [rbp-D8h]
  int lpDataa; // [rsp+20h] [rbp-D8h]
  unsigned int lpDatab; // [rsp+20h] [rbp-D8h]
  int lpDatac; // [rsp+20h] [rbp-D8h]
  int lpDatad; // [rsp+20h] [rbp-D8h]
  unsigned int lpDatae; // [rsp+20h] [rbp-D8h]
  BYTE *pbBinary; // [rsp+40h] [rbp-B8h] BYREF
  DWORD pcbBinary; // [rsp+48h] [rbp-B0h] BYREF
  signed int v41; // [rsp+4Ch] [rbp-ACh]
  LPCSTR pszString[3]; // [rsp+50h] [rbp-A8h] BYREF
  unsigned __int64 v43; // [rsp+68h] [rbp-90h]
  _BYTE v44[32]; // [rsp+70h] [rbp-88h] BYREF
  _BYTE v45[32]; // [rsp+90h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  if ( *a3 )
  {
    if ( *a3 != 1 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x28,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)0x80070057LL,
          lpDataa);
      return 2147942487LL;
    }
    v9 = L"Base64EncodedUtf16DarkLogo";
  }
  else
  {
    v9 = L"Base64EncodedUtf16LightLogo";
  }
  v10 = *a2;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)&v10[2 * v11] );
  v12 = RegSetValueExW(hKey, v9, 0, 1u, v10, 2 * v11);
  if ( v12 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x31,
             (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
             (const char *)v12,
             lpDatab);
  std::string::string(pszString);
  try
  {
    std::wstring::wstring(v44, v10);
    v14 = anonymous_namespace_::Utf16ToUtf8(v45, v44);
    std::string::operator=(pszString, v14);
    std::string::_Tidy_deallocate(v45);
    std::wstring::_Tidy_deallocate(v44);
    pcbBinary = 0;
    v15 = (const CHAR *)pszString;
    if ( v43 > 0xF )
      v15 = pszString[0];
    v16 = CryptStringToBinaryA(v15, 0, 1u, 0, &pcbBinary, 0, 0);
  }
  catch ( ... )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      v32 = wil::ResultFromCaughtException(v31);
      v41 = v32;
      if ( v32 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3C,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)(unsigned int)v32,
          lpData);
    }
    else
    {
      v41 = wil::ResultFromCaughtException(v31);
    }
    v18 = v41;
    goto LABEL_52;
  }
  if ( !v16 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      LastError = GetLastError();
      v18 = LastError;
      if ( LastError > 0 )
        v18 = (unsigned __int16)LastError | 0x80070000;
      if ( v18 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x50,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)(unsigned int)v18,
          lpDatac);
    }
    else
    {
      v19 = GetLastError();
      if ( v19 > 0 )
        v19 = (unsigned __int16)v19 | 0x80070000;
      v18 = v19;
    }
LABEL_52:
    std::string::_Tidy_deallocate(pszString);
    return (unsigned int)v18;
  }
  wil::make_unique_hlocal<unsigned char [0]>(&pbBinary, pcbBinary);
  v20 = (const CHAR *)pszString;
  if ( v43 > 0xF )
    v20 = pszString[0];
  if ( !CryptStringToBinaryA(v20, 0, 1u, pbBinary, &pcbBinary, 0, 0) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      v21 = GetLastError();
      v18 = v21;
      if ( v21 > 0 )
        v18 = (unsigned __int16)v21 | 0x80070000;
      if ( v18 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x64,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)(unsigned int)v18,
          lpDatad);
    }
    else
    {
      v23 = GetLastError();
      v18 = v23;
      if ( v23 > 0 )
        v18 = (unsigned __int16)v23 | 0x80070000;
    }
    goto LABEL_30;
  }
  if ( *a3 )
  {
    if ( *a3 != 1 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x79,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)0x80070057LL,
          lpDatad);
      v29 = pbBinary;
      v30 = pbBinary == 0;
      pbBinary = 0;
      if ( !v30 )
        LocalFree(v29);
      v18 = -2147024809;
      goto LABEL_52;
    }
    v24 = L"DecodedUftf8DarkLogo";
  }
  else
  {
    v24 = L"DecodedUtf8LightLogo";
  }
  v25 = pbBinary;
  if ( pbBinary )
  {
    v26 = RegSetValueExW(hKey, v24, 0, 3u, pbBinary, pcbBinary);
    if ( v26 )
    {
      v18 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x84,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)v26,
              lpDatae);
LABEL_30:
      v22 = pbBinary;
      pbBinary = 0;
      if ( v22 )
        LocalFree(v22);
      goto LABEL_52;
    }
    v25 = pbBinary;
  }
  v27 = 0;
  pbBinary = 0;
  v28 = *a5;
  *a5 = v25;
  if ( v28 )
  {
    LocalFree(v28);
    v27 = pbBinary;
  }
  *a4 = pcbBinary;
  pbBinary = 0;
  if ( v27 )
    LocalFree(v27);
  std::string::_Tidy_deallocate(pszString);
  return 0;
}

```

## disassembly

```asm
0x18010ca28  push    rbx
0x18010ca2a  push    rsi
0x18010ca2b  push    rdi
0x18010ca2c  push    r12
0x18010ca2e  push    r13
0x18010ca30  push    r14
0x18010ca32  push    r15
0x18010ca34  sub     rsp, 0C0h
0x18010ca3b  mov     rax, cs:__security_cookie
0x18010ca42  xor     rax, rsp
0x18010ca45  mov     [rsp+0F8h+var_48], rax
0x18010ca4d  mov     r12, r9
0x18010ca50  mov     r14, r8
0x18010ca53  mov     rdi, rdx
0x18010ca56  mov     r15, rcx
0x18010ca59  mov     rsi, [rsp+0F8h+arg_20]
0x18010ca61  xor     r13d, r13d
0x18010ca64  lea     ebx, [r13+1]
0x18010ca68  cmp     [r8], r13d
0x18010ca6b  jnz     short loc_18010CA76
0x18010ca6d  lea     rdx, aBase64encodedu; "Base64EncodedUtf16LightLogo"
0x18010ca74  jmp     short loc_18010CA86
0x18010ca76  cmp     [r8], ebx
0x18010ca79  jnz     loc_18010CDA6
0x18010ca7f  lea     rdx, aBase64encodedu_0; "Base64EncodedUtf16DarkLogo"
0x18010ca86  mov     rdi, [rdi]
0x18010ca89  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010ca8d  inc     rax
0x18010ca90  cmp     [rdi+rax*2], r13w
0x18010ca95  jnz     short loc_18010CA8D
0x18010ca97  add     eax, eax
0x18010ca99  mov     [rsp+0F8h+cbData], eax; cbData
0x18010ca9d  mov     [rsp+0F8h+lpData], rdi; unsigned int
0x18010caa2  mov     r9d, ebx; dwType
0x18010caa5  xor     r8d, r8d; Reserved
0x18010caa8  call    cs:__imp_RegSetValueExW
0x18010caae  test    eax, eax
0x18010cab0  jz      short loc_18010CAD3
0x18010cab2  mov     rcx, [rsp+0F8h]; this
0x18010caba  mov     r9d, eax; char *
0x18010cabd  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010cac4  mov     edx, 31h ; '1'; void *
0x18010cac9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010cace  jmp     loc_18010CDDA
0x18010cad3  lea     rcx, [rsp+0F8h+pszString]
0x18010cad8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18010cadd  nop
0x18010cade  mov     rdx, rdi
0x18010cae1  lea     rcx, [rsp+0F8h+var_88]
0x18010cae6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010caeb  nop
0x18010caec  lea     rdx, [rsp+0F8h+var_88]
0x18010caf1  lea     rcx, [rsp+0F8h+var_68]
0x18010caf9  call    _anonymous_namespace___Utf16ToUtf8
0x18010cafe  mov     rdx, rax
0x18010cb01  lea     rcx, [rsp+0F8h+pszString]
0x18010cb06  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18010cb0b  lea     rcx, [rsp+0F8h+var_68]
0x18010cb13  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010cb18  nop
0x18010cb19  lea     rcx, [rsp+0F8h+var_88]
0x18010cb1e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010cb23  nop
0x18010cb24  mov     [rsp+0F8h+pcbBinary], r13d
0x18010cb29  lea     rcx, [rsp+0F8h+pszString]
0x18010cb2e  cmp     [rsp+0F8h+var_90], 0Fh
0x18010cb34  cmova   rcx, [rsp+0F8h+pszString]; pszString
0x18010cb3a  mov     [rsp+0F8h+pdwFlags], r13; pdwFlags
0x18010cb3f  mov     qword ptr [rsp+0F8h+cbData], r13; pdwSkip
0x18010cb44  lea     rax, [rsp+0F8h+pcbBinary]
0x18010cb49  mov     [rsp+0F8h+lpData], rax; int
0x18010cb4e  xor     r9d, r9d; pbBinary
0x18010cb51  mov     r8d, ebx; dwFlags
0x18010cb54  xor     edx, edx; cchString
0x18010cb56  call    cs:__imp_CryptStringToBinaryA
0x18010cb5c  test    eax, eax
0x18010cb5e  jnz     short loc_18010CBC7
0x18010cb60  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x18010cb67  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x18010cb6c  test    al, al
0x18010cb6e  jz      short loc_18010CBAE
0x18010cb70  call    cs:__imp_GetLastError
0x18010cb76  mov     ebx, eax
0x18010cb78  test    eax, eax
0x18010cb7a  jle     short loc_18010CB85
0x18010cb7c  movzx   ebx, ax
0x18010cb7f  or      ebx, 80070000h
0x18010cb85  test    ebx, ebx
0x18010cb87  jns     loc_18010CD98
0x18010cb8d  mov     rcx, [rsp+0F8h]; this
0x18010cb95  mov     r9d, ebx; char *
0x18010cb98  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010cb9f  mov     edx, 50h ; 'P'; void *
0x18010cba4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010cba9  jmp     loc_18010CD98
0x18010cbae  call    cs:__imp_GetLastError
0x18010cbb4  test    eax, eax
0x18010cbb6  jle     short loc_18010CBC0
0x18010cbb8  movzx   eax, ax
0x18010cbbb  or      eax, 80070000h
0x18010cbc0  mov     ebx, eax
0x18010cbc2  jmp     loc_18010CD98
0x18010cbc7  mov     edx, [rsp+0F8h+pcbBinary]
0x18010cbcb  lea     rcx, [rsp+0F8h+pbBinary]
0x18010cbd0  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x18010cbd5  nop
0x18010cbd6  lea     rcx, [rsp+0F8h+pszString]
0x18010cbdb  cmp     [rsp+0F8h+var_90], 0Fh
0x18010cbe1  cmova   rcx, [rsp+0F8h+pszString]; pszString
0x18010cbe7  mov     [rsp+0F8h+pdwFlags], r13; pdwFlags
0x18010cbec  mov     qword ptr [rsp+0F8h+cbData], r13; pdwSkip
0x18010cbf1  lea     rax, [rsp+0F8h+pcbBinary]
0x18010cbf6  mov     [rsp+0F8h+lpData], rax; int
0x18010cbfb  mov     r9, [rsp+0F8h+pbBinary]; pbBinary
0x18010cc00  mov     r8d, ebx; dwFlags
0x18010cc03  xor     edx, edx; cchString
0x18010cc05  call    cs:__imp_CryptStringToBinaryA
0x18010cc0b  test    eax, eax
0x18010cc0d  jnz     short loc_18010CC8A
0x18010cc0f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x18010cc16  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x18010cc1b  test    al, al
0x18010cc1d  jz      short loc_18010CC73
0x18010cc1f  call    cs:__imp_GetLastError
0x18010cc25  mov     ebx, eax
0x18010cc27  test    eax, eax
0x18010cc29  jle     short loc_18010CC34
0x18010cc2b  movzx   ebx, ax
0x18010cc2e  or      ebx, 80070000h
0x18010cc34  test    ebx, ebx
0x18010cc36  jns     short loc_18010CC55
0x18010cc38  mov     rcx, [rsp+0F8h]; this
0x18010cc40  mov     r9d, ebx; char *
0x18010cc43  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010cc4a  mov     edx, 64h ; 'd'; void *
0x18010cc4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010cc54  nop
0x18010cc55  mov     rcx, [rsp+0F8h+pbBinary]; hMem
0x18010cc5a  mov     [rsp+0F8h+pbBinary], r13
0x18010cc5f  test    rcx, rcx
0x18010cc62  jz      loc_18010CD98
0x18010cc68  call    cs:__imp_LocalFree
0x18010cc6e  jmp     loc_18010CD98
0x18010cc73  call    cs:__imp_GetLastError
0x18010cc79  mov     ebx, eax
0x18010cc7b  test    eax, eax
0x18010cc7d  jle     short loc_18010CC55
0x18010cc7f  movzx   ebx, ax
0x18010cc82  or      ebx, 80070000h
0x18010cc88  jmp     short loc_18010CC55
0x18010cc8a  cmp     [r14], r13d
0x18010cc8d  jnz     short loc_18010CC98
0x18010cc8f  lea     rdx, aDecodedutf8lig; "DecodedUtf8LightLogo"
0x18010cc96  jmp     short loc_18010CCA8
0x18010cc98  cmp     [r14], ebx
0x18010cc9b  jnz     loc_18010CD48
0x18010cca1  lea     rdx, aDecodeduftf8da; "DecodedUftf8DarkLogo"
0x18010cca8  mov     r8, [rsp+0F8h+pbBinary]
0x18010ccad  test    r8, r8
0x18010ccb0  jz      short loc_18010CCFD
0x18010ccb2  mov     eax, [rsp+0F8h+pcbBinary]
0x18010ccb6  mov     [rsp+0F8h+cbData], eax; cbData
0x18010ccba  mov     [rsp+0F8h+lpData], r8; unsigned int
0x18010ccbf  mov     r9d, 3; dwType
0x18010ccc5  xor     r8d, r8d; Reserved
0x18010ccc8  mov     rcx, r15; hKey
0x18010cccb  call    cs:__imp_RegSetValueExW
0x18010ccd1  test    eax, eax
0x18010ccd3  jz      short loc_18010CCF8
0x18010ccd5  mov     rcx, [rsp+0F8h]; this
0x18010ccdd  mov     r9d, eax; char *
0x18010cce0  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010cce7  mov     edx, 84h; void *
0x18010ccec  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010ccf1  mov     ebx, eax
0x18010ccf3  jmp     loc_18010CC55
0x18010ccf8  mov     r8, [rsp+0F8h+pbBinary]
0x18010ccfd  mov     rcx, r13
0x18010cd00  mov     [rsp+0F8h+pbBinary], rcx
0x18010cd05  mov     rax, [rsi]
0x18010cd08  mov     [rsi], r8
0x18010cd0b  test    rax, rax
0x18010cd0e  jz      short loc_18010CD1E
0x18010cd10  mov     rcx, rax; hMem
0x18010cd13  call    cs:__imp_LocalFree
0x18010cd19  mov     rcx, [rsp+0F8h+pbBinary]; hMem
0x18010cd1e  mov     eax, [rsp+0F8h+pcbBinary]
0x18010cd22  mov     [r12], eax
0x18010cd26  mov     [rsp+0F8h+pbBinary], r13
0x18010cd2b  test    rcx, rcx
0x18010cd2e  jz      short loc_18010CD37
0x18010cd30  call    cs:__imp_LocalFree
0x18010cd36  nop
0x18010cd37  lea     rcx, [rsp+0F8h+pszString]
0x18010cd3c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010cd41  xor     eax, eax
0x18010cd43  jmp     loc_18010CDDA
0x18010cd48  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x18010cd4f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x18010cd54  test    al, al
0x18010cd56  jz      short loc_18010CD78
0x18010cd58  mov     rcx, [rsp+0F8h]; this
0x18010cd60  mov     r9d, 80070057h; char *
0x18010cd66  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010cd6d  mov     edx, 79h ; 'y'; void *
0x18010cd72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010cd77  nop
0x18010cd78  mov     rcx, [rsp+0F8h+pbBinary]; hMem
0x18010cd7d  test    rcx, rcx
0x18010cd80  mov     [rsp+0F8h+pbBinary], r13
0x18010cd85  jz      short loc_18010CD8D
0x18010cd87  call    cs:__imp_LocalFree
0x18010cd8d  mov     ebx, 80070057h
0x18010cd92  jmp     short loc_18010CD98
0x18010cd94  mov     ebx, [rsp+0F8h+var_AC]
0x18010cd98  lea     rcx, [rsp+0F8h+pszString]
0x18010cd9d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010cda2  mov     eax, ebx
0x18010cda4  jmp     short loc_18010CDDA
0x18010cda6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x18010cdad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x18010cdb2  test    al, al
0x18010cdb4  jz      short loc_18010CDD5
0x18010cdb6  mov     rcx, [rsp+0F8h]; this
0x18010cdbe  mov     r9d, 80070057h; char *
0x18010cdc4  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010cdcb  mov     edx, 28h ; '('; void *
0x18010cdd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010cdd5  mov     eax, 80070057h
0x18010cdda  mov     rcx, [rsp+0F8h+var_48]
0x18010cde2  xor     rcx, rsp; StackCookie
0x18010cde5  call    __security_check_cookie
0x18010cdea  add     rsp, 0C0h
0x18010cdf1  pop     r15
0x18010cdf3  pop     r14
0x18010cdf5  pop     r13
0x18010cdf7  pop     r12
0x18010cdf9  pop     rdi
0x18010cdfa  pop     rsi
0x18010cdfb  pop     rbx
0x18010cdfc  retn
```
