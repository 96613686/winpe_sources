# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180009cc4`
- end: `0x18000a45b`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180009954`
- `0x180009cc4`

## callees

- `0x180004410`
- `0x180006df0`
- `0x180007520`
- `0x180007538`
- `0x180007c50`
- `0x180008f08`
- `0x180009804`
- `0x180009cc4`
- `0x18000b0f0`
- `0x18003e3f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000a1a2`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000a1a2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180009f27`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180009f27`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a2ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a364`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a2ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a364`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009f0a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009fb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a001`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a150`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009f0a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009fb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a001`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a150`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009f40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009fcc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a015`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a077`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a16b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a382`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a3dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a418`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a428`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009f40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009fcc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a015`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a077`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a16b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a382`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a3dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a418`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a428`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a05f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a05f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009da6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009f71`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009da6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009f71`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009d41`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009d54`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009dd2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009e3b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009e69`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a2f1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009d41`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009d54`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009dd2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009e3b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009e69`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a2f1`

## string_xrefs

- `0x180009d4a`: `ForceRemove`
- `0x180009e31`: `NoRemove`
- `0x180009d37`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r12d
  HKEY v6; // r15
  HKEY v9; // rbx
  __int64 result; // rax
  int Token; // edi
  int v12; // r14d
  int v13; // edi
  WCHAR v14; // ax
  const WCHAR *v15; // rcx
  int v16; // r12d
  int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // edx
  HKEY v20; // r14
  unsigned int v21; // eax
  unsigned int v22; // edx
  int v23; // eax
  WCHAR v24; // ax
  const WCHAR *v25; // rcx
  LSTATUS v26; // eax
  LSTATUS v27; // eax
  __int64 v28; // rax
  unsigned int v29; // r14d
  int v30; // r15d
  int v31; // eax
  __int64 v32; // rax
  int v33; // r14d
  winrt::impl *v34; // rcx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+68h] [rbp-98h]
  HKEY v37; // [rsp+70h] [rbp-90h]
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v39[3]; // [rsp+80h] [rbp-80h] BYREF
  HKEY v40; // [rsp+98h] [rbp-68h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-60h]
  __int64 v42; // [rsp+A8h] [rbp-58h]
  WCHAR String1[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v5 = a4;
  v36 = a4;
  v6 = a3;
  v37 = a3;
  v9 = 0;
  memset(v39, 0, sizeof(v39));
  result = ATL::CRegParser::NextToken(this, a2);
  Token = result;
  if ( (int)result < 0 )
    return result;
  if ( *a2 == 125 )
    goto LABEL_111;
  while ( 1 )
  {
    v12 = lstrcmpiW(a2, L"Delete");
    if ( !lstrcmpiW(a2, L"ForceRemove") || !v12 )
    {
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
      v13 = 0;
      if ( v5 )
      {
        v40 = 0;
        v41 = 0;
        v42 = 0;
        v14 = *a2;
        if ( !*a2 )
          goto LABEL_13;
        v15 = a2;
        do
        {
          if ( v14 == 92 )
          {
            if ( !v15 )
              break;
            goto LABEL_117;
          }
          v15 = CharNextW(v15);
          v14 = *v15;
        }
        while ( *v15 );
LABEL_13:
        while ( lstrcmpiW(a2, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v13]) )
        {
          if ( ++v13 >= 12 )
          {
            v40 = v6;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v40, a2);
            break;
          }
        }
        if ( !v12 )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_111;
          Token = ATL::CRegParser::SkipAssignment(this, a2);
          if ( Token < 0 )
            goto LABEL_111;
          goto LABEL_61;
        }
      }
    }
    v16 = 1;
    if ( !lstrcmpiW(a2, L"NoRemove") )
    {
      v16 = 0;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
    }
    if ( !lstrcmpiW(a2, L"Val") )
      break;
    v24 = *a2;
    if ( *a2 )
    {
      v25 = a2;
      while ( v24 != 92 )
      {
        v25 = CharNextW(v25);
        v24 = *v25;
        if ( !*v25 )
          goto LABEL_43;
      }
      if ( v25 )
        goto LABEL_117;
    }
