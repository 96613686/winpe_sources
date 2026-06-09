# _IsMethodValidForKey

- ea: `0x18000f7d0`
- end: `0x18000fc5e`
- name: `_IsMethodValidForKey`
- size: `1166`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject, DWORD dwKeySpec)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b3b0`

## callees

- `0x1800070d0`
- `0x18000f7d0`
- `0x180014ce0`
- `0x180018625`
- `0x180018640`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f92a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f9be`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fa37`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fad3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fb0e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fbc2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f92a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f9be`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fa37`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fad3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fb0e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fbc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f83a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f83a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8a5`
- `ncrypt!NCryptGetProperty` at `0x18000fa6f`
- `ncrypt!NCryptGetProperty` at `0x18000fb61`
- `ncrypt!NCryptGetProperty` at `0x18000fa6f`
- `ncrypt!NCryptGetProperty` at `0x18000fb61`
- `ncrypt!NCryptIsKeyHandle` at `0x18000f800`
- `ncrypt!NCryptIsKeyHandle` at `0x18000f800`
- `CRYPTSP!CryptDestroyKey` at `0x18000fc2c`
- `CRYPTSP!CryptDestroyKey` at `0x18000fc2c`
- `CRYPTSP!CryptGetKeyParam` at `0x18000f895`
- `CRYPTSP!CryptGetKeyParam` at `0x18000f895`
- `CRYPTSP!CryptGetUserKey` at `0x18000f82a`
- `CRYPTSP!CryptGetUserKey` at `0x18000f82a`

## string_xrefs

- `0x18000f855`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x18000f8c0`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x18000f93f`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x18000f96c`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x18000f9d3`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x18000fa81`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x18000fb23`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x18000fb73`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x18000fbdf`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`

## pseudocode

```c
__int64 __fastcall IsMethodValidForKey(NCRYPT_HANDLE hObject, DWORD dwKeySpec, __int64 a3)
{
  signed int LastError; // eax
  unsigned int v7; // ebx
  const char *v8; // rax
  signed int v9; // eax
  const char *v10; // rax
  const char *v11; // rax
  const char *v12; // rax
  const char *v13; // rax
  SECURITY_STATUS Property; // eax
  const char *v15; // rax
  const char *v16; // rax
  SECURITY_STATUS v17; // eax
  const char *v18; // rax
  const char *v19; // r8
  char v20; // al
  const char *v21; // rdx
  bool v22; // zf
  BYTE pbData[4]; // [rsp+30h] [rbp-238h] BYREF
  DWORD pdwDataLen; // [rsp+34h] [rbp-234h] BYREF
  HCRYPTKEY phUserKey; // [rsp+38h] [rbp-230h] BYREF
  wchar_t pbOutput[256]; // [rsp+40h] [rbp-228h] BYREF

  phUserKey = 0;
  *(_DWORD *)pbData = 0;
  if ( !NCryptIsKeyHandle(hObject) )
  {
    pdwDataLen = 4;
    if ( !CryptGetUserKey(hObject, dwKeySpec, &phUserKey) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v7, v8, 1203);
      goto LABEL_34;
    }
    if ( !CryptGetKeyParam(phUserKey, 7u, pbData, &pdwDataLen, 0) )
    {
      v9 = GetLastError();
      v7 = v9;
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v7, v10, 1216);
      goto LABEL_34;
    }
    if ( ((*(_DWORD *)pbData - 9216) & 0xFFFF7FFF) != 0 )
    {
      if ( *(_DWORD *)pbData != 8704 )
      {
        v7 = -2146885372;
        v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885372, v12, 1243);
        goto LABEL_34;
      }
      if ( CompareStringW(0, 1u, *(PCNZWCH *)(a3 + 40), -1, L"DSA", -1) != 2 )
      {
        v7 = -2146885372;
        v11 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885372, v11, 1236);
        goto LABEL_34;
      }
    }
    else if ( CompareStringW(0, 1u, *(PCNZWCH *)(a3 + 40), -1, L"RSA", -1) != 2 )
    {
      v7 = -2146885372;
      v13 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885372, v13, 1226);
      goto LABEL_34;
    }
