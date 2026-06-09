# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180005764`
- end: `0x180005efb`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1800053f8`
- `0x180005764`

## callees

- `0x180003280`
- `0x180003abc`
- `0x180004328`
- `0x180004998`
- `0x180004c80`
- `0x1800052a8`
- `0x180005764`
- `0x180006184`
- `0x18000a9d0`
- `0x18000aa90`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180005c42`
- `msvcrt!wcsncpy_s` at `0x180005c42`
- `KERNEL32!lstrcmpiW` at `0x1800057e1`
- `KERNEL32!lstrcmpiW` at `0x1800057f4`
- `KERNEL32!lstrcmpiW` at `0x180005872`
- `KERNEL32!lstrcmpiW` at `0x1800058db`
- `KERNEL32!lstrcmpiW` at `0x180005909`
- `KERNEL32!lstrcmpiW` at `0x180005d91`
- `KERNEL32!lstrcmpiW` at `0x1800057e1`
- `KERNEL32!lstrcmpiW` at `0x1800057f4`
- `KERNEL32!lstrcmpiW` at `0x180005872`
- `KERNEL32!lstrcmpiW` at `0x1800058db`
- `KERNEL32!lstrcmpiW` at `0x180005909`
- `KERNEL32!lstrcmpiW` at `0x180005d91`
- `USER32!CharNextW` at `0x180005846`
- `USER32!CharNextW` at `0x180005a11`
- `USER32!CharNextW` at `0x180005846`
- `USER32!CharNextW` at `0x180005a11`
- `ADVAPI32!RegOpenKeyExW` at `0x1800059aa`
- `ADVAPI32!RegOpenKeyExW` at `0x180005a58`
- `ADVAPI32!RegOpenKeyExW` at `0x180005aa1`
- `ADVAPI32!RegOpenKeyExW` at `0x180005bf0`
- `ADVAPI32!RegOpenKeyExW` at `0x1800059aa`
- `ADVAPI32!RegOpenKeyExW` at `0x180005a58`
- `ADVAPI32!RegOpenKeyExW` at `0x180005aa1`
- `ADVAPI32!RegOpenKeyExW` at `0x180005bf0`
- `ADVAPI32!RegCloseKey` at `0x1800059e0`
- `ADVAPI32!RegCloseKey` at `0x180005a6c`
- `ADVAPI32!RegCloseKey` at `0x180005ab5`
- `ADVAPI32!RegCloseKey` at `0x180005b17`
- `ADVAPI32!RegCloseKey` at `0x180005c0b`
- `ADVAPI32!RegCloseKey` at `0x180005e22`
- `ADVAPI32!RegCloseKey` at `0x180005e7c`
- `ADVAPI32!RegCloseKey` at `0x180005eb8`
- `ADVAPI32!RegCloseKey` at `0x180005ec8`
- `ADVAPI32!RegCloseKey` at `0x1800059e0`
- `ADVAPI32!RegCloseKey` at `0x180005a6c`
- `ADVAPI32!RegCloseKey` at `0x180005ab5`
- `ADVAPI32!RegCloseKey` at `0x180005b17`
- `ADVAPI32!RegCloseKey` at `0x180005c0b`
- `ADVAPI32!RegCloseKey` at `0x180005e22`
- `ADVAPI32!RegCloseKey` at `0x180005e7c`
- `ADVAPI32!RegCloseKey` at `0x180005eb8`
- `ADVAPI32!RegCloseKey` at `0x180005ec8`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005d6e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005e04`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005d6e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005e04`
- `ADVAPI32!RegCreateKeyExW` at `0x180005aff`
- `ADVAPI32!RegCreateKeyExW` at `0x180005aff`
- `ADVAPI32!RegDeleteValueW` at `0x1800059c7`
- `ADVAPI32!RegDeleteValueW` at `0x1800059c7`

## string_xrefs

