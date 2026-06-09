# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000a844`
- end: `0x18000afdb`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18000a4d4`
- `0x18000a844`

## callees

- `0x180005020`
- `0x180007970`
- `0x1800080a0`
- `0x1800080b8`
- `0x1800087d0`
- `0x180009a88`
- `0x18000a384`
- `0x18000a844`
- `0x18000bc70`
- `0x1800599b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000ad22`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000ad22`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000abdf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000abdf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000aaa7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000aaa7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aac0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000abf7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aceb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000af02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000af5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000af98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000afa8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aac0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000abf7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aceb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000af02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000af5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000af98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000afa8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000aa8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ab38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ab81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000acd0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000aa8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ab38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ab81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000acd0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000ae4e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000aee4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000ae4e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000aee4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000a926`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000aaf1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000a926`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000aaf1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a8c1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a8d4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a952`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a9bb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a9e9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ae71`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a8c1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a8d4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a952`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a9bb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a9e9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ae71`

## string_xrefs

- `0x18000a8ca`: `ForceRemove`
- `0x18000a9b1`: `NoRemove`
- `0x18000a8b7`: `Delete`

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
0x18000a844  push    rbp
0x18000a846  push    rbx
0x18000a847  push    rsi
0x18000a848  push    rdi
0x18000a849  push    r12
0x18000a84b  push    r13
0x18000a84d  push    r14
0x18000a84f  push    r15
0x18000a851  lea     rbp, [rsp-21D8h]
0x18000a859  mov     eax, 22D8h
0x18000a85e  call    _alloca_probe
0x18000a863  sub     rsp, rax
0x18000a866  mov     rax, cs:__security_cookie
0x18000a86d  xor     rax, rsp
0x18000a870  mov     [rbp+2210h+var_50], rax
0x18000a877  mov     r12d, r9d
0x18000a87a  mov     [rsp+2310h+var_22A8], r9d
0x18000a87f  mov     r15, r8
0x18000a882  mov     [rsp+2310h+var_22A0], r8
0x18000a887  mov     rsi, rdx
0x18000a88a  mov     r13, rcx
0x18000a88d  xor     eax, eax
0x18000a88f  mov     ebx, eax
0x18000a891  mov     [rbp+2210h+var_2290], rax
0x18000a895  mov     [rbp+2210h+var_2288], rax
0x18000a899  mov     [rbp+2210h+var_2280], rax
0x18000a89d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a8a2  mov     edi, eax
0x18000a8a4  test    eax, eax
0x18000a8a6  jns     short loc_18000A8AD
0x18000a8a8  jmp     loc_18000AF64
0x18000a8ad  cmp     word ptr [rsi], 7Dh ; '}'
0x18000a8b1  jz      loc_18000AF54
0x18000a8b7  lea     rdx, String2; "Delete"
0x18000a8be  mov     rcx, rsi; lpString1
0x18000a8c1  call    cs:__imp_lstrcmpiW
0x18000a8c7  mov     r14d, eax
0x18000a8ca  lea     rdx, aForceremove; "ForceRemove"
0x18000a8d1  mov     rcx, rsi; lpString1
0x18000a8d4  call    cs:__imp_lstrcmpiW
0x18000a8da  xor     edi, edi
0x18000a8dc  test    eax, eax
0x18000a8de  jz      short loc_18000A8E9
0x18000a8e0  test    r14d, r14d
0x18000a8e3  jnz     loc_18000A9AB
0x18000a8e9  mov     rdx, rsi; unsigned __int16 *
0x18000a8ec  mov     rcx, r13; this
0x18000a8ef  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a8f4  mov     edi, eax
0x18000a8f6  test    eax, eax
0x18000a8f8  js      loc_18000AF54
0x18000a8fe  xor     edi, edi
0x18000a900  test    r12d, r12d
0x18000a903  jz      loc_18000A9AB
0x18000a909  mov     [rbp+2210h+var_2278], rdi
0x18000a90d  mov     [rbp+2210h+var_2270], rdi
0x18000a911  mov     [rbp+2210h+var_2268], rdi
0x18000a915  movzx   eax, word ptr [rsi]
0x18000a918  test    ax, ax
0x18000a91b  jz      short loc_18000A942
0x18000a91d  mov     rcx, rsi; lpsz
0x18000a920  cmp     ax, 5Ch ; '\'
0x18000a924  jz      short loc_18000A939
0x18000a926  call    cs:__imp_CharNextW
0x18000a92c  mov     rcx, rax
0x18000a92f  movzx   eax, word ptr [rax]
0x18000a932  test    ax, ax
0x18000a935  jnz     short loc_18000A920
0x18000a937  jmp     short loc_18000A942
0x18000a939  test    rcx, rcx
0x18000a93c  jnz     loc_18000AFA0
0x18000a942  mov     edx, edi
0x18000a944  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x18000a94b  mov     rdx, [rax+rdx*8]; lpString2
0x18000a94f  mov     rcx, rsi; lpString1
0x18000a952  call    cs:__imp_lstrcmpiW
0x18000a958  test    eax, eax
0x18000a95a  jz      short loc_18000A973
0x18000a95c  inc     edi
0x18000a95e  cmp     edi, 0Ch
0x18000a961  jl      short loc_18000A942
0x18000a963  mov     [rbp+2210h+var_2278], r15
0x18000a967  mov     rdx, rsi; unsigned __int16 *
0x18000a96a  lea     rcx, [rbp+2210h+var_2278]; this
0x18000a96e  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000a973  xor     edi, edi
0x18000a975  test    r14d, r14d
0x18000a978  jnz     short loc_18000A9AB
0x18000a97a  mov     rdx, rsi; unsigned __int16 *
0x18000a97d  mov     rcx, r13; this
0x18000a980  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a985  mov     edi, eax
0x18000a987  test    eax, eax
0x18000a989  js      loc_18000AF54
0x18000a98f  mov     rdx, rsi; unsigned __int16 *
0x18000a992  mov     rcx, r13; this
0x18000a995  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000a99a  mov     edi, eax
0x18000a99c  xor     ecx, ecx
0x18000a99e  test    eax, eax
0x18000a9a0  js      loc_18000AF54
0x18000a9a6  jmp     loc_18000AC52
0x18000a9ab  mov     r12d, 1
0x18000a9b1  lea     rdx, aNoremove; "NoRemove"
0x18000a9b8  mov     rcx, rsi; lpString1
0x18000a9bb  call    cs:__imp_lstrcmpiW
0x18000a9c1  test    eax, eax
0x18000a9c3  jnz     short loc_18000A9DF
0x18000a9c5  mov     r12d, edi
0x18000a9c8  mov     rdx, rsi; unsigned __int16 *
0x18000a9cb  mov     rcx, r13; this
0x18000a9ce  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a9d3  mov     edi, eax
0x18000a9d5  test    eax, eax
0x18000a9d7  js      loc_18000AF54
0x18000a9dd  xor     edi, edi
0x18000a9df  lea     rdx, aVal; "Val"
0x18000a9e6  mov     rcx, rsi; lpString1
0x18000a9e9  call    cs:__imp_lstrcmpiW
0x18000a9ef  test    eax, eax
0x18000a9f1  jnz     loc_18000AAE0
0x18000a9f7  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x18000a9fe  mov     rcx, r13; this
0x18000aa01  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000aa06  mov     edi, eax
0x18000aa08  test    eax, eax
0x18000aa0a  js      loc_18000AF54
0x18000aa10  mov     rdx, rsi; unsigned __int16 *
0x18000aa13  mov     rcx, r13; this
0x18000aa16  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000aa1b  mov     edi, eax
0x18000aa1d  test    eax, eax
0x18000aa1f  js      loc_18000AF54
0x18000aa25  cmp     word ptr [rsi], 3Dh ; '='
0x18000aa29  jnz     loc_18000AFA0
0x18000aa2f  xor     edi, edi
0x18000aa31  cmp     [rsp+2310h+var_22A8], edi
0x18000aa35  jz      short loc_18000AA60
0x18000aa37  mov     [rbp+2210h+var_2270], rdi
0x18000aa3b  mov     [rbp+2210h+var_2268], rdi
0x18000aa3f  mov     [rbp+2210h+var_2278], r15
0x18000aa43  mov     r9, rsi; unsigned __int16 *
0x18000aa46  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x18000aa4d  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x18000aa51  mov     rcx, r13; this
0x18000aa54  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000aa59  mov     edi, eax
0x18000aa5b  jmp     loc_18000AC43
0x18000aa60  cmp     [rbp+2210h+arg_20], edi
0x18000aa66  jnz     short loc_18000AAC6
0x18000aa68  test    r12d, r12d
0x18000aa6b  jz      short loc_18000AAC6
0x18000aa6d  mov     [rsp+2310h+hKey], rdi
0x18000aa72  lea     rax, [rsp+2310h+hKey]
0x18000aa77  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000aa7c  mov     r9d, 20006h; samDesired
0x18000aa82  xor     r8d, r8d; ulOptions
0x18000aa85  xor     edx, edx; lpSubKey
0x18000aa87  mov     rcx, r15; hKey
0x18000aa8a  call    cs:__imp_RegOpenKeyExW
0x18000aa90  test    eax, eax
0x18000aa92  jnz     loc_18000AF4B
0x18000aa98  mov     r14, [rsp+2310h+hKey]
0x18000aa9d  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18000aaa4  mov     rcx, r14; hKey
0x18000aaa7  call    cs:__imp_RegDeleteValueW
0x18000aaad  test    eax, 0FFFFFFFDh
0x18000aab2  jnz     loc_18000AF87
0x18000aab8  test    r14, r14
0x18000aabb  jz      short loc_18000AAC6
0x18000aabd  mov     rcx, r14; hKey
0x18000aac0  call    cs:__imp_RegCloseKey
0x18000aac6  mov     rdx, rsi; unsigned __int16 *
0x18000aac9  mov     rcx, r13; this
0x18000aacc  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000aad1  mov     edi, eax
0x18000aad3  test    eax, eax
0x18000aad5  js      loc_18000AF54
0x18000aadb  jmp     loc_18000ADED
0x18000aae0  movzx   eax, word ptr [rsi]
0x18000aae3  test    ax, ax
0x18000aae6  jz      short loc_18000AB0D
0x18000aae8  mov     rcx, rsi; lpsz
0x18000aaeb  cmp     ax, 5Ch ; '\'
0x18000aaef  jz      short loc_18000AB04
0x18000aaf1  call    cs:__imp_CharNextW
0x18000aaf7  mov     rcx, rax
0x18000aafa  movzx   eax, word ptr [rax]
0x18000aafd  test    ax, ax
0x18000ab00  jnz     short loc_18000AAEB
0x18000ab02  jmp     short loc_18000AB0D
0x18000ab04  test    rcx, rcx
0x18000ab07  jnz     loc_18000AFA0
0x18000ab0d  cmp     [rsp+2310h+var_22A8], edi
0x18000ab11  jz      loc_18000ACA6
0x18000ab17  mov     [rsp+2310h+hKey], rdi
0x18000ab1c  lea     rax, [rsp+2310h+hKey]
0x18000ab21  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000ab26  mov     r14d, 2001Fh
0x18000ab2c  mov     r9d, r14d; samDesired
0x18000ab2f  xor     r8d, r8d; ulOptions
0x18000ab32  mov     rdx, rsi; lpSubKey
0x18000ab35  mov     rcx, r15; hKey
0x18000ab38  call    cs:__imp_RegOpenKeyExW
0x18000ab3e  test    eax, eax
0x18000ab40  jnz     short loc_18000AB63
0x18000ab42  mov     eax, edi
0x18000ab44  test    rbx, rbx
0x18000ab47  jz      short loc_18000AB52
0x18000ab49  mov     rcx, rbx; hKey
0x18000ab4c  call    cs:__imp_RegCloseKey
0x18000ab52  mov     rbx, [rsp+2310h+hKey]
0x18000ab57  mov     [rbp+2210h+var_2290], rbx
0x18000ab5b  test    eax, eax
0x18000ab5d  jz      loc_18000AC0E
0x18000ab63  mov     [rsp+2310h+hKey], rdi
0x18000ab68  lea     rax, [rsp+2310h+hKey]
0x18000ab6d  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000ab72  mov     r9d, 20019h; samDesired
0x18000ab78  xor     r8d, r8d; ulOptions
0x18000ab7b  mov     rdx, rsi; lpSubKey
0x18000ab7e  mov     rcx, r15; hKey
0x18000ab81  call    cs:__imp_RegOpenKeyExW
0x18000ab87  test    eax, eax
0x18000ab89  jnz     short loc_18000ABA8
0x18000ab8b  mov     eax, edi
0x18000ab8d  test    rbx, rbx
0x18000ab90  jz      short loc_18000AB9B
0x18000ab92  mov     rcx, rbx; hKey
0x18000ab95  call    cs:__imp_RegCloseKey
0x18000ab9b  mov     rbx, [rsp+2310h+hKey]
0x18000aba0  mov     [rbp+2210h+var_2290], rbx
0x18000aba4  test    eax, eax
0x18000aba6  jz      short loc_18000AC0E
0x18000aba8  mov     dword ptr [rsp+2310h+hKey], edi
0x18000abac  mov     [rsp+2310h+var_2298], rdi
0x18000abb1  lea     rax, [rsp+2310h+hKey]
0x18000abb6  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x18000abbb  lea     rax, [rsp+2310h+var_2298]
0x18000abc0  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18000abc5  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000abca  mov     [rsp+2310h+samDesired], r14d; samDesired
0x18000abcf  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x18000abd3  xor     r9d, r9d; lpClass
0x18000abd6  xor     r8d, r8d; Reserved
0x18000abd9  mov     rdx, rsi; lpSubKey
0x18000abdc  mov     rcx, r15; hKey
0x18000abdf  call    cs:__imp_RegCreateKeyExW
0x18000abe5  test    eax, eax
0x18000abe7  jnz     loc_18000AF4B
0x18000abed  mov     eax, edi
0x18000abef  test    rbx, rbx
0x18000abf2  jz      short loc_18000ABFD
0x18000abf4  mov     rcx, rbx; hKey
0x18000abf7  call    cs:__imp_RegCloseKey
0x18000abfd  mov     rbx, [rsp+2310h+var_2298]
0x18000ac02  mov     [rbp+2210h+var_2290], rbx
0x18000ac06  test    eax, eax
0x18000ac08  jnz     loc_18000AF4B
0x18000ac0e  mov     rdx, rsi; unsigned __int16 *
0x18000ac11  mov     rcx, r13; this
0x18000ac14  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000ac19  mov     edi, eax
0x18000ac1b  xor     ecx, ecx
0x18000ac1d  test    eax, eax
0x18000ac1f  js      loc_18000AF54
0x18000ac25  cmp     word ptr [rsi], 3Dh ; '='
0x18000ac29  jnz     short loc_18000AC4D
0x18000ac2b  mov     r9, rsi; unsigned __int16 *
0x18000ac2e  xor     r8d, r8d; unsigned __int16 *
0x18000ac31  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x18000ac35  mov     rcx, r13; this
0x18000ac38  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000ac3d  mov     edi, eax
0x18000ac3f  mov     rbx, [rbp+2210h+var_2290]
0x18000ac43  test    eax, eax
0x18000ac45  js      loc_18000AF54
0x18000ac4b  xor     ecx, ecx
0x18000ac4d  mov     r12d, [rsp+2310h+var_22A8]
0x18000ac52  cmp     word ptr [rsi], 7Bh ; '{'
0x18000ac56  jnz     loc_18000ADED
0x18000ac5c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ac60  inc     rax
0x18000ac63  cmp     [rsi+rax*2], cx
0x18000ac67  jnz     short loc_18000AC60
0x18000ac69  cmp     rax, 1
0x18000ac6d  jnz     loc_18000ADED
0x18000ac73  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x18000ac7b  mov     r9d, r12d; int
0x18000ac7e  mov     r8, rbx; HKEY
0x18000ac81  mov     rdx, rsi; unsigned __int16 *
0x18000ac84  mov     rcx, r13; this
0x18000ac87  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000ac8c  mov     edi, eax
0x18000ac8e  test    eax, eax
0x18000ac90  js      loc_18000AF54
0x18000ac96  mov     rdx, rsi; unsigned __int16 *
0x18000ac99  mov     rcx, r13; this
0x18000ac9c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000aca1  jmp     loc_18000AAD1
  ... truncated ...
```
