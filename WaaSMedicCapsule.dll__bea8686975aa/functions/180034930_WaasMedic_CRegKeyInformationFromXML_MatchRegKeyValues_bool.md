# WaasMedic::CRegKeyInformationFromXML::MatchRegKeyValues(bool *)

- ea: `0x180034930`
- end: `0x180034ef7`
- name: `?MatchRegKeyValues@CRegKeyInformationFromXML@WaasMedic@@QEAAJPEA_N@Z`
- size: `1479`
- prototype: `__int64 __fastcall(WaasMedic::CRegKeyInformationFromXML *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004bc00`

## callees

- `0x180003bb0`
- `0x180003bd4`
- `0x1800040b8`
- `0x180005e1c`
- `0x180007590`
- `0x180009a54`
- `0x18000b308`
- `0x18002543c`
- `0x1800281c8`
- `0x1800334b0`
- `0x180033f58`
- `0x180034930`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180034d8a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180034e9f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180034d8a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180034e9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800349f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800349f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034a06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034a06`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034ab4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034b12`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034ab4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034b12`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034a36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034a36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800349cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800349dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800349fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034cf2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034d01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034dea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034df9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034eb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034ec8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800349cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800349dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800349fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034cf2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034d01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034dea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034df9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034eb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034ec8`

## string_xrefs