LABEL_43:
    if ( v36 )
    {
      hKey = 0;
      if ( RegOpenKeyExW(v6, a2, 0, 0x2001Fu, &hKey) )
        goto LABEL_126;
      v26 = 0;
      if ( v9 )
        v26 = RegCloseKey(v9);
      v9 = hKey;
      v39[0] = hKey;
      if ( v26 )
      {
LABEL_126:
        hKey = 0;
        if ( RegOpenKeyExW(v6, a2, 0, 0x20019u, &hKey) )
          goto LABEL_127;
        v27 = 0;
        if ( v9 )
          v27 = RegCloseKey(v9);
        v9 = hKey;
        v39[0] = hKey;
        if ( v27 )
        {
LABEL_127:
          LODWORD(hKey) = 0;
          phkResult = 0;
          v18 = RegCreateKeyExW(v6, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, (LPDWORD)&hKey);
          if ( v18 )
            goto LABEL_109;
          v18 = 0;
          if ( v9 )
            v18 = RegCloseKey(v9);
          v9 = phkResult;
          v39[0] = phkResult;
          if ( v18 )
            goto LABEL_109;
        }
      }
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
      if ( *a2 == 61 )
      {
        v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)v39, 0, a2);
        Token = v17;
        v9 = (HKEY)v39[0];
        goto LABEL_59;
      }
LABEL_60:
      v5 = v36;
LABEL_61:
      if ( *a2 != 123 )
        goto LABEL_93;
      v28 = -1;
      do
        ++v28;
      while ( a2[v28] );
      if ( v28 != 1 )
        goto LABEL_93;
      Token = ATL::CRegParser::RegisterSubkeys(this, a2, v9, v5, 0);
      if ( Token < 0 )
        goto LABEL_111;
      v23 = ATL::CRegParser::NextToken(this, a2);
LABEL_35:
      Token = v23;
      if ( v23 < 0 )
        goto LABEL_111;
      goto LABEL_93;
    }
    if ( a5 )
    {
      v29 = 2;
    }
    else
    {
      phkResult = 0;
      v29 = RegOpenKeyExW(v6, a2, 0, 0x20019u, &phkResult);
      if ( !v29 )
      {
        v29 = 0;
        if ( v9 )
          v29 = RegCloseKey(v9);
        v9 = phkResult;
        v39[0] = phkResult;
      }
    }
    v30 = 1;
    if ( !v29 )
      v30 = a5;
    v31 = _o_wcsncpy_s(String1, 260, a2, -1);
    if ( v31 )
    {
      if ( v31 == 12 )
        ATL::AtlThrowImpl(-2147024882);
      if ( v31 == 22 || v31 == 34 )
        ATL::AtlThrowImpl(-2147024809);
      if ( v31 != 80 )
        ATL::AtlThrowImpl(-2147467259);
    }
    Token = ATL::CRegParser::NextToken(this, a2);
    if ( Token < 0 )
      goto LABEL_111;
    Token = ATL::CRegParser::SkipAssignment(this, a2);
    if ( Token < 0 )
      goto LABEL_111;
    if ( *a2 == 123 )
    {
      v32 = -1;
      do
        ++v32;
      while ( a2[v32] );
      if ( v32 == 1 )
      {
        Token = ATL::CRegParser::RegisterSubkeys(this, a2, v9, 0, v30);
        if ( Token < 0 && !v30 )
          goto LABEL_111;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_111;
      }
    }
    if ( v29 == 2 )
      goto LABEL_92;
    if ( v29 )
    {
      if ( a5 )
      {
LABEL_92:
        v6 = v37;
        goto LABEL_93;
      }
      v34 = (winrt::impl *)v29;
LABEL_110:
      Token = winrt::impl::hresult_from_win32(v34, v19);
      goto LABEL_111;
    }
    v33 = 0;
    if ( a5 )
    {
      LODWORD(hKey) = 0;
      if ( !RegQueryInfoKeyW(v9, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      {
        if ( (_DWORD)hKey )
        {
          while ( lstrcmpiW(String1, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v33]) )
          {
            if ( ++v33 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v39, String1);
                v9 = (HKEY)v39[0];
              }
              goto LABEL_92;
            }
          }
          goto LABEL_92;
        }
      }
    }
    LODWORD(hKey) = 0;
    if ( !RegQueryInfoKeyW(v9, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      LOBYTE(v33) = (_DWORD)hKey != 0;
    if ( v9 )
    {
      v18 = RegCloseKey(v9);
      v9 = 0;
      v39[0] = 0;
      if ( v18 )
      {
LABEL_109:
        v34 = (winrt::impl *)v18;
        goto LABEL_110;
      }
    }
    if ( !v16 || v33 )
      goto LABEL_92;
    v41 = 0;
    v42 = 0;
    v6 = v37;
    v40 = v37;
    v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v40, String1);
    if ( v18 )
      goto LABEL_109;
LABEL_93:
    if ( *a2 == 125 )
      goto LABEL_111;
    v5 = v36;
  }
  Token = ATL::CRegParser::NextToken(this, ValueName);
  if ( Token < 0 )
    goto LABEL_111;
  Token = ATL::CRegParser::NextToken(this, a2);
  if ( Token < 0 )
    goto LABEL_111;
  if ( *a2 != 61 )
  {
LABEL_117:
    if ( v9 )
      RegCloseKey(v9);
    return 2147614729LL;
  }
  if ( v36 )
  {
    v41 = 0;
    v42 = 0;
    v40 = v6;
    v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)&v40, ValueName, a2);
    Token = v17;
