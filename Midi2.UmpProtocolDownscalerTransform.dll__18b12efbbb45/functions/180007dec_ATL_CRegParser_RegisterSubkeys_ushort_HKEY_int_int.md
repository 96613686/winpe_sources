# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180007dec`
- end: `0x180008583`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180007a7c`
- `0x180007dec`

## callees

- `0x180002e70`
- `0x180005290`
- `0x1800059c0`
- `0x1800059d8`
- `0x1800060f0`
- `0x1800072bc`
- `0x18000792c`
- `0x180007dec`
- `0x180009200`
- `0x180012080`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800082ca`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800082ca`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000804f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000804f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008032`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800080e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008129`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008278`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008032`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800080e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008129`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008278`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008187`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008187`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008068`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800080f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000813d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000819f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008293`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800084aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008504`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008540`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008550`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008068`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800080f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000813d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000819f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008293`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800084aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008504`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008540`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008550`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800083f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000848c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800083f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000848c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007ece`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008099`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007ece`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008099`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007e69`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007e7c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007efa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007f63`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007f91`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008419`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007e69`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007e7c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007efa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007f63`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007f91`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008419`

## string_xrefs

- `0x180007e72`: `ForceRemove`
- `0x180007f59`: `NoRemove`
- `0x180007e5f`: `Delete`

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
0x180007dec  push    rbp
0x180007dee  push    rbx
0x180007def  push    rsi
0x180007df0  push    rdi
0x180007df1  push    r12
0x180007df3  push    r13
0x180007df5  push    r14
0x180007df7  push    r15
0x180007df9  lea     rbp, [rsp-21D8h]
0x180007e01  mov     eax, 22D8h
0x180007e06  call    _alloca_probe
0x180007e0b  sub     rsp, rax
0x180007e0e  mov     rax, cs:__security_cookie
0x180007e15  xor     rax, rsp
0x180007e18  mov     [rbp+2210h+var_50], rax
0x180007e1f  mov     r12d, r9d
0x180007e22  mov     [rsp+2310h+var_22A8], r9d
0x180007e27  mov     r15, r8
0x180007e2a  mov     [rsp+2310h+var_22A0], r8
0x180007e2f  mov     rsi, rdx
0x180007e32  mov     r13, rcx
0x180007e35  xor     eax, eax
0x180007e37  mov     ebx, eax
0x180007e39  mov     [rbp+2210h+var_2290], rax
0x180007e3d  mov     [rbp+2210h+var_2288], rax
0x180007e41  mov     [rbp+2210h+var_2280], rax
0x180007e45  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007e4a  mov     edi, eax
0x180007e4c  test    eax, eax
0x180007e4e  jns     short loc_180007E55
0x180007e50  jmp     loc_18000850C
0x180007e55  cmp     word ptr [rsi], 7Dh ; '}'
0x180007e59  jz      loc_1800084FC
0x180007e5f  lea     rdx, String2; "Delete"
0x180007e66  mov     rcx, rsi; lpString1
0x180007e69  call    cs:__imp_lstrcmpiW
0x180007e6f  mov     r14d, eax
0x180007e72  lea     rdx, aForceremove; "ForceRemove"
0x180007e79  mov     rcx, rsi; lpString1
0x180007e7c  call    cs:__imp_lstrcmpiW
0x180007e82  xor     edi, edi
0x180007e84  test    eax, eax
0x180007e86  jz      short loc_180007E91
0x180007e88  test    r14d, r14d
0x180007e8b  jnz     loc_180007F53
0x180007e91  mov     rdx, rsi; unsigned __int16 *
0x180007e94  mov     rcx, r13; this
0x180007e97  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007e9c  mov     edi, eax
0x180007e9e  test    eax, eax
0x180007ea0  js      loc_1800084FC
0x180007ea6  xor     edi, edi
0x180007ea8  test    r12d, r12d
0x180007eab  jz      loc_180007F53
0x180007eb1  mov     [rbp+2210h+var_2278], rdi
0x180007eb5  mov     [rbp+2210h+var_2270], rdi
0x180007eb9  mov     [rbp+2210h+var_2268], rdi
0x180007ebd  movzx   eax, word ptr [rsi]
0x180007ec0  test    ax, ax
0x180007ec3  jz      short loc_180007EEA
0x180007ec5  mov     rcx, rsi; lpsz
0x180007ec8  cmp     ax, 5Ch ; '\'
0x180007ecc  jz      short loc_180007EE1
0x180007ece  call    cs:__imp_CharNextW
0x180007ed4  mov     rcx, rax
0x180007ed7  movzx   eax, word ptr [rax]
0x180007eda  test    ax, ax
0x180007edd  jnz     short loc_180007EC8
0x180007edf  jmp     short loc_180007EEA
0x180007ee1  test    rcx, rcx
0x180007ee4  jnz     loc_180008548
0x180007eea  mov     edx, edi
0x180007eec  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180007ef3  mov     rdx, [rax+rdx*8]; lpString2
0x180007ef7  mov     rcx, rsi; lpString1
0x180007efa  call    cs:__imp_lstrcmpiW
0x180007f00  test    eax, eax
0x180007f02  jz      short loc_180007F1B
0x180007f04  inc     edi
0x180007f06  cmp     edi, 0Ch
0x180007f09  jl      short loc_180007EEA
0x180007f0b  mov     [rbp+2210h+var_2278], r15
0x180007f0f  mov     rdx, rsi; unsigned __int16 *
0x180007f12  lea     rcx, [rbp+2210h+var_2278]; this
0x180007f16  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180007f1b  xor     edi, edi
0x180007f1d  test    r14d, r14d
0x180007f20  jnz     short loc_180007F53
0x180007f22  mov     rdx, rsi; unsigned __int16 *
0x180007f25  mov     rcx, r13; this
0x180007f28  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007f2d  mov     edi, eax
0x180007f2f  test    eax, eax
0x180007f31  js      loc_1800084FC
0x180007f37  mov     rdx, rsi; unsigned __int16 *
0x180007f3a  mov     rcx, r13; this
0x180007f3d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180007f42  mov     edi, eax
0x180007f44  xor     ecx, ecx
0x180007f46  test    eax, eax
0x180007f48  js      loc_1800084FC
0x180007f4e  jmp     loc_1800081FA
0x180007f53  mov     r12d, 1
0x180007f59  lea     rdx, aNoremove; "NoRemove"
0x180007f60  mov     rcx, rsi; lpString1
0x180007f63  call    cs:__imp_lstrcmpiW
0x180007f69  test    eax, eax
0x180007f6b  jnz     short loc_180007F87
0x180007f6d  mov     r12d, edi
0x180007f70  mov     rdx, rsi; unsigned __int16 *
0x180007f73  mov     rcx, r13; this
0x180007f76  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007f7b  mov     edi, eax
0x180007f7d  test    eax, eax
0x180007f7f  js      loc_1800084FC
0x180007f85  xor     edi, edi
0x180007f87  lea     rdx, aVal; "Val"
0x180007f8e  mov     rcx, rsi; lpString1
0x180007f91  call    cs:__imp_lstrcmpiW
0x180007f97  test    eax, eax
0x180007f99  jnz     loc_180008088
0x180007f9f  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180007fa6  mov     rcx, r13; this
0x180007fa9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007fae  mov     edi, eax
0x180007fb0  test    eax, eax
0x180007fb2  js      loc_1800084FC
0x180007fb8  mov     rdx, rsi; unsigned __int16 *
0x180007fbb  mov     rcx, r13; this
0x180007fbe  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007fc3  mov     edi, eax
0x180007fc5  test    eax, eax
0x180007fc7  js      loc_1800084FC
0x180007fcd  cmp     word ptr [rsi], 3Dh ; '='
0x180007fd1  jnz     loc_180008548
0x180007fd7  xor     edi, edi
0x180007fd9  cmp     [rsp+2310h+var_22A8], edi
0x180007fdd  jz      short loc_180008008
0x180007fdf  mov     [rbp+2210h+var_2270], rdi
0x180007fe3  mov     [rbp+2210h+var_2268], rdi
0x180007fe7  mov     [rbp+2210h+var_2278], r15
0x180007feb  mov     r9, rsi; unsigned __int16 *
0x180007fee  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180007ff5  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180007ff9  mov     rcx, r13; this
0x180007ffc  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180008001  mov     edi, eax
0x180008003  jmp     loc_1800081EB
0x180008008  cmp     [rbp+2210h+arg_20], edi
0x18000800e  jnz     short loc_18000806E
0x180008010  test    r12d, r12d
0x180008013  jz      short loc_18000806E
0x180008015  mov     [rsp+2310h+hKey], rdi
0x18000801a  lea     rax, [rsp+2310h+hKey]
0x18000801f  mov     [rsp+2310h+phkResult], rax; phkResult
0x180008024  mov     r9d, 20006h; samDesired
0x18000802a  xor     r8d, r8d; ulOptions
0x18000802d  xor     edx, edx; lpSubKey
0x18000802f  mov     rcx, r15; hKey
0x180008032  call    cs:__imp_RegOpenKeyExW
0x180008038  test    eax, eax
0x18000803a  jnz     loc_1800084F3
0x180008040  mov     r14, [rsp+2310h+hKey]
0x180008045  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x18000804c  mov     rcx, r14; hKey
0x18000804f  call    cs:__imp_RegDeleteValueW
0x180008055  test    eax, 0FFFFFFFDh
0x18000805a  jnz     loc_18000852F
0x180008060  test    r14, r14
0x180008063  jz      short loc_18000806E
0x180008065  mov     rcx, r14; hKey
0x180008068  call    cs:__imp_RegCloseKey
0x18000806e  mov     rdx, rsi; unsigned __int16 *
0x180008071  mov     rcx, r13; this
0x180008074  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180008079  mov     edi, eax
0x18000807b  test    eax, eax
0x18000807d  js      loc_1800084FC
0x180008083  jmp     loc_180008395
0x180008088  movzx   eax, word ptr [rsi]
0x18000808b  test    ax, ax
0x18000808e  jz      short loc_1800080B5
0x180008090  mov     rcx, rsi; lpsz
0x180008093  cmp     ax, 5Ch ; '\'
0x180008097  jz      short loc_1800080AC
0x180008099  call    cs:__imp_CharNextW
0x18000809f  mov     rcx, rax
0x1800080a2  movzx   eax, word ptr [rax]
0x1800080a5  test    ax, ax
0x1800080a8  jnz     short loc_180008093
0x1800080aa  jmp     short loc_1800080B5
0x1800080ac  test    rcx, rcx
0x1800080af  jnz     loc_180008548
0x1800080b5  cmp     [rsp+2310h+var_22A8], edi
0x1800080b9  jz      loc_18000824E
0x1800080bf  mov     [rsp+2310h+hKey], rdi
0x1800080c4  lea     rax, [rsp+2310h+hKey]
0x1800080c9  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800080ce  mov     r14d, 2001Fh
0x1800080d4  mov     r9d, r14d; samDesired
0x1800080d7  xor     r8d, r8d; ulOptions
0x1800080da  mov     rdx, rsi; lpSubKey
0x1800080dd  mov     rcx, r15; hKey
0x1800080e0  call    cs:__imp_RegOpenKeyExW
0x1800080e6  test    eax, eax
0x1800080e8  jnz     short loc_18000810B
0x1800080ea  mov     eax, edi
0x1800080ec  test    rbx, rbx
0x1800080ef  jz      short loc_1800080FA
0x1800080f1  mov     rcx, rbx; hKey
0x1800080f4  call    cs:__imp_RegCloseKey
0x1800080fa  mov     rbx, [rsp+2310h+hKey]
0x1800080ff  mov     [rbp+2210h+var_2290], rbx
0x180008103  test    eax, eax
0x180008105  jz      loc_1800081B6
0x18000810b  mov     [rsp+2310h+hKey], rdi
0x180008110  lea     rax, [rsp+2310h+hKey]
0x180008115  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000811a  mov     r9d, 20019h; samDesired
0x180008120  xor     r8d, r8d; ulOptions
0x180008123  mov     rdx, rsi; lpSubKey
0x180008126  mov     rcx, r15; hKey
0x180008129  call    cs:__imp_RegOpenKeyExW
0x18000812f  test    eax, eax
0x180008131  jnz     short loc_180008150
0x180008133  mov     eax, edi
0x180008135  test    rbx, rbx
0x180008138  jz      short loc_180008143
0x18000813a  mov     rcx, rbx; hKey
0x18000813d  call    cs:__imp_RegCloseKey
0x180008143  mov     rbx, [rsp+2310h+hKey]
0x180008148  mov     [rbp+2210h+var_2290], rbx
0x18000814c  test    eax, eax
0x18000814e  jz      short loc_1800081B6
0x180008150  mov     dword ptr [rsp+2310h+hKey], edi
0x180008154  mov     [rsp+2310h+var_2298], rdi
0x180008159  lea     rax, [rsp+2310h+hKey]
0x18000815e  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180008163  lea     rax, [rsp+2310h+var_2298]
0x180008168  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18000816d  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180008172  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180008177  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x18000817b  xor     r9d, r9d; lpClass
0x18000817e  xor     r8d, r8d; Reserved
0x180008181  mov     rdx, rsi; lpSubKey
0x180008184  mov     rcx, r15; hKey
0x180008187  call    cs:__imp_RegCreateKeyExW
0x18000818d  test    eax, eax
0x18000818f  jnz     loc_1800084F3
0x180008195  mov     eax, edi
0x180008197  test    rbx, rbx
0x18000819a  jz      short loc_1800081A5
0x18000819c  mov     rcx, rbx; hKey
0x18000819f  call    cs:__imp_RegCloseKey
0x1800081a5  mov     rbx, [rsp+2310h+var_2298]
0x1800081aa  mov     [rbp+2210h+var_2290], rbx
0x1800081ae  test    eax, eax
0x1800081b0  jnz     loc_1800084F3
0x1800081b6  mov     rdx, rsi; unsigned __int16 *
0x1800081b9  mov     rcx, r13; this
0x1800081bc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800081c1  mov     edi, eax
0x1800081c3  xor     ecx, ecx
0x1800081c5  test    eax, eax
0x1800081c7  js      loc_1800084FC
0x1800081cd  cmp     word ptr [rsi], 3Dh ; '='
0x1800081d1  jnz     short loc_1800081F5
0x1800081d3  mov     r9, rsi; unsigned __int16 *
0x1800081d6  xor     r8d, r8d; unsigned __int16 *
0x1800081d9  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x1800081dd  mov     rcx, r13; this
0x1800081e0  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800081e5  mov     edi, eax
0x1800081e7  mov     rbx, [rbp+2210h+var_2290]
0x1800081eb  test    eax, eax
0x1800081ed  js      loc_1800084FC
0x1800081f3  xor     ecx, ecx
0x1800081f5  mov     r12d, [rsp+2310h+var_22A8]
0x1800081fa  cmp     word ptr [rsi], 7Bh ; '{'
0x1800081fe  jnz     loc_180008395
0x180008204  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008208  inc     rax
0x18000820b  cmp     [rsi+rax*2], cx
0x18000820f  jnz     short loc_180008208
0x180008211  cmp     rax, 1
0x180008215  jnz     loc_180008395
0x18000821b  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180008223  mov     r9d, r12d; int
0x180008226  mov     r8, rbx; HKEY
0x180008229  mov     rdx, rsi; unsigned __int16 *
0x18000822c  mov     rcx, r13; this
0x18000822f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008234  mov     edi, eax
0x180008236  test    eax, eax
0x180008238  js      loc_1800084FC
0x18000823e  mov     rdx, rsi; unsigned __int16 *
0x180008241  mov     rcx, r13; this
0x180008244  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008249  jmp     loc_180008079
  ... truncated ...
```