- `0x180034e06`: `key is not accessible: %s`
- `0x180034d5c`: `Registry Value for %ws under %ws is 0.`
- `0x180034db6`: `Failed to open reg key for %ws`
- `0x180034b93`: `RegistryValue type of %s under %s doesn't match. Expected: %s, actual: %s.`
- `0x180034cb5`: `Failed to compare registryValue`
- `0x180034bf7`: `RegistryValue %s not found under %s`
- `0x180034bcd`: `Failed to read RegistryValue %s under %s, hr = 0x%08x`
- `0x180034c30`: `Failed to get size of RegistryValue %s under %s, hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WaasMedic::CRegKeyInformationFromXML::MatchRegKeyValues(
        WaasMedic::CRegKeyInformationFromXML *this,
        bool *a2)
{
  bool *v2; // r15
  WaasMedic::CRegKeyInformationFromXML *v3; // rsi
  int RootKeyAndSubKeyFromPath; // eax
  unsigned int v5; // ebx
  const WCHAR *v7; // rdx
  HKEY v8; // rbx
  LSTATUS v9; // eax
  unsigned int v10; // edi
  _QWORD *v11; // r13
  __int64 *v12; // rdi
  void *v13; // rsi
  const WCHAR *v14; // rdx
  int v15; // eax
  const WCHAR *v16; // rdx
  unsigned int v17; // edx
  const struct std::nothrow_t *v18; // rdx
  int v19; // r14d
  bool v20; // al
  unsigned int v21; // eax
  __int64 v22; // r10
  unsigned __int16 *v23; // rax
  __int64 v24; // rdx
  _QWORD *v25; // r10
  LPCWSTR *v26; // r9
  LPCWSTR *v27; // r9
  _QWORD *v28; // r8
  const unsigned __int16 *v29; // rdx
  LPCWSTR *v30; // r9
  _QWORD *v31; // r8
  __int64 v32; // r14
  __int64 v33; // r15
  _QWORD *v34; // rax
  _QWORD *v35; // rcx
  const struct std::nothrow_t *v36; // rdx
  LPCWSTR *v37; // rdx
  const char *v38; // rax
  LPCWSTR *v39; // rax
  const unsigned __int16 *v40; // rdx
  LPCWSTR *v41; // r8
  _QWORD *v42; // rdi
  __int64 v43; // rsi
  __int64 v44; // r14
  _QWORD *v45; // rax
  _QWORD *v46; // rcx
  int phkResult; // [rsp+20h] [rbp-69h]
  PHKEY phkResulta; // [rsp+20h] [rbp-69h]
  const char *lpcbData; // [rsp+28h] [rbp-61h]
  bool v50; // [rsp+40h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-41h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-39h] BYREF
  DWORD Type; // [rsp+54h] [rbp-35h] BYREF
  HKEY v54; // [rsp+58h] [rbp-31h] BYREF
  WaasMedic::CRegKeyInformationFromXML *v55; // [rsp+60h] [rbp-29h]
  _QWORD *v56; // [rsp+68h] [rbp-21h]
  __int64 v57; // [rsp+70h] [rbp-19h]
  void *v58; // [rsp+78h] [rbp-11h]
  bool *v59; // [rsp+80h] [rbp-9h]
  LPCWSTR lpSubKey[2]; // [rsp+88h] [rbp-1h] BYREF
  __int64 v61; // [rsp+98h] [rbp+Fh]
  unsigned __int64 v62; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v2 = a2;
  v59 = a2;
  v3 = this;
  v55 = this;
  *a2 = 1;
  hKey = 0;
  *(_OWORD *)lpSubKey = 0;
  v61 = 0;
  v62 = 7;
  LOWORD(lpSubKey[0]) = 0;
  v54 = 0;
  RootKeyAndSubKeyFromPath = WaasMedic::RegGetRootKeyAndSubKeyFromPath(this, &v54, lpSubKey);
  v5 = RootKeyAndSubKeyFromPath;
  if ( RootKeyAndSubKeyFromPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5FE,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
      (const char *)(unsigned int)RootKeyAndSubKeyFromPath,
      phkResult);
    std::wstring::~wstring(lpSubKey);
    if ( v54 )
      RegCloseKey(v54);
    return v5;
  }
  hKey = 0;
  v7 = (const WCHAR *)lpSubKey;
  if ( v62 > 7 )
    v7 = lpSubKey[0];
  v8 = v54;
  v9 = RegOpenKeyExW(v54, v7, 0, 1u, &hKey);
  v10 = v9;
  v11 = (_QWORD *)((char *)v3 + 80);
  switch ( v9 )
  {
    case 2:
      v40 = L"Missing reg key: %s";
LABEL_81:
      v41 = lpSubKey;
      if ( v62 > 7 )
        v41 = (LPCWSTR *)lpSubKey[0];
      LogLevelW(3u, v40, v41);
      *v2 = 0;
      v42 = (_QWORD *)*((_QWORD *)v3 + 8);
      while ( 1 )
      {
        v42 = (_QWORD *)*v42;
        if ( v42 == *((_QWORD **)v3 + 8) )
          break;
        if ( v11[1] == 0xAAAAAAAAAAAAAAALL )
          std::_Xlength_error("list too long");
        v43 = v42[2];
        v44 = *v11;
        v56 = v11;
        v57 = 0;
        v45 = operator new(0x18u);
        v45[2] = v43;
        ++v11[1];
        v46 = *(_QWORD **)(v44 + 8);
        *v45 = v44;
        v45[1] = v46;
        v57 = 0;
        *(_QWORD *)(v44 + 8) = v45;
        *v46 = v45;
        v3 = v55;
      }
LABEL_88:
      std::wstring::~wstring(lpSubKey);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v8 )
        RegCloseKey(v8);
      return 0;
    case 5:
      v40 = L"key is not accessible: %s";
      goto LABEL_81;
    case 0:
      v12 = (__int64 *)*((_QWORD *)v3 + 8);
      while ( 1 )
      {
        v12 = (__int64 *)*v12;
        if ( v12 == *((__int64 **)v3 + 8) )
          goto LABEL_88;
        Type = 0;
        v13 = 0;
        v58 = 0;
        cbData = 0;
        v50 = 1;
        v14 = (const WCHAR *)v12[2];
        if ( *((_QWORD *)v14 + 3) > 7u )
          v14 = *(const WCHAR **)v14;
        v15 = RegQueryValueExW(hKey, v14, 0, &Type, 0, &cbData);
        if ( !v15 )
          break;
        if ( v15 != 2 )
        {
          if ( v15 > 0 )
            v15 = (unsigned __int16)v15 | 0x80070000;
          v27 = lpSubKey;
          if ( v62 > 7 )
            v27 = (LPCWSTR *)lpSubKey[0];
          v28 = (_QWORD *)v12[2];
          if ( v28[3] > 7u )
            v28 = (_QWORD *)*v28;
          v29 = L"Failed to get size of RegistryValue %s under %s, hr = 0x%08x";
LABEL_48:
          LODWORD(phkResulta) = v15;
          LogLevelW(3u, v29, v28, v27, phkResulta);
LABEL_49:
          v20 = 0;
          goto LABEL_50;
        }
        v30 = lpSubKey;
        if ( v62 > 7 )
          v30 = (LPCWSTR *)lpSubKey[0];
        v31 = (_QWORD *)v12[2];
        if ( v31[3] > 7u )
          v31 = (_QWORD *)*v31;
        LogLevelW(3u, L"RegistryValue %s not found under %s", v31, v30);
LABEL_51:
        *v2 = 0;
        if ( v11[1] == 0xAAAAAAAAAAAAAAALL )
          std::_Xlength_error("list too long");
        v32 = v12[2];
        v33 = *v11;
        v56 = v11;
        v57 = 0;
        v34 = operator new(0x18u);
        v34[2] = v32;
        ++v11[1];
        v35 = *(_QWORD **)(v33 + 8);
        *v34 = v33;
        v34[1] = v35;
        v57 = 0;
        *(_QWORD *)(v33 + 8) = v34;
        *v35 = v34;
        v2 = v59;
LABEL_53:
        if ( v13 )
          operator delete(v13, v18);
        v3 = v55;
      }
      if ( !cbData )
      {
        v37 = lpSubKey;
        if ( v62 > 7 )
          v37 = (LPCWSTR *)lpSubKey[0];
        v38 = (const char *)v12[2];
        if ( *((_QWORD *)v38 + 3) > 7u )
          v38 = *(const char **)v38;
        v10 = -2147024809;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x635,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
          (const char *)0x80070057LL,
          (int)"Registry Value for %ws under %ws is 0.",
          v38,
          v37);
        goto LABEL_74;
      }
      v13 = operator new[](cbData, (const struct std::nothrow_t *)&std::nothrow);
      v58 = v13;
      if ( !v13 )
      {
        v10 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x637,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
          (const char *)0x8007000ELL,
          (int)phkResulta);
        goto LABEL_74;
      }
      v16 = (const WCHAR *)v12[2];
      if ( *((_QWORD *)v16 + 3) > 7u )
        v16 = *(const WCHAR **)v16;
      v15 = RegQueryValueExW(hKey, v16, 0, &Type, (LPBYTE)v13, &cbData);
      if ( v15 )
      {
        if ( v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
        v27 = lpSubKey;
        if ( v62 > 7 )
          v27 = (LPCWSTR *)lpSubKey[0];
        v28 = (_QWORD *)v12[2];
        if ( v28[3] > 7u )
          v28 = (_QWORD *)*v28;
        v29 = L"Failed to read RegistryValue %s under %s, hr = 0x%08x";
        goto LABEL_48;
      }
      if ( Type != *(_DWORD *)(v12[2] + 32) )
      {
        v21 = (unsigned int)WaasMedic::ConvertToRegValueTypeToString((WaasMedic *)Type, v17);
        v23 = WaasMedic::ConvertToRegValueTypeToString((WaasMedic *)*(unsigned int *)(v22 + 32), v21);
        v26 = lpSubKey;
        if ( v62 > 7 )
          v26 = (LPCWSTR *)lpSubKey[0];
        if ( v25[3] > 7u )
          v25 = (_QWORD *)*v25;
        LogLevelW(3u, L"RegistryValue type of %s under %s doesn't match. Expected: %s, actual: %s.", v25, v26, v23, v24);
        goto LABEL_49;
      }
      v19 = WaasMedic::CRegistryValueFromXML::CompareRegKeyValue(
              (WaasMedic::CRegistryValueFromXML *)v12[2],
              v13,
              cbData,
              &v50);
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x643,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
          (const char *)(unsigned int)v19,
          (int)"Failed to compare registryValue",
          lpcbData);
        operator delete(v13, v36);
        std::wstring::~wstring(lpSubKey);
        if ( hKey )
          RegCloseKey(hKey);
        if ( v8 )
          RegCloseKey(v8);
        return (unsigned int)v19;
      }
      v20 = v50;
LABEL_50:
      if ( v20 )
        goto LABEL_53;
      goto LABEL_51;
  }
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( (v10 & 0x80000000) != 0 )
  {
    v39 = lpSubKey;
    if ( v62 > 7 )
      v39 = (LPCWSTR *)lpSubKey[0];
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x621,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
      (const char *)v10,
      (int)"Failed to open reg key for %ws",
      (const char *)v39);
  }
LABEL_74:
  std::wstring::~wstring(lpSubKey);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v8 )
    RegCloseKey(v8);
  return v10;
}

```

