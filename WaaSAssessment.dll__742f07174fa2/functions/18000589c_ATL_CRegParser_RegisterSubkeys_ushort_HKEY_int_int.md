# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000589c`
- end: `0x180006033`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180005528`
- `0x18000589c`

## callees

- `0x18000369c`
- `0x180003ed8`
- `0x180004740`
- `0x180004be8`
- `0x180004ef0`
- `0x1800053d8`
- `0x18000589c`
- `0x180006164`
- `0x180019760`
- `0x180019820`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180005d7a`
- `msvcrt!wcsncpy_s` at `0x180005d7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005ea6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005f3c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005ea6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005f3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005b18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005ba4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005bed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005c4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005d43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005f5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005fb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005ff0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006000`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005b18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005ba4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005bed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005c4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005d43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005f5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005fb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005ff0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006000`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180005aff`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180005aff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005ae2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005b90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005bd9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005d28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005ae2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005b90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005bd9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005d28`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005c37`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005c37`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000597e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005b49`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000597e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005b49`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005919`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000592c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800059aa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005a13`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005a41`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005ec9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005919`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000592c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800059aa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005a13`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005a41`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005ec9`

## string_xrefs

- `0x180005922`: `ForceRemove`
- `0x180005a09`: `NoRemove`
- `0x18000590f`: `Delete`

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
  errno_t v29; // eax
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
  wchar_t Destination[264]; // [rsp+B0h] [rbp-50h] BYREF
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
    v29 = wcsncpy_s(Destination, 0x104u, a2, 0xFFFFFFFFFFFFFFFFuLL);
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
          while ( lstrcmpiW(Destination, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v31]) )
          {
            if ( ++v31 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v37, Destination);
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
    v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v38, Destination);
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
0x18000589c  push    rbp
0x18000589e  push    rbx
0x18000589f  push    rsi
0x1800058a0  push    rdi
0x1800058a1  push    r12
0x1800058a3  push    r13
0x1800058a5  push    r14
0x1800058a7  push    r15
0x1800058a9  lea     rbp, [rsp-21D8h]
0x1800058b1  mov     eax, 22D8h
0x1800058b6  call    _alloca_probe
0x1800058bb  sub     rsp, rax
0x1800058be  mov     rax, cs:__security_cookie
0x1800058c5  xor     rax, rsp
0x1800058c8  mov     [rbp+2210h+var_50], rax
0x1800058cf  mov     r12d, r9d
0x1800058d2  mov     [rsp+2310h+var_22A8], r9d
0x1800058d7  mov     r15, r8
0x1800058da  mov     [rsp+2310h+var_22A0], r8
0x1800058df  mov     rsi, rdx
0x1800058e2  mov     r13, rcx
0x1800058e5  xor     eax, eax
0x1800058e7  mov     ebx, eax
0x1800058e9  mov     [rbp+2210h+var_2290], rax
0x1800058ed  mov     [rbp+2210h+var_2288], rax
0x1800058f1  mov     [rbp+2210h+var_2280], rax
0x1800058f5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800058fa  mov     edi, eax
0x1800058fc  test    eax, eax
0x1800058fe  jns     short loc_180005905
0x180005900  jmp     loc_180005FBC
0x180005905  cmp     word ptr [rsi], 7Dh ; '}'
0x180005909  jz      loc_180005FAC
0x18000590f  lea     rdx, String2; "Delete"
0x180005916  mov     rcx, rsi; lpString1
0x180005919  call    cs:__imp_lstrcmpiW
0x18000591f  mov     r14d, eax
0x180005922  lea     rdx, aForceremove; "ForceRemove"
0x180005929  mov     rcx, rsi; lpString1
0x18000592c  call    cs:__imp_lstrcmpiW
0x180005932  xor     edi, edi
0x180005934  test    eax, eax
0x180005936  jz      short loc_180005941
0x180005938  test    r14d, r14d
0x18000593b  jnz     loc_180005A03
0x180005941  mov     rdx, rsi; unsigned __int16 *
0x180005944  mov     rcx, r13; this
0x180005947  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000594c  mov     edi, eax
0x18000594e  test    eax, eax
0x180005950  js      loc_180005FAC
0x180005956  xor     edi, edi
0x180005958  test    r12d, r12d
0x18000595b  jz      loc_180005A03
0x180005961  mov     [rbp+2210h+var_2278], rdi
0x180005965  mov     [rbp+2210h+var_2270], rdi
0x180005969  mov     [rbp+2210h+var_2268], rdi
0x18000596d  movzx   eax, word ptr [rsi]
0x180005970  test    ax, ax
0x180005973  jz      short loc_18000599A
0x180005975  mov     rcx, rsi; lpsz
0x180005978  cmp     ax, 5Ch ; '\'
0x18000597c  jz      short loc_180005991
0x18000597e  call    cs:__imp_CharNextW
0x180005984  mov     rcx, rax
0x180005987  movzx   eax, word ptr [rax]
0x18000598a  test    ax, ax
0x18000598d  jnz     short loc_180005978
0x18000598f  jmp     short loc_18000599A
0x180005991  test    rcx, rcx
0x180005994  jnz     loc_180005FF8
0x18000599a  mov     edx, edi
0x18000599c  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x1800059a3  mov     rdx, [rax+rdx*8]; lpString2
0x1800059a7  mov     rcx, rsi; lpString1
0x1800059aa  call    cs:__imp_lstrcmpiW
0x1800059b0  test    eax, eax
0x1800059b2  jz      short loc_1800059CB
0x1800059b4  inc     edi
0x1800059b6  cmp     edi, 0Ch
0x1800059b9  jl      short loc_18000599A
0x1800059bb  mov     [rbp+2210h+var_2278], r15
0x1800059bf  mov     rdx, rsi; unsigned __int16 *
0x1800059c2  lea     rcx, [rbp+2210h+var_2278]; this
0x1800059c6  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800059cb  xor     edi, edi
0x1800059cd  test    r14d, r14d
0x1800059d0  jnz     short loc_180005A03
0x1800059d2  mov     rdx, rsi; unsigned __int16 *
0x1800059d5  mov     rcx, r13; this
0x1800059d8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800059dd  mov     edi, eax
0x1800059df  test    eax, eax
0x1800059e1  js      loc_180005FAC
0x1800059e7  mov     rdx, rsi; unsigned __int16 *
0x1800059ea  mov     rcx, r13; this
0x1800059ed  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800059f2  mov     edi, eax
0x1800059f4  xor     ecx, ecx
0x1800059f6  test    eax, eax
0x1800059f8  js      loc_180005FAC
0x1800059fe  jmp     loc_180005CAA
0x180005a03  mov     r12d, 1
0x180005a09  lea     rdx, aNoremove; "NoRemove"
0x180005a10  mov     rcx, rsi; lpString1
0x180005a13  call    cs:__imp_lstrcmpiW
0x180005a19  test    eax, eax
0x180005a1b  jnz     short loc_180005A37
0x180005a1d  mov     r12d, edi
0x180005a20  mov     rdx, rsi; unsigned __int16 *
0x180005a23  mov     rcx, r13; this
0x180005a26  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005a2b  mov     edi, eax
0x180005a2d  test    eax, eax
0x180005a2f  js      loc_180005FAC
0x180005a35  xor     edi, edi
0x180005a37  lea     rdx, aVal; "Val"
0x180005a3e  mov     rcx, rsi; lpString1
0x180005a41  call    cs:__imp_lstrcmpiW
0x180005a47  test    eax, eax
0x180005a49  jnz     loc_180005B38
0x180005a4f  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180005a56  mov     rcx, r13; this
0x180005a59  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005a5e  mov     edi, eax
0x180005a60  test    eax, eax
0x180005a62  js      loc_180005FAC
0x180005a68  mov     rdx, rsi; unsigned __int16 *
0x180005a6b  mov     rcx, r13; this
0x180005a6e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005a73  mov     edi, eax
0x180005a75  test    eax, eax
0x180005a77  js      loc_180005FAC
0x180005a7d  cmp     word ptr [rsi], 3Dh ; '='
0x180005a81  jnz     loc_180005FF8
0x180005a87  xor     edi, edi
0x180005a89  cmp     [rsp+2310h+var_22A8], edi
0x180005a8d  jz      short loc_180005AB8
0x180005a8f  mov     [rbp+2210h+var_2270], rdi
0x180005a93  mov     [rbp+2210h+var_2268], rdi
0x180005a97  mov     [rbp+2210h+var_2278], r15
0x180005a9b  mov     r9, rsi; unsigned __int16 *
0x180005a9e  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180005aa5  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180005aa9  mov     rcx, r13; this
0x180005aac  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005ab1  mov     edi, eax
0x180005ab3  jmp     loc_180005C9B
0x180005ab8  cmp     [rbp+2210h+arg_20], edi
0x180005abe  jnz     short loc_180005B1E
0x180005ac0  test    r12d, r12d
0x180005ac3  jz      short loc_180005B1E
0x180005ac5  mov     [rsp+2310h+hKey], rdi
0x180005aca  lea     rax, [rsp+2310h+hKey]
0x180005acf  mov     [rsp+2310h+phkResult], rax; phkResult
0x180005ad4  mov     r9d, 20006h; samDesired
0x180005ada  xor     r8d, r8d; ulOptions
0x180005add  xor     edx, edx; lpSubKey
0x180005adf  mov     rcx, r15; hKey
0x180005ae2  call    cs:__imp_RegOpenKeyExW
0x180005ae8  test    eax, eax
0x180005aea  jnz     loc_180005FA3
0x180005af0  mov     r14, [rsp+2310h+hKey]
0x180005af5  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180005afc  mov     rcx, r14; hKey
0x180005aff  call    cs:__imp_RegDeleteValueW
0x180005b05  test    eax, 0FFFFFFFDh
0x180005b0a  jnz     loc_180005FDF
0x180005b10  test    r14, r14
0x180005b13  jz      short loc_180005B1E
0x180005b15  mov     rcx, r14; hKey
0x180005b18  call    cs:__imp_RegCloseKey
0x180005b1e  mov     rdx, rsi; unsigned __int16 *
0x180005b21  mov     rcx, r13; this
0x180005b24  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180005b29  mov     edi, eax
0x180005b2b  test    eax, eax
0x180005b2d  js      loc_180005FAC
0x180005b33  jmp     loc_180005E45
0x180005b38  movzx   eax, word ptr [rsi]
0x180005b3b  test    ax, ax
0x180005b3e  jz      short loc_180005B65
0x180005b40  mov     rcx, rsi; lpsz
0x180005b43  cmp     ax, 5Ch ; '\'
0x180005b47  jz      short loc_180005B5C
0x180005b49  call    cs:__imp_CharNextW
0x180005b4f  mov     rcx, rax
0x180005b52  movzx   eax, word ptr [rax]
0x180005b55  test    ax, ax
0x180005b58  jnz     short loc_180005B43
0x180005b5a  jmp     short loc_180005B65
0x180005b5c  test    rcx, rcx
0x180005b5f  jnz     loc_180005FF8
0x180005b65  cmp     [rsp+2310h+var_22A8], edi
0x180005b69  jz      loc_180005CFE
0x180005b6f  mov     [rsp+2310h+hKey], rdi
0x180005b74  lea     rax, [rsp+2310h+hKey]
0x180005b79  mov     [rsp+2310h+phkResult], rax; phkResult
0x180005b7e  mov     r14d, 2001Fh
0x180005b84  mov     r9d, r14d; samDesired
0x180005b87  xor     r8d, r8d; ulOptions
0x180005b8a  mov     rdx, rsi; lpSubKey
0x180005b8d  mov     rcx, r15; hKey
0x180005b90  call    cs:__imp_RegOpenKeyExW
0x180005b96  test    eax, eax
0x180005b98  jnz     short loc_180005BBB
0x180005b9a  mov     eax, edi
0x180005b9c  test    rbx, rbx
0x180005b9f  jz      short loc_180005BAA
0x180005ba1  mov     rcx, rbx; hKey
0x180005ba4  call    cs:__imp_RegCloseKey
0x180005baa  mov     rbx, [rsp+2310h+hKey]
0x180005baf  mov     [rbp+2210h+var_2290], rbx
0x180005bb3  test    eax, eax
0x180005bb5  jz      loc_180005C66
0x180005bbb  mov     [rsp+2310h+hKey], rdi
0x180005bc0  lea     rax, [rsp+2310h+hKey]
0x180005bc5  mov     [rsp+2310h+phkResult], rax; phkResult
0x180005bca  mov     r9d, 20019h; samDesired
0x180005bd0  xor     r8d, r8d; ulOptions
0x180005bd3  mov     rdx, rsi; lpSubKey
0x180005bd6  mov     rcx, r15; hKey
0x180005bd9  call    cs:__imp_RegOpenKeyExW
0x180005bdf  test    eax, eax
0x180005be1  jnz     short loc_180005C00
0x180005be3  mov     eax, edi
0x180005be5  test    rbx, rbx
0x180005be8  jz      short loc_180005BF3
0x180005bea  mov     rcx, rbx; hKey
0x180005bed  call    cs:__imp_RegCloseKey
0x180005bf3  mov     rbx, [rsp+2310h+hKey]
0x180005bf8  mov     [rbp+2210h+var_2290], rbx
0x180005bfc  test    eax, eax
0x180005bfe  jz      short loc_180005C66
0x180005c00  mov     dword ptr [rsp+2310h+hKey], edi
0x180005c04  mov     [rsp+2310h+var_2298], rdi
0x180005c09  lea     rax, [rsp+2310h+hKey]
0x180005c0e  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180005c13  lea     rax, [rsp+2310h+var_2298]
0x180005c18  mov     [rsp+2310h+var_22D8], rax; phkResult
0x180005c1d  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180005c22  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180005c27  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180005c2b  xor     r9d, r9d; lpClass
0x180005c2e  xor     r8d, r8d; Reserved
0x180005c31  mov     rdx, rsi; lpSubKey
0x180005c34  mov     rcx, r15; hKey
0x180005c37  call    cs:__imp_RegCreateKeyExW
0x180005c3d  test    eax, eax
0x180005c3f  jnz     loc_180005FA3
0x180005c45  mov     eax, edi
0x180005c47  test    rbx, rbx
0x180005c4a  jz      short loc_180005C55
0x180005c4c  mov     rcx, rbx; hKey
0x180005c4f  call    cs:__imp_RegCloseKey
0x180005c55  mov     rbx, [rsp+2310h+var_2298]
0x180005c5a  mov     [rbp+2210h+var_2290], rbx
0x180005c5e  test    eax, eax
0x180005c60  jnz     loc_180005FA3
0x180005c66  mov     rdx, rsi; unsigned __int16 *
0x180005c69  mov     rcx, r13; this
0x180005c6c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005c71  mov     edi, eax
0x180005c73  xor     ecx, ecx
0x180005c75  test    eax, eax
0x180005c77  js      loc_180005FAC
0x180005c7d  cmp     word ptr [rsi], 3Dh ; '='
0x180005c81  jnz     short loc_180005CA5
0x180005c83  mov     r9, rsi; unsigned __int16 *
0x180005c86  xor     r8d, r8d; unsigned __int16 *
0x180005c89  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180005c8d  mov     rcx, r13; this
0x180005c90  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005c95  mov     edi, eax
0x180005c97  mov     rbx, [rbp+2210h+var_2290]
0x180005c9b  test    eax, eax
0x180005c9d  js      loc_180005FAC
0x180005ca3  xor     ecx, ecx
0x180005ca5  mov     r12d, [rsp+2310h+var_22A8]
0x180005caa  cmp     word ptr [rsi], 7Bh ; '{'
0x180005cae  jnz     loc_180005E45
0x180005cb4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005cb8  inc     rax
0x180005cbb  cmp     [rsi+rax*2], cx
0x180005cbf  jnz     short loc_180005CB8
0x180005cc1  cmp     rax, 1
0x180005cc5  jnz     loc_180005E45
0x180005ccb  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180005cd3  mov     r9d, r12d; int
0x180005cd6  mov     r8, rbx; HKEY
0x180005cd9  mov     rdx, rsi; unsigned __int16 *
0x180005cdc  mov     rcx, r13; this
0x180005cdf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005ce4  mov     edi, eax
0x180005ce6  test    eax, eax
0x180005ce8  js      loc_180005FAC
0x180005cee  mov     rdx, rsi; unsigned __int16 *
0x180005cf1  mov     rcx, r13; this
0x180005cf4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005cf9  jmp     loc_180005B29
  ... truncated ...
```
