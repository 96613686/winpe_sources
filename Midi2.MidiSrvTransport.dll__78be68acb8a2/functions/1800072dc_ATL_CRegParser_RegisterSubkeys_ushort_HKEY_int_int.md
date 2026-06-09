# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800072dc`
- end: `0x180007a73`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180006f6c`
- `0x1800072dc`

## callees

- `0x180002470`
- `0x180004770`
- `0x180004ea0`
- `0x180004eb8`
- `0x1800055d0`
- `0x1800067ac`
- `0x180006e1c`
- `0x1800072dc`
- `0x180008700`
- `0x180014020`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800077ba`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800077ba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007677`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007677`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007522`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800075d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007619`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007768`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007522`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800075d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007619`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007768`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000753f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000753f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007558`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800075e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000762d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000768f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007783`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000799a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800079f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007558`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800075e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000762d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000768f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007783`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000799a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800079f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a40`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800078e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000797c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800078e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000797c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800073be`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007589`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800073be`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007589`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007359`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000736c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800073ea`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007453`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007481`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007909`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007359`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000736c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800073ea`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007453`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007481`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007909`

## string_xrefs

- `0x180007362`: `ForceRemove`
- `0x180007449`: `NoRemove`
- `0x18000734f`: `Delete`

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
0x1800072dc  push    rbp
0x1800072de  push    rbx
0x1800072df  push    rsi
0x1800072e0  push    rdi
0x1800072e1  push    r12
0x1800072e3  push    r13
0x1800072e5  push    r14
0x1800072e7  push    r15
0x1800072e9  lea     rbp, [rsp-21D8h]
0x1800072f1  mov     eax, 22D8h
0x1800072f6  call    _alloca_probe
0x1800072fb  sub     rsp, rax
0x1800072fe  mov     rax, cs:__security_cookie
0x180007305  xor     rax, rsp
0x180007308  mov     [rbp+2210h+var_50], rax
0x18000730f  mov     r12d, r9d
0x180007312  mov     [rsp+2310h+var_22A8], r9d
0x180007317  mov     r15, r8
0x18000731a  mov     [rsp+2310h+var_22A0], r8
0x18000731f  mov     rsi, rdx
0x180007322  mov     r13, rcx
0x180007325  xor     eax, eax
0x180007327  mov     ebx, eax
0x180007329  mov     [rbp+2210h+var_2290], rax
0x18000732d  mov     [rbp+2210h+var_2288], rax
0x180007331  mov     [rbp+2210h+var_2280], rax
0x180007335  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000733a  mov     edi, eax
0x18000733c  test    eax, eax
0x18000733e  jns     short loc_180007345
0x180007340  jmp     loc_1800079FC
0x180007345  cmp     word ptr [rsi], 7Dh ; '}'
0x180007349  jz      loc_1800079EC
0x18000734f  lea     rdx, String2; "Delete"
0x180007356  mov     rcx, rsi; lpString1
0x180007359  call    cs:__imp_lstrcmpiW
0x18000735f  mov     r14d, eax
0x180007362  lea     rdx, aForceremove; "ForceRemove"
0x180007369  mov     rcx, rsi; lpString1
0x18000736c  call    cs:__imp_lstrcmpiW
0x180007372  xor     edi, edi
0x180007374  test    eax, eax
0x180007376  jz      short loc_180007381
0x180007378  test    r14d, r14d
0x18000737b  jnz     loc_180007443
0x180007381  mov     rdx, rsi; unsigned __int16 *
0x180007384  mov     rcx, r13; this
0x180007387  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000738c  mov     edi, eax
0x18000738e  test    eax, eax
0x180007390  js      loc_1800079EC
0x180007396  xor     edi, edi
0x180007398  test    r12d, r12d
0x18000739b  jz      loc_180007443
0x1800073a1  mov     [rbp+2210h+var_2278], rdi
0x1800073a5  mov     [rbp+2210h+var_2270], rdi
0x1800073a9  mov     [rbp+2210h+var_2268], rdi
0x1800073ad  movzx   eax, word ptr [rsi]
0x1800073b0  test    ax, ax
0x1800073b3  jz      short loc_1800073DA
0x1800073b5  mov     rcx, rsi; lpsz
0x1800073b8  cmp     ax, 5Ch ; '\'
0x1800073bc  jz      short loc_1800073D1
0x1800073be  call    cs:__imp_CharNextW
0x1800073c4  mov     rcx, rax
0x1800073c7  movzx   eax, word ptr [rax]
0x1800073ca  test    ax, ax
0x1800073cd  jnz     short loc_1800073B8
0x1800073cf  jmp     short loc_1800073DA
0x1800073d1  test    rcx, rcx
0x1800073d4  jnz     loc_180007A38
0x1800073da  mov     edx, edi
0x1800073dc  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x1800073e3  mov     rdx, [rax+rdx*8]; lpString2
0x1800073e7  mov     rcx, rsi; lpString1
0x1800073ea  call    cs:__imp_lstrcmpiW
0x1800073f0  test    eax, eax
0x1800073f2  jz      short loc_18000740B
0x1800073f4  inc     edi
0x1800073f6  cmp     edi, 0Ch
0x1800073f9  jl      short loc_1800073DA
0x1800073fb  mov     [rbp+2210h+var_2278], r15
0x1800073ff  mov     rdx, rsi; unsigned __int16 *
0x180007402  lea     rcx, [rbp+2210h+var_2278]; this
0x180007406  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000740b  xor     edi, edi
0x18000740d  test    r14d, r14d
0x180007410  jnz     short loc_180007443
0x180007412  mov     rdx, rsi; unsigned __int16 *
0x180007415  mov     rcx, r13; this
0x180007418  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000741d  mov     edi, eax
0x18000741f  test    eax, eax
0x180007421  js      loc_1800079EC
0x180007427  mov     rdx, rsi; unsigned __int16 *
0x18000742a  mov     rcx, r13; this
0x18000742d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180007432  mov     edi, eax
0x180007434  xor     ecx, ecx
0x180007436  test    eax, eax
0x180007438  js      loc_1800079EC
0x18000743e  jmp     loc_1800076EA
0x180007443  mov     r12d, 1
0x180007449  lea     rdx, aNoremove; "NoRemove"
0x180007450  mov     rcx, rsi; lpString1
0x180007453  call    cs:__imp_lstrcmpiW
0x180007459  test    eax, eax
0x18000745b  jnz     short loc_180007477
0x18000745d  mov     r12d, edi
0x180007460  mov     rdx, rsi; unsigned __int16 *
0x180007463  mov     rcx, r13; this
0x180007466  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000746b  mov     edi, eax
0x18000746d  test    eax, eax
0x18000746f  js      loc_1800079EC
0x180007475  xor     edi, edi
0x180007477  lea     rdx, aVal; "Val"
0x18000747e  mov     rcx, rsi; lpString1
0x180007481  call    cs:__imp_lstrcmpiW
0x180007487  test    eax, eax
0x180007489  jnz     loc_180007578
0x18000748f  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180007496  mov     rcx, r13; this
0x180007499  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000749e  mov     edi, eax
0x1800074a0  test    eax, eax
0x1800074a2  js      loc_1800079EC
0x1800074a8  mov     rdx, rsi; unsigned __int16 *
0x1800074ab  mov     rcx, r13; this
0x1800074ae  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800074b3  mov     edi, eax
0x1800074b5  test    eax, eax
0x1800074b7  js      loc_1800079EC
0x1800074bd  cmp     word ptr [rsi], 3Dh ; '='
0x1800074c1  jnz     loc_180007A38
0x1800074c7  xor     edi, edi
0x1800074c9  cmp     [rsp+2310h+var_22A8], edi
0x1800074cd  jz      short loc_1800074F8
0x1800074cf  mov     [rbp+2210h+var_2270], rdi
0x1800074d3  mov     [rbp+2210h+var_2268], rdi
0x1800074d7  mov     [rbp+2210h+var_2278], r15
0x1800074db  mov     r9, rsi; unsigned __int16 *
0x1800074de  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x1800074e5  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x1800074e9  mov     rcx, r13; this
0x1800074ec  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800074f1  mov     edi, eax
0x1800074f3  jmp     loc_1800076DB
0x1800074f8  cmp     [rbp+2210h+arg_20], edi
0x1800074fe  jnz     short loc_18000755E
0x180007500  test    r12d, r12d
0x180007503  jz      short loc_18000755E
0x180007505  mov     [rsp+2310h+hKey], rdi
0x18000750a  lea     rax, [rsp+2310h+hKey]
0x18000750f  mov     [rsp+2310h+phkResult], rax; phkResult
0x180007514  mov     r9d, 20006h; samDesired
0x18000751a  xor     r8d, r8d; ulOptions
0x18000751d  xor     edx, edx; lpSubKey
0x18000751f  mov     rcx, r15; hKey
0x180007522  call    cs:__imp_RegOpenKeyExW
0x180007528  test    eax, eax
0x18000752a  jnz     loc_1800079E3
0x180007530  mov     r14, [rsp+2310h+hKey]
0x180007535  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18000753c  mov     rcx, r14; hKey
0x18000753f  call    cs:__imp_RegDeleteValueW
0x180007545  test    eax, 0FFFFFFFDh
0x18000754a  jnz     loc_180007A1F
0x180007550  test    r14, r14
0x180007553  jz      short loc_18000755E
0x180007555  mov     rcx, r14; hKey
0x180007558  call    cs:__imp_RegCloseKey
0x18000755e  mov     rdx, rsi; unsigned __int16 *
0x180007561  mov     rcx, r13; this
0x180007564  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180007569  mov     edi, eax
0x18000756b  test    eax, eax
0x18000756d  js      loc_1800079EC
0x180007573  jmp     loc_180007885
0x180007578  movzx   eax, word ptr [rsi]
0x18000757b  test    ax, ax
0x18000757e  jz      short loc_1800075A5
0x180007580  mov     rcx, rsi; lpsz
0x180007583  cmp     ax, 5Ch ; '\'
0x180007587  jz      short loc_18000759C
0x180007589  call    cs:__imp_CharNextW
0x18000758f  mov     rcx, rax
0x180007592  movzx   eax, word ptr [rax]
0x180007595  test    ax, ax
0x180007598  jnz     short loc_180007583
0x18000759a  jmp     short loc_1800075A5
0x18000759c  test    rcx, rcx
0x18000759f  jnz     loc_180007A38
0x1800075a5  cmp     [rsp+2310h+var_22A8], edi
0x1800075a9  jz      loc_18000773E
0x1800075af  mov     [rsp+2310h+hKey], rdi
0x1800075b4  lea     rax, [rsp+2310h+hKey]
0x1800075b9  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800075be  mov     r14d, 2001Fh
0x1800075c4  mov     r9d, r14d; samDesired
0x1800075c7  xor     r8d, r8d; ulOptions
0x1800075ca  mov     rdx, rsi; lpSubKey
0x1800075cd  mov     rcx, r15; hKey
0x1800075d0  call    cs:__imp_RegOpenKeyExW
0x1800075d6  test    eax, eax
0x1800075d8  jnz     short loc_1800075FB
0x1800075da  mov     eax, edi
0x1800075dc  test    rbx, rbx
0x1800075df  jz      short loc_1800075EA
0x1800075e1  mov     rcx, rbx; hKey
0x1800075e4  call    cs:__imp_RegCloseKey
0x1800075ea  mov     rbx, [rsp+2310h+hKey]
0x1800075ef  mov     [rbp+2210h+var_2290], rbx
0x1800075f3  test    eax, eax
0x1800075f5  jz      loc_1800076A6
0x1800075fb  mov     [rsp+2310h+hKey], rdi
0x180007600  lea     rax, [rsp+2310h+hKey]
0x180007605  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000760a  mov     r9d, 20019h; samDesired
0x180007610  xor     r8d, r8d; ulOptions
0x180007613  mov     rdx, rsi; lpSubKey
0x180007616  mov     rcx, r15; hKey
0x180007619  call    cs:__imp_RegOpenKeyExW
0x18000761f  test    eax, eax
0x180007621  jnz     short loc_180007640
0x180007623  mov     eax, edi
0x180007625  test    rbx, rbx
0x180007628  jz      short loc_180007633
0x18000762a  mov     rcx, rbx; hKey
0x18000762d  call    cs:__imp_RegCloseKey
0x180007633  mov     rbx, [rsp+2310h+hKey]
0x180007638  mov     [rbp+2210h+var_2290], rbx
0x18000763c  test    eax, eax
0x18000763e  jz      short loc_1800076A6
0x180007640  mov     dword ptr [rsp+2310h+hKey], edi
0x180007644  mov     [rsp+2310h+var_2298], rdi
0x180007649  lea     rax, [rsp+2310h+hKey]
0x18000764e  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180007653  lea     rax, [rsp+2310h+var_2298]
0x180007658  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18000765d  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180007662  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180007667  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x18000766b  xor     r9d, r9d; lpClass
0x18000766e  xor     r8d, r8d; Reserved
0x180007671  mov     rdx, rsi; lpSubKey
0x180007674  mov     rcx, r15; hKey
0x180007677  call    cs:__imp_RegCreateKeyExW
0x18000767d  test    eax, eax
0x18000767f  jnz     loc_1800079E3
0x180007685  mov     eax, edi
0x180007687  test    rbx, rbx
0x18000768a  jz      short loc_180007695
0x18000768c  mov     rcx, rbx; hKey
0x18000768f  call    cs:__imp_RegCloseKey
0x180007695  mov     rbx, [rsp+2310h+var_2298]
0x18000769a  mov     [rbp+2210h+var_2290], rbx
0x18000769e  test    eax, eax
0x1800076a0  jnz     loc_1800079E3
0x1800076a6  mov     rdx, rsi; unsigned __int16 *
0x1800076a9  mov     rcx, r13; this
0x1800076ac  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800076b1  mov     edi, eax
0x1800076b3  xor     ecx, ecx
0x1800076b5  test    eax, eax
0x1800076b7  js      loc_1800079EC
0x1800076bd  cmp     word ptr [rsi], 3Dh ; '='
0x1800076c1  jnz     short loc_1800076E5
0x1800076c3  mov     r9, rsi; unsigned __int16 *
0x1800076c6  xor     r8d, r8d; unsigned __int16 *
0x1800076c9  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x1800076cd  mov     rcx, r13; this
0x1800076d0  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800076d5  mov     edi, eax
0x1800076d7  mov     rbx, [rbp+2210h+var_2290]
0x1800076db  test    eax, eax
0x1800076dd  js      loc_1800079EC
0x1800076e3  xor     ecx, ecx
0x1800076e5  mov     r12d, [rsp+2310h+var_22A8]
0x1800076ea  cmp     word ptr [rsi], 7Bh ; '{'
0x1800076ee  jnz     loc_180007885
0x1800076f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800076f8  inc     rax
0x1800076fb  cmp     [rsi+rax*2], cx
0x1800076ff  jnz     short loc_1800076F8
0x180007701  cmp     rax, 1
0x180007705  jnz     loc_180007885
0x18000770b  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180007713  mov     r9d, r12d; int
0x180007716  mov     r8, rbx; HKEY
0x180007719  mov     rdx, rsi; unsigned __int16 *
0x18000771c  mov     rcx, r13; this
0x18000771f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007724  mov     edi, eax
0x180007726  test    eax, eax
0x180007728  js      loc_1800079EC
0x18000772e  mov     rdx, rsi; unsigned __int16 *
0x180007731  mov     rcx, r13; this
0x180007734  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007739  jmp     loc_180007569
  ... truncated ...
```