## disassembly

```asm
0x180034930  mov     [rsp-8+arg_10], rbx
0x180034935  push    rbp
0x180034936  push    rsi
0x180034937  push    rdi
0x180034938  push    r12
0x18003493a  push    r13
0x18003493c  push    r14
0x18003493e  push    r15
0x180034940  lea     rbp, [rsp-27h]
0x180034945  sub     rsp, 0B0h
0x18003494c  mov     rax, cs:__security_cookie
0x180034953  xor     rax, rsp
0x180034956  mov     [rbp+57h+var_38], rax
0x18003495a  mov     r15, rdx
0x18003495d  mov     [rbp+57h+var_60], rdx
0x180034961  mov     rsi, rcx
0x180034964  mov     [rbp+57h+var_80], rcx
0x180034968  mov     byte ptr [rdx], 1
0x18003496b  xor     r14d, r14d
0x18003496e  mov     [rbp+57h+hKey], r14
0x180034972  xorps   xmm0, xmm0
0x180034975  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x180034979  mov     [rbp+57h+var_48], r14
0x18003497d  lea     r12d, [r14+7]
0x180034981  mov     [rbp+57h+var_40], r12
0x180034985  mov     word ptr [rbp+57h+lpSubKey], r14w
0x18003498a  mov     [rbp+57h+var_88], r14
0x18003498e  lea     r8, [rbp+57h+lpSubKey]
0x180034992  lea     rdx, [rbp+57h+var_88]
0x180034996  call    ?RegGetRootKeyAndSubKeyFromPath@WaasMedic@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAPEAUHKEY__@@AEAV23@@Z; WaasMedic::RegGetRootKeyAndSubKeyFromPath(std::wstring const &,HKEY__ * &,std::wstring &)
0x18003499b  mov     ebx, eax
0x18003499d  test    eax, eax
0x18003499f  jns     short loc_1800349EA
0x1800349a1  mov     rcx, [rbp+5Fh]; this
0x1800349a5  mov     r9d, eax; char *
0x1800349a8  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800349af  mov     edx, 5FEh; void *
0x1800349b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800349b9  nop
0x1800349ba  lea     rcx, [rbp+57h+lpSubKey]; void *
0x1800349be  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800349c3  nop
0x1800349c4  mov     rcx, [rbp+57h+hKey]; hKey
0x1800349c8  test    rcx, rcx
0x1800349cb  jz      short loc_1800349D4
0x1800349cd  call    cs:__imp_RegCloseKey
0x1800349d3  nop
0x1800349d4  mov     rcx, [rbp+57h+var_88]; hKey
0x1800349d8  test    rcx, rcx
0x1800349db  jz      short loc_1800349E3
0x1800349dd  call    cs:__imp_RegCloseKey
0x1800349e3  mov     eax, ebx
0x1800349e5  jmp     loc_180034ED0
0x1800349ea  mov     rdi, [rbp+57h+hKey]
0x1800349ee  test    rdi, rdi
0x1800349f1  jz      short loc_180034A0C
0x1800349f3  call    cs:__imp_GetLastError
0x1800349f9  mov     ebx, eax
0x1800349fb  mov     rcx, rdi; hKey
0x1800349fe  call    cs:__imp_RegCloseKey
0x180034a04  mov     ecx, ebx; dwErrCode
0x180034a06  call    cs:__imp_SetLastError
0x180034a0c  mov     [rbp+57h+hKey], r14
0x180034a10  lea     rdx, [rbp+57h+lpSubKey]
0x180034a14  cmp     [rbp+57h+var_40], r12
0x180034a18  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180034a1d  lea     rax, [rbp+57h+hKey]
0x180034a21  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180034a26  mov     r9d, 1; samDesired
0x180034a2c  xor     r8d, r8d; ulOptions
0x180034a2f  mov     rbx, [rbp+57h+var_88]
0x180034a33  mov     rcx, rbx; hKey
0x180034a36  call    cs:__imp_RegOpenKeyExW
0x180034a3c  mov     edi, eax
0x180034a3e  lea     r13, [rsi+50h]
0x180034a42  cmp     eax, 2
0x180034a45  jz      loc_180034E0F
0x180034a4b  cmp     eax, 5
0x180034a4e  jz      loc_180034E06
0x180034a54  test    eax, eax
0x180034a56  jnz     loc_180034D91
0x180034a5c  mov     rdi, [rsi+40h]
0x180034a60  lea     r12d, [rax+3]
0x180034a64  mov     r14, 0AAAAAAAAAAAAAAAh
0x180034a6e  mov     rdi, [rdi]
0x180034a71  cmp     rdi, [rsi+40h]
0x180034a75  jz      loc_180034EA6
0x180034a7b  xor     ecx, ecx
0x180034a7d  mov     [rbp+57h+Type], ecx
0x180034a80  mov     esi, ecx
0x180034a82  mov     [rbp+57h+var_68], rcx
0x180034a86  mov     [rbp+57h+cbData], ecx
0x180034a89  mov     [rbp+57h+var_A0], 1
0x180034a8d  mov     rdx, [rdi+10h]
0x180034a91  cmp     qword ptr [rdx+18h], 7
0x180034a96  jbe     short loc_180034A9B
0x180034a98  mov     rdx, [rdx]; lpValueName
0x180034a9b  lea     rax, [rbp+57h+cbData]
0x180034a9f  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x180034aa4  mov     [rsp+0E0h+phkResult], rcx; int
0x180034aa9  lea     r9, [rbp+57h+Type]; lpType
0x180034aad  xor     r8d, r8d; lpReserved
0x180034ab0  mov     rcx, [rbp+57h+hKey]; hKey
0x180034ab4  call    cs:__imp_RegQueryValueExW
0x180034aba  test    eax, eax
0x180034abc  jnz     loc_180034BD6
0x180034ac2  mov     eax, [rbp+57h+cbData]
0x180034ac5  test    eax, eax
0x180034ac7  jz      loc_180034D32
0x180034acd  mov     ecx, eax; unsigned __int64
0x180034acf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180034ad6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180034adb  mov     rsi, rax
0x180034ade  mov     [rbp+57h+var_68], rax
0x180034ae2  test    rax, rax
0x180034ae5  jz      loc_180034D0F
0x180034aeb  mov     rdx, [rdi+10h]
0x180034aef  cmp     qword ptr [rdx+18h], 7
0x180034af4  jbe     short loc_180034AF9
0x180034af6  mov     rdx, [rdx]; lpValueName
0x180034af9  lea     rax, [rbp+57h+cbData]
0x180034afd  mov     [rsp+0E0h+lpcbData], rax; char *
0x180034b02  mov     [rsp+0E0h+phkResult], rsi; lpData
0x180034b07  lea     r9, [rbp+57h+Type]; lpType
0x180034b0b  xor     r8d, r8d; lpReserved
0x180034b0e  mov     rcx, [rbp+57h+hKey]; hKey
0x180034b12  call    cs:__imp_RegQueryValueExW
0x180034b18  test    eax, eax
0x180034b1a  jnz     loc_180034BA7
0x180034b20  mov     r10, [rdi+10h]
0x180034b24  mov     ecx, [rbp+57h+Type]; this
0x180034b27  cmp     ecx, [r10+20h]
0x180034b2b  jnz     short loc_180034B5D
0x180034b2d  lea     r9, [rbp+57h+var_A0]; bool *
0x180034b31  mov     r8d, [rbp+57h+cbData]; unsigned int
0x180034b35  mov     rdx, rsi; void *
0x180034b38  mov     rcx, r10; this
0x180034b3b  call    ?CompareRegKeyValue@CRegistryValueFromXML@WaasMedic@@QEAAJPEAXKAEA_N@Z; WaasMedic::CRegistryValueFromXML::CompareRegKeyValue(void *,ulong,bool &)
0x180034b40  mov     r14d, eax
0x180034b43  test    eax, eax
0x180034b45  js      loc_180034CB1
0x180034b4b  mov     al, [rbp+57h+var_A0]
0x180034b4e  mov     r14, 0AAAAAAAAAAAAAAAh
0x180034b58  jmp     loc_180034C45
0x180034b5d  call    ?ConvertToRegValueTypeToString@WaasMedic@@YAPEAGK@Z; WaasMedic::ConvertToRegValueTypeToString(ulong)
0x180034b62  mov     rdx, rax; unsigned int
0x180034b65  mov     ecx, [r10+20h]; this
0x180034b69  call    ?ConvertToRegValueTypeToString@WaasMedic@@YAPEAGK@Z; WaasMedic::ConvertToRegValueTypeToString(ulong)
0x180034b6e  lea     r9, [rbp+57h+lpSubKey]
0x180034b72  cmp     [rbp+57h+var_40], 7
0x180034b77  cmova   r9, [rbp+57h+lpSubKey]
0x180034b7c  cmp     qword ptr [r10+18h], 7
0x180034b81  jbe     short loc_180034B86
0x180034b83  mov     r10, [r10]
0x180034b86  mov     [rsp+0E0h+lpcbData], rdx
0x180034b8b  mov     [rsp+0E0h+phkResult], rax
0x180034b90  mov     r8, r10
0x180034b93  lea     rdx, aRegistryvalueT; "RegistryValue type of %s under %s doesn"...
0x180034b9a  mov     ecx, r12d; unsigned __int8
0x180034b9d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180034ba2  jmp     loc_180034C43
0x180034ba7  jle     short loc_180034BB1
0x180034ba9  movzx   eax, ax
0x180034bac  or      eax, 80070000h
0x180034bb1  lea     r9, [rbp+57h+lpSubKey]
0x180034bb5  cmp     [rbp+57h+var_40], 7
0x180034bba  cmova   r9, [rbp+57h+lpSubKey]
0x180034bbf  mov     r8, [rdi+10h]
0x180034bc3  cmp     qword ptr [r8+18h], 7
0x180034bc8  jbe     short loc_180034BCD
0x180034bca  mov     r8, [r8]
0x180034bcd  lea     rdx, aFailedToReadRe_0; "Failed to read RegistryValue %s under %"...
0x180034bd4  jmp     short loc_180034C37
0x180034bd6  cmp     eax, 2
0x180034bd9  jnz     short loc_180034C08
0x180034bdb  lea     r9, [rbp+57h+lpSubKey]
0x180034bdf  cmp     [rbp+57h+var_40], 7
0x180034be4  cmova   r9, [rbp+57h+lpSubKey]
0x180034be9  mov     r8, [rdi+10h]
0x180034bed  cmp     qword ptr [r8+18h], 7
0x180034bf2  jbe     short loc_180034BF7
0x180034bf4  mov     r8, [r8]
0x180034bf7  lea     rdx, aRegistryvalueS; "RegistryValue %s not found under %s"
0x180034bfe  mov     ecx, r12d; unsigned __int8
0x180034c01  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180034c06  jmp     short loc_180034C49
0x180034c08  test    eax, eax
0x180034c0a  jle     short loc_180034C14
0x180034c0c  movzx   eax, ax
0x180034c0f  or      eax, 80070000h
0x180034c14  lea     r9, [rbp+57h+lpSubKey]
0x180034c18  cmp     [rbp+57h+var_40], 7
0x180034c1d  cmova   r9, [rbp+57h+lpSubKey]
0x180034c22  mov     r8, [rdi+10h]
0x180034c26  cmp     qword ptr [r8+18h], 7
0x180034c2b  jbe     short loc_180034C30
0x180034c2d  mov     r8, [r8]
0x180034c30  lea     rdx, aFailedToGetSiz; "Failed to get size of RegistryValue %s "...
0x180034c37  mov     dword ptr [rsp+0E0h+phkResult], eax
0x180034c3b  mov     ecx, r12d; unsigned __int8
0x180034c3e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180034c43  xor     al, al
0x180034c45  test    al, al
0x180034c47  jnz     short loc_180034C9B
0x180034c49  mov     byte ptr [r15], 0
0x180034c4d  cmp     [r13+8], r14
0x180034c51  jz      loc_180034D83
0x180034c57  mov     r14, [rdi+10h]
0x180034c5b  mov     r15, [r13+0]
0x180034c5f  mov     [rbp+57h+var_78], r13
0x180034c63  mov     [rbp+57h+var_70], 0
0x180034c6b  mov     ecx, 18h; Size
0x180034c70  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034c75  mov     [rax+10h], r14
0x180034c79  inc     qword ptr [r13+8]
0x180034c7d  mov     rcx, [r15+8]
0x180034c81  mov     [rax], r15
0x180034c84  mov     [rax+8], rcx
0x180034c88  mov     [rbp+57h+var_70], 0
0x180034c90  mov     [r15+8], rax
0x180034c94  mov     [rcx], rax
0x180034c97  mov     r15, [rbp+57h+var_60]
0x180034c9b  test    rsi, rsi
0x180034c9e  jz      short loc_180034CA8
0x180034ca0  mov     rcx, rsi; void *
0x180034ca3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180034ca8  mov     rsi, [rbp+57h+var_80]
0x180034cac  jmp     loc_180034A64
0x180034cb1  mov     rcx, [rbp+5Fh]; this
0x180034cb5  lea     rax, aFailedToCompar; "Failed to compare registryValue"
0x180034cbc  mov     [rsp+0E0h+phkResult], rax; int
0x180034cc1  mov     r9d, r14d; char *
0x180034cc4  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180034ccb  mov     edx, 643h; void *
0x180034cd0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180034cd5  nop
0x180034cd6  mov     rcx, rsi; void *
0x180034cd9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180034cde  nop
0x180034cdf  lea     rcx, [rbp+57h+lpSubKey]; void *
0x180034ce3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180034ce8  nop
0x180034ce9  mov     rcx, [rbp+57h+hKey]; hKey
0x180034ced  test    rcx, rcx
0x180034cf0  jz      short loc_180034CF9
0x180034cf2  call    cs:__imp_RegCloseKey
0x180034cf8  nop
0x180034cf9  test    rbx, rbx
0x180034cfc  jz      short loc_180034D07
0x180034cfe  mov     rcx, rbx; hKey
0x180034d01  call    cs:__imp_RegCloseKey
0x180034d07  mov     eax, r14d
0x180034d0a  jmp     loc_180034ED0
0x180034d0f  mov     rcx, [rbp+5Fh]; this
0x180034d13  mov     edi, 8007000Eh
0x180034d18  mov     r9d, edi; char *
0x180034d1b  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180034d22  mov     edx, 637h; void *
0x180034d27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034d2c  nop
0x180034d2d  jmp     loc_180034DD7
0x180034d32  lea     rdx, [rbp+57h+lpSubKey]
0x180034d36  cmp     [rbp+57h+var_40], 7
0x180034d3b  cmova   rdx, [rbp+57h+lpSubKey]
0x180034d40  mov     rax, [rdi+10h]
0x180034d44  cmp     qword ptr [rax+18h], 7
0x180034d49  jbe     short loc_180034D4E
0x180034d4b  mov     rax, [rax]
0x180034d4e  mov     rcx, [rbp+5Fh]; this
0x180034d52  mov     [rsp+0E0h+var_B0], rdx
0x180034d57  mov     [rsp+0E0h+lpcbData], rax; char *
0x180034d5c  lea     rax, aRegistryValueF; "Registry Value for %ws under %ws is 0."
0x180034d63  mov     [rsp+0E0h+phkResult], rax; int
0x180034d68  mov     edi, 80070057h
0x180034d6d  mov     r9d, edi; char *
0x180034d70  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180034d77  mov     edx, 635h; void *
0x180034d7c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180034d81  jmp     short loc_180034D2D
0x180034d83  lea     rcx, aListTooLong; "list too long"
0x180034d8a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180034d91  jle     short loc_180034D9C
0x180034d93  movzx   edi, ax
0x180034d96  or      edi, 80070000h
0x180034d9c  test    edi, edi
0x180034d9e  jns     short loc_180034DD7
0x180034da0  lea     rax, [rbp+57h+lpSubKey]
0x180034da4  cmp     [rbp+57h+var_40], r12
0x180034da8  cmova   rax, [rbp+57h+lpSubKey]
0x180034dad  mov     rcx, [rbp+5Fh]; this
0x180034db1  mov     [rsp+0E0h+lpcbData], rax; char *
0x180034db6  lea     rax, aFailedToOpenRe; "Failed to open reg key for %ws"
0x180034dbd  mov     [rsp+0E0h+phkResult], rax; int
0x180034dc2  mov     r9d, edi; char *
0x180034dc5  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180034dcc  mov     edx, 621h; void *
0x180034dd1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180034dd6  nop
0x180034dd7  lea     rcx, [rbp+57h+lpSubKey]; void *
0x180034ddb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
  ... truncated ...
```
