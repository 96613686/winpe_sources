# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180015e40`
- end: `0x1800165d7`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180015acc`
- `0x180015e40`

## callees

- `0x180001800`
- `0x180003858`
- `0x180012a40`
- `0x180013218`
- `0x180014148`
- `0x180015400`
- `0x18001597c`
- `0x180015e40`
- `0x1800170d8`
- `0x180032a50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001631e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001631e`
- `ADVAPI32!RegDeleteValueW` at `0x1800160a3`
- `ADVAPI32!RegDeleteValueW` at `0x1800160a3`
- `ADVAPI32!RegCloseKey` at `0x1800160bc`
- `ADVAPI32!RegCloseKey` at `0x180016148`
- `ADVAPI32!RegCloseKey` at `0x180016191`
- `ADVAPI32!RegCloseKey` at `0x1800161f3`
- `ADVAPI32!RegCloseKey` at `0x1800162e7`
- `ADVAPI32!RegCloseKey` at `0x1800164fe`
- `ADVAPI32!RegCloseKey` at `0x180016558`
- `ADVAPI32!RegCloseKey` at `0x180016594`
- `ADVAPI32!RegCloseKey` at `0x1800165a4`
- `ADVAPI32!RegCloseKey` at `0x1800160bc`
- `ADVAPI32!RegCloseKey` at `0x180016148`
- `ADVAPI32!RegCloseKey` at `0x180016191`
- `ADVAPI32!RegCloseKey` at `0x1800161f3`
- `ADVAPI32!RegCloseKey` at `0x1800162e7`
- `ADVAPI32!RegCloseKey` at `0x1800164fe`
- `ADVAPI32!RegCloseKey` at `0x180016558`
- `ADVAPI32!RegCloseKey` at `0x180016594`
- `ADVAPI32!RegCloseKey` at `0x1800165a4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001644a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800164e0`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001644a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800164e0`
- `ADVAPI32!RegOpenKeyExW` at `0x180016086`
- `ADVAPI32!RegOpenKeyExW` at `0x180016134`
- `ADVAPI32!RegOpenKeyExW` at `0x18001617d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800162cc`
- `ADVAPI32!RegOpenKeyExW` at `0x180016086`
- `ADVAPI32!RegOpenKeyExW` at `0x180016134`
- `ADVAPI32!RegOpenKeyExW` at `0x18001617d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800162cc`
- `ADVAPI32!RegCreateKeyExW` at `0x1800161db`
- `ADVAPI32!RegCreateKeyExW` at `0x1800161db`
- `KERNEL32!lstrcmpiW` at `0x180015ebd`
- `KERNEL32!lstrcmpiW` at `0x180015ed0`
- `KERNEL32!lstrcmpiW` at `0x180015f4e`
- `KERNEL32!lstrcmpiW` at `0x180015fb7`
- `KERNEL32!lstrcmpiW` at `0x180015fe5`
- `KERNEL32!lstrcmpiW` at `0x18001646d`
- `KERNEL32!lstrcmpiW` at `0x180015ebd`
- `KERNEL32!lstrcmpiW` at `0x180015ed0`
- `KERNEL32!lstrcmpiW` at `0x180015f4e`
- `KERNEL32!lstrcmpiW` at `0x180015fb7`
- `KERNEL32!lstrcmpiW` at `0x180015fe5`
- `KERNEL32!lstrcmpiW` at `0x18001646d`
- `USER32!CharNextW` at `0x180015f22`
- `USER32!CharNextW` at `0x1800160ed`
- `USER32!CharNextW` at `0x180015f22`
- `USER32!CharNextW` at `0x1800160ed`

## string_xrefs