- `0x1800057ea`: `ForceRemove`
- `0x1800058d1`: `NoRemove`
- `0x1800057d7`: `Delete`

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
0x180005764  push    rbp
0x180005766  push    rbx
0x180005767  push    rsi
0x180005768  push    rdi
0x180005769  push    r12
0x18000576b  push    r13
0x18000576d  push    r14
0x18000576f  push    r15
0x180005771  lea     rbp, [rsp-21D8h]
0x180005779  mov     eax, 22D8h
0x18000577e  call    _alloca_probe
0x180005783  sub     rsp, rax
0x180005786  mov     rax, cs:__security_cookie
0x18000578d  xor     rax, rsp
0x180005790  mov     [rbp+2210h+var_50], rax
0x180005797  mov     r12d, r9d
0x18000579a  mov     [rsp+2310h+var_22A8], r9d
0x18000579f  mov     r15, r8
0x1800057a2  mov     [rsp+2310h+var_22A0], r8
0x1800057a7  mov     rsi, rdx
0x1800057aa  mov     r13, rcx
0x1800057ad  xor     eax, eax
0x1800057af  mov     ebx, eax
0x1800057b1  mov     [rbp+2210h+var_2290], rax
0x1800057b5  mov     [rbp+2210h+var_2288], rax
0x1800057b9  mov     [rbp+2210h+var_2280], rax
0x1800057bd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800057c2  mov     edi, eax
0x1800057c4  test    eax, eax
0x1800057c6  jns     short loc_1800057CD
0x1800057c8  jmp     loc_180005E84
0x1800057cd  cmp     word ptr [rsi], 7Dh ; '}'
0x1800057d1  jz      loc_180005E74
0x1800057d7  lea     rdx, String2; "Delete"
0x1800057de  mov     rcx, rsi; lpString1
0x1800057e1  call    cs:__imp_lstrcmpiW
0x1800057e7  mov     r14d, eax
0x1800057ea  lea     rdx, aForceremove; "ForceRemove"
0x1800057f1  mov     rcx, rsi; lpString1
0x1800057f4  call    cs:__imp_lstrcmpiW
0x1800057fa  xor     edi, edi
0x1800057fc  test    eax, eax
0x1800057fe  jz      short loc_180005809
0x180005800  test    r14d, r14d
0x180005803  jnz     loc_1800058CB
0x180005809  mov     rdx, rsi; unsigned __int16 *
0x18000580c  mov     rcx, r13; this
0x18000580f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005814  mov     edi, eax
0x180005816  test    eax, eax
0x180005818  js      loc_180005E74
0x18000581e  xor     edi, edi
0x180005820  test    r12d, r12d
0x180005823  jz      loc_1800058CB
0x180005829  mov     [rbp+2210h+var_2278], rdi
0x18000582d  mov     [rbp+2210h+var_2270], rdi
0x180005831  mov     [rbp+2210h+var_2268], rdi
0x180005835  movzx   eax, word ptr [rsi]
0x180005838  test    ax, ax
0x18000583b  jz      short loc_180005862
0x18000583d  mov     rcx, rsi; lpsz
0x180005840  cmp     ax, 5Ch ; '\'
0x180005844  jz      short loc_180005859
0x180005846  call    cs:__imp_CharNextW
0x18000584c  mov     rcx, rax
0x18000584f  movzx   eax, word ptr [rax]
0x180005852  test    ax, ax
0x180005855  jnz     short loc_180005840
0x180005857  jmp     short loc_180005862
0x180005859  test    rcx, rcx
0x18000585c  jnz     loc_180005EC0
0x180005862  mov     edx, edi
0x180005864  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x18000586b  mov     rdx, [rax+rdx*8]; lpString2
0x18000586f  mov     rcx, rsi; lpString1
0x180005872  call    cs:__imp_lstrcmpiW
0x180005878  test    eax, eax
0x18000587a  jz      short loc_180005893
0x18000587c  inc     edi
0x18000587e  cmp     edi, 0Ch
0x180005881  jl      short loc_180005862
0x180005883  mov     [rbp+2210h+var_2278], r15
0x180005887  mov     rdx, rsi; unsigned __int16 *
0x18000588a  lea     rcx, [rbp+2210h+var_2278]; this
0x18000588e  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180005893  xor     edi, edi
0x180005895  test    r14d, r14d
0x180005898  jnz     short loc_1800058CB
0x18000589a  mov     rdx, rsi; unsigned __int16 *
0x18000589d  mov     rcx, r13; this
0x1800058a0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800058a5  mov     edi, eax
0x1800058a7  test    eax, eax
0x1800058a9  js      loc_180005E74
0x1800058af  mov     rdx, rsi; unsigned __int16 *
0x1800058b2  mov     rcx, r13; this
0x1800058b5  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800058ba  mov     edi, eax
0x1800058bc  xor     ecx, ecx
0x1800058be  test    eax, eax
0x1800058c0  js      loc_180005E74
0x1800058c6  jmp     loc_180005B72
0x1800058cb  mov     r12d, 1
0x1800058d1  lea     rdx, aNoremove; "NoRemove"
0x1800058d8  mov     rcx, rsi; lpString1
0x1800058db  call    cs:__imp_lstrcmpiW
0x1800058e1  test    eax, eax
0x1800058e3  jnz     short loc_1800058FF
0x1800058e5  mov     r12d, edi
0x1800058e8  mov     rdx, rsi; unsigned __int16 *
0x1800058eb  mov     rcx, r13; this
0x1800058ee  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800058f3  mov     edi, eax
0x1800058f5  test    eax, eax
0x1800058f7  js      loc_180005E74
0x1800058fd  xor     edi, edi
0x1800058ff  lea     rdx, aVal; "Val"
0x180005906  mov     rcx, rsi; lpString1
0x180005909  call    cs:__imp_lstrcmpiW
0x18000590f  test    eax, eax
0x180005911  jnz     loc_180005A00
0x180005917  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x18000591e  mov     rcx, r13; this
0x180005921  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005926  mov     edi, eax
0x180005928  test    eax, eax
0x18000592a  js      loc_180005E74
0x180005930  mov     rdx, rsi; unsigned __int16 *
0x180005933  mov     rcx, r13; this
0x180005936  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000593b  mov     edi, eax
0x18000593d  test    eax, eax
0x18000593f  js      loc_180005E74
0x180005945  cmp     word ptr [rsi], 3Dh ; '='
0x180005949  jnz     loc_180005EC0
0x18000594f  xor     edi, edi
0x180005951  cmp     [rsp+2310h+var_22A8], edi
0x180005955  jz      short loc_180005980
0x180005957  mov     [rbp+2210h+var_2270], rdi
0x18000595b  mov     [rbp+2210h+var_2268], rdi
0x18000595f  mov     [rbp+2210h+var_2278], r15
0x180005963  mov     r9, rsi; unsigned __int16 *
0x180005966  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x18000596d  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180005971  mov     rcx, r13; this
0x180005974  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005979  mov     edi, eax
0x18000597b  jmp     loc_180005B63
0x180005980  cmp     [rbp+2210h+arg_20], edi
0x180005986  jnz     short loc_1800059E6
0x180005988  test    r12d, r12d
0x18000598b  jz      short loc_1800059E6
0x18000598d  mov     [rsp+2310h+hKey], rdi
0x180005992  lea     rax, [rsp+2310h+hKey]
0x180005997  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000599c  mov     r9d, 20006h; samDesired
0x1800059a2  xor     r8d, r8d; ulOptions
0x1800059a5  xor     edx, edx; lpSubKey
0x1800059a7  mov     rcx, r15; hKey
0x1800059aa  call    cs:__imp_RegOpenKeyExW
0x1800059b0  test    eax, eax
0x1800059b2  jnz     loc_180005E6B
0x1800059b8  mov     r14, [rsp+2310h+hKey]
0x1800059bd  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x1800059c4  mov     rcx, r14; hKey
0x1800059c7  call    cs:__imp_RegDeleteValueW
0x1800059cd  test    eax, 0FFFFFFFDh
0x1800059d2  jnz     loc_180005EA7
0x1800059d8  test    r14, r14
0x1800059db  jz      short loc_1800059E6
0x1800059dd  mov     rcx, r14; hKey
0x1800059e0  call    cs:__imp_RegCloseKey
0x1800059e6  mov     rdx, rsi; unsigned __int16 *
0x1800059e9  mov     rcx, r13; this
0x1800059ec  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800059f1  mov     edi, eax
0x1800059f3  test    eax, eax
0x1800059f5  js      loc_180005E74
0x1800059fb  jmp     loc_180005D0D
0x180005a00  movzx   eax, word ptr [rsi]
0x180005a03  test    ax, ax
0x180005a06  jz      short loc_180005A2D
0x180005a08  mov     rcx, rsi; lpsz
0x180005a0b  cmp     ax, 5Ch ; '\'
0x180005a0f  jz      short loc_180005A24
0x180005a11  call    cs:__imp_CharNextW
0x180005a17  mov     rcx, rax
0x180005a1a  movzx   eax, word ptr [rax]
0x180005a1d  test    ax, ax
0x180005a20  jnz     short loc_180005A0B
0x180005a22  jmp     short loc_180005A2D
0x180005a24  test    rcx, rcx
0x180005a27  jnz     loc_180005EC0
0x180005a2d  cmp     [rsp+2310h+var_22A8], edi
0x180005a31  jz      loc_180005BC6
0x180005a37  mov     [rsp+2310h+hKey], rdi
0x180005a3c  lea     rax, [rsp+2310h+hKey]
0x180005a41  mov     [rsp+2310h+phkResult], rax; phkResult
0x180005a46  mov     r14d, 2001Fh
0x180005a4c  mov     r9d, r14d; samDesired
0x180005a4f  xor     r8d, r8d; ulOptions
0x180005a52  mov     rdx, rsi; lpSubKey
0x180005a55  mov     rcx, r15; hKey
0x180005a58  call    cs:__imp_RegOpenKeyExW
0x180005a5e  test    eax, eax
0x180005a60  jnz     short loc_180005A83
0x180005a62  mov     eax, edi
0x180005a64  test    rbx, rbx
0x180005a67  jz      short loc_180005A72
0x180005a69  mov     rcx, rbx; hKey
0x180005a6c  call    cs:__imp_RegCloseKey
0x180005a72  mov     rbx, [rsp+2310h+hKey]
0x180005a77  mov     [rbp+2210h+var_2290], rbx
0x180005a7b  test    eax, eax
0x180005a7d  jz      loc_180005B2E
0x180005a83  mov     [rsp+2310h+hKey], rdi
0x180005a88  lea     rax, [rsp+2310h+hKey]
0x180005a8d  mov     [rsp+2310h+phkResult], rax; phkResult
0x180005a92  mov     r9d, 20019h; samDesired
0x180005a98  xor     r8d, r8d; ulOptions
0x180005a9b  mov     rdx, rsi; lpSubKey
0x180005a9e  mov     rcx, r15; hKey
0x180005aa1  call    cs:__imp_RegOpenKeyExW
0x180005aa7  test    eax, eax
0x180005aa9  jnz     short loc_180005AC8
0x180005aab  mov     eax, edi
0x180005aad  test    rbx, rbx
0x180005ab0  jz      short loc_180005ABB
0x180005ab2  mov     rcx, rbx; hKey
0x180005ab5  call    cs:__imp_RegCloseKey
0x180005abb  mov     rbx, [rsp+2310h+hKey]
0x180005ac0  mov     [rbp+2210h+var_2290], rbx
0x180005ac4  test    eax, eax
0x180005ac6  jz      short loc_180005B2E
0x180005ac8  mov     dword ptr [rsp+2310h+hKey], edi
0x180005acc  mov     [rsp+2310h+var_2298], rdi
0x180005ad1  lea     rax, [rsp+2310h+hKey]
0x180005ad6  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180005adb  lea     rax, [rsp+2310h+var_2298]
0x180005ae0  mov     [rsp+2310h+var_22D8], rax; phkResult
0x180005ae5  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180005aea  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180005aef  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180005af3  xor     r9d, r9d; lpClass
0x180005af6  xor     r8d, r8d; Reserved
0x180005af9  mov     rdx, rsi; lpSubKey
0x180005afc  mov     rcx, r15; hKey
0x180005aff  call    cs:__imp_RegCreateKeyExW
0x180005b05  test    eax, eax
0x180005b07  jnz     loc_180005E6B
0x180005b0d  mov     eax, edi
0x180005b0f  test    rbx, rbx
0x180005b12  jz      short loc_180005B1D
0x180005b14  mov     rcx, rbx; hKey
0x180005b17  call    cs:__imp_RegCloseKey
0x180005b1d  mov     rbx, [rsp+2310h+var_2298]
0x180005b22  mov     [rbp+2210h+var_2290], rbx
0x180005b26  test    eax, eax
0x180005b28  jnz     loc_180005E6B
0x180005b2e  mov     rdx, rsi; unsigned __int16 *
0x180005b31  mov     rcx, r13; this
0x180005b34  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005b39  mov     edi, eax
0x180005b3b  xor     ecx, ecx
0x180005b3d  test    eax, eax
0x180005b3f  js      loc_180005E74
0x180005b45  cmp     word ptr [rsi], 3Dh ; '='
0x180005b49  jnz     short loc_180005B6D
0x180005b4b  mov     r9, rsi; unsigned __int16 *
0x180005b4e  xor     r8d, r8d; unsigned __int16 *
0x180005b51  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180005b55  mov     rcx, r13; this
0x180005b58  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005b5d  mov     edi, eax
0x180005b5f  mov     rbx, [rbp+2210h+var_2290]
0x180005b63  test    eax, eax
0x180005b65  js      loc_180005E74
0x180005b6b  xor     ecx, ecx
0x180005b6d  mov     r12d, [rsp+2310h+var_22A8]
0x180005b72  cmp     word ptr [rsi], 7Bh ; '{'
0x180005b76  jnz     loc_180005D0D
0x180005b7c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005b80  inc     rax
0x180005b83  cmp     [rsi+rax*2], cx
0x180005b87  jnz     short loc_180005B80
0x180005b89  cmp     rax, 1
0x180005b8d  jnz     loc_180005D0D
0x180005b93  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180005b9b  mov     r9d, r12d; int
0x180005b9e  mov     r8, rbx; HKEY
0x180005ba1  mov     rdx, rsi; unsigned __int16 *
0x180005ba4  mov     rcx, r13; this
0x180005ba7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005bac  mov     edi, eax
0x180005bae  test    eax, eax
0x180005bb0  js      loc_180005E74
0x180005bb6  mov     rdx, rsi; unsigned __int16 *
0x180005bb9  mov     rcx, r13; this
0x180005bbc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005bc1  jmp     loc_1800059F1
  ... truncated ...
```
