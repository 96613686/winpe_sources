# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800094ec`
- end: `0x180009c83`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18000917c`
- `0x1800094ec`

## callees

- `0x180004180`
- `0x180006970`
- `0x1800070a0`
- `0x1800070b8`
- `0x1800077f0`
- `0x1800089bc`
- `0x18000902c`
- `0x1800094ec`
- `0x18000a900`
- `0x1800300d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800099ca`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800099ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009887`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009887`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009af6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009b8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009af6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009b8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009768`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800097f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000983d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000989f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009993`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009baa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009768`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800097f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000983d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000989f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009993`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009baa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009732`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800097e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009829`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009978`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009732`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800097e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009829`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009978`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000974f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000974f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800095ce`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009799`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800095ce`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009799`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009569`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000957c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800095fa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009663`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009691`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009b19`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009569`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000957c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800095fa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009663`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009691`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009b19`

## string_xrefs

- `0x180009572`: `ForceRemove`
- `0x180009659`: `NoRemove`
- `0x18000955f`: `Delete`

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
0x1800094ec  push    rbp
0x1800094ee  push    rbx
0x1800094ef  push    rsi
0x1800094f0  push    rdi
0x1800094f1  push    r12
0x1800094f3  push    r13
0x1800094f5  push    r14
0x1800094f7  push    r15
0x1800094f9  lea     rbp, [rsp-21D8h]
0x180009501  mov     eax, 22D8h
0x180009506  call    _alloca_probe
0x18000950b  sub     rsp, rax
0x18000950e  mov     rax, cs:__security_cookie
0x180009515  xor     rax, rsp
0x180009518  mov     [rbp+2210h+var_50], rax
0x18000951f  mov     r12d, r9d
0x180009522  mov     [rsp+2310h+var_22A8], r9d
0x180009527  mov     r15, r8
0x18000952a  mov     [rsp+2310h+var_22A0], r8
0x18000952f  mov     rsi, rdx
0x180009532  mov     r13, rcx
0x180009535  xor     eax, eax
0x180009537  mov     ebx, eax
0x180009539  mov     [rbp+2210h+var_2290], rax
0x18000953d  mov     [rbp+2210h+var_2288], rax
0x180009541  mov     [rbp+2210h+var_2280], rax
0x180009545  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000954a  mov     edi, eax
0x18000954c  test    eax, eax
0x18000954e  jns     short loc_180009555
0x180009550  jmp     loc_180009C0C
0x180009555  cmp     word ptr [rsi], 7Dh ; '}'
0x180009559  jz      loc_180009BFC
0x18000955f  lea     rdx, String2; "Delete"
0x180009566  mov     rcx, rsi; lpString1
0x180009569  call    cs:__imp_lstrcmpiW
0x18000956f  mov     r14d, eax
0x180009572  lea     rdx, aForceremove; "ForceRemove"
0x180009579  mov     rcx, rsi; lpString1
0x18000957c  call    cs:__imp_lstrcmpiW
0x180009582  xor     edi, edi
0x180009584  test    eax, eax
0x180009586  jz      short loc_180009591
0x180009588  test    r14d, r14d
0x18000958b  jnz     loc_180009653
0x180009591  mov     rdx, rsi; unsigned __int16 *
0x180009594  mov     rcx, r13; this
0x180009597  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000959c  mov     edi, eax
0x18000959e  test    eax, eax
0x1800095a0  js      loc_180009BFC
0x1800095a6  xor     edi, edi
0x1800095a8  test    r12d, r12d
0x1800095ab  jz      loc_180009653
0x1800095b1  mov     [rbp+2210h+var_2278], rdi
0x1800095b5  mov     [rbp+2210h+var_2270], rdi
0x1800095b9  mov     [rbp+2210h+var_2268], rdi
0x1800095bd  movzx   eax, word ptr [rsi]
0x1800095c0  test    ax, ax
0x1800095c3  jz      short loc_1800095EA
0x1800095c5  mov     rcx, rsi; lpsz
0x1800095c8  cmp     ax, 5Ch ; '\'
0x1800095cc  jz      short loc_1800095E1
0x1800095ce  call    cs:__imp_CharNextW
0x1800095d4  mov     rcx, rax
0x1800095d7  movzx   eax, word ptr [rax]
0x1800095da  test    ax, ax
0x1800095dd  jnz     short loc_1800095C8
0x1800095df  jmp     short loc_1800095EA
0x1800095e1  test    rcx, rcx
0x1800095e4  jnz     loc_180009C48
0x1800095ea  mov     edx, edi
0x1800095ec  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x1800095f3  mov     rdx, [rax+rdx*8]; lpString2
0x1800095f7  mov     rcx, rsi; lpString1
0x1800095fa  call    cs:__imp_lstrcmpiW
0x180009600  test    eax, eax
0x180009602  jz      short loc_18000961B
0x180009604  inc     edi
0x180009606  cmp     edi, 0Ch
0x180009609  jl      short loc_1800095EA
0x18000960b  mov     [rbp+2210h+var_2278], r15
0x18000960f  mov     rdx, rsi; unsigned __int16 *
0x180009612  lea     rcx, [rbp+2210h+var_2278]; this
0x180009616  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000961b  xor     edi, edi
0x18000961d  test    r14d, r14d
0x180009620  jnz     short loc_180009653
0x180009622  mov     rdx, rsi; unsigned __int16 *
0x180009625  mov     rcx, r13; this
0x180009628  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000962d  mov     edi, eax
0x18000962f  test    eax, eax
0x180009631  js      loc_180009BFC
0x180009637  mov     rdx, rsi; unsigned __int16 *
0x18000963a  mov     rcx, r13; this
0x18000963d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180009642  mov     edi, eax
0x180009644  xor     ecx, ecx
0x180009646  test    eax, eax
0x180009648  js      loc_180009BFC
0x18000964e  jmp     loc_1800098FA
0x180009653  mov     r12d, 1
0x180009659  lea     rdx, aNoremove; "NoRemove"
0x180009660  mov     rcx, rsi; lpString1
0x180009663  call    cs:__imp_lstrcmpiW
0x180009669  test    eax, eax
0x18000966b  jnz     short loc_180009687
0x18000966d  mov     r12d, edi
0x180009670  mov     rdx, rsi; unsigned __int16 *
0x180009673  mov     rcx, r13; this
0x180009676  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000967b  mov     edi, eax
0x18000967d  test    eax, eax
0x18000967f  js      loc_180009BFC
0x180009685  xor     edi, edi
0x180009687  lea     rdx, aVal; "Val"
0x18000968e  mov     rcx, rsi; lpString1
0x180009691  call    cs:__imp_lstrcmpiW
0x180009697  test    eax, eax
0x180009699  jnz     loc_180009788
0x18000969f  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x1800096a6  mov     rcx, r13; this
0x1800096a9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800096ae  mov     edi, eax
0x1800096b0  test    eax, eax
0x1800096b2  js      loc_180009BFC
0x1800096b8  mov     rdx, rsi; unsigned __int16 *
0x1800096bb  mov     rcx, r13; this
0x1800096be  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800096c3  mov     edi, eax
0x1800096c5  test    eax, eax
0x1800096c7  js      loc_180009BFC
0x1800096cd  cmp     word ptr [rsi], 3Dh ; '='
0x1800096d1  jnz     loc_180009C48
0x1800096d7  xor     edi, edi
0x1800096d9  cmp     [rsp+2310h+var_22A8], edi
0x1800096dd  jz      short loc_180009708
0x1800096df  mov     [rbp+2210h+var_2270], rdi
0x1800096e3  mov     [rbp+2210h+var_2268], rdi
0x1800096e7  mov     [rbp+2210h+var_2278], r15
0x1800096eb  mov     r9, rsi; unsigned __int16 *
0x1800096ee  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x1800096f5  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x1800096f9  mov     rcx, r13; this
0x1800096fc  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180009701  mov     edi, eax
0x180009703  jmp     loc_1800098EB
0x180009708  cmp     [rbp+2210h+arg_20], edi
0x18000970e  jnz     short loc_18000976E
0x180009710  test    r12d, r12d
0x180009713  jz      short loc_18000976E
0x180009715  mov     [rsp+2310h+hKey], rdi
0x18000971a  lea     rax, [rsp+2310h+hKey]
0x18000971f  mov     [rsp+2310h+phkResult], rax; phkResult
0x180009724  mov     r9d, 20006h; samDesired
0x18000972a  xor     r8d, r8d; ulOptions
0x18000972d  xor     edx, edx; lpSubKey
0x18000972f  mov     rcx, r15; hKey
0x180009732  call    cs:__imp_RegOpenKeyExW
0x180009738  test    eax, eax
0x18000973a  jnz     loc_180009BF3
0x180009740  mov     r14, [rsp+2310h+hKey]
0x180009745  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18000974c  mov     rcx, r14; hKey
0x18000974f  call    cs:__imp_RegDeleteValueW
0x180009755  test    eax, 0FFFFFFFDh
0x18000975a  jnz     loc_180009C2F
0x180009760  test    r14, r14
0x180009763  jz      short loc_18000976E
0x180009765  mov     rcx, r14; hKey
0x180009768  call    cs:__imp_RegCloseKey
0x18000976e  mov     rdx, rsi; unsigned __int16 *
0x180009771  mov     rcx, r13; this
0x180009774  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180009779  mov     edi, eax
0x18000977b  test    eax, eax
0x18000977d  js      loc_180009BFC
0x180009783  jmp     loc_180009A95
0x180009788  movzx   eax, word ptr [rsi]
0x18000978b  test    ax, ax
0x18000978e  jz      short loc_1800097B5
0x180009790  mov     rcx, rsi; lpsz
0x180009793  cmp     ax, 5Ch ; '\'
0x180009797  jz      short loc_1800097AC
0x180009799  call    cs:__imp_CharNextW
0x18000979f  mov     rcx, rax
0x1800097a2  movzx   eax, word ptr [rax]
0x1800097a5  test    ax, ax
0x1800097a8  jnz     short loc_180009793
0x1800097aa  jmp     short loc_1800097B5
0x1800097ac  test    rcx, rcx
0x1800097af  jnz     loc_180009C48
0x1800097b5  cmp     [rsp+2310h+var_22A8], edi
0x1800097b9  jz      loc_18000994E
0x1800097bf  mov     [rsp+2310h+hKey], rdi
0x1800097c4  lea     rax, [rsp+2310h+hKey]
0x1800097c9  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800097ce  mov     r14d, 2001Fh
0x1800097d4  mov     r9d, r14d; samDesired
0x1800097d7  xor     r8d, r8d; ulOptions
0x1800097da  mov     rdx, rsi; lpSubKey
0x1800097dd  mov     rcx, r15; hKey
0x1800097e0  call    cs:__imp_RegOpenKeyExW
0x1800097e6  test    eax, eax
0x1800097e8  jnz     short loc_18000980B
0x1800097ea  mov     eax, edi
0x1800097ec  test    rbx, rbx
0x1800097ef  jz      short loc_1800097FA
0x1800097f1  mov     rcx, rbx; hKey
0x1800097f4  call    cs:__imp_RegCloseKey
0x1800097fa  mov     rbx, [rsp+2310h+hKey]
0x1800097ff  mov     [rbp+2210h+var_2290], rbx
0x180009803  test    eax, eax
0x180009805  jz      loc_1800098B6
0x18000980b  mov     [rsp+2310h+hKey], rdi
0x180009810  lea     rax, [rsp+2310h+hKey]
0x180009815  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000981a  mov     r9d, 20019h; samDesired
0x180009820  xor     r8d, r8d; ulOptions
0x180009823  mov     rdx, rsi; lpSubKey
0x180009826  mov     rcx, r15; hKey
0x180009829  call    cs:__imp_RegOpenKeyExW
0x18000982f  test    eax, eax
0x180009831  jnz     short loc_180009850
0x180009833  mov     eax, edi
0x180009835  test    rbx, rbx
0x180009838  jz      short loc_180009843
0x18000983a  mov     rcx, rbx; hKey
0x18000983d  call    cs:__imp_RegCloseKey
0x180009843  mov     rbx, [rsp+2310h+hKey]
0x180009848  mov     [rbp+2210h+var_2290], rbx
0x18000984c  test    eax, eax
0x18000984e  jz      short loc_1800098B6
0x180009850  mov     dword ptr [rsp+2310h+hKey], edi
0x180009854  mov     [rsp+2310h+var_2298], rdi
0x180009859  lea     rax, [rsp+2310h+hKey]
0x18000985e  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180009863  lea     rax, [rsp+2310h+var_2298]
0x180009868  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18000986d  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180009872  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180009877  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x18000987b  xor     r9d, r9d; lpClass
0x18000987e  xor     r8d, r8d; Reserved
0x180009881  mov     rdx, rsi; lpSubKey
0x180009884  mov     rcx, r15; hKey
0x180009887  call    cs:__imp_RegCreateKeyExW
0x18000988d  test    eax, eax
0x18000988f  jnz     loc_180009BF3
0x180009895  mov     eax, edi
0x180009897  test    rbx, rbx
0x18000989a  jz      short loc_1800098A5
0x18000989c  mov     rcx, rbx; hKey
0x18000989f  call    cs:__imp_RegCloseKey
0x1800098a5  mov     rbx, [rsp+2310h+var_2298]
0x1800098aa  mov     [rbp+2210h+var_2290], rbx
0x1800098ae  test    eax, eax
0x1800098b0  jnz     loc_180009BF3
0x1800098b6  mov     rdx, rsi; unsigned __int16 *
0x1800098b9  mov     rcx, r13; this
0x1800098bc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800098c1  mov     edi, eax
0x1800098c3  xor     ecx, ecx
0x1800098c5  test    eax, eax
0x1800098c7  js      loc_180009BFC
0x1800098cd  cmp     word ptr [rsi], 3Dh ; '='
0x1800098d1  jnz     short loc_1800098F5
0x1800098d3  mov     r9, rsi; unsigned __int16 *
0x1800098d6  xor     r8d, r8d; unsigned __int16 *
0x1800098d9  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x1800098dd  mov     rcx, r13; this
0x1800098e0  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800098e5  mov     edi, eax
0x1800098e7  mov     rbx, [rbp+2210h+var_2290]
0x1800098eb  test    eax, eax
0x1800098ed  js      loc_180009BFC
0x1800098f3  xor     ecx, ecx
0x1800098f5  mov     r12d, [rsp+2310h+var_22A8]
0x1800098fa  cmp     word ptr [rsi], 7Bh ; '{'
0x1800098fe  jnz     loc_180009A95
0x180009904  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009908  inc     rax
0x18000990b  cmp     [rsi+rax*2], cx
0x18000990f  jnz     short loc_180009908
0x180009911  cmp     rax, 1
0x180009915  jnz     loc_180009A95
0x18000991b  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180009923  mov     r9d, r12d; int
0x180009926  mov     r8, rbx; HKEY
0x180009929  mov     rdx, rsi; unsigned __int16 *
0x18000992c  mov     rcx, r13; this
0x18000992f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180009934  mov     edi, eax
0x180009936  test    eax, eax
0x180009938  js      loc_180009BFC
0x18000993e  mov     rdx, rsi; unsigned __int16 *
0x180009941  mov     rcx, r13; this
0x180009944  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009949  jmp     loc_180009779
  ... truncated ...
```