- `0x180015ec6`: `ForceRemove`
- `0x180015fad`: `NoRemove`
- `0x180015eb3`: `Delete`

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
  HRESULT v17; // eax
  DWORD v18; // eax
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
  HKEY v37[3]; // [rsp+80h] [rbp-80h] BYREF
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
        v17 = ATL::CRegParser::AddValue((LPCWSTR *)this, v37, 0, a2);
        Token = v17;
        v9 = v37[0];
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
                v9 = v37[0];
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
    v17 = ATL::CRegParser::AddValue((LPCWSTR *)this, &v38, ValueName, a2);
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
0x180015e40  push    rbp
0x180015e42  push    rbx
0x180015e43  push    rsi
0x180015e44  push    rdi
0x180015e45  push    r12
0x180015e47  push    r13
0x180015e49  push    r14
0x180015e4b  push    r15
0x180015e4d  lea     rbp, [rsp-21D8h]
0x180015e55  mov     eax, 22D8h
0x180015e5a  call    _alloca_probe
0x180015e5f  sub     rsp, rax
0x180015e62  mov     rax, cs:__security_cookie
0x180015e69  xor     rax, rsp
0x180015e6c  mov     [rbp+2210h+var_50], rax
0x180015e73  mov     r12d, r9d
0x180015e76  mov     [rsp+2310h+var_22A8], r9d
0x180015e7b  mov     r15, r8
0x180015e7e  mov     [rsp+2310h+var_22A0], r8
0x180015e83  mov     rsi, rdx
0x180015e86  mov     r13, rcx
0x180015e89  xor     eax, eax
0x180015e8b  mov     ebx, eax
0x180015e8d  mov     [rbp+2210h+var_2290], rax
0x180015e91  mov     [rbp+2210h+var_2288], rax
0x180015e95  mov     [rbp+2210h+var_2280], rax
0x180015e99  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180015e9e  mov     edi, eax
0x180015ea0  test    eax, eax
0x180015ea2  jns     short loc_180015EA9
0x180015ea4  jmp     loc_180016560
0x180015ea9  cmp     word ptr [rsi], 7Dh ; '}'
0x180015ead  jz      loc_180016550
0x180015eb3  lea     rdx, aDelete; "Delete"
0x180015eba  mov     rcx, rsi; lpString1
0x180015ebd  call    cs:__imp_lstrcmpiW
0x180015ec3  mov     r14d, eax
0x180015ec6  lea     rdx, aForceremove; "ForceRemove"
0x180015ecd  mov     rcx, rsi; lpString1
0x180015ed0  call    cs:__imp_lstrcmpiW
0x180015ed6  xor     edi, edi
0x180015ed8  test    eax, eax
0x180015eda  jz      short loc_180015EE5
0x180015edc  test    r14d, r14d
0x180015edf  jnz     loc_180015FA7
0x180015ee5  mov     rdx, rsi; unsigned __int16 *
0x180015ee8  mov     rcx, r13; this
0x180015eeb  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180015ef0  mov     edi, eax
0x180015ef2  test    eax, eax
0x180015ef4  js      loc_180016550
0x180015efa  xor     edi, edi
0x180015efc  test    r12d, r12d
0x180015eff  jz      loc_180015FA7
0x180015f05  mov     [rbp+2210h+var_2278], rdi
0x180015f09  mov     [rbp+2210h+var_2270], rdi
0x180015f0d  mov     [rbp+2210h+var_2268], rdi
0x180015f11  movzx   eax, word ptr [rsi]
0x180015f14  test    ax, ax
0x180015f17  jz      short loc_180015F3E
0x180015f19  mov     rcx, rsi; lpsz
0x180015f1c  cmp     ax, 5Ch ; '\'
0x180015f20  jz      short loc_180015F35
0x180015f22  call    cs:__imp_CharNextW
0x180015f28  mov     rcx, rax
0x180015f2b  movzx   eax, word ptr [rax]
0x180015f2e  test    ax, ax
0x180015f31  jnz     short loc_180015F1C
0x180015f33  jmp     short loc_180015F3E
0x180015f35  test    rcx, rcx
0x180015f38  jnz     loc_18001659C
0x180015f3e  mov     edx, edi
0x180015f40  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180015f47  mov     rdx, [rax+rdx*8]; lpString2
0x180015f4b  mov     rcx, rsi; lpString1
0x180015f4e  call    cs:__imp_lstrcmpiW
0x180015f54  test    eax, eax
0x180015f56  jz      short loc_180015F6F
0x180015f58  inc     edi
0x180015f5a  cmp     edi, 0Ch
0x180015f5d  jl      short loc_180015F3E
0x180015f5f  mov     [rbp+2210h+var_2278], r15
0x180015f63  mov     rdx, rsi; unsigned __int16 *
0x180015f66  lea     rcx, [rbp+2210h+var_2278]; this
0x180015f6a  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180015f6f  xor     edi, edi
0x180015f71  test    r14d, r14d
0x180015f74  jnz     short loc_180015FA7
0x180015f76  mov     rdx, rsi; unsigned __int16 *
0x180015f79  mov     rcx, r13; this
0x180015f7c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180015f81  mov     edi, eax
0x180015f83  test    eax, eax
0x180015f85  js      loc_180016550
0x180015f8b  mov     rdx, rsi; unsigned __int16 *
0x180015f8e  mov     rcx, r13; this
0x180015f91  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180015f96  mov     edi, eax
0x180015f98  xor     ecx, ecx
0x180015f9a  test    eax, eax
0x180015f9c  js      loc_180016550
0x180015fa2  jmp     loc_18001624E
0x180015fa7  mov     r12d, 1
0x180015fad  lea     rdx, aNoremove; "NoRemove"
0x180015fb4  mov     rcx, rsi; lpString1
0x180015fb7  call    cs:__imp_lstrcmpiW
0x180015fbd  test    eax, eax
0x180015fbf  jnz     short loc_180015FDB
0x180015fc1  mov     r12d, edi
0x180015fc4  mov     rdx, rsi; unsigned __int16 *
0x180015fc7  mov     rcx, r13; this
0x180015fca  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180015fcf  mov     edi, eax
0x180015fd1  test    eax, eax
0x180015fd3  js      loc_180016550
0x180015fd9  xor     edi, edi
0x180015fdb  lea     rdx, aVal; "Val"
0x180015fe2  mov     rcx, rsi; lpString1
0x180015fe5  call    cs:__imp_lstrcmpiW
0x180015feb  test    eax, eax
0x180015fed  jnz     loc_1800160DC
0x180015ff3  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180015ffa  mov     rcx, r13; this
0x180015ffd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180016002  mov     edi, eax
0x180016004  test    eax, eax
0x180016006  js      loc_180016550
0x18001600c  mov     rdx, rsi; unsigned __int16 *
0x18001600f  mov     rcx, r13; this
0x180016012  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180016017  mov     edi, eax
0x180016019  test    eax, eax
0x18001601b  js      loc_180016550
0x180016021  cmp     word ptr [rsi], 3Dh ; '='
0x180016025  jnz     loc_18001659C
0x18001602b  xor     edi, edi
0x18001602d  cmp     [rsp+2310h+var_22A8], edi
0x180016031  jz      short loc_18001605C
0x180016033  mov     [rbp+2210h+var_2270], rdi
0x180016037  mov     [rbp+2210h+var_2268], rdi
0x18001603b  mov     [rbp+2210h+var_2278], r15
0x18001603f  mov     r9, rsi; unsigned __int16 *
0x180016042  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180016049  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x18001604d  mov     rcx, r13; this
0x180016050  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180016055  mov     edi, eax
0x180016057  jmp     loc_18001623F
0x18001605c  cmp     [rbp+2210h+arg_20], edi
0x180016062  jnz     short loc_1800160C2
0x180016064  test    r12d, r12d
0x180016067  jz      short loc_1800160C2
0x180016069  mov     [rsp+2310h+hKey], rdi
0x18001606e  lea     rax, [rsp+2310h+hKey]
0x180016073  mov     [rsp+2310h+phkResult], rax; phkResult
0x180016078  mov     r9d, 20006h; samDesired
0x18001607e  xor     r8d, r8d; ulOptions
0x180016081  xor     edx, edx; lpSubKey
0x180016083  mov     rcx, r15; hKey
0x180016086  call    cs:__imp_RegOpenKeyExW
0x18001608c  test    eax, eax
0x18001608e  jnz     loc_180016547
0x180016094  mov     r14, [rsp+2310h+hKey]
0x180016099  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x1800160a0  mov     rcx, r14; hKey
0x1800160a3  call    cs:__imp_RegDeleteValueW
0x1800160a9  test    eax, 0FFFFFFFDh
0x1800160ae  jnz     loc_180016583
0x1800160b4  test    r14, r14
0x1800160b7  jz      short loc_1800160C2
0x1800160b9  mov     rcx, r14; hKey
0x1800160bc  call    cs:__imp_RegCloseKey
0x1800160c2  mov     rdx, rsi; unsigned __int16 *
0x1800160c5  mov     rcx, r13; this
0x1800160c8  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800160cd  mov     edi, eax
0x1800160cf  test    eax, eax
0x1800160d1  js      loc_180016550
0x1800160d7  jmp     loc_1800163E9
0x1800160dc  movzx   eax, word ptr [rsi]
0x1800160df  test    ax, ax
0x1800160e2  jz      short loc_180016109
0x1800160e4  mov     rcx, rsi; lpsz
0x1800160e7  cmp     ax, 5Ch ; '\'
0x1800160eb  jz      short loc_180016100
0x1800160ed  call    cs:__imp_CharNextW
0x1800160f3  mov     rcx, rax
0x1800160f6  movzx   eax, word ptr [rax]
0x1800160f9  test    ax, ax
0x1800160fc  jnz     short loc_1800160E7
0x1800160fe  jmp     short loc_180016109
0x180016100  test    rcx, rcx
0x180016103  jnz     loc_18001659C
0x180016109  cmp     [rsp+2310h+var_22A8], edi
0x18001610d  jz      loc_1800162A2
0x180016113  mov     [rsp+2310h+hKey], rdi
0x180016118  lea     rax, [rsp+2310h+hKey]
0x18001611d  mov     [rsp+2310h+phkResult], rax; phkResult
0x180016122  mov     r14d, 2001Fh
0x180016128  mov     r9d, r14d; samDesired
0x18001612b  xor     r8d, r8d; ulOptions
0x18001612e  mov     rdx, rsi; lpSubKey
0x180016131  mov     rcx, r15; hKey
0x180016134  call    cs:__imp_RegOpenKeyExW
0x18001613a  test    eax, eax
0x18001613c  jnz     short loc_18001615F
0x18001613e  mov     eax, edi
0x180016140  test    rbx, rbx
0x180016143  jz      short loc_18001614E
0x180016145  mov     rcx, rbx; hKey
0x180016148  call    cs:__imp_RegCloseKey
0x18001614e  mov     rbx, [rsp+2310h+hKey]
0x180016153  mov     [rbp+2210h+var_2290], rbx
0x180016157  test    eax, eax
0x180016159  jz      loc_18001620A
0x18001615f  mov     [rsp+2310h+hKey], rdi
0x180016164  lea     rax, [rsp+2310h+hKey]
0x180016169  mov     [rsp+2310h+phkResult], rax; phkResult
0x18001616e  mov     r9d, 20019h; samDesired
0x180016174  xor     r8d, r8d; ulOptions
0x180016177  mov     rdx, rsi; lpSubKey
0x18001617a  mov     rcx, r15; hKey
0x18001617d  call    cs:__imp_RegOpenKeyExW
0x180016183  test    eax, eax
0x180016185  jnz     short loc_1800161A4
0x180016187  mov     eax, edi
0x180016189  test    rbx, rbx
0x18001618c  jz      short loc_180016197
0x18001618e  mov     rcx, rbx; hKey
0x180016191  call    cs:__imp_RegCloseKey
0x180016197  mov     rbx, [rsp+2310h+hKey]
0x18001619c  mov     [rbp+2210h+var_2290], rbx
0x1800161a0  test    eax, eax
0x1800161a2  jz      short loc_18001620A
0x1800161a4  mov     dword ptr [rsp+2310h+hKey], edi
0x1800161a8  mov     [rsp+2310h+var_2298], rdi
0x1800161ad  lea     rax, [rsp+2310h+hKey]
0x1800161b2  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x1800161b7  lea     rax, [rsp+2310h+var_2298]
0x1800161bc  mov     [rsp+2310h+var_22D8], rax; phkResult
0x1800161c1  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800161c6  mov     [rsp+2310h+samDesired], r14d; samDesired
0x1800161cb  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x1800161cf  xor     r9d, r9d; lpClass
0x1800161d2  xor     r8d, r8d; Reserved
0x1800161d5  mov     rdx, rsi; lpSubKey
0x1800161d8  mov     rcx, r15; hKey
0x1800161db  call    cs:__imp_RegCreateKeyExW
0x1800161e1  test    eax, eax
0x1800161e3  jnz     loc_180016547
0x1800161e9  mov     eax, edi
0x1800161eb  test    rbx, rbx
0x1800161ee  jz      short loc_1800161F9
0x1800161f0  mov     rcx, rbx; hKey
0x1800161f3  call    cs:__imp_RegCloseKey
0x1800161f9  mov     rbx, [rsp+2310h+var_2298]
0x1800161fe  mov     [rbp+2210h+var_2290], rbx
0x180016202  test    eax, eax
0x180016204  jnz     loc_180016547
0x18001620a  mov     rdx, rsi; unsigned __int16 *
0x18001620d  mov     rcx, r13; this
0x180016210  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180016215  mov     edi, eax
0x180016217  xor     ecx, ecx
0x180016219  test    eax, eax
0x18001621b  js      loc_180016550
0x180016221  cmp     word ptr [rsi], 3Dh ; '='
0x180016225  jnz     short loc_180016249
0x180016227  mov     r9, rsi; unsigned __int16 *
0x18001622a  xor     r8d, r8d; unsigned __int16 *
0x18001622d  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180016231  mov     rcx, r13; this
0x180016234  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180016239  mov     edi, eax
0x18001623b  mov     rbx, [rbp+2210h+var_2290]
0x18001623f  test    eax, eax
0x180016241  js      loc_180016550
0x180016247  xor     ecx, ecx
0x180016249  mov     r12d, [rsp+2310h+var_22A8]
0x18001624e  cmp     word ptr [rsi], 7Bh ; '{'
0x180016252  jnz     loc_1800163E9
0x180016258  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001625c  inc     rax
0x18001625f  cmp     [rsi+rax*2], cx
0x180016263  jnz     short loc_18001625C
0x180016265  cmp     rax, 1
0x180016269  jnz     loc_1800163E9
0x18001626f  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180016277  mov     r9d, r12d; int
0x18001627a  mov     r8, rbx; HKEY
0x18001627d  mov     rdx, rsi; unsigned __int16 *
0x180016280  mov     rcx, r13; this
0x180016283  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180016288  mov     edi, eax
0x18001628a  test    eax, eax
0x18001628c  js      loc_180016550
0x180016292  mov     rdx, rsi; unsigned __int16 *
0x180016295  mov     rcx, r13; this
0x180016298  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001629d  jmp     loc_1800160CD
  ... truncated ...
```
