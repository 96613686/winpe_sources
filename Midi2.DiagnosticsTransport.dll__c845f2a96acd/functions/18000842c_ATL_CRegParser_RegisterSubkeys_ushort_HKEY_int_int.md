# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000842c`
- end: `0x180008bc3`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1800080bc`
- `0x18000842c`

## callees

- `0x1800033d0`
- `0x1800058d0`
- `0x180006000`
- `0x180006018`
- `0x180006730`
- `0x1800078fc`
- `0x180007f6c`
- `0x18000842c`
- `0x180009840`
- `0x180011f90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000890a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000890a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008672`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008720`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008769`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800088b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008672`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008720`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008769`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800088b8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000868f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000868f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800086a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008734`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000877d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800087df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800088d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008aea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008b44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008b80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008b90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800086a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008734`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000877d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800087df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800088d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008aea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008b44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008b80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008b90`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800087c7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800087c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180008a36`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180008acc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180008a36`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180008acc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000850e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800086d9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000850e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800086d9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800084a9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800084bc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000853a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800085a3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800085d1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008a59`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800084a9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800084bc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000853a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800085a3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800085d1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008a59`

## string_xrefs

- `0x1800084b2`: `ForceRemove`
- `0x180008599`: `NoRemove`
- `0x18000849f`: `Delete`

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
  LSTATUS v18; // eax
  HKEY v19; // r14
  LSTATUS v20; // eax
  int v21; // eax
  WCHAR v22; // ax
  const WCHAR *v23; // rcx
  LSTATUS v24; // eax
  LSTATUS v25; // eax
  __int64 v26; // rax
  LSTATUS v27; // r14d
  int v28; // r15d
  int v29; // eax
  __int64 v30; // rax
  int v31; // r14d
  unsigned int v32; // ecx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+68h] [rbp-98h]
  HKEY v35; // [rsp+70h] [rbp-90h]
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v37[3]; // [rsp+80h] [rbp-80h] BYREF
  HKEY v38; // [rsp+98h] [rbp-68h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+A8h] [rbp-58h]
  WCHAR String1[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v5 = a4;
  v34 = a4;
  v6 = a3;
  v35 = a3;
  v9 = 0;
  memset(v37, 0, sizeof(v37));
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
        v38 = 0;
        v39 = 0;
        v40 = 0;
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
            v38 = v6;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v38, a2);
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
    v22 = *a2;
    if ( *a2 )
    {
      v23 = a2;
      while ( v22 != 92 )
      {
        v23 = CharNextW(v23);
        v22 = *v23;
        if ( !*v23 )
          goto LABEL_43;
      }
      if ( v23 )
        goto LABEL_117;
    }
LABEL_43:
    if ( v34 )
    {
      hKey = 0;
      if ( RegOpenKeyExW(v6, a2, 0, 0x2001Fu, &hKey) )
        goto LABEL_126;
      v24 = 0;
      if ( v9 )
        v24 = RegCloseKey(v9);
      v9 = hKey;
      v37[0] = hKey;
      if ( v24 )
      {
LABEL_126:
        hKey = 0;
        if ( RegOpenKeyExW(v6, a2, 0, 0x20019u, &hKey) )
          goto LABEL_127;
        v25 = 0;
        if ( v9 )
          v25 = RegCloseKey(v9);
        v9 = hKey;
        v37[0] = hKey;
        if ( v25 )
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
          v37[0] = phkResult;
          if ( v18 )
            goto LABEL_109;
        }
      }
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
      if ( *a2 == 61 )
      {
        v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)v37, 0, a2);
        Token = v17;
        v9 = (HKEY)v37[0];
        goto LABEL_59;
      }
LABEL_60:
      v5 = v34;
LABEL_61:
      if ( *a2 != 123 )
        goto LABEL_93;
      v26 = -1;
      do
        ++v26;
      while ( a2[v26] );
      if ( v26 != 1 )
        goto LABEL_93;
      Token = ATL::CRegParser::RegisterSubkeys(this, a2, v9, v5, 0);
      if ( Token < 0 )
        goto LABEL_111;
      v21 = ATL::CRegParser::NextToken(this, a2);
LABEL_35:
      Token = v21;
      if ( v21 < 0 )
        goto LABEL_111;
      goto LABEL_93;
    }
    if ( a5 )
    {
      v27 = 2;
    }
    else
    {
      phkResult = 0;
      v27 = RegOpenKeyExW(v6, a2, 0, 0x20019u, &phkResult);
      if ( !v27 )
      {
        v27 = 0;
        if ( v9 )
          v27 = RegCloseKey(v9);
        v9 = phkResult;
        v37[0] = phkResult;
      }
    }
    v28 = 1;
    if ( !v27 )
      v28 = a5;
    v29 = _o_wcsncpy_s(String1, 260, a2, -1);
    if ( v29 )
    {
      if ( v29 == 12 )
        ATL::AtlThrowImpl(-2147024882);
      if ( v29 == 22 || v29 == 34 )
        ATL::AtlThrowImpl(-2147024809);
      if ( v29 != 80 )
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
      v30 = -1;
      do
        ++v30;
      while ( a2[v30] );
      if ( v30 == 1 )
      {
        Token = ATL::CRegParser::RegisterSubkeys(this, a2, v9, 0, v28);
        if ( Token < 0 && !v28 )
          goto LABEL_111;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_111;
      }
    }
    if ( v27 == 2 )
      goto LABEL_92;
    if ( v27 )
    {
      if ( a5 )
      {
LABEL_92:
        v6 = v35;
        goto LABEL_93;
      }
      v32 = v27;
LABEL_110:
      Token = ATL::AtlHresultFromWin32(v32);
      goto LABEL_111;
    }
    v31 = 0;
    if ( a5 )
    {
      LODWORD(hKey) = 0;
      if ( !RegQueryInfoKeyW(v9, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      {
        if ( (_DWORD)hKey )
        {
          while ( lstrcmpiW(String1, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v31]) )
          {
            if ( ++v31 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v37, String1);
                v9 = (HKEY)v37[0];
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
      LOBYTE(v31) = (_DWORD)hKey != 0;
    if ( v9 )
    {
      v18 = RegCloseKey(v9);
      v9 = 0;
      v37[0] = 0;
      if ( v18 )
      {
LABEL_109:
        v32 = v18;
        goto LABEL_110;
      }
    }
    if ( !v16 || v31 )
      goto LABEL_92;
    v39 = 0;
    v40 = 0;
    v6 = v35;
    v38 = v35;
    v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v38, String1);
    if ( v18 )
      goto LABEL_109;
LABEL_93:
    if ( *a2 == 125 )
      goto LABEL_111;
    v5 = v34;
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
  if ( v34 )
  {
    v39 = 0;
    v40 = 0;
    v38 = v6;
    v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)&v38, ValueName, a2);
    Token = v17;
LABEL_59:
    if ( v17 < 0 )
      goto LABEL_111;
    goto LABEL_60;
  }
  if ( a5 || !v16 )
  {
LABEL_34:
    v21 = ATL::CRegParser::SkipAssignment(this, a2);
    goto LABEL_35;
  }
  hKey = 0;
  v18 = RegOpenKeyExW(v6, 0, 0, 0x20006u, &hKey);
  if ( v18 )
    goto LABEL_109;
  v19 = hKey;
  v20 = RegDeleteValueW(hKey, ValueName);
  if ( (v20 & 0xFFFFFFFD) == 0 )
  {
    if ( v19 )
      RegCloseKey(v19);
    goto LABEL_34;
  }
  Token = ATL::AtlHresultFromWin32(v20);
  if ( v19 )
    RegCloseKey(v19);
LABEL_111:
  if ( v9 )
    RegCloseKey(v9);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x18000842c  push    rbp
0x18000842e  push    rbx
0x18000842f  push    rsi
0x180008430  push    rdi
0x180008431  push    r12
0x180008433  push    r13
0x180008435  push    r14
0x180008437  push    r15
0x180008439  lea     rbp, [rsp-21D8h]
0x180008441  mov     eax, 22D8h
0x180008446  call    _alloca_probe
0x18000844b  sub     rsp, rax
0x18000844e  mov     rax, cs:__security_cookie
0x180008455  xor     rax, rsp
0x180008458  mov     [rbp+2210h+var_50], rax
0x18000845f  mov     r12d, r9d
0x180008462  mov     [rsp+2310h+var_22A8], r9d
0x180008467  mov     r15, r8
0x18000846a  mov     [rsp+2310h+var_22A0], r8
0x18000846f  mov     rsi, rdx
0x180008472  mov     r13, rcx
0x180008475  xor     eax, eax
0x180008477  mov     ebx, eax
0x180008479  mov     [rbp+2210h+var_2290], rax
0x18000847d  mov     [rbp+2210h+var_2288], rax
0x180008481  mov     [rbp+2210h+var_2280], rax
0x180008485  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000848a  mov     edi, eax
0x18000848c  test    eax, eax
0x18000848e  jns     short loc_180008495
0x180008490  jmp     loc_180008B4C
0x180008495  cmp     word ptr [rsi], 7Dh ; '}'
0x180008499  jz      loc_180008B3C
0x18000849f  lea     rdx, String2; "Delete"
0x1800084a6  mov     rcx, rsi; lpString1
0x1800084a9  call    cs:__imp_lstrcmpiW
0x1800084af  mov     r14d, eax
0x1800084b2  lea     rdx, aForceremove; "ForceRemove"
0x1800084b9  mov     rcx, rsi; lpString1
0x1800084bc  call    cs:__imp_lstrcmpiW
0x1800084c2  xor     edi, edi
0x1800084c4  test    eax, eax
0x1800084c6  jz      short loc_1800084D1
0x1800084c8  test    r14d, r14d
0x1800084cb  jnz     loc_180008593
0x1800084d1  mov     rdx, rsi; unsigned __int16 *
0x1800084d4  mov     rcx, r13; this
0x1800084d7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800084dc  mov     edi, eax
0x1800084de  test    eax, eax
0x1800084e0  js      loc_180008B3C
0x1800084e6  xor     edi, edi
0x1800084e8  test    r12d, r12d
0x1800084eb  jz      loc_180008593
0x1800084f1  mov     [rbp+2210h+var_2278], rdi
0x1800084f5  mov     [rbp+2210h+var_2270], rdi
0x1800084f9  mov     [rbp+2210h+var_2268], rdi
0x1800084fd  movzx   eax, word ptr [rsi]
0x180008500  test    ax, ax
0x180008503  jz      short loc_18000852A
0x180008505  mov     rcx, rsi; lpsz
0x180008508  cmp     ax, 5Ch ; '\'
0x18000850c  jz      short loc_180008521
0x18000850e  call    cs:__imp_CharNextW
0x180008514  mov     rcx, rax
0x180008517  movzx   eax, word ptr [rax]
0x18000851a  test    ax, ax
0x18000851d  jnz     short loc_180008508
0x18000851f  jmp     short loc_18000852A
0x180008521  test    rcx, rcx
0x180008524  jnz     loc_180008B88
0x18000852a  mov     edx, edi
0x18000852c  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180008533  mov     rdx, [rax+rdx*8]; lpString2
0x180008537  mov     rcx, rsi; lpString1
0x18000853a  call    cs:__imp_lstrcmpiW
0x180008540  test    eax, eax
0x180008542  jz      short loc_18000855B
0x180008544  inc     edi
0x180008546  cmp     edi, 0Ch
0x180008549  jl      short loc_18000852A
0x18000854b  mov     [rbp+2210h+var_2278], r15
0x18000854f  mov     rdx, rsi; unsigned __int16 *
0x180008552  lea     rcx, [rbp+2210h+var_2278]; this
0x180008556  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000855b  xor     edi, edi
0x18000855d  test    r14d, r14d
0x180008560  jnz     short loc_180008593
0x180008562  mov     rdx, rsi; unsigned __int16 *
0x180008565  mov     rcx, r13; this
0x180008568  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000856d  mov     edi, eax
0x18000856f  test    eax, eax
0x180008571  js      loc_180008B3C
0x180008577  mov     rdx, rsi; unsigned __int16 *
0x18000857a  mov     rcx, r13; this
0x18000857d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180008582  mov     edi, eax
0x180008584  xor     ecx, ecx
0x180008586  test    eax, eax
0x180008588  js      loc_180008B3C
0x18000858e  jmp     loc_18000883A
0x180008593  mov     r12d, 1
0x180008599  lea     rdx, aNoremove; "NoRemove"
0x1800085a0  mov     rcx, rsi; lpString1
0x1800085a3  call    cs:__imp_lstrcmpiW
0x1800085a9  test    eax, eax
0x1800085ab  jnz     short loc_1800085C7
0x1800085ad  mov     r12d, edi
0x1800085b0  mov     rdx, rsi; unsigned __int16 *
0x1800085b3  mov     rcx, r13; this
0x1800085b6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800085bb  mov     edi, eax
0x1800085bd  test    eax, eax
0x1800085bf  js      loc_180008B3C
0x1800085c5  xor     edi, edi
0x1800085c7  lea     rdx, aVal; "Val"
0x1800085ce  mov     rcx, rsi; lpString1
0x1800085d1  call    cs:__imp_lstrcmpiW
0x1800085d7  test    eax, eax
0x1800085d9  jnz     loc_1800086C8
0x1800085df  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x1800085e6  mov     rcx, r13; this
0x1800085e9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800085ee  mov     edi, eax
0x1800085f0  test    eax, eax
0x1800085f2  js      loc_180008B3C
0x1800085f8  mov     rdx, rsi; unsigned __int16 *
0x1800085fb  mov     rcx, r13; this
0x1800085fe  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008603  mov     edi, eax
0x180008605  test    eax, eax
0x180008607  js      loc_180008B3C
0x18000860d  cmp     word ptr [rsi], 3Dh ; '='
0x180008611  jnz     loc_180008B88
0x180008617  xor     edi, edi
0x180008619  cmp     [rsp+2310h+var_22A8], edi
0x18000861d  jz      short loc_180008648
0x18000861f  mov     [rbp+2210h+var_2270], rdi
0x180008623  mov     [rbp+2210h+var_2268], rdi
0x180008627  mov     [rbp+2210h+var_2278], r15
0x18000862b  mov     r9, rsi; unsigned __int16 *
0x18000862e  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180008635  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180008639  mov     rcx, r13; this
0x18000863c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180008641  mov     edi, eax
0x180008643  jmp     loc_18000882B
0x180008648  cmp     [rbp+2210h+arg_20], edi
0x18000864e  jnz     short loc_1800086AE
0x180008650  test    r12d, r12d
0x180008653  jz      short loc_1800086AE
0x180008655  mov     [rsp+2310h+hKey], rdi
0x18000865a  lea     rax, [rsp+2310h+hKey]
0x18000865f  mov     [rsp+2310h+phkResult], rax; phkResult
0x180008664  mov     r9d, 20006h; samDesired
0x18000866a  xor     r8d, r8d; ulOptions
0x18000866d  xor     edx, edx; lpSubKey
0x18000866f  mov     rcx, r15; hKey
0x180008672  call    cs:__imp_RegOpenKeyExW
0x180008678  test    eax, eax
0x18000867a  jnz     loc_180008B33
0x180008680  mov     r14, [rsp+2310h+hKey]
0x180008685  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18000868c  mov     rcx, r14; hKey
0x18000868f  call    cs:__imp_RegDeleteValueW
0x180008695  test    eax, 0FFFFFFFDh
0x18000869a  jnz     loc_180008B6F
0x1800086a0  test    r14, r14
0x1800086a3  jz      short loc_1800086AE
0x1800086a5  mov     rcx, r14; hKey
0x1800086a8  call    cs:__imp_RegCloseKey
0x1800086ae  mov     rdx, rsi; unsigned __int16 *
0x1800086b1  mov     rcx, r13; this
0x1800086b4  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800086b9  mov     edi, eax
0x1800086bb  test    eax, eax
0x1800086bd  js      loc_180008B3C
0x1800086c3  jmp     loc_1800089D5
0x1800086c8  movzx   eax, word ptr [rsi]
0x1800086cb  test    ax, ax
0x1800086ce  jz      short loc_1800086F5
0x1800086d0  mov     rcx, rsi; lpsz
0x1800086d3  cmp     ax, 5Ch ; '\'
0x1800086d7  jz      short loc_1800086EC
0x1800086d9  call    cs:__imp_CharNextW
0x1800086df  mov     rcx, rax
0x1800086e2  movzx   eax, word ptr [rax]
0x1800086e5  test    ax, ax
0x1800086e8  jnz     short loc_1800086D3
0x1800086ea  jmp     short loc_1800086F5
0x1800086ec  test    rcx, rcx
0x1800086ef  jnz     loc_180008B88
0x1800086f5  cmp     [rsp+2310h+var_22A8], edi
0x1800086f9  jz      loc_18000888E
0x1800086ff  mov     [rsp+2310h+hKey], rdi
0x180008704  lea     rax, [rsp+2310h+hKey]
0x180008709  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000870e  mov     r14d, 2001Fh
0x180008714  mov     r9d, r14d; samDesired
0x180008717  xor     r8d, r8d; ulOptions
0x18000871a  mov     rdx, rsi; lpSubKey
0x18000871d  mov     rcx, r15; hKey
0x180008720  call    cs:__imp_RegOpenKeyExW
0x180008726  test    eax, eax
0x180008728  jnz     short loc_18000874B
0x18000872a  mov     eax, edi
0x18000872c  test    rbx, rbx
0x18000872f  jz      short loc_18000873A
0x180008731  mov     rcx, rbx; hKey
0x180008734  call    cs:__imp_RegCloseKey
0x18000873a  mov     rbx, [rsp+2310h+hKey]
0x18000873f  mov     [rbp+2210h+var_2290], rbx
0x180008743  test    eax, eax
0x180008745  jz      loc_1800087F6
0x18000874b  mov     [rsp+2310h+hKey], rdi
0x180008750  lea     rax, [rsp+2310h+hKey]
0x180008755  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000875a  mov     r9d, 20019h; samDesired
0x180008760  xor     r8d, r8d; ulOptions
0x180008763  mov     rdx, rsi; lpSubKey
0x180008766  mov     rcx, r15; hKey
0x180008769  call    cs:__imp_RegOpenKeyExW
0x18000876f  test    eax, eax
0x180008771  jnz     short loc_180008790
0x180008773  mov     eax, edi
0x180008775  test    rbx, rbx
0x180008778  jz      short loc_180008783
0x18000877a  mov     rcx, rbx; hKey
0x18000877d  call    cs:__imp_RegCloseKey
0x180008783  mov     rbx, [rsp+2310h+hKey]
0x180008788  mov     [rbp+2210h+var_2290], rbx
0x18000878c  test    eax, eax
0x18000878e  jz      short loc_1800087F6
0x180008790  mov     dword ptr [rsp+2310h+hKey], edi
0x180008794  mov     [rsp+2310h+var_2298], rdi
0x180008799  lea     rax, [rsp+2310h+hKey]
0x18000879e  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x1800087a3  lea     rax, [rsp+2310h+var_2298]
0x1800087a8  mov     [rsp+2310h+var_22D8], rax; phkResult
0x1800087ad  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800087b2  mov     [rsp+2310h+samDesired], r14d; samDesired
0x1800087b7  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x1800087bb  xor     r9d, r9d; lpClass
0x1800087be  xor     r8d, r8d; Reserved
0x1800087c1  mov     rdx, rsi; lpSubKey
0x1800087c4  mov     rcx, r15; hKey
0x1800087c7  call    cs:__imp_RegCreateKeyExW
0x1800087cd  test    eax, eax
0x1800087cf  jnz     loc_180008B33
0x1800087d5  mov     eax, edi
0x1800087d7  test    rbx, rbx
0x1800087da  jz      short loc_1800087E5
0x1800087dc  mov     rcx, rbx; hKey
0x1800087df  call    cs:__imp_RegCloseKey
0x1800087e5  mov     rbx, [rsp+2310h+var_2298]
0x1800087ea  mov     [rbp+2210h+var_2290], rbx
0x1800087ee  test    eax, eax
0x1800087f0  jnz     loc_180008B33
0x1800087f6  mov     rdx, rsi; unsigned __int16 *
0x1800087f9  mov     rcx, r13; this
0x1800087fc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008801  mov     edi, eax
0x180008803  xor     ecx, ecx
0x180008805  test    eax, eax
0x180008807  js      loc_180008B3C
0x18000880d  cmp     word ptr [rsi], 3Dh ; '='
0x180008811  jnz     short loc_180008835
0x180008813  mov     r9, rsi; unsigned __int16 *
0x180008816  xor     r8d, r8d; unsigned __int16 *
0x180008819  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x18000881d  mov     rcx, r13; this
0x180008820  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180008825  mov     edi, eax
0x180008827  mov     rbx, [rbp+2210h+var_2290]
0x18000882b  test    eax, eax
0x18000882d  js      loc_180008B3C
0x180008833  xor     ecx, ecx
0x180008835  mov     r12d, [rsp+2310h+var_22A8]
0x18000883a  cmp     word ptr [rsi], 7Bh ; '{'
0x18000883e  jnz     loc_1800089D5
0x180008844  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008848  inc     rax
0x18000884b  cmp     [rsi+rax*2], cx
0x18000884f  jnz     short loc_180008848
0x180008851  cmp     rax, 1
0x180008855  jnz     loc_1800089D5
0x18000885b  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180008863  mov     r9d, r12d; int
0x180008866  mov     r8, rbx; HKEY
0x180008869  mov     rdx, rsi; unsigned __int16 *
0x18000886c  mov     rcx, r13; this
0x18000886f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008874  mov     edi, eax
0x180008876  test    eax, eax
0x180008878  js      loc_180008B3C
0x18000887e  mov     rdx, rsi; unsigned __int16 *
0x180008881  mov     rcx, r13; this
0x180008884  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008889  jmp     loc_1800086B9
  ... truncated ...
```
