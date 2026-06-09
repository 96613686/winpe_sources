# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180006c0c`
- end: `0x1800073a3`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18000689c`
- `0x180006c0c`

## callees

- `0x180001ef0`
- `0x1800040b0`
- `0x1800047e0`
- `0x1800047f8`
- `0x180004f10`
- `0x1800060dc`
- `0x18000674c`
- `0x180006c0c`
- `0x180008020`
- `0x18000e890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800070ea`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800070ea`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180006e6f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180006e6f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006fa7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006fa7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006e52`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006f00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006f49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007098`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006e52`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006f00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006f49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007098`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006e88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006fbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800070b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800072ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007324`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007360`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007370`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006e88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006fbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800070b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800072ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007324`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007360`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007370`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180007216`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800072ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180007216`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800072ac`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006cee`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006eb9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006cee`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006eb9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006c89`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006c9c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006d1a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006d83`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006db1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007239`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006c89`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006c9c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006d1a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006d83`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006db1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007239`

## string_xrefs

- `0x180006c92`: `ForceRemove`
- `0x180006d79`: `NoRemove`
- `0x180006c7f`: `Delete`

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
0x180006c0c  push    rbp
0x180006c0e  push    rbx
0x180006c0f  push    rsi
0x180006c10  push    rdi
0x180006c11  push    r12
0x180006c13  push    r13
0x180006c15  push    r14
0x180006c17  push    r15
0x180006c19  lea     rbp, [rsp-21D8h]
0x180006c21  mov     eax, 22D8h
0x180006c26  call    _alloca_probe
0x180006c2b  sub     rsp, rax
0x180006c2e  mov     rax, cs:__security_cookie
0x180006c35  xor     rax, rsp
0x180006c38  mov     [rbp+2210h+var_50], rax
0x180006c3f  mov     r12d, r9d
0x180006c42  mov     [rsp+2310h+var_22A8], r9d
0x180006c47  mov     r15, r8
0x180006c4a  mov     [rsp+2310h+var_22A0], r8
0x180006c4f  mov     rsi, rdx
0x180006c52  mov     r13, rcx
0x180006c55  xor     eax, eax
0x180006c57  mov     ebx, eax
0x180006c59  mov     [rbp+2210h+var_2290], rax
0x180006c5d  mov     [rbp+2210h+var_2288], rax
0x180006c61  mov     [rbp+2210h+var_2280], rax
0x180006c65  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006c6a  mov     edi, eax
0x180006c6c  test    eax, eax
0x180006c6e  jns     short loc_180006C75
0x180006c70  jmp     loc_18000732C
0x180006c75  cmp     word ptr [rsi], 7Dh ; '}'
0x180006c79  jz      loc_18000731C
0x180006c7f  lea     rdx, String2; "Delete"
0x180006c86  mov     rcx, rsi; lpString1
0x180006c89  call    cs:__imp_lstrcmpiW
0x180006c8f  mov     r14d, eax
0x180006c92  lea     rdx, aForceremove; "ForceRemove"
0x180006c99  mov     rcx, rsi; lpString1
0x180006c9c  call    cs:__imp_lstrcmpiW
0x180006ca2  xor     edi, edi
0x180006ca4  test    eax, eax
0x180006ca6  jz      short loc_180006CB1
0x180006ca8  test    r14d, r14d
0x180006cab  jnz     loc_180006D73
0x180006cb1  mov     rdx, rsi; unsigned __int16 *
0x180006cb4  mov     rcx, r13; this
0x180006cb7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006cbc  mov     edi, eax
0x180006cbe  test    eax, eax
0x180006cc0  js      loc_18000731C
0x180006cc6  xor     edi, edi
0x180006cc8  test    r12d, r12d
0x180006ccb  jz      loc_180006D73
0x180006cd1  mov     [rbp+2210h+var_2278], rdi
0x180006cd5  mov     [rbp+2210h+var_2270], rdi
0x180006cd9  mov     [rbp+2210h+var_2268], rdi
0x180006cdd  movzx   eax, word ptr [rsi]
0x180006ce0  test    ax, ax
0x180006ce3  jz      short loc_180006D0A
0x180006ce5  mov     rcx, rsi; lpsz
0x180006ce8  cmp     ax, 5Ch ; '\'
0x180006cec  jz      short loc_180006D01
0x180006cee  call    cs:__imp_CharNextW
0x180006cf4  mov     rcx, rax
0x180006cf7  movzx   eax, word ptr [rax]
0x180006cfa  test    ax, ax
0x180006cfd  jnz     short loc_180006CE8
0x180006cff  jmp     short loc_180006D0A
0x180006d01  test    rcx, rcx
0x180006d04  jnz     loc_180007368
0x180006d0a  mov     edx, edi
0x180006d0c  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180006d13  mov     rdx, [rax+rdx*8]; lpString2
0x180006d17  mov     rcx, rsi; lpString1
0x180006d1a  call    cs:__imp_lstrcmpiW
0x180006d20  test    eax, eax
0x180006d22  jz      short loc_180006D3B
0x180006d24  inc     edi
0x180006d26  cmp     edi, 0Ch
0x180006d29  jl      short loc_180006D0A
0x180006d2b  mov     [rbp+2210h+var_2278], r15
0x180006d2f  mov     rdx, rsi; unsigned __int16 *
0x180006d32  lea     rcx, [rbp+2210h+var_2278]; this
0x180006d36  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180006d3b  xor     edi, edi
0x180006d3d  test    r14d, r14d
0x180006d40  jnz     short loc_180006D73
0x180006d42  mov     rdx, rsi; unsigned __int16 *
0x180006d45  mov     rcx, r13; this
0x180006d48  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006d4d  mov     edi, eax
0x180006d4f  test    eax, eax
0x180006d51  js      loc_18000731C
0x180006d57  mov     rdx, rsi; unsigned __int16 *
0x180006d5a  mov     rcx, r13; this
0x180006d5d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180006d62  mov     edi, eax
0x180006d64  xor     ecx, ecx
0x180006d66  test    eax, eax
0x180006d68  js      loc_18000731C
0x180006d6e  jmp     loc_18000701A
0x180006d73  mov     r12d, 1
0x180006d79  lea     rdx, aNoremove; "NoRemove"
0x180006d80  mov     rcx, rsi; lpString1
0x180006d83  call    cs:__imp_lstrcmpiW
0x180006d89  test    eax, eax
0x180006d8b  jnz     short loc_180006DA7
0x180006d8d  mov     r12d, edi
0x180006d90  mov     rdx, rsi; unsigned __int16 *
0x180006d93  mov     rcx, r13; this
0x180006d96  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006d9b  mov     edi, eax
0x180006d9d  test    eax, eax
0x180006d9f  js      loc_18000731C
0x180006da5  xor     edi, edi
0x180006da7  lea     rdx, aVal; "Val"
0x180006dae  mov     rcx, rsi; lpString1
0x180006db1  call    cs:__imp_lstrcmpiW
0x180006db7  test    eax, eax
0x180006db9  jnz     loc_180006EA8
0x180006dbf  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180006dc6  mov     rcx, r13; this
0x180006dc9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006dce  mov     edi, eax
0x180006dd0  test    eax, eax
0x180006dd2  js      loc_18000731C
0x180006dd8  mov     rdx, rsi; unsigned __int16 *
0x180006ddb  mov     rcx, r13; this
0x180006dde  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006de3  mov     edi, eax
0x180006de5  test    eax, eax
0x180006de7  js      loc_18000731C
0x180006ded  cmp     word ptr [rsi], 3Dh ; '='
0x180006df1  jnz     loc_180007368
0x180006df7  xor     edi, edi
0x180006df9  cmp     [rsp+2310h+var_22A8], edi
0x180006dfd  jz      short loc_180006E28
0x180006dff  mov     [rbp+2210h+var_2270], rdi
0x180006e03  mov     [rbp+2210h+var_2268], rdi
0x180006e07  mov     [rbp+2210h+var_2278], r15
0x180006e0b  mov     r9, rsi; unsigned __int16 *
0x180006e0e  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180006e15  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180006e19  mov     rcx, r13; this
0x180006e1c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180006e21  mov     edi, eax
0x180006e23  jmp     loc_18000700B
0x180006e28  cmp     [rbp+2210h+arg_20], edi
0x180006e2e  jnz     short loc_180006E8E
0x180006e30  test    r12d, r12d
0x180006e33  jz      short loc_180006E8E
0x180006e35  mov     [rsp+2310h+hKey], rdi
0x180006e3a  lea     rax, [rsp+2310h+hKey]
0x180006e3f  mov     [rsp+2310h+phkResult], rax; phkResult
0x180006e44  mov     r9d, 20006h; samDesired
0x180006e4a  xor     r8d, r8d; ulOptions
0x180006e4d  xor     edx, edx; lpSubKey
0x180006e4f  mov     rcx, r15; hKey
0x180006e52  call    cs:__imp_RegOpenKeyExW
0x180006e58  test    eax, eax
0x180006e5a  jnz     loc_180007313
0x180006e60  mov     r14, [rsp+2310h+hKey]
0x180006e65  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180006e6c  mov     rcx, r14; hKey
0x180006e6f  call    cs:__imp_RegDeleteValueW
0x180006e75  test    eax, 0FFFFFFFDh
0x180006e7a  jnz     loc_18000734F
0x180006e80  test    r14, r14
0x180006e83  jz      short loc_180006E8E
0x180006e85  mov     rcx, r14; hKey
0x180006e88  call    cs:__imp_RegCloseKey
0x180006e8e  mov     rdx, rsi; unsigned __int16 *
0x180006e91  mov     rcx, r13; this
0x180006e94  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180006e99  mov     edi, eax
0x180006e9b  test    eax, eax
0x180006e9d  js      loc_18000731C
0x180006ea3  jmp     loc_1800071B5
0x180006ea8  movzx   eax, word ptr [rsi]
0x180006eab  test    ax, ax
0x180006eae  jz      short loc_180006ED5
0x180006eb0  mov     rcx, rsi; lpsz
0x180006eb3  cmp     ax, 5Ch ; '\'
0x180006eb7  jz      short loc_180006ECC
0x180006eb9  call    cs:__imp_CharNextW
0x180006ebf  mov     rcx, rax
0x180006ec2  movzx   eax, word ptr [rax]
0x180006ec5  test    ax, ax
0x180006ec8  jnz     short loc_180006EB3
0x180006eca  jmp     short loc_180006ED5
0x180006ecc  test    rcx, rcx
0x180006ecf  jnz     loc_180007368
0x180006ed5  cmp     [rsp+2310h+var_22A8], edi
0x180006ed9  jz      loc_18000706E
0x180006edf  mov     [rsp+2310h+hKey], rdi
0x180006ee4  lea     rax, [rsp+2310h+hKey]
0x180006ee9  mov     [rsp+2310h+phkResult], rax; phkResult
0x180006eee  mov     r14d, 2001Fh
0x180006ef4  mov     r9d, r14d; samDesired
0x180006ef7  xor     r8d, r8d; ulOptions
0x180006efa  mov     rdx, rsi; lpSubKey
0x180006efd  mov     rcx, r15; hKey
0x180006f00  call    cs:__imp_RegOpenKeyExW
0x180006f06  test    eax, eax
0x180006f08  jnz     short loc_180006F2B
0x180006f0a  mov     eax, edi
0x180006f0c  test    rbx, rbx
0x180006f0f  jz      short loc_180006F1A
0x180006f11  mov     rcx, rbx; hKey
0x180006f14  call    cs:__imp_RegCloseKey
0x180006f1a  mov     rbx, [rsp+2310h+hKey]
0x180006f1f  mov     [rbp+2210h+var_2290], rbx
0x180006f23  test    eax, eax
0x180006f25  jz      loc_180006FD6
0x180006f2b  mov     [rsp+2310h+hKey], rdi
0x180006f30  lea     rax, [rsp+2310h+hKey]
0x180006f35  mov     [rsp+2310h+phkResult], rax; phkResult
0x180006f3a  mov     r9d, 20019h; samDesired
0x180006f40  xor     r8d, r8d; ulOptions
0x180006f43  mov     rdx, rsi; lpSubKey
0x180006f46  mov     rcx, r15; hKey
0x180006f49  call    cs:__imp_RegOpenKeyExW
0x180006f4f  test    eax, eax
0x180006f51  jnz     short loc_180006F70
0x180006f53  mov     eax, edi
0x180006f55  test    rbx, rbx
0x180006f58  jz      short loc_180006F63
0x180006f5a  mov     rcx, rbx; hKey
0x180006f5d  call    cs:__imp_RegCloseKey
0x180006f63  mov     rbx, [rsp+2310h+hKey]
0x180006f68  mov     [rbp+2210h+var_2290], rbx
0x180006f6c  test    eax, eax
0x180006f6e  jz      short loc_180006FD6
0x180006f70  mov     dword ptr [rsp+2310h+hKey], edi
0x180006f74  mov     [rsp+2310h+var_2298], rdi
0x180006f79  lea     rax, [rsp+2310h+hKey]
0x180006f7e  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180006f83  lea     rax, [rsp+2310h+var_2298]
0x180006f88  mov     [rsp+2310h+var_22D8], rax; phkResult
0x180006f8d  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180006f92  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180006f97  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180006f9b  xor     r9d, r9d; lpClass
0x180006f9e  xor     r8d, r8d; Reserved
0x180006fa1  mov     rdx, rsi; lpSubKey
0x180006fa4  mov     rcx, r15; hKey
0x180006fa7  call    cs:__imp_RegCreateKeyExW
0x180006fad  test    eax, eax
0x180006faf  jnz     loc_180007313
0x180006fb5  mov     eax, edi
0x180006fb7  test    rbx, rbx
0x180006fba  jz      short loc_180006FC5
0x180006fbc  mov     rcx, rbx; hKey
0x180006fbf  call    cs:__imp_RegCloseKey
0x180006fc5  mov     rbx, [rsp+2310h+var_2298]
0x180006fca  mov     [rbp+2210h+var_2290], rbx
0x180006fce  test    eax, eax
0x180006fd0  jnz     loc_180007313
0x180006fd6  mov     rdx, rsi; unsigned __int16 *
0x180006fd9  mov     rcx, r13; this
0x180006fdc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006fe1  mov     edi, eax
0x180006fe3  xor     ecx, ecx
0x180006fe5  test    eax, eax
0x180006fe7  js      loc_18000731C
0x180006fed  cmp     word ptr [rsi], 3Dh ; '='
0x180006ff1  jnz     short loc_180007015
0x180006ff3  mov     r9, rsi; unsigned __int16 *
0x180006ff6  xor     r8d, r8d; unsigned __int16 *
0x180006ff9  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180006ffd  mov     rcx, r13; this
0x180007000  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180007005  mov     edi, eax
0x180007007  mov     rbx, [rbp+2210h+var_2290]
0x18000700b  test    eax, eax
0x18000700d  js      loc_18000731C
0x180007013  xor     ecx, ecx
0x180007015  mov     r12d, [rsp+2310h+var_22A8]
0x18000701a  cmp     word ptr [rsi], 7Bh ; '{'
0x18000701e  jnz     loc_1800071B5
0x180007024  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007028  inc     rax
0x18000702b  cmp     [rsi+rax*2], cx
0x18000702f  jnz     short loc_180007028
0x180007031  cmp     rax, 1
0x180007035  jnz     loc_1800071B5
0x18000703b  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180007043  mov     r9d, r12d; int
0x180007046  mov     r8, rbx; HKEY
0x180007049  mov     rdx, rsi; unsigned __int16 *
0x18000704c  mov     rcx, r13; this
0x18000704f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007054  mov     edi, eax
0x180007056  test    eax, eax
0x180007058  js      loc_18000731C
0x18000705e  mov     rdx, rsi; unsigned __int16 *
0x180007061  mov     rcx, r13; this
0x180007064  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007069  jmp     loc_180006E99
  ... truncated ...
```