LABEL_59:
    if ( v17 < 0 )
      goto LABEL_111;
    goto LABEL_60;
  }
  if ( a5 || !v16 )
  {
LABEL_34:
    v23 = ATL::CRegParser::SkipAssignment(this, a2);
    goto LABEL_35;
  }
  hKey = 0;
  v18 = RegOpenKeyExW(v6, 0, 0, 0x20006u, &hKey);
  if ( v18 )
    goto LABEL_109;
  v20 = hKey;
  v21 = RegDeleteValueW(hKey, ValueName);
  if ( (v21 & 0xFFFFFFFD) == 0 )
  {
    if ( v20 )
      RegCloseKey(v20);
    goto LABEL_34;
  }
  Token = winrt::impl::hresult_from_win32((winrt::impl *)v21, v22);
  if ( v20 )
    RegCloseKey(v20);
LABEL_111:
  if ( v9 )
    RegCloseKey(v9);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x180009cc4  push    rbp
0x180009cc6  push    rbx
0x180009cc7  push    rsi
0x180009cc8  push    rdi
0x180009cc9  push    r12
0x180009ccb  push    r13
0x180009ccd  push    r14
0x180009ccf  push    r15
0x180009cd1  lea     rbp, [rsp-21D8h]
0x180009cd9  mov     eax, 22D8h
0x180009cde  call    _alloca_probe
0x180009ce3  sub     rsp, rax
0x180009ce6  mov     rax, cs:__security_cookie
0x180009ced  xor     rax, rsp
0x180009cf0  mov     [rbp+2210h+var_50], rax
0x180009cf7  mov     r12d, r9d
0x180009cfa  mov     [rsp+2310h+var_22A8], r9d
0x180009cff  mov     r15, r8
0x180009d02  mov     [rsp+2310h+var_22A0], r8
0x180009d07  mov     rsi, rdx
0x180009d0a  mov     r13, rcx
0x180009d0d  xor     eax, eax
0x180009d0f  mov     ebx, eax
0x180009d11  mov     [rbp+2210h+var_2290], rax
0x180009d15  mov     [rbp+2210h+var_2288], rax
0x180009d19  mov     [rbp+2210h+var_2280], rax
0x180009d1d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009d22  mov     edi, eax
0x180009d24  test    eax, eax
0x180009d26  jns     short loc_180009D2D
0x180009d28  jmp     loc_18000A3E4
0x180009d2d  cmp     word ptr [rsi], 7Dh ; '}'
0x180009d31  jz      loc_18000A3D4
0x180009d37  lea     rdx, String2; "Delete"
0x180009d3e  mov     rcx, rsi; lpString1
0x180009d41  call    cs:__imp_lstrcmpiW
0x180009d47  mov     r14d, eax
0x180009d4a  lea     rdx, aForceremove; "ForceRemove"
0x180009d51  mov     rcx, rsi; lpString1
0x180009d54  call    cs:__imp_lstrcmpiW
0x180009d5a  xor     edi, edi
0x180009d5c  test    eax, eax
0x180009d5e  jz      short loc_180009D69
0x180009d60  test    r14d, r14d
0x180009d63  jnz     loc_180009E2B
0x180009d69  mov     rdx, rsi; unsigned __int16 *
0x180009d6c  mov     rcx, r13; this
0x180009d6f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009d74  mov     edi, eax
0x180009d76  test    eax, eax
0x180009d78  js      loc_18000A3D4
0x180009d7e  xor     edi, edi
0x180009d80  test    r12d, r12d
0x180009d83  jz      loc_180009E2B
0x180009d89  mov     [rbp+2210h+var_2278], rdi
0x180009d8d  mov     [rbp+2210h+var_2270], rdi
0x180009d91  mov     [rbp+2210h+var_2268], rdi
0x180009d95  movzx   eax, word ptr [rsi]
0x180009d98  test    ax, ax
0x180009d9b  jz      short loc_180009DC2
0x180009d9d  mov     rcx, rsi; lpsz
0x180009da0  cmp     ax, 5Ch ; '\'
0x180009da4  jz      short loc_180009DB9
0x180009da6  call    cs:__imp_CharNextW
0x180009dac  mov     rcx, rax
0x180009daf  movzx   eax, word ptr [rax]
0x180009db2  test    ax, ax
0x180009db5  jnz     short loc_180009DA0
0x180009db7  jmp     short loc_180009DC2
0x180009db9  test    rcx, rcx
0x180009dbc  jnz     loc_18000A420
0x180009dc2  mov     edx, edi
0x180009dc4  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180009dcb  mov     rdx, [rax+rdx*8]; lpString2
0x180009dcf  mov     rcx, rsi; lpString1
0x180009dd2  call    cs:__imp_lstrcmpiW
0x180009dd8  test    eax, eax
0x180009dda  jz      short loc_180009DF3
0x180009ddc  inc     edi
0x180009dde  cmp     edi, 0Ch
0x180009de1  jl      short loc_180009DC2
0x180009de3  mov     [rbp+2210h+var_2278], r15
0x180009de7  mov     rdx, rsi; unsigned __int16 *
0x180009dea  lea     rcx, [rbp+2210h+var_2278]; this
0x180009dee  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180009df3  xor     edi, edi
0x180009df5  test    r14d, r14d
0x180009df8  jnz     short loc_180009E2B
0x180009dfa  mov     rdx, rsi; unsigned __int16 *
0x180009dfd  mov     rcx, r13; this
0x180009e00  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009e05  mov     edi, eax
0x180009e07  test    eax, eax
0x180009e09  js      loc_18000A3D4
0x180009e0f  mov     rdx, rsi; unsigned __int16 *
0x180009e12  mov     rcx, r13; this
0x180009e15  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180009e1a  mov     edi, eax
0x180009e1c  xor     ecx, ecx
0x180009e1e  test    eax, eax
0x180009e20  js      loc_18000A3D4
0x180009e26  jmp     loc_18000A0D2
0x180009e2b  mov     r12d, 1
0x180009e31  lea     rdx, aNoremove; "NoRemove"
0x180009e38  mov     rcx, rsi; lpString1
0x180009e3b  call    cs:__imp_lstrcmpiW
0x180009e41  test    eax, eax
0x180009e43  jnz     short loc_180009E5F
0x180009e45  mov     r12d, edi
0x180009e48  mov     rdx, rsi; unsigned __int16 *
0x180009e4b  mov     rcx, r13; this
0x180009e4e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009e53  mov     edi, eax
0x180009e55  test    eax, eax
0x180009e57  js      loc_18000A3D4
0x180009e5d  xor     edi, edi
0x180009e5f  lea     rdx, aVal; "Val"
0x180009e66  mov     rcx, rsi; lpString1
0x180009e69  call    cs:__imp_lstrcmpiW
0x180009e6f  test    eax, eax
0x180009e71  jnz     loc_180009F60
0x180009e77  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180009e7e  mov     rcx, r13; this
0x180009e81  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009e86  mov     edi, eax
0x180009e88  test    eax, eax
0x180009e8a  js      loc_18000A3D4
0x180009e90  mov     rdx, rsi; unsigned __int16 *
0x180009e93  mov     rcx, r13; this
0x180009e96  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009e9b  mov     edi, eax
0x180009e9d  test    eax, eax
0x180009e9f  js      loc_18000A3D4
0x180009ea5  cmp     word ptr [rsi], 3Dh ; '='
0x180009ea9  jnz     loc_18000A420
0x180009eaf  xor     edi, edi
0x180009eb1  cmp     [rsp+2310h+var_22A8], edi
0x180009eb5  jz      short loc_180009EE0
0x180009eb7  mov     [rbp+2210h+var_2270], rdi
0x180009ebb  mov     [rbp+2210h+var_2268], rdi
0x180009ebf  mov     [rbp+2210h+var_2278], r15
0x180009ec3  mov     r9, rsi; unsigned __int16 *
0x180009ec6  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180009ecd  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180009ed1  mov     rcx, r13; this
0x180009ed4  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180009ed9  mov     edi, eax
0x180009edb  jmp     loc_18000A0C3
0x180009ee0  cmp     [rbp+2210h+arg_20], edi
0x180009ee6  jnz     short loc_180009F46
0x180009ee8  test    r12d, r12d
0x180009eeb  jz      short loc_180009F46
0x180009eed  mov     [rsp+2310h+hKey], rdi
0x180009ef2  lea     rax, [rsp+2310h+hKey]
0x180009ef7  mov     [rsp+2310h+phkResult], rax; phkResult
0x180009efc  mov     r9d, 20006h; samDesired
0x180009f02  xor     r8d, r8d; ulOptions
0x180009f05  xor     edx, edx; lpSubKey
0x180009f07  mov     rcx, r15; hKey
0x180009f0a  call    cs:__imp_RegOpenKeyExW
0x180009f10  test    eax, eax
0x180009f12  jnz     loc_18000A3CB
0x180009f18  mov     r14, [rsp+2310h+hKey]
0x180009f1d  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180009f24  mov     rcx, r14; hKey
0x180009f27  call    cs:__imp_RegDeleteValueW
0x180009f2d  test    eax, 0FFFFFFFDh
0x180009f32  jnz     loc_18000A407
0x180009f38  test    r14, r14
0x180009f3b  jz      short loc_180009F46
0x180009f3d  mov     rcx, r14; hKey
0x180009f40  call    cs:__imp_RegCloseKey
0x180009f46  mov     rdx, rsi; unsigned __int16 *
0x180009f49  mov     rcx, r13; this
0x180009f4c  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180009f51  mov     edi, eax
0x180009f53  test    eax, eax
0x180009f55  js      loc_18000A3D4
0x180009f5b  jmp     loc_18000A26D
0x180009f60  movzx   eax, word ptr [rsi]
0x180009f63  test    ax, ax
0x180009f66  jz      short loc_180009F8D
0x180009f68  mov     rcx, rsi; lpsz
0x180009f6b  cmp     ax, 5Ch ; '\'
0x180009f6f  jz      short loc_180009F84
0x180009f71  call    cs:__imp_CharNextW
0x180009f77  mov     rcx, rax
0x180009f7a  movzx   eax, word ptr [rax]
0x180009f7d  test    ax, ax
0x180009f80  jnz     short loc_180009F6B
0x180009f82  jmp     short loc_180009F8D
0x180009f84  test    rcx, rcx
0x180009f87  jnz     loc_18000A420
0x180009f8d  cmp     [rsp+2310h+var_22A8], edi
0x180009f91  jz      loc_18000A126
0x180009f97  mov     [rsp+2310h+hKey], rdi
0x180009f9c  lea     rax, [rsp+2310h+hKey]
0x180009fa1  mov     [rsp+2310h+phkResult], rax; phkResult
0x180009fa6  mov     r14d, 2001Fh
0x180009fac  mov     r9d, r14d; samDesired
0x180009faf  xor     r8d, r8d; ulOptions
0x180009fb2  mov     rdx, rsi; lpSubKey
0x180009fb5  mov     rcx, r15; hKey
0x180009fb8  call    cs:__imp_RegOpenKeyExW
0x180009fbe  test    eax, eax
0x180009fc0  jnz     short loc_180009FE3
0x180009fc2  mov     eax, edi
0x180009fc4  test    rbx, rbx
0x180009fc7  jz      short loc_180009FD2
0x180009fc9  mov     rcx, rbx; hKey
0x180009fcc  call    cs:__imp_RegCloseKey
0x180009fd2  mov     rbx, [rsp+2310h+hKey]
0x180009fd7  mov     [rbp+2210h+var_2290], rbx
0x180009fdb  test    eax, eax
0x180009fdd  jz      loc_18000A08E
0x180009fe3  mov     [rsp+2310h+hKey], rdi
0x180009fe8  lea     rax, [rsp+2310h+hKey]
0x180009fed  mov     [rsp+2310h+phkResult], rax; phkResult
0x180009ff2  mov     r9d, 20019h; samDesired
0x180009ff8  xor     r8d, r8d; ulOptions
0x180009ffb  mov     rdx, rsi; lpSubKey
0x180009ffe  mov     rcx, r15; hKey
0x18000a001  call    cs:__imp_RegOpenKeyExW
0x18000a007  test    eax, eax
0x18000a009  jnz     short loc_18000A028
0x18000a00b  mov     eax, edi
0x18000a00d  test    rbx, rbx
0x18000a010  jz      short loc_18000A01B
0x18000a012  mov     rcx, rbx; hKey
0x18000a015  call    cs:__imp_RegCloseKey
0x18000a01b  mov     rbx, [rsp+2310h+hKey]
0x18000a020  mov     [rbp+2210h+var_2290], rbx
0x18000a024  test    eax, eax
0x18000a026  jz      short loc_18000A08E
0x18000a028  mov     dword ptr [rsp+2310h+hKey], edi
0x18000a02c  mov     [rsp+2310h+var_2298], rdi
0x18000a031  lea     rax, [rsp+2310h+hKey]
0x18000a036  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x18000a03b  lea     rax, [rsp+2310h+var_2298]
0x18000a040  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18000a045  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000a04a  mov     [rsp+2310h+samDesired], r14d; samDesired
0x18000a04f  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x18000a053  xor     r9d, r9d; lpClass
0x18000a056  xor     r8d, r8d; Reserved
0x18000a059  mov     rdx, rsi; lpSubKey
0x18000a05c  mov     rcx, r15; hKey
0x18000a05f  call    cs:__imp_RegCreateKeyExW
0x18000a065  test    eax, eax
0x18000a067  jnz     loc_18000A3CB
0x18000a06d  mov     eax, edi
0x18000a06f  test    rbx, rbx
0x18000a072  jz      short loc_18000A07D
0x18000a074  mov     rcx, rbx; hKey
0x18000a077  call    cs:__imp_RegCloseKey
0x18000a07d  mov     rbx, [rsp+2310h+var_2298]
0x18000a082  mov     [rbp+2210h+var_2290], rbx
0x18000a086  test    eax, eax
0x18000a088  jnz     loc_18000A3CB
0x18000a08e  mov     rdx, rsi; unsigned __int16 *
0x18000a091  mov     rcx, r13; this
0x18000a094  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a099  mov     edi, eax
0x18000a09b  xor     ecx, ecx
0x18000a09d  test    eax, eax
0x18000a09f  js      loc_18000A3D4
0x18000a0a5  cmp     word ptr [rsi], 3Dh ; '='
0x18000a0a9  jnz     short loc_18000A0CD
0x18000a0ab  mov     r9, rsi; unsigned __int16 *
0x18000a0ae  xor     r8d, r8d; unsigned __int16 *
0x18000a0b1  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x18000a0b5  mov     rcx, r13; this
0x18000a0b8  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000a0bd  mov     edi, eax
0x18000a0bf  mov     rbx, [rbp+2210h+var_2290]
0x18000a0c3  test    eax, eax
0x18000a0c5  js      loc_18000A3D4
0x18000a0cb  xor     ecx, ecx
0x18000a0cd  mov     r12d, [rsp+2310h+var_22A8]
0x18000a0d2  cmp     word ptr [rsi], 7Bh ; '{'
0x18000a0d6  jnz     loc_18000A26D
0x18000a0dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a0e0  inc     rax
0x18000a0e3  cmp     [rsi+rax*2], cx
0x18000a0e7  jnz     short loc_18000A0E0
0x18000a0e9  cmp     rax, 1
0x18000a0ed  jnz     loc_18000A26D
0x18000a0f3  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x18000a0fb  mov     r9d, r12d; int
0x18000a0fe  mov     r8, rbx; HKEY
0x18000a101  mov     rdx, rsi; unsigned __int16 *
0x18000a104  mov     rcx, r13; this
0x18000a107  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000a10c  mov     edi, eax
0x18000a10e  test    eax, eax
0x18000a110  js      loc_18000A3D4
0x18000a116  mov     rdx, rsi; unsigned __int16 *
0x18000a119  mov     rcx, r13; this
0x18000a11c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a121  jmp     loc_180009F51
  ... truncated ...
```
