# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x140016794`
- end: `0x140016f2b`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x140016420`
- `0x140016794`

## callees

- `0x1400042f0`
- `0x14000d92c`
- `0x14000e530`
- `0x14000e548`
- `0x14000e87c`
- `0x140013988`
- `0x1400161e8`
- `0x140016794`
- `0x140018178`
- `0x140059180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140016c72`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140016c72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400169da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016a88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016ad1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016c20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400169da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016a88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016ad1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016c20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016a10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016a9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016ae5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016b47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016c3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016e52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016eac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016ee8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016ef8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016a10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016a9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016ae5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016b47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016c3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016e52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016eac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016ee8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016ef8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140016d9e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140016e34`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140016d9e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140016e34`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400169f7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400169f7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140016b2f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140016b2f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140016876`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140016a41`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140016876`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140016a41`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140016811`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140016824`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400168a2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14001690b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140016939`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140016dc1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140016811`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140016824`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400168a2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14001690b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140016939`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140016dc1`

## string_xrefs

- `0x14001681a`: `ForceRemove`
- `0x140016901`: `NoRemove`
- `0x140016807`: `Delete`

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
0x140016794  push    rbp
0x140016796  push    rbx
0x140016797  push    rsi
0x140016798  push    rdi
0x140016799  push    r12
0x14001679b  push    r13
0x14001679d  push    r14
0x14001679f  push    r15
0x1400167a1  lea     rbp, [rsp-21D8h]
0x1400167a9  mov     eax, 22D8h
0x1400167ae  call    _alloca_probe
0x1400167b3  sub     rsp, rax
0x1400167b6  mov     rax, cs:__security_cookie
0x1400167bd  xor     rax, rsp
0x1400167c0  mov     [rbp+2210h+var_50], rax
0x1400167c7  mov     r12d, r9d
0x1400167ca  mov     [rsp+2310h+var_22A8], r9d
0x1400167cf  mov     r15, r8
0x1400167d2  mov     [rsp+2310h+var_22A0], r8
0x1400167d7  mov     rsi, rdx
0x1400167da  mov     r13, rcx
0x1400167dd  xor     eax, eax
0x1400167df  mov     ebx, eax
0x1400167e1  mov     [rbp+2210h+var_2290], rax
0x1400167e5  mov     [rbp+2210h+var_2288], rax
0x1400167e9  mov     [rbp+2210h+var_2280], rax
0x1400167ed  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400167f2  mov     edi, eax
0x1400167f4  test    eax, eax
0x1400167f6  jns     short loc_1400167FD
0x1400167f8  jmp     loc_140016EB4
0x1400167fd  cmp     word ptr [rsi], 7Dh ; '}'
0x140016801  jz      loc_140016EA4
0x140016807  lea     rdx, String2; "Delete"
0x14001680e  mov     rcx, rsi; lpString1
0x140016811  call    cs:__imp_lstrcmpiW
0x140016817  mov     r14d, eax
0x14001681a  lea     rdx, aForceremove; "ForceRemove"
0x140016821  mov     rcx, rsi; lpString1
0x140016824  call    cs:__imp_lstrcmpiW
0x14001682a  xor     edi, edi
0x14001682c  test    eax, eax
0x14001682e  jz      short loc_140016839
0x140016830  test    r14d, r14d
0x140016833  jnz     loc_1400168FB
0x140016839  mov     rdx, rsi; unsigned __int16 *
0x14001683c  mov     rcx, r13; this
0x14001683f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140016844  mov     edi, eax
0x140016846  test    eax, eax
0x140016848  js      loc_140016EA4
0x14001684e  xor     edi, edi
0x140016850  test    r12d, r12d
0x140016853  jz      loc_1400168FB
0x140016859  mov     [rbp+2210h+var_2278], rdi
0x14001685d  mov     [rbp+2210h+var_2270], rdi
0x140016861  mov     [rbp+2210h+var_2268], rdi
0x140016865  movzx   eax, word ptr [rsi]
0x140016868  test    ax, ax
0x14001686b  jz      short loc_140016892
0x14001686d  mov     rcx, rsi; lpsz
0x140016870  cmp     ax, 5Ch ; '\'
0x140016874  jz      short loc_140016889
0x140016876  call    cs:__imp_CharNextW
0x14001687c  mov     rcx, rax
0x14001687f  movzx   eax, word ptr [rax]
0x140016882  test    ax, ax
0x140016885  jnz     short loc_140016870
0x140016887  jmp     short loc_140016892
0x140016889  test    rcx, rcx
0x14001688c  jnz     loc_140016EF0
0x140016892  mov     edx, edi
0x140016894  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x14001689b  mov     rdx, [rax+rdx*8]; lpString2
0x14001689f  mov     rcx, rsi; lpString1
0x1400168a2  call    cs:__imp_lstrcmpiW
0x1400168a8  test    eax, eax
0x1400168aa  jz      short loc_1400168C3
0x1400168ac  inc     edi
0x1400168ae  cmp     edi, 0Ch
0x1400168b1  jl      short loc_140016892
0x1400168b3  mov     [rbp+2210h+var_2278], r15
0x1400168b7  mov     rdx, rsi; unsigned __int16 *
0x1400168ba  lea     rcx, [rbp+2210h+var_2278]; this
0x1400168be  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1400168c3  xor     edi, edi
0x1400168c5  test    r14d, r14d
0x1400168c8  jnz     short loc_1400168FB
0x1400168ca  mov     rdx, rsi; unsigned __int16 *
0x1400168cd  mov     rcx, r13; this
0x1400168d0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400168d5  mov     edi, eax
0x1400168d7  test    eax, eax
0x1400168d9  js      loc_140016EA4
0x1400168df  mov     rdx, rsi; unsigned __int16 *
0x1400168e2  mov     rcx, r13; this
0x1400168e5  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1400168ea  mov     edi, eax
0x1400168ec  xor     ecx, ecx
0x1400168ee  test    eax, eax
0x1400168f0  js      loc_140016EA4
0x1400168f6  jmp     loc_140016BA2
0x1400168fb  mov     r12d, 1
0x140016901  lea     rdx, aNoremove; "NoRemove"
0x140016908  mov     rcx, rsi; lpString1
0x14001690b  call    cs:__imp_lstrcmpiW
0x140016911  test    eax, eax
0x140016913  jnz     short loc_14001692F
0x140016915  mov     r12d, edi
0x140016918  mov     rdx, rsi; unsigned __int16 *
0x14001691b  mov     rcx, r13; this
0x14001691e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140016923  mov     edi, eax
0x140016925  test    eax, eax
0x140016927  js      loc_140016EA4
0x14001692d  xor     edi, edi
0x14001692f  lea     rdx, aVal; "Val"
0x140016936  mov     rcx, rsi; lpString1
0x140016939  call    cs:__imp_lstrcmpiW
0x14001693f  test    eax, eax
0x140016941  jnz     loc_140016A30
0x140016947  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x14001694e  mov     rcx, r13; this
0x140016951  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140016956  mov     edi, eax
0x140016958  test    eax, eax
0x14001695a  js      loc_140016EA4
0x140016960  mov     rdx, rsi; unsigned __int16 *
0x140016963  mov     rcx, r13; this
0x140016966  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14001696b  mov     edi, eax
0x14001696d  test    eax, eax
0x14001696f  js      loc_140016EA4
0x140016975  cmp     word ptr [rsi], 3Dh ; '='
0x140016979  jnz     loc_140016EF0
0x14001697f  xor     edi, edi
0x140016981  cmp     [rsp+2310h+var_22A8], edi
0x140016985  jz      short loc_1400169B0
0x140016987  mov     [rbp+2210h+var_2270], rdi
0x14001698b  mov     [rbp+2210h+var_2268], rdi
0x14001698f  mov     [rbp+2210h+var_2278], r15
0x140016993  mov     r9, rsi; unsigned __int16 *
0x140016996  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x14001699d  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x1400169a1  mov     rcx, r13; this
0x1400169a4  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1400169a9  mov     edi, eax
0x1400169ab  jmp     loc_140016B93
0x1400169b0  cmp     [rbp+2210h+arg_20], edi
0x1400169b6  jnz     short loc_140016A16
0x1400169b8  test    r12d, r12d
0x1400169bb  jz      short loc_140016A16
0x1400169bd  mov     [rsp+2310h+hKey], rdi
0x1400169c2  lea     rax, [rsp+2310h+hKey]
0x1400169c7  mov     [rsp+2310h+phkResult], rax; phkResult
0x1400169cc  mov     r9d, 20006h; samDesired
0x1400169d2  xor     r8d, r8d; ulOptions
0x1400169d5  xor     edx, edx; lpSubKey
0x1400169d7  mov     rcx, r15; hKey
0x1400169da  call    cs:__imp_RegOpenKeyExW
0x1400169e0  test    eax, eax
0x1400169e2  jnz     loc_140016E9B
0x1400169e8  mov     r14, [rsp+2310h+hKey]
0x1400169ed  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x1400169f4  mov     rcx, r14; hKey
0x1400169f7  call    cs:__imp_RegDeleteValueW
0x1400169fd  test    eax, 0FFFFFFFDh
0x140016a02  jnz     loc_140016ED7
0x140016a08  test    r14, r14
0x140016a0b  jz      short loc_140016A16
0x140016a0d  mov     rcx, r14; hKey
0x140016a10  call    cs:__imp_RegCloseKey
0x140016a16  mov     rdx, rsi; unsigned __int16 *
0x140016a19  mov     rcx, r13; this
0x140016a1c  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x140016a21  mov     edi, eax
0x140016a23  test    eax, eax
0x140016a25  js      loc_140016EA4
0x140016a2b  jmp     loc_140016D3D
0x140016a30  movzx   eax, word ptr [rsi]
0x140016a33  test    ax, ax
0x140016a36  jz      short loc_140016A5D
0x140016a38  mov     rcx, rsi; lpsz
0x140016a3b  cmp     ax, 5Ch ; '\'
0x140016a3f  jz      short loc_140016A54
0x140016a41  call    cs:__imp_CharNextW
0x140016a47  mov     rcx, rax
0x140016a4a  movzx   eax, word ptr [rax]
0x140016a4d  test    ax, ax
0x140016a50  jnz     short loc_140016A3B
0x140016a52  jmp     short loc_140016A5D
0x140016a54  test    rcx, rcx
0x140016a57  jnz     loc_140016EF0
0x140016a5d  cmp     [rsp+2310h+var_22A8], edi
0x140016a61  jz      loc_140016BF6
0x140016a67  mov     [rsp+2310h+hKey], rdi
0x140016a6c  lea     rax, [rsp+2310h+hKey]
0x140016a71  mov     [rsp+2310h+phkResult], rax; phkResult
0x140016a76  mov     r14d, 2001Fh
0x140016a7c  mov     r9d, r14d; samDesired
0x140016a7f  xor     r8d, r8d; ulOptions
0x140016a82  mov     rdx, rsi; lpSubKey
0x140016a85  mov     rcx, r15; hKey
0x140016a88  call    cs:__imp_RegOpenKeyExW
0x140016a8e  test    eax, eax
0x140016a90  jnz     short loc_140016AB3
0x140016a92  mov     eax, edi
0x140016a94  test    rbx, rbx
0x140016a97  jz      short loc_140016AA2
0x140016a99  mov     rcx, rbx; hKey
0x140016a9c  call    cs:__imp_RegCloseKey
0x140016aa2  mov     rbx, [rsp+2310h+hKey]
0x140016aa7  mov     [rbp+2210h+var_2290], rbx
0x140016aab  test    eax, eax
0x140016aad  jz      loc_140016B5E
0x140016ab3  mov     [rsp+2310h+hKey], rdi
0x140016ab8  lea     rax, [rsp+2310h+hKey]
0x140016abd  mov     [rsp+2310h+phkResult], rax; phkResult
0x140016ac2  mov     r9d, 20019h; samDesired
0x140016ac8  xor     r8d, r8d; ulOptions
0x140016acb  mov     rdx, rsi; lpSubKey
0x140016ace  mov     rcx, r15; hKey
0x140016ad1  call    cs:__imp_RegOpenKeyExW
0x140016ad7  test    eax, eax
0x140016ad9  jnz     short loc_140016AF8
0x140016adb  mov     eax, edi
0x140016add  test    rbx, rbx
0x140016ae0  jz      short loc_140016AEB
0x140016ae2  mov     rcx, rbx; hKey
0x140016ae5  call    cs:__imp_RegCloseKey
0x140016aeb  mov     rbx, [rsp+2310h+hKey]
0x140016af0  mov     [rbp+2210h+var_2290], rbx
0x140016af4  test    eax, eax
0x140016af6  jz      short loc_140016B5E
0x140016af8  mov     dword ptr [rsp+2310h+hKey], edi
0x140016afc  mov     [rsp+2310h+var_2298], rdi
0x140016b01  lea     rax, [rsp+2310h+hKey]
0x140016b06  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x140016b0b  lea     rax, [rsp+2310h+var_2298]
0x140016b10  mov     [rsp+2310h+var_22D8], rax; phkResult
0x140016b15  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x140016b1a  mov     [rsp+2310h+samDesired], r14d; samDesired
0x140016b1f  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x140016b23  xor     r9d, r9d; lpClass
0x140016b26  xor     r8d, r8d; Reserved
0x140016b29  mov     rdx, rsi; lpSubKey
0x140016b2c  mov     rcx, r15; hKey
0x140016b2f  call    cs:__imp_RegCreateKeyExW
0x140016b35  test    eax, eax
0x140016b37  jnz     loc_140016E9B
0x140016b3d  mov     eax, edi
0x140016b3f  test    rbx, rbx
0x140016b42  jz      short loc_140016B4D
0x140016b44  mov     rcx, rbx; hKey
0x140016b47  call    cs:__imp_RegCloseKey
0x140016b4d  mov     rbx, [rsp+2310h+var_2298]
0x140016b52  mov     [rbp+2210h+var_2290], rbx
0x140016b56  test    eax, eax
0x140016b58  jnz     loc_140016E9B
0x140016b5e  mov     rdx, rsi; unsigned __int16 *
0x140016b61  mov     rcx, r13; this
0x140016b64  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140016b69  mov     edi, eax
0x140016b6b  xor     ecx, ecx
0x140016b6d  test    eax, eax
0x140016b6f  js      loc_140016EA4
0x140016b75  cmp     word ptr [rsi], 3Dh ; '='
0x140016b79  jnz     short loc_140016B9D
0x140016b7b  mov     r9, rsi; unsigned __int16 *
0x140016b7e  xor     r8d, r8d; unsigned __int16 *
0x140016b81  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x140016b85  mov     rcx, r13; this
0x140016b88  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x140016b8d  mov     edi, eax
0x140016b8f  mov     rbx, [rbp+2210h+var_2290]
0x140016b93  test    eax, eax
0x140016b95  js      loc_140016EA4
0x140016b9b  xor     ecx, ecx
0x140016b9d  mov     r12d, [rsp+2310h+var_22A8]
0x140016ba2  cmp     word ptr [rsi], 7Bh ; '{'
0x140016ba6  jnz     loc_140016D3D
0x140016bac  or      rax, 0FFFFFFFFFFFFFFFFh
0x140016bb0  inc     rax
0x140016bb3  cmp     [rsi+rax*2], cx
0x140016bb7  jnz     short loc_140016BB0
0x140016bb9  cmp     rax, 1
0x140016bbd  jnz     loc_140016D3D
0x140016bc3  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x140016bcb  mov     r9d, r12d; int
0x140016bce  mov     r8, rbx; HKEY
0x140016bd1  mov     rdx, rsi; unsigned __int16 *
0x140016bd4  mov     rcx, r13; this
0x140016bd7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140016bdc  mov     edi, eax
0x140016bde  test    eax, eax
0x140016be0  js      loc_140016EA4
0x140016be6  mov     rdx, rsi; unsigned __int16 *
0x140016be9  mov     rcx, r13; this
0x140016bec  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140016bf1  jmp     loc_140016A21
  ... truncated ...
```
