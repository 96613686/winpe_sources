# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180006b7c`
- end: `0x180007313`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18000680c`
- `0x180006b7c`

## callees

- `0x180001e60`
- `0x180004020`
- `0x180004750`
- `0x180004768`
- `0x180004e80`
- `0x18000604c`
- `0x1800066bc`
- `0x180006b7c`
- `0x180007f90`
- `0x18000b390`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000705a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000705a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006f17`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006f17`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180006ddf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180006ddf`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180007186`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000721c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180007186`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000721c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006df8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006e84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ecd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007023`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000723a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007294`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800072d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800072e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006df8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006e84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ecd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007023`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000723a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007294`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800072d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800072e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006dc2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006e70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006eb9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007008`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006dc2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006e70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006eb9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007008`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006c5e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006e29`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006c5e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006e29`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006bf9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006c0c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006c8a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006cf3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006d21`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800071a9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006bf9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006c0c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006c8a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006cf3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006d21`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800071a9`

## string_xrefs

- `0x180006c02`: `ForceRemove`
- `0x180006ce9`: `NoRemove`
- `0x180006bef`: `Delete`

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
0x180006b7c  push    rbp
0x180006b7e  push    rbx
0x180006b7f  push    rsi
0x180006b80  push    rdi
0x180006b81  push    r12
0x180006b83  push    r13
0x180006b85  push    r14
0x180006b87  push    r15
0x180006b89  lea     rbp, [rsp-21D8h]
0x180006b91  mov     eax, 22D8h
0x180006b96  call    _alloca_probe
0x180006b9b  sub     rsp, rax
0x180006b9e  mov     rax, cs:__security_cookie
0x180006ba5  xor     rax, rsp
0x180006ba8  mov     [rbp+2210h+var_50], rax
0x180006baf  mov     r12d, r9d
0x180006bb2  mov     [rsp+2310h+var_22A8], r9d
0x180006bb7  mov     r15, r8
0x180006bba  mov     [rsp+2310h+var_22A0], r8
0x180006bbf  mov     rsi, rdx
0x180006bc2  mov     r13, rcx
0x180006bc5  xor     eax, eax
0x180006bc7  mov     ebx, eax
0x180006bc9  mov     [rbp+2210h+var_2290], rax
0x180006bcd  mov     [rbp+2210h+var_2288], rax
0x180006bd1  mov     [rbp+2210h+var_2280], rax
0x180006bd5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006bda  mov     edi, eax
0x180006bdc  test    eax, eax
0x180006bde  jns     short loc_180006BE5
0x180006be0  jmp     loc_18000729C
0x180006be5  cmp     word ptr [rsi], 7Dh ; '}'
0x180006be9  jz      loc_18000728C
0x180006bef  lea     rdx, String2; "Delete"
0x180006bf6  mov     rcx, rsi; lpString1
0x180006bf9  call    cs:__imp_lstrcmpiW
0x180006bff  mov     r14d, eax
0x180006c02  lea     rdx, aForceremove; "ForceRemove"
0x180006c09  mov     rcx, rsi; lpString1
0x180006c0c  call    cs:__imp_lstrcmpiW
0x180006c12  xor     edi, edi
0x180006c14  test    eax, eax
0x180006c16  jz      short loc_180006C21
0x180006c18  test    r14d, r14d
0x180006c1b  jnz     loc_180006CE3
0x180006c21  mov     rdx, rsi; unsigned __int16 *
0x180006c24  mov     rcx, r13; this
0x180006c27  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006c2c  mov     edi, eax
0x180006c2e  test    eax, eax
0x180006c30  js      loc_18000728C
0x180006c36  xor     edi, edi
0x180006c38  test    r12d, r12d
0x180006c3b  jz      loc_180006CE3
0x180006c41  mov     [rbp+2210h+var_2278], rdi
0x180006c45  mov     [rbp+2210h+var_2270], rdi
0x180006c49  mov     [rbp+2210h+var_2268], rdi
0x180006c4d  movzx   eax, word ptr [rsi]
0x180006c50  test    ax, ax
0x180006c53  jz      short loc_180006C7A
0x180006c55  mov     rcx, rsi; lpsz
0x180006c58  cmp     ax, 5Ch ; '\'
0x180006c5c  jz      short loc_180006C71
0x180006c5e  call    cs:__imp_CharNextW
0x180006c64  mov     rcx, rax
0x180006c67  movzx   eax, word ptr [rax]
0x180006c6a  test    ax, ax
0x180006c6d  jnz     short loc_180006C58
0x180006c6f  jmp     short loc_180006C7A
0x180006c71  test    rcx, rcx
0x180006c74  jnz     loc_1800072D8
0x180006c7a  mov     edx, edi
0x180006c7c  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180006c83  mov     rdx, [rax+rdx*8]; lpString2
0x180006c87  mov     rcx, rsi; lpString1
0x180006c8a  call    cs:__imp_lstrcmpiW
0x180006c90  test    eax, eax
0x180006c92  jz      short loc_180006CAB
0x180006c94  inc     edi
0x180006c96  cmp     edi, 0Ch
0x180006c99  jl      short loc_180006C7A
0x180006c9b  mov     [rbp+2210h+var_2278], r15
0x180006c9f  mov     rdx, rsi; unsigned __int16 *
0x180006ca2  lea     rcx, [rbp+2210h+var_2278]; this
0x180006ca6  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180006cab  xor     edi, edi
0x180006cad  test    r14d, r14d
0x180006cb0  jnz     short loc_180006CE3
0x180006cb2  mov     rdx, rsi; unsigned __int16 *
0x180006cb5  mov     rcx, r13; this
0x180006cb8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006cbd  mov     edi, eax
0x180006cbf  test    eax, eax
0x180006cc1  js      loc_18000728C
0x180006cc7  mov     rdx, rsi; unsigned __int16 *
0x180006cca  mov     rcx, r13; this
0x180006ccd  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180006cd2  mov     edi, eax
0x180006cd4  xor     ecx, ecx
0x180006cd6  test    eax, eax
0x180006cd8  js      loc_18000728C
0x180006cde  jmp     loc_180006F8A
0x180006ce3  mov     r12d, 1
0x180006ce9  lea     rdx, aNoremove; "NoRemove"
0x180006cf0  mov     rcx, rsi; lpString1
0x180006cf3  call    cs:__imp_lstrcmpiW
0x180006cf9  test    eax, eax
0x180006cfb  jnz     short loc_180006D17
0x180006cfd  mov     r12d, edi
0x180006d00  mov     rdx, rsi; unsigned __int16 *
0x180006d03  mov     rcx, r13; this
0x180006d06  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006d0b  mov     edi, eax
0x180006d0d  test    eax, eax
0x180006d0f  js      loc_18000728C
0x180006d15  xor     edi, edi
0x180006d17  lea     rdx, aVal; "Val"
0x180006d1e  mov     rcx, rsi; lpString1
0x180006d21  call    cs:__imp_lstrcmpiW
0x180006d27  test    eax, eax
0x180006d29  jnz     loc_180006E18
0x180006d2f  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180006d36  mov     rcx, r13; this
0x180006d39  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006d3e  mov     edi, eax
0x180006d40  test    eax, eax
0x180006d42  js      loc_18000728C
0x180006d48  mov     rdx, rsi; unsigned __int16 *
0x180006d4b  mov     rcx, r13; this
0x180006d4e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006d53  mov     edi, eax
0x180006d55  test    eax, eax
0x180006d57  js      loc_18000728C
0x180006d5d  cmp     word ptr [rsi], 3Dh ; '='
0x180006d61  jnz     loc_1800072D8
0x180006d67  xor     edi, edi
0x180006d69  cmp     [rsp+2310h+var_22A8], edi
0x180006d6d  jz      short loc_180006D98
0x180006d6f  mov     [rbp+2210h+var_2270], rdi
0x180006d73  mov     [rbp+2210h+var_2268], rdi
0x180006d77  mov     [rbp+2210h+var_2278], r15
0x180006d7b  mov     r9, rsi; unsigned __int16 *
0x180006d7e  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180006d85  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180006d89  mov     rcx, r13; this
0x180006d8c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180006d91  mov     edi, eax
0x180006d93  jmp     loc_180006F7B
0x180006d98  cmp     [rbp+2210h+arg_20], edi
0x180006d9e  jnz     short loc_180006DFE
0x180006da0  test    r12d, r12d
0x180006da3  jz      short loc_180006DFE
0x180006da5  mov     [rsp+2310h+hKey], rdi
0x180006daa  lea     rax, [rsp+2310h+hKey]
0x180006daf  mov     [rsp+2310h+phkResult], rax; phkResult
0x180006db4  mov     r9d, 20006h; samDesired
0x180006dba  xor     r8d, r8d; ulOptions
0x180006dbd  xor     edx, edx; lpSubKey
0x180006dbf  mov     rcx, r15; hKey
0x180006dc2  call    cs:__imp_RegOpenKeyExW
0x180006dc8  test    eax, eax
0x180006dca  jnz     loc_180007283
0x180006dd0  mov     r14, [rsp+2310h+hKey]
0x180006dd5  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180006ddc  mov     rcx, r14; hKey
0x180006ddf  call    cs:__imp_RegDeleteValueW
0x180006de5  test    eax, 0FFFFFFFDh
0x180006dea  jnz     loc_1800072BF
0x180006df0  test    r14, r14
0x180006df3  jz      short loc_180006DFE
0x180006df5  mov     rcx, r14; hKey
0x180006df8  call    cs:__imp_RegCloseKey
0x180006dfe  mov     rdx, rsi; unsigned __int16 *
0x180006e01  mov     rcx, r13; this
0x180006e04  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180006e09  mov     edi, eax
0x180006e0b  test    eax, eax
0x180006e0d  js      loc_18000728C
0x180006e13  jmp     loc_180007125
0x180006e18  movzx   eax, word ptr [rsi]
0x180006e1b  test    ax, ax
0x180006e1e  jz      short loc_180006E45
0x180006e20  mov     rcx, rsi; lpsz
0x180006e23  cmp     ax, 5Ch ; '\'
0x180006e27  jz      short loc_180006E3C
0x180006e29  call    cs:__imp_CharNextW
0x180006e2f  mov     rcx, rax
0x180006e32  movzx   eax, word ptr [rax]
0x180006e35  test    ax, ax
0x180006e38  jnz     short loc_180006E23
0x180006e3a  jmp     short loc_180006E45
0x180006e3c  test    rcx, rcx
0x180006e3f  jnz     loc_1800072D8
0x180006e45  cmp     [rsp+2310h+var_22A8], edi
0x180006e49  jz      loc_180006FDE
0x180006e4f  mov     [rsp+2310h+hKey], rdi
0x180006e54  lea     rax, [rsp+2310h+hKey]
0x180006e59  mov     [rsp+2310h+phkResult], rax; phkResult
0x180006e5e  mov     r14d, 2001Fh
0x180006e64  mov     r9d, r14d; samDesired
0x180006e67  xor     r8d, r8d; ulOptions
0x180006e6a  mov     rdx, rsi; lpSubKey
0x180006e6d  mov     rcx, r15; hKey
0x180006e70  call    cs:__imp_RegOpenKeyExW
0x180006e76  test    eax, eax
0x180006e78  jnz     short loc_180006E9B
0x180006e7a  mov     eax, edi
0x180006e7c  test    rbx, rbx
0x180006e7f  jz      short loc_180006E8A
0x180006e81  mov     rcx, rbx; hKey
0x180006e84  call    cs:__imp_RegCloseKey
0x180006e8a  mov     rbx, [rsp+2310h+hKey]
0x180006e8f  mov     [rbp+2210h+var_2290], rbx
0x180006e93  test    eax, eax
0x180006e95  jz      loc_180006F46
0x180006e9b  mov     [rsp+2310h+hKey], rdi
0x180006ea0  lea     rax, [rsp+2310h+hKey]
0x180006ea5  mov     [rsp+2310h+phkResult], rax; phkResult
0x180006eaa  mov     r9d, 20019h; samDesired
0x180006eb0  xor     r8d, r8d; ulOptions
0x180006eb3  mov     rdx, rsi; lpSubKey
0x180006eb6  mov     rcx, r15; hKey
0x180006eb9  call    cs:__imp_RegOpenKeyExW
0x180006ebf  test    eax, eax
0x180006ec1  jnz     short loc_180006EE0
0x180006ec3  mov     eax, edi
0x180006ec5  test    rbx, rbx
0x180006ec8  jz      short loc_180006ED3
0x180006eca  mov     rcx, rbx; hKey
0x180006ecd  call    cs:__imp_RegCloseKey
0x180006ed3  mov     rbx, [rsp+2310h+hKey]
0x180006ed8  mov     [rbp+2210h+var_2290], rbx
0x180006edc  test    eax, eax
0x180006ede  jz      short loc_180006F46
0x180006ee0  mov     dword ptr [rsp+2310h+hKey], edi
0x180006ee4  mov     [rsp+2310h+var_2298], rdi
0x180006ee9  lea     rax, [rsp+2310h+hKey]
0x180006eee  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180006ef3  lea     rax, [rsp+2310h+var_2298]
0x180006ef8  mov     [rsp+2310h+var_22D8], rax; phkResult
0x180006efd  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180006f02  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180006f07  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180006f0b  xor     r9d, r9d; lpClass
0x180006f0e  xor     r8d, r8d; Reserved
0x180006f11  mov     rdx, rsi; lpSubKey
0x180006f14  mov     rcx, r15; hKey
0x180006f17  call    cs:__imp_RegCreateKeyExW
0x180006f1d  test    eax, eax
0x180006f1f  jnz     loc_180007283
0x180006f25  mov     eax, edi
0x180006f27  test    rbx, rbx
0x180006f2a  jz      short loc_180006F35
0x180006f2c  mov     rcx, rbx; hKey
0x180006f2f  call    cs:__imp_RegCloseKey
0x180006f35  mov     rbx, [rsp+2310h+var_2298]
0x180006f3a  mov     [rbp+2210h+var_2290], rbx
0x180006f3e  test    eax, eax
0x180006f40  jnz     loc_180007283
0x180006f46  mov     rdx, rsi; unsigned __int16 *
0x180006f49  mov     rcx, r13; this
0x180006f4c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006f51  mov     edi, eax
0x180006f53  xor     ecx, ecx
0x180006f55  test    eax, eax
0x180006f57  js      loc_18000728C
0x180006f5d  cmp     word ptr [rsi], 3Dh ; '='
0x180006f61  jnz     short loc_180006F85
0x180006f63  mov     r9, rsi; unsigned __int16 *
0x180006f66  xor     r8d, r8d; unsigned __int16 *
0x180006f69  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180006f6d  mov     rcx, r13; this
0x180006f70  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180006f75  mov     edi, eax
0x180006f77  mov     rbx, [rbp+2210h+var_2290]
0x180006f7b  test    eax, eax
0x180006f7d  js      loc_18000728C
0x180006f83  xor     ecx, ecx
0x180006f85  mov     r12d, [rsp+2310h+var_22A8]
0x180006f8a  cmp     word ptr [rsi], 7Bh ; '{'
0x180006f8e  jnz     loc_180007125
0x180006f94  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006f98  inc     rax
0x180006f9b  cmp     [rsi+rax*2], cx
0x180006f9f  jnz     short loc_180006F98
0x180006fa1  cmp     rax, 1
0x180006fa5  jnz     loc_180007125
0x180006fab  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180006fb3  mov     r9d, r12d; int
0x180006fb6  mov     r8, rbx; HKEY
0x180006fb9  mov     rdx, rsi; unsigned __int16 *
0x180006fbc  mov     rcx, r13; this
0x180006fbf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180006fc4  mov     edi, eax
0x180006fc6  test    eax, eax
0x180006fc8  js      loc_18000728C
0x180006fce  mov     rdx, rsi; unsigned __int16 *
0x180006fd1  mov     rcx, r13; this
0x180006fd4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006fd9  jmp     loc_180006E09
  ... truncated ...
```
