# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18002ba78`
- end: `0x18002c217`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1951`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18002b6f8`
- `0x18002ba78`

## callees

- `0x1800032e0`
- `0x18001047c`
- `0x180027658`
- `0x180027f58`
- `0x180029298`
- `0x18002b05c`
- `0x18002b5a8`
- `0x18002ba78`
- `0x18002c6e0`
- `0x1801adab0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002bf5e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002bf5e`
- `KERNEL32!lstrcmpiW` at `0x18002bafd`
- `KERNEL32!lstrcmpiW` at `0x18002bb10`
- `KERNEL32!lstrcmpiW` at `0x18002bb8e`
- `KERNEL32!lstrcmpiW` at `0x18002bbf7`
- `KERNEL32!lstrcmpiW` at `0x18002bc25`
- `KERNEL32!lstrcmpiW` at `0x18002c0ad`
- `KERNEL32!lstrcmpiW` at `0x18002bafd`
- `KERNEL32!lstrcmpiW` at `0x18002bb10`
- `KERNEL32!lstrcmpiW` at `0x18002bb8e`
- `KERNEL32!lstrcmpiW` at `0x18002bbf7`
- `KERNEL32!lstrcmpiW` at `0x18002bc25`
- `KERNEL32!lstrcmpiW` at `0x18002c0ad`
- `ADVAPI32!RegCloseKey` at `0x18002bcfc`
- `ADVAPI32!RegCloseKey` at `0x18002bd88`
- `ADVAPI32!RegCloseKey` at `0x18002bdd1`
- `ADVAPI32!RegCloseKey` at `0x18002be33`
- `ADVAPI32!RegCloseKey` at `0x18002bf27`
- `ADVAPI32!RegCloseKey` at `0x18002c13e`
- `ADVAPI32!RegCloseKey` at `0x18002c198`
- `ADVAPI32!RegCloseKey` at `0x18002c1d4`
- `ADVAPI32!RegCloseKey` at `0x18002c1e4`
- `ADVAPI32!RegCloseKey` at `0x18002bcfc`
- `ADVAPI32!RegCloseKey` at `0x18002bd88`
- `ADVAPI32!RegCloseKey` at `0x18002bdd1`
- `ADVAPI32!RegCloseKey` at `0x18002be33`
- `ADVAPI32!RegCloseKey` at `0x18002bf27`
- `ADVAPI32!RegCloseKey` at `0x18002c13e`
- `ADVAPI32!RegCloseKey` at `0x18002c198`
- `ADVAPI32!RegCloseKey` at `0x18002c1d4`
- `ADVAPI32!RegCloseKey` at `0x18002c1e4`
- `ADVAPI32!RegCreateKeyExW` at `0x18002be1b`
- `ADVAPI32!RegCreateKeyExW` at `0x18002be1b`
- `ADVAPI32!RegOpenKeyExW` at `0x18002bcc6`
- `ADVAPI32!RegOpenKeyExW` at `0x18002bd74`
- `ADVAPI32!RegOpenKeyExW` at `0x18002bdbd`
- `ADVAPI32!RegOpenKeyExW` at `0x18002bf0c`
- `ADVAPI32!RegOpenKeyExW` at `0x18002bcc6`
- `ADVAPI32!RegOpenKeyExW` at `0x18002bd74`
- `ADVAPI32!RegOpenKeyExW` at `0x18002bdbd`
- `ADVAPI32!RegOpenKeyExW` at `0x18002bf0c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002c08a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002c120`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002c08a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002c120`
- `ADVAPI32!RegDeleteValueW` at `0x18002bce3`
- `ADVAPI32!RegDeleteValueW` at `0x18002bce3`
- `USER32!CharNextW` at `0x18002bb62`
- `USER32!CharNextW` at `0x18002bd2d`
- `USER32!CharNextW` at `0x18002bb62`
- `USER32!CharNextW` at `0x18002bd2d`

## string_xrefs

- `0x18002bb06`: `ForceRemove`
- `0x18002bbed`: `NoRemove`
- `0x18002baf3`: `Delete`

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
  __int64 v41; // [rsp+B0h] [rbp-50h]
  WCHAR String1[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR ValueName[4096]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v41 = -2;
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
0x18002ba78  push    rbp
0x18002ba7a  push    rbx
0x18002ba7b  push    rsi
0x18002ba7c  push    rdi
0x18002ba7d  push    r12
0x18002ba7f  push    r13
0x18002ba81  push    r14
0x18002ba83  push    r15
0x18002ba85  lea     rbp, [rsp-21E8h]
0x18002ba8d  mov     eax, 22E8h
0x18002ba92  call    _alloca_probe
0x18002ba97  sub     rsp, rax
0x18002ba9a  mov     [rbp+2220h+var_2270], 0FFFFFFFFFFFFFFFEh
0x18002baa2  mov     rax, cs:__security_cookie
0x18002baa9  xor     rax, rsp
0x18002baac  mov     [rbp+2220h+var_50], rax
0x18002bab3  mov     r12d, r9d
0x18002bab6  mov     [rsp+2320h+var_22B8], r9d
0x18002babb  mov     r15, r8
0x18002babe  mov     [rsp+2320h+var_22B0], r8
0x18002bac3  mov     rsi, rdx
0x18002bac6  mov     r13, rcx
0x18002bac9  xor     eax, eax
0x18002bacb  mov     ebx, eax
0x18002bacd  mov     [rbp+2220h+var_22A0], rax
0x18002bad1  mov     [rbp+2220h+var_2298], rax
0x18002bad5  mov     [rbp+2220h+var_2290], rax
0x18002bad9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002bade  mov     edi, eax
0x18002bae0  test    eax, eax
0x18002bae2  jns     short loc_18002BAE9
0x18002bae4  jmp     loc_18002C1A0
0x18002bae9  cmp     word ptr [rsi], 7Dh ; '}'
0x18002baed  jz      loc_18002C190
0x18002baf3  lea     rdx, aDelete; "Delete"
0x18002bafa  mov     rcx, rsi; lpString1
0x18002bafd  call    cs:__imp_lstrcmpiW
0x18002bb03  mov     r14d, eax
0x18002bb06  lea     rdx, aForceremove; "ForceRemove"
0x18002bb0d  mov     rcx, rsi; lpString1
0x18002bb10  call    cs:__imp_lstrcmpiW
0x18002bb16  xor     edi, edi
0x18002bb18  test    eax, eax
0x18002bb1a  jz      short loc_18002BB25
0x18002bb1c  test    r14d, r14d
0x18002bb1f  jnz     loc_18002BBE7
0x18002bb25  mov     rdx, rsi; unsigned __int16 *
0x18002bb28  mov     rcx, r13; this
0x18002bb2b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002bb30  mov     edi, eax
0x18002bb32  test    eax, eax
0x18002bb34  js      loc_18002C190
0x18002bb3a  xor     edi, edi
0x18002bb3c  test    r12d, r12d
0x18002bb3f  jz      loc_18002BBE7
0x18002bb45  mov     [rbp+2220h+var_2288], rdi
0x18002bb49  mov     [rbp+2220h+var_2280], rdi
0x18002bb4d  mov     [rbp+2220h+var_2278], rdi
0x18002bb51  movzx   eax, word ptr [rsi]
0x18002bb54  test    ax, ax
0x18002bb57  jz      short loc_18002BB7E
0x18002bb59  mov     rcx, rsi; lpsz
0x18002bb5c  cmp     ax, 5Ch ; '\'
0x18002bb60  jz      short loc_18002BB75
0x18002bb62  call    cs:__imp_CharNextW
0x18002bb68  mov     rcx, rax
0x18002bb6b  movzx   eax, word ptr [rax]
0x18002bb6e  test    ax, ax
0x18002bb71  jnz     short loc_18002BB5C
0x18002bb73  jmp     short loc_18002BB7E
0x18002bb75  test    rcx, rcx
0x18002bb78  jnz     loc_18002C1DC
0x18002bb7e  mov     edx, edi
0x18002bb80  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x18002bb87  mov     rdx, [rax+rdx*8]; lpString2
0x18002bb8b  mov     rcx, rsi; lpString1
0x18002bb8e  call    cs:__imp_lstrcmpiW
0x18002bb94  test    eax, eax
0x18002bb96  jz      short loc_18002BBAF
0x18002bb98  inc     edi
0x18002bb9a  cmp     edi, 0Ch
0x18002bb9d  jl      short loc_18002BB7E
0x18002bb9f  mov     [rbp+2220h+var_2288], r15
0x18002bba3  mov     rdx, rsi; unsigned __int16 *
0x18002bba6  lea     rcx, [rbp+2220h+var_2288]; this
0x18002bbaa  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18002bbaf  xor     edi, edi
0x18002bbb1  test    r14d, r14d
0x18002bbb4  jnz     short loc_18002BBE7
0x18002bbb6  mov     rdx, rsi; unsigned __int16 *
0x18002bbb9  mov     rcx, r13; this
0x18002bbbc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002bbc1  mov     edi, eax
0x18002bbc3  test    eax, eax
0x18002bbc5  js      loc_18002C190
0x18002bbcb  mov     rdx, rsi; unsigned __int16 *
0x18002bbce  mov     rcx, r13; this
0x18002bbd1  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18002bbd6  mov     edi, eax
0x18002bbd8  xor     ecx, ecx
0x18002bbda  test    eax, eax
0x18002bbdc  js      loc_18002C190
0x18002bbe2  jmp     loc_18002BE8E
0x18002bbe7  mov     r12d, 1
0x18002bbed  lea     rdx, aNoremove; "NoRemove"
0x18002bbf4  mov     rcx, rsi; lpString1
0x18002bbf7  call    cs:__imp_lstrcmpiW
0x18002bbfd  test    eax, eax
0x18002bbff  jnz     short loc_18002BC1B
0x18002bc01  mov     r12d, edi
0x18002bc04  mov     rdx, rsi; unsigned __int16 *
0x18002bc07  mov     rcx, r13; this
0x18002bc0a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002bc0f  mov     edi, eax
0x18002bc11  test    eax, eax
0x18002bc13  js      loc_18002C190
0x18002bc19  xor     edi, edi
0x18002bc1b  lea     rdx, aVal; "Val"
0x18002bc22  mov     rcx, rsi; lpString1
0x18002bc25  call    cs:__imp_lstrcmpiW
0x18002bc2b  test    eax, eax
0x18002bc2d  jnz     loc_18002BD1C
0x18002bc33  lea     rdx, [rbp+2220h+ValueName]; unsigned __int16 *
0x18002bc3a  mov     rcx, r13; this
0x18002bc3d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002bc42  mov     edi, eax
0x18002bc44  test    eax, eax
0x18002bc46  js      loc_18002C190
0x18002bc4c  mov     rdx, rsi; unsigned __int16 *
0x18002bc4f  mov     rcx, r13; this
0x18002bc52  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002bc57  mov     edi, eax
0x18002bc59  test    eax, eax
0x18002bc5b  js      loc_18002C190
0x18002bc61  cmp     word ptr [rsi], 3Dh ; '='
0x18002bc65  jnz     loc_18002C1DC
0x18002bc6b  xor     edi, edi
0x18002bc6d  cmp     [rsp+2320h+var_22B8], edi
0x18002bc71  jz      short loc_18002BC9C
0x18002bc73  mov     [rbp+2220h+var_2280], rdi
0x18002bc77  mov     [rbp+2220h+var_2278], rdi
0x18002bc7b  mov     [rbp+2220h+var_2288], r15
0x18002bc7f  mov     r9, rsi; unsigned __int16 *
0x18002bc82  lea     r8, [rbp+2220h+ValueName]; unsigned __int16 *
0x18002bc89  lea     rdx, [rbp+2220h+var_2288]; struct ATL::CRegKey *
0x18002bc8d  mov     rcx, r13; this
0x18002bc90  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18002bc95  mov     edi, eax
0x18002bc97  jmp     loc_18002BE7F
0x18002bc9c  cmp     [rbp+2220h+arg_20], edi
0x18002bca2  jnz     short loc_18002BD02
0x18002bca4  test    r12d, r12d
0x18002bca7  jz      short loc_18002BD02
0x18002bca9  mov     [rsp+2320h+hKey], rdi
0x18002bcae  lea     rax, [rsp+2320h+hKey]
0x18002bcb3  mov     [rsp+2320h+phkResult], rax; phkResult
0x18002bcb8  mov     r9d, 20006h; samDesired
0x18002bcbe  xor     r8d, r8d; ulOptions
0x18002bcc1  xor     edx, edx; lpSubKey
0x18002bcc3  mov     rcx, r15; hKey
0x18002bcc6  call    cs:__imp_RegOpenKeyExW
0x18002bccc  test    eax, eax
0x18002bcce  jnz     loc_18002C187
0x18002bcd4  mov     r14, [rsp+2320h+hKey]
0x18002bcd9  lea     rdx, [rbp+2220h+ValueName]; lpValueName
0x18002bce0  mov     rcx, r14; hKey
0x18002bce3  call    cs:__imp_RegDeleteValueW
0x18002bce9  test    eax, 0FFFFFFFDh
0x18002bcee  jnz     loc_18002C1C3
0x18002bcf4  test    r14, r14
0x18002bcf7  jz      short loc_18002BD02
0x18002bcf9  mov     rcx, r14; hKey
0x18002bcfc  call    cs:__imp_RegCloseKey
0x18002bd02  mov     rdx, rsi; unsigned __int16 *
0x18002bd05  mov     rcx, r13; this
0x18002bd08  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18002bd0d  mov     edi, eax
0x18002bd0f  test    eax, eax
0x18002bd11  js      loc_18002C190
0x18002bd17  jmp     loc_18002C029
0x18002bd1c  movzx   eax, word ptr [rsi]
0x18002bd1f  test    ax, ax
0x18002bd22  jz      short loc_18002BD49
0x18002bd24  mov     rcx, rsi; lpsz
0x18002bd27  cmp     ax, 5Ch ; '\'
0x18002bd2b  jz      short loc_18002BD40
0x18002bd2d  call    cs:__imp_CharNextW
0x18002bd33  mov     rcx, rax
0x18002bd36  movzx   eax, word ptr [rax]
0x18002bd39  test    ax, ax
0x18002bd3c  jnz     short loc_18002BD27
0x18002bd3e  jmp     short loc_18002BD49
0x18002bd40  test    rcx, rcx
0x18002bd43  jnz     loc_18002C1DC
0x18002bd49  cmp     [rsp+2320h+var_22B8], edi
0x18002bd4d  jz      loc_18002BEE2
0x18002bd53  mov     [rsp+2320h+hKey], rdi
0x18002bd58  lea     rax, [rsp+2320h+hKey]
0x18002bd5d  mov     [rsp+2320h+phkResult], rax; phkResult
0x18002bd62  mov     r14d, 2001Fh
0x18002bd68  mov     r9d, r14d; samDesired
0x18002bd6b  xor     r8d, r8d; ulOptions
0x18002bd6e  mov     rdx, rsi; lpSubKey
0x18002bd71  mov     rcx, r15; hKey
0x18002bd74  call    cs:__imp_RegOpenKeyExW
0x18002bd7a  test    eax, eax
0x18002bd7c  jnz     short loc_18002BD9F
0x18002bd7e  mov     eax, edi
0x18002bd80  test    rbx, rbx
0x18002bd83  jz      short loc_18002BD8E
0x18002bd85  mov     rcx, rbx; hKey
0x18002bd88  call    cs:__imp_RegCloseKey
0x18002bd8e  mov     rbx, [rsp+2320h+hKey]
0x18002bd93  mov     [rbp+2220h+var_22A0], rbx
0x18002bd97  test    eax, eax
0x18002bd99  jz      loc_18002BE4A
0x18002bd9f  mov     [rsp+2320h+hKey], rdi
0x18002bda4  lea     rax, [rsp+2320h+hKey]
0x18002bda9  mov     [rsp+2320h+phkResult], rax; phkResult
0x18002bdae  mov     r9d, 20019h; samDesired
0x18002bdb4  xor     r8d, r8d; ulOptions
0x18002bdb7  mov     rdx, rsi; lpSubKey
0x18002bdba  mov     rcx, r15; hKey
0x18002bdbd  call    cs:__imp_RegOpenKeyExW
0x18002bdc3  test    eax, eax
0x18002bdc5  jnz     short loc_18002BDE4
0x18002bdc7  mov     eax, edi
0x18002bdc9  test    rbx, rbx
0x18002bdcc  jz      short loc_18002BDD7
0x18002bdce  mov     rcx, rbx; hKey
0x18002bdd1  call    cs:__imp_RegCloseKey
0x18002bdd7  mov     rbx, [rsp+2320h+hKey]
0x18002bddc  mov     [rbp+2220h+var_22A0], rbx
0x18002bde0  test    eax, eax
0x18002bde2  jz      short loc_18002BE4A
0x18002bde4  mov     dword ptr [rsp+2320h+hKey], edi
0x18002bde8  mov     [rsp+2320h+var_22A8], rdi
0x18002bded  lea     rax, [rsp+2320h+hKey]
0x18002bdf2  mov     [rsp+2320h+lpdwDisposition], rax; lpdwDisposition
0x18002bdf7  lea     rax, [rsp+2320h+var_22A8]
0x18002bdfc  mov     [rsp+2320h+var_22E8], rax; phkResult
0x18002be01  mov     [rsp+2320h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18002be06  mov     [rsp+2320h+samDesired], r14d; samDesired
0x18002be0b  mov     dword ptr [rsp+2320h+phkResult], edi; dwOptions
0x18002be0f  xor     r9d, r9d; lpClass
0x18002be12  xor     r8d, r8d; Reserved
0x18002be15  mov     rdx, rsi; lpSubKey
0x18002be18  mov     rcx, r15; hKey
0x18002be1b  call    cs:__imp_RegCreateKeyExW
0x18002be21  test    eax, eax
0x18002be23  jnz     loc_18002C187
0x18002be29  mov     eax, edi
0x18002be2b  test    rbx, rbx
0x18002be2e  jz      short loc_18002BE39
0x18002be30  mov     rcx, rbx; hKey
0x18002be33  call    cs:__imp_RegCloseKey
0x18002be39  mov     rbx, [rsp+2320h+var_22A8]
0x18002be3e  mov     [rbp+2220h+var_22A0], rbx
0x18002be42  test    eax, eax
0x18002be44  jnz     loc_18002C187
0x18002be4a  mov     rdx, rsi; unsigned __int16 *
0x18002be4d  mov     rcx, r13; this
0x18002be50  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002be55  mov     edi, eax
0x18002be57  xor     ecx, ecx
0x18002be59  test    eax, eax
0x18002be5b  js      loc_18002C190
0x18002be61  cmp     word ptr [rsi], 3Dh ; '='
0x18002be65  jnz     short loc_18002BE89
0x18002be67  mov     r9, rsi; unsigned __int16 *
0x18002be6a  xor     r8d, r8d; unsigned __int16 *
0x18002be6d  lea     rdx, [rbp+2220h+var_22A0]; struct ATL::CRegKey *
0x18002be71  mov     rcx, r13; this
0x18002be74  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18002be79  mov     edi, eax
0x18002be7b  mov     rbx, [rbp+2220h+var_22A0]
0x18002be7f  test    eax, eax
0x18002be81  js      loc_18002C190
0x18002be87  xor     ecx, ecx
0x18002be89  mov     r12d, [rsp+2320h+var_22B8]
0x18002be8e  cmp     word ptr [rsi], 7Bh ; '{'
0x18002be92  jnz     loc_18002C029
0x18002be98  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002be9c  inc     rax
0x18002be9f  cmp     [rsi+rax*2], cx
0x18002bea3  jnz     short loc_18002BE9C
0x18002bea5  cmp     rax, 1
0x18002bea9  jnz     loc_18002C029
0x18002beaf  mov     dword ptr [rsp+2320h+phkResult], 0; int
0x18002beb7  mov     r9d, r12d; int
0x18002beba  mov     r8, rbx; HKEY
0x18002bebd  mov     rdx, rsi; unsigned __int16 *
0x18002bec0  mov     rcx, r13; this
0x18002bec3  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18002bec8  mov     edi, eax
0x18002beca  test    eax, eax
0x18002becc  js      loc_18002C190
0x18002bed2  mov     rdx, rsi; unsigned __int16 *
0x18002bed5  mov     rcx, r13; this
0x18002bed8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
  ... truncated ...
```