LABEL_33:
    v7 = 0;
    goto LABEL_34;
  }
  memset_0(pbOutput, 0, sizeof(pbOutput));
  if ( CompareStringW(0, 1u, L"CryptOIDInfoECCParameters", -1, *(PCNZWCH *)(a3 + 40), -1) == 2 )
  {
    Property = NCryptGetProperty(hObject, L"Algorithm Group", (PBYTE)pbOutput, 0x200u, (DWORD *)pbData, 0);
    if ( Property < 0 )
    {
      v7 = Property | 0x10000000;
      v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v7, v15, 1267);
      goto LABEL_34;
    }
    if ( CompareStringW(0, 1u, pbOutput, -1, L"ECDSA", -1) != 2 && CompareStringW(0, 1u, pbOutput, -1, L"ECDH", -1) != 2 )
    {
      v7 = -2146885372;
      v16 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %S", -2146885372, v16, 1280, pbOutput);
      goto LABEL_34;
    }
    goto LABEL_33;
  }
  v17 = NCryptGetProperty(hObject, L"Algorithm Name", (PBYTE)pbOutput, 0x200u, (DWORD *)pbData, 0);
  if ( v17 < 0 )
  {
    v7 = v17 | 0x10000000;
    v18 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v7, v18, 1297);
    goto LABEL_34;
  }
  if ( CompareStringW(0, 1u, pbOutput, -1, *(PCNZWCH *)(a3 + 40), -1) == 2 )
    goto LABEL_33;
  v7 = -2146885372;
  v19 = "";
  while ( 1 )
  {
    v20 = *(v19 - 1);
    v21 = v19--;
    v22 = v20 == 92;
    if ( v20 == 92 )
      break;
    if ( v19 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp" )
    {
      v22 = v20 == 92;
      break;
    }
  }
  if ( v22 )
    v19 = v21;
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %S", -2146885372, v19, 1307, pbOutput);
LABEL_34:
  if ( phUserKey )
    CryptDestroyKey(phUserKey);
  return v7;
}

