# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18002140c`
- end: `0x180021ba3`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180021098`
- `0x18002140c`

## callees

- `0x1800018f0`
- `0x18001afd0`
- `0x18001f49c`
- `0x18001fc98`
- `0x180020178`
- `0x180020698`
- `0x180020980`
- `0x180020f48`
- `0x18002140c`
- `0x180021de8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800218ea`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800218ea`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002166f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002166f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800217a7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800217a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021688`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021714`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002175d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800217bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800218b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021aca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021b24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021b60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021b70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021688`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021714`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002175d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800217bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800218b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021aca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021b24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021b60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021b70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021652`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021700`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021749`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021898`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021652`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021700`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021749`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021898`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180021a16`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180021aac`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180021a16`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180021aac`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800214ee`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800216b9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800214ee`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800216b9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180021489`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002149c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002151a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180021583`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800215b1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180021a39`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180021489`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002149c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002151a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180021583`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800215b1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180021a39`

## string_xrefs

- `0x180021492`: `ForceRemove`
- `0x180021579`: `NoRemove`
- `0x18002147f`: `Delete`

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
0x18002140c  push    rbp
0x18002140e  push    rbx
0x18002140f  push    rsi
0x180021410  push    rdi
0x180021411  push    r12
0x180021413  push    r13
0x180021415  push    r14
0x180021417  push    r15
0x180021419  lea     rbp, [rsp-21D8h]
0x180021421  mov     eax, 22D8h
0x180021426  call    _alloca_probe
0x18002142b  sub     rsp, rax
0x18002142e  mov     rax, cs:__security_cookie
0x180021435  xor     rax, rsp
0x180021438  mov     [rbp+2210h+var_50], rax
0x18002143f  mov     r12d, r9d
0x180021442  mov     [rsp+2310h+var_22A8], r9d
0x180021447  mov     r15, r8
0x18002144a  mov     [rsp+2310h+var_22A0], r8
0x18002144f  mov     rsi, rdx
0x180021452  mov     r13, rcx
0x180021455  xor     eax, eax
0x180021457  mov     ebx, eax
0x180021459  mov     [rbp+2210h+var_2290], rax
0x18002145d  mov     [rbp+2210h+var_2288], rax
0x180021461  mov     [rbp+2210h+var_2280], rax
0x180021465  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002146a  mov     edi, eax
0x18002146c  test    eax, eax
0x18002146e  jns     short loc_180021475
0x180021470  jmp     loc_180021B2C
0x180021475  cmp     word ptr [rsi], 7Dh ; '}'
0x180021479  jz      loc_180021B1C
0x18002147f  lea     rdx, String2; "Delete"
0x180021486  mov     rcx, rsi; lpString1
0x180021489  call    cs:__imp_lstrcmpiW
0x18002148f  mov     r14d, eax
0x180021492  lea     rdx, aForceremove; "ForceRemove"
0x180021499  mov     rcx, rsi; lpString1
0x18002149c  call    cs:__imp_lstrcmpiW
0x1800214a2  xor     edi, edi
0x1800214a4  test    eax, eax
0x1800214a6  jz      short loc_1800214B1
0x1800214a8  test    r14d, r14d
0x1800214ab  jnz     loc_180021573
0x1800214b1  mov     rdx, rsi; unsigned __int16 *
0x1800214b4  mov     rcx, r13; this
0x1800214b7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800214bc  mov     edi, eax
0x1800214be  test    eax, eax
0x1800214c0  js      loc_180021B1C
0x1800214c6  xor     edi, edi
0x1800214c8  test    r12d, r12d
0x1800214cb  jz      loc_180021573
0x1800214d1  mov     [rbp+2210h+var_2278], rdi
0x1800214d5  mov     [rbp+2210h+var_2270], rdi
0x1800214d9  mov     [rbp+2210h+var_2268], rdi
0x1800214dd  movzx   eax, word ptr [rsi]
0x1800214e0  test    ax, ax
0x1800214e3  jz      short loc_18002150A
0x1800214e5  mov     rcx, rsi; lpsz
0x1800214e8  cmp     ax, 5Ch ; '\'
0x1800214ec  jz      short loc_180021501
0x1800214ee  call    cs:__imp_CharNextW
0x1800214f4  mov     rcx, rax
0x1800214f7  movzx   eax, word ptr [rax]
0x1800214fa  test    ax, ax
0x1800214fd  jnz     short loc_1800214E8
0x1800214ff  jmp     short loc_18002150A
0x180021501  test    rcx, rcx
0x180021504  jnz     loc_180021B68
0x18002150a  mov     edx, edi
0x18002150c  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180021513  mov     rdx, [rax+rdx*8]; lpString2
0x180021517  mov     rcx, rsi; lpString1
0x18002151a  call    cs:__imp_lstrcmpiW
0x180021520  test    eax, eax
0x180021522  jz      short loc_18002153B
0x180021524  inc     edi
0x180021526  cmp     edi, 0Ch
0x180021529  jl      short loc_18002150A
0x18002152b  mov     [rbp+2210h+var_2278], r15
0x18002152f  mov     rdx, rsi; unsigned __int16 *
0x180021532  lea     rcx, [rbp+2210h+var_2278]; this
0x180021536  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18002153b  xor     edi, edi
0x18002153d  test    r14d, r14d
0x180021540  jnz     short loc_180021573
0x180021542  mov     rdx, rsi; unsigned __int16 *
0x180021545  mov     rcx, r13; this
0x180021548  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002154d  mov     edi, eax
0x18002154f  test    eax, eax
0x180021551  js      loc_180021B1C
0x180021557  mov     rdx, rsi; unsigned __int16 *
0x18002155a  mov     rcx, r13; this
0x18002155d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180021562  mov     edi, eax
0x180021564  xor     ecx, ecx
0x180021566  test    eax, eax
0x180021568  js      loc_180021B1C
0x18002156e  jmp     loc_18002181A
0x180021573  mov     r12d, 1
0x180021579  lea     rdx, aNoremove; "NoRemove"
0x180021580  mov     rcx, rsi; lpString1
0x180021583  call    cs:__imp_lstrcmpiW
0x180021589  test    eax, eax
0x18002158b  jnz     short loc_1800215A7
0x18002158d  mov     r12d, edi
0x180021590  mov     rdx, rsi; unsigned __int16 *
0x180021593  mov     rcx, r13; this
0x180021596  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002159b  mov     edi, eax
0x18002159d  test    eax, eax
0x18002159f  js      loc_180021B1C
0x1800215a5  xor     edi, edi
0x1800215a7  lea     rdx, aVal; "Val"
0x1800215ae  mov     rcx, rsi; lpString1
0x1800215b1  call    cs:__imp_lstrcmpiW
0x1800215b7  test    eax, eax
0x1800215b9  jnz     loc_1800216A8
0x1800215bf  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x1800215c6  mov     rcx, r13; this
0x1800215c9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800215ce  mov     edi, eax
0x1800215d0  test    eax, eax
0x1800215d2  js      loc_180021B1C
0x1800215d8  mov     rdx, rsi; unsigned __int16 *
0x1800215db  mov     rcx, r13; this
0x1800215de  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800215e3  mov     edi, eax
0x1800215e5  test    eax, eax
0x1800215e7  js      loc_180021B1C
0x1800215ed  cmp     word ptr [rsi], 3Dh ; '='
0x1800215f1  jnz     loc_180021B68
0x1800215f7  xor     edi, edi
0x1800215f9  cmp     [rsp+2310h+var_22A8], edi
0x1800215fd  jz      short loc_180021628
0x1800215ff  mov     [rbp+2210h+var_2270], rdi
0x180021603  mov     [rbp+2210h+var_2268], rdi
0x180021607  mov     [rbp+2210h+var_2278], r15
0x18002160b  mov     r9, rsi; unsigned __int16 *
0x18002160e  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180021615  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180021619  mov     rcx, r13; this
0x18002161c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180021621  mov     edi, eax
0x180021623  jmp     loc_18002180B
0x180021628  cmp     [rbp+2210h+arg_20], edi
0x18002162e  jnz     short loc_18002168E
0x180021630  test    r12d, r12d
0x180021633  jz      short loc_18002168E
0x180021635  mov     [rsp+2310h+hKey], rdi
0x18002163a  lea     rax, [rsp+2310h+hKey]
0x18002163f  mov     [rsp+2310h+phkResult], rax; phkResult
0x180021644  mov     r9d, 20006h; samDesired
0x18002164a  xor     r8d, r8d; ulOptions
0x18002164d  xor     edx, edx; lpSubKey
0x18002164f  mov     rcx, r15; hKey
0x180021652  call    cs:__imp_RegOpenKeyExW
0x180021658  test    eax, eax
0x18002165a  jnz     loc_180021B13
0x180021660  mov     r14, [rsp+2310h+hKey]
0x180021665  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18002166c  mov     rcx, r14; hKey
0x18002166f  call    cs:__imp_RegDeleteValueW
0x180021675  test    eax, 0FFFFFFFDh
0x18002167a  jnz     loc_180021B4F
0x180021680  test    r14, r14
0x180021683  jz      short loc_18002168E
0x180021685  mov     rcx, r14; hKey
0x180021688  call    cs:__imp_RegCloseKey
0x18002168e  mov     rdx, rsi; unsigned __int16 *
0x180021691  mov     rcx, r13; this
0x180021694  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180021699  mov     edi, eax
0x18002169b  test    eax, eax
0x18002169d  js      loc_180021B1C
0x1800216a3  jmp     loc_1800219B5
0x1800216a8  movzx   eax, word ptr [rsi]
0x1800216ab  test    ax, ax
0x1800216ae  jz      short loc_1800216D5
0x1800216b0  mov     rcx, rsi; lpsz
0x1800216b3  cmp     ax, 5Ch ; '\'
0x1800216b7  jz      short loc_1800216CC
0x1800216b9  call    cs:__imp_CharNextW
0x1800216bf  mov     rcx, rax
0x1800216c2  movzx   eax, word ptr [rax]
0x1800216c5  test    ax, ax
0x1800216c8  jnz     short loc_1800216B3
0x1800216ca  jmp     short loc_1800216D5
0x1800216cc  test    rcx, rcx
0x1800216cf  jnz     loc_180021B68
0x1800216d5  cmp     [rsp+2310h+var_22A8], edi
0x1800216d9  jz      loc_18002186E
0x1800216df  mov     [rsp+2310h+hKey], rdi
0x1800216e4  lea     rax, [rsp+2310h+hKey]
0x1800216e9  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800216ee  mov     r14d, 2001Fh
0x1800216f4  mov     r9d, r14d; samDesired
0x1800216f7  xor     r8d, r8d; ulOptions
0x1800216fa  mov     rdx, rsi; lpSubKey
0x1800216fd  mov     rcx, r15; hKey
0x180021700  call    cs:__imp_RegOpenKeyExW
0x180021706  test    eax, eax
0x180021708  jnz     short loc_18002172B
0x18002170a  mov     eax, edi
0x18002170c  test    rbx, rbx
0x18002170f  jz      short loc_18002171A
0x180021711  mov     rcx, rbx; hKey
0x180021714  call    cs:__imp_RegCloseKey
0x18002171a  mov     rbx, [rsp+2310h+hKey]
0x18002171f  mov     [rbp+2210h+var_2290], rbx
0x180021723  test    eax, eax
0x180021725  jz      loc_1800217D6
0x18002172b  mov     [rsp+2310h+hKey], rdi
0x180021730  lea     rax, [rsp+2310h+hKey]
0x180021735  mov     [rsp+2310h+phkResult], rax; phkResult
0x18002173a  mov     r9d, 20019h; samDesired
0x180021740  xor     r8d, r8d; ulOptions
0x180021743  mov     rdx, rsi; lpSubKey
0x180021746  mov     rcx, r15; hKey
0x180021749  call    cs:__imp_RegOpenKeyExW
0x18002174f  test    eax, eax
0x180021751  jnz     short loc_180021770
0x180021753  mov     eax, edi
0x180021755  test    rbx, rbx
0x180021758  jz      short loc_180021763
0x18002175a  mov     rcx, rbx; hKey
0x18002175d  call    cs:__imp_RegCloseKey
0x180021763  mov     rbx, [rsp+2310h+hKey]
0x180021768  mov     [rbp+2210h+var_2290], rbx
0x18002176c  test    eax, eax
0x18002176e  jz      short loc_1800217D6
0x180021770  mov     dword ptr [rsp+2310h+hKey], edi
0x180021774  mov     [rsp+2310h+var_2298], rdi
0x180021779  lea     rax, [rsp+2310h+hKey]
0x18002177e  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180021783  lea     rax, [rsp+2310h+var_2298]
0x180021788  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18002178d  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180021792  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180021797  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x18002179b  xor     r9d, r9d; lpClass
0x18002179e  xor     r8d, r8d; Reserved
0x1800217a1  mov     rdx, rsi; lpSubKey
0x1800217a4  mov     rcx, r15; hKey
0x1800217a7  call    cs:__imp_RegCreateKeyExW
0x1800217ad  test    eax, eax
0x1800217af  jnz     loc_180021B13
0x1800217b5  mov     eax, edi
0x1800217b7  test    rbx, rbx
0x1800217ba  jz      short loc_1800217C5
0x1800217bc  mov     rcx, rbx; hKey
0x1800217bf  call    cs:__imp_RegCloseKey
0x1800217c5  mov     rbx, [rsp+2310h+var_2298]
0x1800217ca  mov     [rbp+2210h+var_2290], rbx
0x1800217ce  test    eax, eax
0x1800217d0  jnz     loc_180021B13
0x1800217d6  mov     rdx, rsi; unsigned __int16 *
0x1800217d9  mov     rcx, r13; this
0x1800217dc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800217e1  mov     edi, eax
0x1800217e3  xor     ecx, ecx
0x1800217e5  test    eax, eax
0x1800217e7  js      loc_180021B1C
0x1800217ed  cmp     word ptr [rsi], 3Dh ; '='
0x1800217f1  jnz     short loc_180021815
0x1800217f3  mov     r9, rsi; unsigned __int16 *
0x1800217f6  xor     r8d, r8d; unsigned __int16 *
0x1800217f9  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x1800217fd  mov     rcx, r13; this
0x180021800  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180021805  mov     edi, eax
0x180021807  mov     rbx, [rbp+2210h+var_2290]
0x18002180b  test    eax, eax
0x18002180d  js      loc_180021B1C
0x180021813  xor     ecx, ecx
0x180021815  mov     r12d, [rsp+2310h+var_22A8]
0x18002181a  cmp     word ptr [rsi], 7Bh ; '{'
0x18002181e  jnz     loc_1800219B5
0x180021824  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021828  inc     rax
0x18002182b  cmp     [rsi+rax*2], cx
0x18002182f  jnz     short loc_180021828
0x180021831  cmp     rax, 1
0x180021835  jnz     loc_1800219B5
0x18002183b  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180021843  mov     r9d, r12d; int
0x180021846  mov     r8, rbx; HKEY
0x180021849  mov     rdx, rsi; unsigned __int16 *
0x18002184c  mov     rcx, r13; this
0x18002184f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180021854  mov     edi, eax
0x180021856  test    eax, eax
0x180021858  js      loc_180021B1C
0x18002185e  mov     rdx, rsi; unsigned __int16 *
0x180021861  mov     rcx, r13; this
0x180021864  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180021869  jmp     loc_180021699
  ... truncated ...
```
