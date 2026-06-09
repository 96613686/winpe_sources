# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180006d1c`
- end: `0x1800074b3`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1800069ac`
- `0x180006d1c`

## callees

- `0x180002000`
- `0x1800041c0`
- `0x1800048f0`
- `0x180004908`
- `0x180005020`
- `0x1800061ec`
- `0x18000685c`
- `0x180006d1c`
- `0x180008140`
- `0x18000cc00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800071fa`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800071fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180007326`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800073bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180007326`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800073bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007024`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000706d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800070cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800071c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800073da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007434`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007470`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007480`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007024`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000706d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800070cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800071c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800073da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007434`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007470`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007480`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800070b7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800070b7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180006f7f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180006f7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006f62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007010`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007059`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800071a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006f62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007010`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007059`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800071a8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006dfe`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006fc9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006dfe`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006fc9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006d99`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006dac`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006e2a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006e93`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006ec1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007349`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006d99`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006dac`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006e2a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006e93`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006ec1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007349`

## string_xrefs

- `0x180006da2`: `ForceRemove`
- `0x180006e89`: `NoRemove`
- `0x180006d8f`: `Delete`

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
0x180006d1c  push    rbp
0x180006d1e  push    rbx
0x180006d1f  push    rsi
0x180006d20  push    rdi
0x180006d21  push    r12
0x180006d23  push    r13
0x180006d25  push    r14
0x180006d27  push    r15
0x180006d29  lea     rbp, [rsp-21D8h]
0x180006d31  mov     eax, 22D8h
0x180006d36  call    _alloca_probe
0x180006d3b  sub     rsp, rax
0x180006d3e  mov     rax, cs:__security_cookie
0x180006d45  xor     rax, rsp
0x180006d48  mov     [rbp+2210h+var_50], rax
0x180006d4f  mov     r12d, r9d
0x180006d52  mov     [rsp+2310h+var_22A8], r9d
0x180006d57  mov     r15, r8
0x180006d5a  mov     [rsp+2310h+var_22A0], r8
0x180006d5f  mov     rsi, rdx
0x180006d62  mov     r13, rcx
0x180006d65  xor     eax, eax
0x180006d67  mov     ebx, eax
0x180006d69  mov     [rbp+2210h+var_2290], rax
0x180006d6d  mov     [rbp+2210h+var_2288], rax
0x180006d71  mov     [rbp+2210h+var_2280], rax
0x180006d75  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006d7a  mov     edi, eax
0x180006d7c  test    eax, eax
0x180006d7e  jns     short loc_180006D85
0x180006d80  jmp     loc_18000743C
0x180006d85  cmp     word ptr [rsi], 7Dh ; '}'
0x180006d89  jz      loc_18000742C
0x180006d8f  lea     rdx, String2; "Delete"
0x180006d96  mov     rcx, rsi; lpString1
0x180006d99  call    cs:__imp_lstrcmpiW
0x180006d9f  mov     r14d, eax
0x180006da2  lea     rdx, aForceremove; "ForceRemove"
0x180006da9  mov     rcx, rsi; lpString1
0x180006dac  call    cs:__imp_lstrcmpiW
0x180006db2  xor     edi, edi
0x180006db4  test    eax, eax
0x180006db6  jz      short loc_180006DC1
0x180006db8  test    r14d, r14d
0x180006dbb  jnz     loc_180006E83
0x180006dc1  mov     rdx, rsi; unsigned __int16 *
0x180006dc4  mov     rcx, r13; this
0x180006dc7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006dcc  mov     edi, eax
0x180006dce  test    eax, eax
0x180006dd0  js      loc_18000742C
0x180006dd6  xor     edi, edi
0x180006dd8  test    r12d, r12d
0x180006ddb  jz      loc_180006E83
0x180006de1  mov     [rbp+2210h+var_2278], rdi
0x180006de5  mov     [rbp+2210h+var_2270], rdi
0x180006de9  mov     [rbp+2210h+var_2268], rdi
0x180006ded  movzx   eax, word ptr [rsi]
0x180006df0  test    ax, ax
0x180006df3  jz      short loc_180006E1A
0x180006df5  mov     rcx, rsi; lpsz
0x180006df8  cmp     ax, 5Ch ; '\'
0x180006dfc  jz      short loc_180006E11
0x180006dfe  call    cs:__imp_CharNextW
0x180006e04  mov     rcx, rax
0x180006e07  movzx   eax, word ptr [rax]
0x180006e0a  test    ax, ax
0x180006e0d  jnz     short loc_180006DF8
0x180006e0f  jmp     short loc_180006E1A
0x180006e11  test    rcx, rcx
0x180006e14  jnz     loc_180007478
0x180006e1a  mov     edx, edi
0x180006e1c  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180006e23  mov     rdx, [rax+rdx*8]; lpString2
0x180006e27  mov     rcx, rsi; lpString1
0x180006e2a  call    cs:__imp_lstrcmpiW
0x180006e30  test    eax, eax
0x180006e32  jz      short loc_180006E4B
0x180006e34  inc     edi
0x180006e36  cmp     edi, 0Ch
0x180006e39  jl      short loc_180006E1A
0x180006e3b  mov     [rbp+2210h+var_2278], r15
0x180006e3f  mov     rdx, rsi; unsigned __int16 *
0x180006e42  lea     rcx, [rbp+2210h+var_2278]; this
0x180006e46  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180006e4b  xor     edi, edi
0x180006e4d  test    r14d, r14d
0x180006e50  jnz     short loc_180006E83
0x180006e52  mov     rdx, rsi; unsigned __int16 *
0x180006e55  mov     rcx, r13; this
0x180006e58  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006e5d  mov     edi, eax
0x180006e5f  test    eax, eax
0x180006e61  js      loc_18000742C
0x180006e67  mov     rdx, rsi; unsigned __int16 *
0x180006e6a  mov     rcx, r13; this
0x180006e6d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180006e72  mov     edi, eax
0x180006e74  xor     ecx, ecx
0x180006e76  test    eax, eax
0x180006e78  js      loc_18000742C
0x180006e7e  jmp     loc_18000712A
0x180006e83  mov     r12d, 1
0x180006e89  lea     rdx, aNoremove; "NoRemove"
0x180006e90  mov     rcx, rsi; lpString1
0x180006e93  call    cs:__imp_lstrcmpiW
0x180006e99  test    eax, eax
0x180006e9b  jnz     short loc_180006EB7
0x180006e9d  mov     r12d, edi
0x180006ea0  mov     rdx, rsi; unsigned __int16 *
0x180006ea3  mov     rcx, r13; this
0x180006ea6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006eab  mov     edi, eax
0x180006ead  test    eax, eax
0x180006eaf  js      loc_18000742C
0x180006eb5  xor     edi, edi
0x180006eb7  lea     rdx, aVal; "Val"
0x180006ebe  mov     rcx, rsi; lpString1
0x180006ec1  call    cs:__imp_lstrcmpiW
0x180006ec7  test    eax, eax
0x180006ec9  jnz     loc_180006FB8
0x180006ecf  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180006ed6  mov     rcx, r13; this
0x180006ed9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006ede  mov     edi, eax
0x180006ee0  test    eax, eax
0x180006ee2  js      loc_18000742C
0x180006ee8  mov     rdx, rsi; unsigned __int16 *
0x180006eeb  mov     rcx, r13; this
0x180006eee  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006ef3  mov     edi, eax
0x180006ef5  test    eax, eax
0x180006ef7  js      loc_18000742C
0x180006efd  cmp     word ptr [rsi], 3Dh ; '='
0x180006f01  jnz     loc_180007478
0x180006f07  xor     edi, edi
0x180006f09  cmp     [rsp+2310h+var_22A8], edi
0x180006f0d  jz      short loc_180006F38
0x180006f0f  mov     [rbp+2210h+var_2270], rdi
0x180006f13  mov     [rbp+2210h+var_2268], rdi
0x180006f17  mov     [rbp+2210h+var_2278], r15
0x180006f1b  mov     r9, rsi; unsigned __int16 *
0x180006f1e  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180006f25  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180006f29  mov     rcx, r13; this
0x180006f2c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180006f31  mov     edi, eax
0x180006f33  jmp     loc_18000711B
0x180006f38  cmp     [rbp+2210h+arg_20], edi
0x180006f3e  jnz     short loc_180006F9E
0x180006f40  test    r12d, r12d
0x180006f43  jz      short loc_180006F9E
0x180006f45  mov     [rsp+2310h+hKey], rdi
0x180006f4a  lea     rax, [rsp+2310h+hKey]
0x180006f4f  mov     [rsp+2310h+phkResult], rax; phkResult
0x180006f54  mov     r9d, 20006h; samDesired
0x180006f5a  xor     r8d, r8d; ulOptions
0x180006f5d  xor     edx, edx; lpSubKey
0x180006f5f  mov     rcx, r15; hKey
0x180006f62  call    cs:__imp_RegOpenKeyExW
0x180006f68  test    eax, eax
0x180006f6a  jnz     loc_180007423
0x180006f70  mov     r14, [rsp+2310h+hKey]
0x180006f75  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180006f7c  mov     rcx, r14; hKey
0x180006f7f  call    cs:__imp_RegDeleteValueW
0x180006f85  test    eax, 0FFFFFFFDh
0x180006f8a  jnz     loc_18000745F
0x180006f90  test    r14, r14
0x180006f93  jz      short loc_180006F9E
0x180006f95  mov     rcx, r14; hKey
0x180006f98  call    cs:__imp_RegCloseKey
0x180006f9e  mov     rdx, rsi; unsigned __int16 *
0x180006fa1  mov     rcx, r13; this
0x180006fa4  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180006fa9  mov     edi, eax
0x180006fab  test    eax, eax
0x180006fad  js      loc_18000742C
0x180006fb3  jmp     loc_1800072C5
0x180006fb8  movzx   eax, word ptr [rsi]
0x180006fbb  test    ax, ax
0x180006fbe  jz      short loc_180006FE5
0x180006fc0  mov     rcx, rsi; lpsz
0x180006fc3  cmp     ax, 5Ch ; '\'
0x180006fc7  jz      short loc_180006FDC
0x180006fc9  call    cs:__imp_CharNextW
0x180006fcf  mov     rcx, rax
0x180006fd2  movzx   eax, word ptr [rax]
0x180006fd5  test    ax, ax
0x180006fd8  jnz     short loc_180006FC3
0x180006fda  jmp     short loc_180006FE5
0x180006fdc  test    rcx, rcx
0x180006fdf  jnz     loc_180007478
0x180006fe5  cmp     [rsp+2310h+var_22A8], edi
0x180006fe9  jz      loc_18000717E
0x180006fef  mov     [rsp+2310h+hKey], rdi
0x180006ff4  lea     rax, [rsp+2310h+hKey]
0x180006ff9  mov     [rsp+2310h+phkResult], rax; phkResult
0x180006ffe  mov     r14d, 2001Fh
0x180007004  mov     r9d, r14d; samDesired
0x180007007  xor     r8d, r8d; ulOptions
0x18000700a  mov     rdx, rsi; lpSubKey
0x18000700d  mov     rcx, r15; hKey
0x180007010  call    cs:__imp_RegOpenKeyExW
0x180007016  test    eax, eax
0x180007018  jnz     short loc_18000703B
0x18000701a  mov     eax, edi
0x18000701c  test    rbx, rbx
0x18000701f  jz      short loc_18000702A
0x180007021  mov     rcx, rbx; hKey
0x180007024  call    cs:__imp_RegCloseKey
0x18000702a  mov     rbx, [rsp+2310h+hKey]
0x18000702f  mov     [rbp+2210h+var_2290], rbx
0x180007033  test    eax, eax
0x180007035  jz      loc_1800070E6
0x18000703b  mov     [rsp+2310h+hKey], rdi
0x180007040  lea     rax, [rsp+2310h+hKey]
0x180007045  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000704a  mov     r9d, 20019h; samDesired
0x180007050  xor     r8d, r8d; ulOptions
0x180007053  mov     rdx, rsi; lpSubKey
0x180007056  mov     rcx, r15; hKey
0x180007059  call    cs:__imp_RegOpenKeyExW
0x18000705f  test    eax, eax
0x180007061  jnz     short loc_180007080
0x180007063  mov     eax, edi
0x180007065  test    rbx, rbx
0x180007068  jz      short loc_180007073
0x18000706a  mov     rcx, rbx; hKey
0x18000706d  call    cs:__imp_RegCloseKey
0x180007073  mov     rbx, [rsp+2310h+hKey]
0x180007078  mov     [rbp+2210h+var_2290], rbx
0x18000707c  test    eax, eax
0x18000707e  jz      short loc_1800070E6
0x180007080  mov     dword ptr [rsp+2310h+hKey], edi
0x180007084  mov     [rsp+2310h+var_2298], rdi
0x180007089  lea     rax, [rsp+2310h+hKey]
0x18000708e  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180007093  lea     rax, [rsp+2310h+var_2298]
0x180007098  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18000709d  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800070a2  mov     [rsp+2310h+samDesired], r14d; samDesired
0x1800070a7  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x1800070ab  xor     r9d, r9d; lpClass
0x1800070ae  xor     r8d, r8d; Reserved
0x1800070b1  mov     rdx, rsi; lpSubKey
0x1800070b4  mov     rcx, r15; hKey
0x1800070b7  call    cs:__imp_RegCreateKeyExW
0x1800070bd  test    eax, eax
0x1800070bf  jnz     loc_180007423
0x1800070c5  mov     eax, edi
0x1800070c7  test    rbx, rbx
0x1800070ca  jz      short loc_1800070D5
0x1800070cc  mov     rcx, rbx; hKey
0x1800070cf  call    cs:__imp_RegCloseKey
0x1800070d5  mov     rbx, [rsp+2310h+var_2298]
0x1800070da  mov     [rbp+2210h+var_2290], rbx
0x1800070de  test    eax, eax
0x1800070e0  jnz     loc_180007423
0x1800070e6  mov     rdx, rsi; unsigned __int16 *
0x1800070e9  mov     rcx, r13; this
0x1800070ec  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800070f1  mov     edi, eax
0x1800070f3  xor     ecx, ecx
0x1800070f5  test    eax, eax
0x1800070f7  js      loc_18000742C
0x1800070fd  cmp     word ptr [rsi], 3Dh ; '='
0x180007101  jnz     short loc_180007125
0x180007103  mov     r9, rsi; unsigned __int16 *
0x180007106  xor     r8d, r8d; unsigned __int16 *
0x180007109  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x18000710d  mov     rcx, r13; this
0x180007110  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180007115  mov     edi, eax
0x180007117  mov     rbx, [rbp+2210h+var_2290]
0x18000711b  test    eax, eax
0x18000711d  js      loc_18000742C
0x180007123  xor     ecx, ecx
0x180007125  mov     r12d, [rsp+2310h+var_22A8]
0x18000712a  cmp     word ptr [rsi], 7Bh ; '{'
0x18000712e  jnz     loc_1800072C5
0x180007134  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007138  inc     rax
0x18000713b  cmp     [rsi+rax*2], cx
0x18000713f  jnz     short loc_180007138
0x180007141  cmp     rax, 1
0x180007145  jnz     loc_1800072C5
0x18000714b  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180007153  mov     r9d, r12d; int
0x180007156  mov     r8, rbx; HKEY
0x180007159  mov     rdx, rsi; unsigned __int16 *
0x18000715c  mov     rcx, r13; this
0x18000715f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007164  mov     edi, eax
0x180007166  test    eax, eax
0x180007168  js      loc_18000742C
0x18000716e  mov     rdx, rsi; unsigned __int16 *
0x180007171  mov     rcx, r13; this
0x180007174  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007179  jmp     loc_180006FA9
  ... truncated ...
```