```

## disassembly

```asm
0x18000f7d0  mov     [rsp+arg_18], rbx
0x18000f7d5  push    rbp
0x18000f7d6  push    rsi
0x18000f7d7  push    rdi
0x18000f7d8  sub     rsp, 250h
0x18000f7df  mov     rax, cs:__security_cookie
0x18000f7e6  xor     rax, rsp
0x18000f7e9  mov     [rsp+268h+var_28], rax
0x18000f7f1  xor     ebp, ebp
0x18000f7f3  mov     rdi, r8
0x18000f7f6  mov     [rsp+268h+phUserKey], rbp
0x18000f7fb  mov     esi, edx
0x18000f7fd  mov     rbx, rcx
0x18000f800  call    cs:__imp_NCryptIsKeyHandle
0x18000f807  nop     dword ptr [rax+rax+00h]
0x18000f80c  mov     dword ptr [rsp+268h+pbData], ebp
0x18000f810  test    eax, eax
0x18000f812  jnz     loc_18000FA00
0x18000f818  lea     r8, [rsp+268h+phUserKey]; phUserKey
0x18000f81d  mov     [rsp+268h+pdwDataLen], 4
0x18000f825  mov     edx, esi; dwKeySpec
0x18000f827  mov     rcx, rbx; hProv
0x18000f82a  call    cs:__imp_CryptGetUserKey
0x18000f831  nop     dword ptr [rax+rax+00h]
0x18000f836  test    eax, eax
0x18000f838  jnz     short loc_18000F87D
0x18000f83a  call    cs:__imp_GetLastError
0x18000f841  nop     dword ptr [rax+rax+00h]
0x18000f846  mov     ebx, eax
0x18000f848  test    eax, eax
0x18000f84a  jle     short loc_18000F855
0x18000f84c  movzx   ebx, ax
0x18000f84f  or      ebx, 80070000h
0x18000f855  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000f85c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000f861  mov     r8, rax
0x18000f864  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000f86b  mov     edx, ebx
0x18000f86d  mov     r9d, 4B3h
0x18000f873  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000f878  jmp     loc_18000FC22
0x18000f87d  mov     rcx, [rsp+268h+phUserKey]; hKey
0x18000f882  lea     r9, [rsp+268h+pdwDataLen]; pdwDataLen
0x18000f887  lea     r8, [rsp+268h+pbData]; pbData
0x18000f88c  mov     [rsp+268h+dwFlags], ebp; dwFlags
0x18000f890  mov     edx, 7; dwParam
0x18000f895  call    cs:__imp_CryptGetKeyParam
0x18000f89c  nop     dword ptr [rax+rax+00h]
0x18000f8a1  test    eax, eax
0x18000f8a3  jnz     short loc_18000F8E8
0x18000f8a5  call    cs:__imp_GetLastError
0x18000f8ac  nop     dword ptr [rax+rax+00h]
0x18000f8b1  mov     ebx, eax
0x18000f8b3  test    eax, eax
0x18000f8b5  jle     short loc_18000F8C0
0x18000f8b7  movzx   ebx, ax
0x18000f8ba  or      ebx, 80070000h
0x18000f8c0  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000f8c7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000f8cc  mov     r8, rax
0x18000f8cf  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000f8d6  mov     edx, ebx
0x18000f8d8  mov     r9d, 4C0h
0x18000f8de  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000f8e3  jmp     loc_18000FC22
0x18000f8e8  mov     ecx, dword ptr [rsp+268h+pbData]
0x18000f8ec  lea     eax, [rcx-2400h]
0x18000f8f2  test    eax, 0FFFF7FFFh
0x18000f8f7  jz      loc_18000F999
0x18000f8fd  cmp     ecx, 2200h
0x18000f903  jnz     short loc_18000F96C
0x18000f905  mov     r8, [rdi+28h]; lpString1
0x18000f909  lea     rax, aDsa; "DSA"
0x18000f910  mov     [rsp+268h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000f918  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000f91e  mov     edx, 1; dwCmpFlags
0x18000f923  mov     qword ptr [rsp+268h+dwFlags], rax; lpString2
0x18000f928  xor     ecx, ecx; Locale
0x18000f92a  call    cs:__imp_CompareStringW
0x18000f931  nop     dword ptr [rax+rax+00h]
0x18000f936  cmp     eax, 2
0x18000f939  jz      loc_18000FC20
0x18000f93f  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000f946  mov     ebx, 80092104h
0x18000f94b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000f950  mov     r8, rax
0x18000f953  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000f95a  mov     edx, ebx
0x18000f95c  mov     r9d, 4D4h
0x18000f962  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000f967  jmp     loc_18000FC22
0x18000f96c  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000f973  mov     ebx, 80092104h
0x18000f978  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000f97d  mov     r8, rax
0x18000f980  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000f987  mov     edx, ebx
0x18000f989  mov     r9d, 4DBh
0x18000f98f  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000f994  jmp     loc_18000FC22
0x18000f999  mov     r8, [rdi+28h]; lpString1
0x18000f99d  lea     rax, aRsa; "RSA"
0x18000f9a4  mov     [rsp+268h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000f9ac  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000f9b2  mov     edx, 1; dwCmpFlags
0x18000f9b7  mov     qword ptr [rsp+268h+dwFlags], rax; lpString2
0x18000f9bc  xor     ecx, ecx; Locale
0x18000f9be  call    cs:__imp_CompareStringW
0x18000f9c5  nop     dword ptr [rax+rax+00h]
0x18000f9ca  cmp     eax, 2
0x18000f9cd  jz      loc_18000FC20
0x18000f9d3  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000f9da  mov     ebx, 80092104h
0x18000f9df  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000f9e4  mov     r8, rax
0x18000f9e7  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000f9ee  mov     edx, ebx
0x18000f9f0  mov     r9d, 4CAh
0x18000f9f6  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000f9fb  jmp     loc_18000FC22
0x18000fa00  xor     edx, edx; Val
0x18000fa02  lea     rcx, [rsp+268h+pbOutput]; void *
0x18000fa07  mov     r8d, 200h; Size
0x18000fa0d  call    memset_0
0x18000fa12  mov     rax, [rdi+28h]
0x18000fa16  lea     r8, aCryptoidinfoec; "CryptOIDInfoECCParameters"
0x18000fa1d  mov     [rsp+268h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000fa25  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000fa2b  mov     edx, 1; dwCmpFlags
0x18000fa30  mov     qword ptr [rsp+268h+dwFlags], rax; lpString2
0x18000fa35  xor     ecx, ecx; Locale
0x18000fa37  call    cs:__imp_CompareStringW
0x18000fa3e  nop     dword ptr [rax+rax+00h]
0x18000fa43  mov     [rsp+268h+cchCount2], ebp; dwFlags
0x18000fa47  lea     r8, [rsp+268h+pbOutput]; pbOutput
0x18000fa4c  cmp     eax, 2
0x18000fa4f  mov     r9d, 200h; cbOutput
0x18000fa55  lea     rax, [rsp+268h+pbData]
0x18000fa5a  mov     rcx, rbx; hObject
0x18000fa5d  mov     qword ptr [rsp+268h+dwFlags], rax; pcbResult
0x18000fa62  jnz     loc_18000FB5A
0x18000fa68  lea     rdx, aAlgorithmGroup; "Algorithm Group"
0x18000fa6f  call    cs:__imp_NCryptGetProperty
0x18000fa76  nop     dword ptr [rax+rax+00h]
0x18000fa7b  mov     ebx, eax
0x18000fa7d  test    eax, eax
0x18000fa7f  jns     short loc_18000FAAD
0x18000fa81  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000fa88  bts     ebx, 1Ch
0x18000fa8c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000fa91  mov     r8, rax
0x18000fa94  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000fa9b  mov     edx, ebx
0x18000fa9d  mov     r9d, 4F3h
0x18000faa3  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000faa8  jmp     loc_18000FC22
0x18000faad  lea     rax, aEcdsa; "ECDSA"
0x18000fab4  mov     [rsp+268h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000fabc  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000fac2  mov     qword ptr [rsp+268h+dwFlags], rax; lpString2
0x18000fac7  lea     r8, [rsp+268h+pbOutput]; lpString1
0x18000facc  mov     edx, 1; dwCmpFlags
0x18000fad1  xor     ecx, ecx; Locale
0x18000fad3  call    cs:__imp_CompareStringW
0x18000fada  nop     dword ptr [rax+rax+00h]
0x18000fadf  cmp     eax, 2
0x18000fae2  jz      loc_18000FC20
0x18000fae8  lea     rax, aEcdh; "ECDH"
0x18000faef  mov     [rsp+268h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000faf7  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000fafd  mov     qword ptr [rsp+268h+dwFlags], rax; lpString2
0x18000fb02  lea     r8, [rsp+268h+pbOutput]; lpString1
0x18000fb07  mov     edx, 1; dwCmpFlags
0x18000fb0c  xor     ecx, ecx; Locale
0x18000fb0e  call    cs:__imp_CompareStringW
0x18000fb15  nop     dword ptr [rax+rax+00h]
0x18000fb1a  cmp     eax, 2
0x18000fb1d  jz      loc_18000FC20
0x18000fb23  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000fb2a  mov     ebx, 80092104h
0x18000fb2f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000fb34  mov     r8, rax
0x18000fb37  lea     rcx, aError0x08xSUS_0; "ERROR  : (0x%08x) %s:%u : %S"
0x18000fb3e  lea     rax, [rsp+268h+pbOutput]
0x18000fb43  mov     edx, ebx
0x18000fb45  mov     r9d, 500h
0x18000fb4b  mov     qword ptr [rsp+268h+dwFlags], rax
0x18000fb50  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000fb55  jmp     loc_18000FC22
0x18000fb5a  lea     rdx, aAlgorithmName; "Algorithm Name"
0x18000fb61  call    cs:__imp_NCryptGetProperty
0x18000fb68  nop     dword ptr [rax+rax+00h]
0x18000fb6d  mov     ebx, eax
0x18000fb6f  test    eax, eax
0x18000fb71  jns     short loc_18000FB9F
0x18000fb73  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000fb7a  bts     ebx, 1Ch
0x18000fb7e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000fb83  mov     r8, rax
0x18000fb86  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000fb8d  mov     edx, ebx
0x18000fb8f  mov     r9d, 511h
0x18000fb95  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000fb9a  jmp     loc_18000FC22
0x18000fb9f  mov     rax, [rdi+28h]
0x18000fba3  lea     r8, [rsp+268h+pbOutput]; lpString1
0x18000fba8  mov     [rsp+268h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000fbb0  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000fbb6  mov     edx, 1; dwCmpFlags
0x18000fbbb  mov     qword ptr [rsp+268h+dwFlags], rax; lpString2
0x18000fbc0  xor     ecx, ecx; Locale
0x18000fbc2  call    cs:__imp_CompareStringW
0x18000fbc9  nop     dword ptr [rax+rax+00h]
0x18000fbce  cmp     eax, 2
0x18000fbd1  jz      short loc_18000FC20
0x18000fbd3  mov     ebx, 80092104h
0x18000fbd8  lea     r8, aOnecoreDsSecur_6+30h; ""
0x18000fbdf  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000fbe6  movzx   eax, byte ptr [r8-1]
0x18000fbeb  mov     rdx, r8
0x18000fbee  dec     r8
0x18000fbf1  cmp     al, 5Ch ; '\'
0x18000fbf3  jz      short loc_18000FBFC
0x18000fbf5  cmp     r8, rcx
0x18000fbf8  ja      short loc_18000FBE6
0x18000fbfa  cmp     al, 5Ch ; '\'
0x18000fbfc  cmovz   r8, rdx
0x18000fc00  lea     rax, [rsp+268h+pbOutput]
0x18000fc05  mov     edx, ebx
0x18000fc07  mov     qword ptr [rsp+268h+dwFlags], rax
0x18000fc0c  mov     r9d, 51Bh
0x18000fc12  lea     rcx, aError0x08xSUS_0; "ERROR  : (0x%08x) %s:%u : %S"
0x18000fc19  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000fc1e  jmp     short loc_18000FC22
0x18000fc20  mov     ebx, ebp
0x18000fc22  mov     rcx, [rsp+268h+phUserKey]; hKey
0x18000fc27  test    rcx, rcx
0x18000fc2a  jz      short loc_18000FC38
0x18000fc2c  call    cs:__imp_CryptDestroyKey
0x18000fc33  nop     dword ptr [rax+rax+00h]
0x18000fc38  mov     eax, ebx
0x18000fc3a  mov     rcx, [rsp+268h+var_28]
0x18000fc42  xor     rcx, rsp; StackCookie
0x18000fc45  call    __security_check_cookie
0x18000fc4a  mov     rbx, [rsp+268h+arg_18]
0x18000fc52  add     rsp, 250h
0x18000fc59  pop     rdi
0x18000fc5a  pop     rsi
0x18000fc5b  pop     rbp
0x18000fc5c  retn
```
