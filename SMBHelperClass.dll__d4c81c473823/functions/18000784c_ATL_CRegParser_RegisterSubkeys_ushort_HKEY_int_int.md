# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000784c`
- end: `0x180007fe3`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1800074dc`
- `0x18000784c`

## callees

- `0x180003f3c`
- `0x18000466c`
- `0x180004684`
- `0x180004d78`
- `0x180006dbc`
- `0x18000738c`
- `0x18000784c`
- `0x180008a98`
- `0x18000fc30`
- `0x18000fcf0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180007d2a`
- `msvcrt!wcsncpy_s` at `0x180007d2a`
- `KERNEL32!lstrcmpiW` at `0x1800078c9`
- `KERNEL32!lstrcmpiW` at `0x1800078dc`
- `KERNEL32!lstrcmpiW` at `0x18000795a`
- `KERNEL32!lstrcmpiW` at `0x1800079c3`
- `KERNEL32!lstrcmpiW` at `0x1800079f1`
- `KERNEL32!lstrcmpiW` at `0x180007e79`
- `KERNEL32!lstrcmpiW` at `0x1800078c9`
- `KERNEL32!lstrcmpiW` at `0x1800078dc`
- `KERNEL32!lstrcmpiW` at `0x18000795a`
- `KERNEL32!lstrcmpiW` at `0x1800079c3`
- `KERNEL32!lstrcmpiW` at `0x1800079f1`
- `KERNEL32!lstrcmpiW` at `0x180007e79`
- `USER32!CharNextW` at `0x18000792e`
- `USER32!CharNextW` at `0x180007af9`
- `USER32!CharNextW` at `0x18000792e`
- `USER32!CharNextW` at `0x180007af9`
- `ADVAPI32!RegDeleteValueW` at `0x180007aaf`
- `ADVAPI32!RegDeleteValueW` at `0x180007aaf`
- `ADVAPI32!RegCreateKeyExW` at `0x180007be7`
- `ADVAPI32!RegCreateKeyExW` at `0x180007be7`
- `ADVAPI32!RegOpenKeyExW` at `0x180007a92`
- `ADVAPI32!RegOpenKeyExW` at `0x180007b40`
- `ADVAPI32!RegOpenKeyExW` at `0x180007b89`
- `ADVAPI32!RegOpenKeyExW` at `0x180007cd8`
- `ADVAPI32!RegOpenKeyExW` at `0x180007a92`
- `ADVAPI32!RegOpenKeyExW` at `0x180007b40`
- `ADVAPI32!RegOpenKeyExW` at `0x180007b89`
- `ADVAPI32!RegOpenKeyExW` at `0x180007cd8`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180007e56`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180007eec`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180007e56`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180007eec`
- `ADVAPI32!RegCloseKey` at `0x180007ac8`
- `ADVAPI32!RegCloseKey` at `0x180007b54`
- `ADVAPI32!RegCloseKey` at `0x180007b9d`
- `ADVAPI32!RegCloseKey` at `0x180007bff`
- `ADVAPI32!RegCloseKey` at `0x180007cf3`
- `ADVAPI32!RegCloseKey` at `0x180007f0a`
- `ADVAPI32!RegCloseKey` at `0x180007f64`
- `ADVAPI32!RegCloseKey` at `0x180007fa0`
- `ADVAPI32!RegCloseKey` at `0x180007fb0`
- `ADVAPI32!RegCloseKey` at `0x180007ac8`
- `ADVAPI32!RegCloseKey` at `0x180007b54`
- `ADVAPI32!RegCloseKey` at `0x180007b9d`
- `ADVAPI32!RegCloseKey` at `0x180007bff`
- `ADVAPI32!RegCloseKey` at `0x180007cf3`
- `ADVAPI32!RegCloseKey` at `0x180007f0a`
- `ADVAPI32!RegCloseKey` at `0x180007f64`
- `ADVAPI32!RegCloseKey` at `0x180007fa0`
- `ADVAPI32!RegCloseKey` at `0x180007fb0`

## string_xrefs

- `0x1800078d2`: `ForceRemove`
- `0x1800079b9`: `NoRemove`
- `0x1800078bf`: `Delete`

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
0x18000784c  push    rbp
0x18000784e  push    rbx
0x18000784f  push    rsi
0x180007850  push    rdi
0x180007851  push    r12
0x180007853  push    r13
0x180007855  push    r14
0x180007857  push    r15
0x180007859  lea     rbp, [rsp-21D8h]
0x180007861  mov     eax, 22D8h
0x180007866  call    _alloca_probe
0x18000786b  sub     rsp, rax
0x18000786e  mov     rax, cs:__security_cookie
0x180007875  xor     rax, rsp
0x180007878  mov     [rbp+2210h+var_50], rax
0x18000787f  mov     r12d, r9d
0x180007882  mov     [rsp+2310h+var_22A8], r9d
0x180007887  mov     r15, r8
0x18000788a  mov     [rsp+2310h+var_22A0], r8
0x18000788f  mov     rsi, rdx
0x180007892  mov     r13, rcx
0x180007895  xor     eax, eax
0x180007897  mov     ebx, eax
0x180007899  mov     [rbp+2210h+var_2290], rax
0x18000789d  mov     [rbp+2210h+var_2288], rax
0x1800078a1  mov     [rbp+2210h+var_2280], rax
0x1800078a5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800078aa  mov     edi, eax
0x1800078ac  test    eax, eax
0x1800078ae  jns     short loc_1800078B5
0x1800078b0  jmp     loc_180007F6C
0x1800078b5  cmp     word ptr [rsi], 7Dh ; '}'
0x1800078b9  jz      loc_180007F5C
0x1800078bf  lea     rdx, String2; "Delete"
0x1800078c6  mov     rcx, rsi; lpString1
0x1800078c9  call    cs:__imp_lstrcmpiW
0x1800078cf  mov     r14d, eax
0x1800078d2  lea     rdx, aForceremove; "ForceRemove"
0x1800078d9  mov     rcx, rsi; lpString1
0x1800078dc  call    cs:__imp_lstrcmpiW
0x1800078e2  xor     edi, edi
0x1800078e4  test    eax, eax
0x1800078e6  jz      short loc_1800078F1
0x1800078e8  test    r14d, r14d
0x1800078eb  jnz     loc_1800079B3
0x1800078f1  mov     rdx, rsi; unsigned __int16 *
0x1800078f4  mov     rcx, r13; this
0x1800078f7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800078fc  mov     edi, eax
0x1800078fe  test    eax, eax
0x180007900  js      loc_180007F5C
0x180007906  xor     edi, edi
0x180007908  test    r12d, r12d
0x18000790b  jz      loc_1800079B3
0x180007911  mov     [rbp+2210h+var_2278], rdi
0x180007915  mov     [rbp+2210h+var_2270], rdi
0x180007919  mov     [rbp+2210h+var_2268], rdi
0x18000791d  movzx   eax, word ptr [rsi]
0x180007920  test    ax, ax
0x180007923  jz      short loc_18000794A
0x180007925  mov     rcx, rsi; lpsz
0x180007928  cmp     ax, 5Ch ; '\'
0x18000792c  jz      short loc_180007941
0x18000792e  call    cs:__imp_CharNextW
0x180007934  mov     rcx, rax
0x180007937  movzx   eax, word ptr [rax]
0x18000793a  test    ax, ax
0x18000793d  jnz     short loc_180007928
0x18000793f  jmp     short loc_18000794A
0x180007941  test    rcx, rcx
0x180007944  jnz     loc_180007FA8
0x18000794a  mov     edx, edi
0x18000794c  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180007953  mov     rdx, [rax+rdx*8]; lpString2
0x180007957  mov     rcx, rsi; lpString1
0x18000795a  call    cs:__imp_lstrcmpiW
0x180007960  test    eax, eax
0x180007962  jz      short loc_18000797B
0x180007964  inc     edi
0x180007966  cmp     edi, 0Ch
0x180007969  jl      short loc_18000794A
0x18000796b  mov     [rbp+2210h+var_2278], r15
0x18000796f  mov     rdx, rsi; unsigned __int16 *
0x180007972  lea     rcx, [rbp+2210h+var_2278]; this
0x180007976  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000797b  xor     edi, edi
0x18000797d  test    r14d, r14d
0x180007980  jnz     short loc_1800079B3
0x180007982  mov     rdx, rsi; unsigned __int16 *
0x180007985  mov     rcx, r13; this
0x180007988  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000798d  mov     edi, eax
0x18000798f  test    eax, eax
0x180007991  js      loc_180007F5C
0x180007997  mov     rdx, rsi; unsigned __int16 *
0x18000799a  mov     rcx, r13; this
0x18000799d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800079a2  mov     edi, eax
0x1800079a4  xor     ecx, ecx
0x1800079a6  test    eax, eax
0x1800079a8  js      loc_180007F5C
0x1800079ae  jmp     loc_180007C5A
0x1800079b3  mov     r12d, 1
0x1800079b9  lea     rdx, aNoremove; "NoRemove"
0x1800079c0  mov     rcx, rsi; lpString1
0x1800079c3  call    cs:__imp_lstrcmpiW
0x1800079c9  test    eax, eax
0x1800079cb  jnz     short loc_1800079E7
0x1800079cd  mov     r12d, edi
0x1800079d0  mov     rdx, rsi; unsigned __int16 *
0x1800079d3  mov     rcx, r13; this
0x1800079d6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800079db  mov     edi, eax
0x1800079dd  test    eax, eax
0x1800079df  js      loc_180007F5C
0x1800079e5  xor     edi, edi
0x1800079e7  lea     rdx, aVal; "Val"
0x1800079ee  mov     rcx, rsi; lpString1
0x1800079f1  call    cs:__imp_lstrcmpiW
0x1800079f7  test    eax, eax
0x1800079f9  jnz     loc_180007AE8
0x1800079ff  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180007a06  mov     rcx, r13; this
0x180007a09  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007a0e  mov     edi, eax
0x180007a10  test    eax, eax
0x180007a12  js      loc_180007F5C
0x180007a18  mov     rdx, rsi; unsigned __int16 *
0x180007a1b  mov     rcx, r13; this
0x180007a1e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007a23  mov     edi, eax
0x180007a25  test    eax, eax
0x180007a27  js      loc_180007F5C
0x180007a2d  cmp     word ptr [rsi], 3Dh ; '='
0x180007a31  jnz     loc_180007FA8
0x180007a37  xor     edi, edi
0x180007a39  cmp     [rsp+2310h+var_22A8], edi
0x180007a3d  jz      short loc_180007A68
0x180007a3f  mov     [rbp+2210h+var_2270], rdi
0x180007a43  mov     [rbp+2210h+var_2268], rdi
0x180007a47  mov     [rbp+2210h+var_2278], r15
0x180007a4b  mov     r9, rsi; unsigned __int16 *
0x180007a4e  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180007a55  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180007a59  mov     rcx, r13; this
0x180007a5c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180007a61  mov     edi, eax
0x180007a63  jmp     loc_180007C4B
0x180007a68  cmp     [rbp+2210h+arg_20], edi
0x180007a6e  jnz     short loc_180007ACE
0x180007a70  test    r12d, r12d
0x180007a73  jz      short loc_180007ACE
0x180007a75  mov     [rsp+2310h+hKey], rdi
0x180007a7a  lea     rax, [rsp+2310h+hKey]
0x180007a7f  mov     [rsp+2310h+phkResult], rax; phkResult
0x180007a84  mov     r9d, 20006h; samDesired
0x180007a8a  xor     r8d, r8d; ulOptions
0x180007a8d  xor     edx, edx; lpSubKey
0x180007a8f  mov     rcx, r15; hKey
0x180007a92  call    cs:__imp_RegOpenKeyExW
0x180007a98  test    eax, eax
0x180007a9a  jnz     loc_180007F53
0x180007aa0  mov     r14, [rsp+2310h+hKey]
0x180007aa5  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180007aac  mov     rcx, r14; hKey
0x180007aaf  call    cs:__imp_RegDeleteValueW
0x180007ab5  test    eax, 0FFFFFFFDh
0x180007aba  jnz     loc_180007F8F
0x180007ac0  test    r14, r14
0x180007ac3  jz      short loc_180007ACE
0x180007ac5  mov     rcx, r14; hKey
0x180007ac8  call    cs:__imp_RegCloseKey
0x180007ace  mov     rdx, rsi; unsigned __int16 *
0x180007ad1  mov     rcx, r13; this
0x180007ad4  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180007ad9  mov     edi, eax
0x180007adb  test    eax, eax
0x180007add  js      loc_180007F5C
0x180007ae3  jmp     loc_180007DF5
0x180007ae8  movzx   eax, word ptr [rsi]
0x180007aeb  test    ax, ax
0x180007aee  jz      short loc_180007B15
0x180007af0  mov     rcx, rsi; lpsz
0x180007af3  cmp     ax, 5Ch ; '\'
0x180007af7  jz      short loc_180007B0C
0x180007af9  call    cs:__imp_CharNextW
0x180007aff  mov     rcx, rax
0x180007b02  movzx   eax, word ptr [rax]
0x180007b05  test    ax, ax
0x180007b08  jnz     short loc_180007AF3
0x180007b0a  jmp     short loc_180007B15
0x180007b0c  test    rcx, rcx
0x180007b0f  jnz     loc_180007FA8
0x180007b15  cmp     [rsp+2310h+var_22A8], edi
0x180007b19  jz      loc_180007CAE
0x180007b1f  mov     [rsp+2310h+hKey], rdi
0x180007b24  lea     rax, [rsp+2310h+hKey]
0x180007b29  mov     [rsp+2310h+phkResult], rax; phkResult
0x180007b2e  mov     r14d, 2001Fh
0x180007b34  mov     r9d, r14d; samDesired
0x180007b37  xor     r8d, r8d; ulOptions
0x180007b3a  mov     rdx, rsi; lpSubKey
0x180007b3d  mov     rcx, r15; hKey
0x180007b40  call    cs:__imp_RegOpenKeyExW
0x180007b46  test    eax, eax
0x180007b48  jnz     short loc_180007B6B
0x180007b4a  mov     eax, edi
0x180007b4c  test    rbx, rbx
0x180007b4f  jz      short loc_180007B5A
0x180007b51  mov     rcx, rbx; hKey
0x180007b54  call    cs:__imp_RegCloseKey
0x180007b5a  mov     rbx, [rsp+2310h+hKey]
0x180007b5f  mov     [rbp+2210h+var_2290], rbx
0x180007b63  test    eax, eax
0x180007b65  jz      loc_180007C16
0x180007b6b  mov     [rsp+2310h+hKey], rdi
0x180007b70  lea     rax, [rsp+2310h+hKey]
0x180007b75  mov     [rsp+2310h+phkResult], rax; phkResult
0x180007b7a  mov     r9d, 20019h; samDesired
0x180007b80  xor     r8d, r8d; ulOptions
0x180007b83  mov     rdx, rsi; lpSubKey
0x180007b86  mov     rcx, r15; hKey
0x180007b89  call    cs:__imp_RegOpenKeyExW
0x180007b8f  test    eax, eax
0x180007b91  jnz     short loc_180007BB0
0x180007b93  mov     eax, edi
0x180007b95  test    rbx, rbx
0x180007b98  jz      short loc_180007BA3
0x180007b9a  mov     rcx, rbx; hKey
0x180007b9d  call    cs:__imp_RegCloseKey
0x180007ba3  mov     rbx, [rsp+2310h+hKey]
0x180007ba8  mov     [rbp+2210h+var_2290], rbx
0x180007bac  test    eax, eax
0x180007bae  jz      short loc_180007C16
0x180007bb0  mov     dword ptr [rsp+2310h+hKey], edi
0x180007bb4  mov     [rsp+2310h+var_2298], rdi
0x180007bb9  lea     rax, [rsp+2310h+hKey]
0x180007bbe  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180007bc3  lea     rax, [rsp+2310h+var_2298]
0x180007bc8  mov     [rsp+2310h+var_22D8], rax; phkResult
0x180007bcd  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180007bd2  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180007bd7  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180007bdb  xor     r9d, r9d; lpClass
0x180007bde  xor     r8d, r8d; Reserved
0x180007be1  mov     rdx, rsi; lpSubKey
0x180007be4  mov     rcx, r15; hKey
0x180007be7  call    cs:__imp_RegCreateKeyExW
0x180007bed  test    eax, eax
0x180007bef  jnz     loc_180007F53
0x180007bf5  mov     eax, edi
0x180007bf7  test    rbx, rbx
0x180007bfa  jz      short loc_180007C05
0x180007bfc  mov     rcx, rbx; hKey
0x180007bff  call    cs:__imp_RegCloseKey
0x180007c05  mov     rbx, [rsp+2310h+var_2298]
0x180007c0a  mov     [rbp+2210h+var_2290], rbx
0x180007c0e  test    eax, eax
0x180007c10  jnz     loc_180007F53
0x180007c16  mov     rdx, rsi; unsigned __int16 *
0x180007c19  mov     rcx, r13; this
0x180007c1c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007c21  mov     edi, eax
0x180007c23  xor     ecx, ecx
0x180007c25  test    eax, eax
0x180007c27  js      loc_180007F5C
0x180007c2d  cmp     word ptr [rsi], 3Dh ; '='
0x180007c31  jnz     short loc_180007C55
0x180007c33  mov     r9, rsi; unsigned __int16 *
0x180007c36  xor     r8d, r8d; unsigned __int16 *
0x180007c39  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180007c3d  mov     rcx, r13; this
0x180007c40  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180007c45  mov     edi, eax
0x180007c47  mov     rbx, [rbp+2210h+var_2290]
0x180007c4b  test    eax, eax
0x180007c4d  js      loc_180007F5C
0x180007c53  xor     ecx, ecx
0x180007c55  mov     r12d, [rsp+2310h+var_22A8]
0x180007c5a  cmp     word ptr [rsi], 7Bh ; '{'
0x180007c5e  jnz     loc_180007DF5
0x180007c64  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007c68  inc     rax
0x180007c6b  cmp     [rsi+rax*2], cx
0x180007c6f  jnz     short loc_180007C68
0x180007c71  cmp     rax, 1
0x180007c75  jnz     loc_180007DF5
0x180007c7b  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180007c83  mov     r9d, r12d; int
0x180007c86  mov     r8, rbx; HKEY
0x180007c89  mov     rdx, rsi; unsigned __int16 *
0x180007c8c  mov     rcx, r13; this
0x180007c8f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007c94  mov     edi, eax
0x180007c96  test    eax, eax
0x180007c98  js      loc_180007F5C
0x180007c9e  mov     rdx, rsi; unsigned __int16 *
0x180007ca1  mov     rcx, r13; this
0x180007ca4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007ca9  jmp     loc_180007AD9
  ... truncated ...
```
