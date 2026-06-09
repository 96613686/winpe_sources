# CLanguageComponentsInstallerHandler::GetAllUsersLanguages(void)

- ea: `0x180016ae0`
- end: `0x180016d50`
- name: `?GetAllUsersLanguages@CLanguageComponentsInstallerHandler@@AEBA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `624`
- prototype: `__int64 *__fastcall(__int64, __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180013e1c`
- `0x180014788`

## callees

- `0x180003520`
- `0x180005954`
- `0x180005a14`
- `0x180006380`
- `0x18000a7fc`
- `0x18000c32c`
- `0x180016ae0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016c22`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016c22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016b1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016bae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016cef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016cfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016b1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016bae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016cef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016cfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016c36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016c36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016b4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016c73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016b4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016c73`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x180016b9f`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x180016b9f`
- `Bcp47Langs!GetUserLanguagesForAllUsers` at `0x180016b37`
- `Bcp47Langs!GetUserLanguagesForAllUsers` at `0x180016b37`
- `Bcp47Langs!Bcp47FromLcid` at `0x180016bbe`
- `Bcp47Langs!Bcp47FromLcid` at `0x180016bbe`
- `Bcp47Langs!Bcp47GetDistance` at `0x180016c47`
- `Bcp47Langs!Bcp47GetDistance` at `0x180016c47`

## string_xrefs

- `0x180016d29`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`
- `0x180016d3e`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`

## pseudocode

```c
__int64 *__fastcall CLanguageComponentsInstallerHandler::GetAllUsersLanguages(__int64 a1, __int64 *a2)
{
  __int64 *v2; // rdi
  int UserLanguagesForAllUsers; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v5; // rsi
  __int64 v6; // r8
  unsigned int SystemDefaultUILanguage; // ebx
  int v8; // eax
  __int64 v9; // rbx
  __int64 v10; // r12
  HSTRING v11; // r13
  const WCHAR *v12; // r15
  unsigned __int64 v13; // r14
  PCWSTR v14; // rax
  _OWORD *v15; // rdx
  _OWORD hstringHeader[2]; // [rsp+20h] [rbp-49h] BYREF
  int v18; // [rsp+40h] [rbp-29h]
  __int64 *v19; // [rsp+48h] [rbp-21h]
  __int64 *v20; // [rsp+50h] [rbp-19h]
  HSTRING v21; // [rsp+58h] [rbp-11h] BYREF
  int v22; // [rsp+60h] [rbp-9h] BYREF
  HSTRING string; // [rsp+68h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v2 = a2;
  v19 = a2;
  v20 = a2;
  v18 = 0;
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  UserLanguagesForAllUsers = GetUserLanguagesForAllUsers(59, &string, 0, 0);
  if ( UserLanguagesForAllUsers < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x109,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
      (const char *)(unsigned int)UserLanguagesForAllUsers,
      hstringHeader[0]);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  memset(hstringHeader, 0, sizeof(hstringHeader));
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( StringRawBuffer[v6] );
  std::wstring::_Construct<1,unsigned short const *>(hstringHeader);
  WstringContainerFromDelimitedString<std::vector<std::wstring>>(v2, hstringHeader);
  std::wstring::~wstring(hstringHeader);
  v18 = 7;
  SystemDefaultUILanguage = GetSystemDefaultUILanguage();
  v21 = 0;
  WindowsDeleteString(0);
  v21 = 0;
  v8 = Bcp47FromLcid(SystemDefaultUILanguage, &v21);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x10E,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
      (const char *)(unsigned int)v8,
      hstringHeader[0]);
  v9 = *v2;
  v10 = v2[1];
  if ( *v2 != v10 )
  {
    do
    {
      v22 = 0;
      v11 = v21;
      if ( *(_QWORD *)(v9 + 24) <= 7u )
        v12 = (const WCHAR *)v9;
      else
        v12 = *(const WCHAR **)v9;
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
      if ( v13 > 0xFFFFFFFF )
      {
        LODWORD(v13) = -1;
        RaiseException(0xC000000D, 1u, 0, 0);
      }
      WindowsCreateStringReference(v12, v13, (HSTRING_HEADER *)((char *)hstringHeader + 8), (HSTRING *)hstringHeader);
      if ( (int)Bcp47GetDistance(*(_QWORD *)&hstringHeader[0], v11, &v22) >= 0 && !v22 )
        break;
      v9 += 32;
    }
    while ( v9 != v10 );
    v2 = v19;
  }
  if ( v9 == v2[1] )
  {
    v14 = WindowsGetStringRawBuffer(v21, 0);
    memset(hstringHeader, 0, sizeof(hstringHeader));
    do
      ++v5;
    while ( v14[v5] );
    std::wstring::_Construct<1,unsigned short const *>(hstringHeader);
    v15 = (_OWORD *)v2[1];
    if ( v15 == (_OWORD *)v2[2] )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v2, v15, hstringHeader);
    }
    else
    {
      *v15 = hstringHeader[0];
      v15[1] = hstringHeader[1];
      hstringHeader[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(hstringHeader[0]) = 0;
      v2[1] += 32;
    }
    std::wstring::~wstring(hstringHeader);
  }
  WindowsDeleteString(v21);
  v21 = 0;
  WindowsDeleteString(string);
  return v2;
}

```

## disassembly

```asm
0x180016ae0  push    rbp
0x180016ae2  push    rbx
0x180016ae3  push    rsi
0x180016ae4  push    rdi
0x180016ae5  push    r12
0x180016ae7  push    r13
0x180016ae9  push    r14
0x180016aeb  push    r15
0x180016aed  lea     rbp, [rsp-1Fh]
0x180016af2  sub     rsp, 88h
0x180016af9  mov     rax, cs:__security_cookie
0x180016b00  xor     rax, rsp
0x180016b03  mov     [rbp+57h+var_50], rax
0x180016b07  mov     rdi, rdx
0x180016b0a  mov     [rbp+57h+var_78], rdx
0x180016b0e  mov     [rbp+57h+var_70], rdx
0x180016b12  xor     r14d, r14d
0x180016b15  mov     [rbp+57h+var_80], r14d
0x180016b19  mov     [rbp+57h+string], r14
0x180016b1d  xor     ecx, ecx; string
0x180016b1f  call    cs:__imp_WindowsDeleteString
0x180016b25  mov     [rbp+57h+string], r14
0x180016b29  lea     ecx, [r14+3Bh]
0x180016b2d  xor     r9d, r9d
0x180016b30  xor     r8d, r8d
0x180016b33  lea     rdx, [rbp+57h+string]
0x180016b37  call    cs:__imp_GetUserLanguagesForAllUsers
0x180016b3d  mov     rcx, [rbp+5Fh]; this
0x180016b41  test    eax, eax
0x180016b43  js      loc_180016D3B
0x180016b49  xor     edx, edx; length
0x180016b4b  mov     rcx, [rbp+57h+string]; string
0x180016b4f  call    cs:__imp_WindowsGetStringRawBuffer
0x180016b55  xorps   xmm0, xmm0
0x180016b58  movups  xmmword ptr [rbp+57h+hstringHeader], xmm0
0x180016b5c  xorps   xmm1, xmm1
0x180016b5f  movdqu  xmmword ptr [rbp+57h+hstringHeader+10h], xmm1
0x180016b64  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180016b68  mov     r8, rsi
0x180016b6b  inc     r8
0x180016b6e  cmp     [rax+r8*2], r14w
0x180016b73  jnz     short loc_180016B6B
0x180016b75  mov     rdx, rax
0x180016b78  lea     rcx, [rbp+57h+hstringHeader]
0x180016b7c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180016b81  nop
0x180016b82  lea     rdx, [rbp+57h+hstringHeader]
0x180016b86  mov     rcx, rdi
0x180016b89  call    ??$WstringContainerFromDelimitedString@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@G@Z; WstringContainerFromDelimitedString<std::vector<std::wstring>>(std::wstring const &,ushort)
0x180016b8e  nop
0x180016b8f  lea     rcx, [rbp+57h+hstringHeader]; void *
0x180016b93  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016b98  mov     [rbp+57h+var_80], 7
0x180016b9f  call    cs:__imp_GetSystemDefaultUILanguage
0x180016ba5  movzx   ebx, ax
0x180016ba8  mov     [rbp+57h+var_68], r14
0x180016bac  xor     ecx, ecx; string
0x180016bae  call    cs:__imp_WindowsDeleteString
0x180016bb4  mov     [rbp+57h+var_68], r14
0x180016bb8  lea     rdx, [rbp+57h+var_68]
0x180016bbc  mov     ecx, ebx
0x180016bbe  call    cs:__imp_Bcp47FromLcid
0x180016bc4  mov     rcx, [rbp+5Fh]; this
0x180016bc8  test    eax, eax
0x180016bca  js      loc_180016D26
0x180016bd0  mov     rbx, [rdi]
0x180016bd3  mov     r12, [rdi+8]
0x180016bd7  cmp     rbx, r12
0x180016bda  jz      loc_180016C67
0x180016be0  mov     edi, 0FFFFFFFFh
0x180016be5  mov     [rbp+57h+var_60], r14d
0x180016be9  mov     r13, [rbp+57h+var_68]
0x180016bed  cmp     qword ptr [rbx+18h], 7
0x180016bf2  jbe     short loc_180016BF9
0x180016bf4  mov     r15, [rbx]
0x180016bf7  jmp     short loc_180016BFC
0x180016bf9  mov     r15, rbx
0x180016bfc  mov     r14, rsi
0x180016bff  xor     eax, eax
0x180016c01  inc     r14
0x180016c04  cmp     [r15+r14*2], ax
0x180016c09  jnz     short loc_180016C01
0x180016c0b  cmp     r14, rdi
0x180016c0e  jbe     short loc_180016C28
0x180016c10  mov     r14d, edi
0x180016c13  xor     r9d, r9d; lpArguments
0x180016c16  xor     r8d, r8d; nNumberOfArguments
0x180016c19  lea     edx, [r9+1]; dwExceptionFlags
0x180016c1d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180016c22  call    cs:__imp_RaiseException
0x180016c28  lea     r9, [rbp+57h+hstringHeader]; string
0x180016c2c  lea     r8, [rbp+57h+hstringHeader+8]; hstringHeader
0x180016c30  mov     edx, r14d; length
0x180016c33  mov     rcx, r15; sourceString
0x180016c36  call    cs:__imp_WindowsCreateStringReference
0x180016c3c  lea     r8, [rbp+57h+var_60]
0x180016c40  mov     rdx, r13
0x180016c43  mov     rcx, qword ptr [rbp+57h+hstringHeader]
0x180016c47  call    cs:__imp_Bcp47GetDistance
0x180016c4d  xor     r14d, r14d
0x180016c50  test    eax, eax
0x180016c52  js      short loc_180016C5A
0x180016c54  cmp     [rbp+57h+var_60], r14d
0x180016c58  jz      short loc_180016C63
0x180016c5a  add     rbx, 20h ; ' '
0x180016c5e  cmp     rbx, r12
0x180016c61  jnz     short loc_180016BE5
0x180016c63  mov     rdi, [rbp+57h+var_78]
0x180016c67  cmp     rbx, [rdi+8]
0x180016c6b  jnz     short loc_180016CEB
0x180016c6d  xor     edx, edx; length
0x180016c6f  mov     rcx, [rbp+57h+var_68]; string
0x180016c73  call    cs:__imp_WindowsGetStringRawBuffer
0x180016c79  xorps   xmm0, xmm0
0x180016c7c  movups  xmmword ptr [rbp+57h+hstringHeader], xmm0
0x180016c80  xorps   xmm1, xmm1
0x180016c83  movdqu  xmmword ptr [rbp+57h+hstringHeader+10h], xmm1
0x180016c88  inc     rsi
0x180016c8b  cmp     [rax+rsi*2], r14w
0x180016c90  jnz     short loc_180016C88
0x180016c92  mov     r8, rsi
0x180016c95  mov     rdx, rax
0x180016c98  lea     rcx, [rbp+57h+hstringHeader]
0x180016c9c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180016ca1  nop
0x180016ca2  mov     rdx, [rdi+8]
0x180016ca6  cmp     rdx, [rdi+10h]
0x180016caa  jz      short loc_180016CD4
0x180016cac  movups  xmm0, xmmword ptr [rbp+57h+hstringHeader]
0x180016cb0  movups  xmmword ptr [rdx], xmm0
0x180016cb3  movups  xmm1, xmmword ptr [rbp+57h+hstringHeader+10h]
0x180016cb7  movups  xmmword ptr [rdx+10h], xmm1
0x180016cbb  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180016cc3  movdqu  xmmword ptr [rbp+57h+hstringHeader+10h], xmm0
0x180016cc8  mov     word ptr [rbp+57h+hstringHeader], r14w
0x180016ccd  add     qword ptr [rdi+8], 20h ; ' '
0x180016cd2  jmp     short loc_180016CE1
0x180016cd4  lea     r8, [rbp+57h+hstringHeader]
0x180016cd8  mov     rcx, rdi
0x180016cdb  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180016ce0  nop
0x180016ce1  lea     rcx, [rbp+57h+hstringHeader]; void *
0x180016ce5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016cea  nop
0x180016ceb  mov     rcx, [rbp+57h+var_68]; string
0x180016cef  call    cs:__imp_WindowsDeleteString
0x180016cf5  mov     [rbp+57h+var_68], r14
0x180016cf9  mov     rcx, [rbp+57h+string]; string
0x180016cfd  call    cs:__imp_WindowsDeleteString
0x180016d03  mov     rax, rdi
0x180016d06  mov     rcx, [rbp+57h+var_50]
0x180016d0a  xor     rcx, rsp; StackCookie
0x180016d0d  call    __security_check_cookie
0x180016d12  add     rsp, 88h
0x180016d19  pop     r15
0x180016d1b  pop     r14
0x180016d1d  pop     r13
0x180016d1f  pop     r12
0x180016d21  pop     rdi
0x180016d22  pop     rsi
0x180016d23  pop     rbx
0x180016d24  pop     rbp
0x180016d25  retn
0x180016d26  mov     r9d, eax; char *
0x180016d29  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x180016d30  mov     edx, 10Eh; void *
0x180016d35  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016d3b  mov     r9d, eax; char *
0x180016d3e  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x180016d45  mov     edx, 109h; void *
0x180016d4a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
