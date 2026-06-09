# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180008afc`
- end: `0x180009293`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18000878c`
- `0x180008afc`

## callees

- `0x1800038f0`
- `0x180005f60`
- `0x180006690`
- `0x1800066a8`
- `0x180006dc0`
- `0x180007f8c`
- `0x18000863c`
- `0x180008afc`
- `0x18000a060`
- `0x18001f830`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180008fda`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180008fda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008d78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008eaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008fa3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800091ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009214`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009250`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009260`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008d78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008eaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008fa3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800091ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009214`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009250`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009260`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008d42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008df0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008e39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008f88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008d42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008df0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008e39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008f88`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009106`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000919c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009106`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000919c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008e97`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008e97`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008d5f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008d5f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008bde`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008da9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008bde`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008da9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008b79`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008b8c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008c0a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008c73`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008ca1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009129`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008b79`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008b8c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008c0a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008c73`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008ca1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009129`

## string_xrefs

- `0x180008b82`: `ForceRemove`
- `0x180008c69`: `NoRemove`
- `0x180008b6f`: `Delete`

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
0x180008afc  push    rbp
0x180008afe  push    rbx
0x180008aff  push    rsi
0x180008b00  push    rdi
0x180008b01  push    r12
0x180008b03  push    r13
0x180008b05  push    r14
0x180008b07  push    r15
0x180008b09  lea     rbp, [rsp-21D8h]
0x180008b11  mov     eax, 22D8h
0x180008b16  call    _alloca_probe
0x180008b1b  sub     rsp, rax
0x180008b1e  mov     rax, cs:__security_cookie
0x180008b25  xor     rax, rsp
0x180008b28  mov     [rbp+2210h+var_50], rax
0x180008b2f  mov     r12d, r9d
0x180008b32  mov     [rsp+2310h+var_22A8], r9d
0x180008b37  mov     r15, r8
0x180008b3a  mov     [rsp+2310h+var_22A0], r8
0x180008b3f  mov     rsi, rdx
0x180008b42  mov     r13, rcx
0x180008b45  xor     eax, eax
0x180008b47  mov     ebx, eax
0x180008b49  mov     [rbp+2210h+var_2290], rax
0x180008b4d  mov     [rbp+2210h+var_2288], rax
0x180008b51  mov     [rbp+2210h+var_2280], rax
0x180008b55  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008b5a  mov     edi, eax
0x180008b5c  test    eax, eax
0x180008b5e  jns     short loc_180008B65
0x180008b60  jmp     loc_18000921C
0x180008b65  cmp     word ptr [rsi], 7Dh ; '}'
0x180008b69  jz      loc_18000920C
0x180008b6f  lea     rdx, String2; "Delete"
0x180008b76  mov     rcx, rsi; lpString1
0x180008b79  call    cs:__imp_lstrcmpiW
0x180008b7f  mov     r14d, eax
0x180008b82  lea     rdx, aForceremove; "ForceRemove"
0x180008b89  mov     rcx, rsi; lpString1
0x180008b8c  call    cs:__imp_lstrcmpiW
0x180008b92  xor     edi, edi
0x180008b94  test    eax, eax
0x180008b96  jz      short loc_180008BA1
0x180008b98  test    r14d, r14d
0x180008b9b  jnz     loc_180008C63
0x180008ba1  mov     rdx, rsi; unsigned __int16 *
0x180008ba4  mov     rcx, r13; this
0x180008ba7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008bac  mov     edi, eax
0x180008bae  test    eax, eax
0x180008bb0  js      loc_18000920C
0x180008bb6  xor     edi, edi
0x180008bb8  test    r12d, r12d
0x180008bbb  jz      loc_180008C63
0x180008bc1  mov     [rbp+2210h+var_2278], rdi
0x180008bc5  mov     [rbp+2210h+var_2270], rdi
0x180008bc9  mov     [rbp+2210h+var_2268], rdi
0x180008bcd  movzx   eax, word ptr [rsi]
0x180008bd0  test    ax, ax
0x180008bd3  jz      short loc_180008BFA
0x180008bd5  mov     rcx, rsi; lpsz
0x180008bd8  cmp     ax, 5Ch ; '\'
0x180008bdc  jz      short loc_180008BF1
0x180008bde  call    cs:__imp_CharNextW
0x180008be4  mov     rcx, rax
0x180008be7  movzx   eax, word ptr [rax]
0x180008bea  test    ax, ax
0x180008bed  jnz     short loc_180008BD8
0x180008bef  jmp     short loc_180008BFA
0x180008bf1  test    rcx, rcx
0x180008bf4  jnz     loc_180009258
0x180008bfa  mov     edx, edi
0x180008bfc  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180008c03  mov     rdx, [rax+rdx*8]; lpString2
0x180008c07  mov     rcx, rsi; lpString1
0x180008c0a  call    cs:__imp_lstrcmpiW
0x180008c10  test    eax, eax
0x180008c12  jz      short loc_180008C2B
0x180008c14  inc     edi
0x180008c16  cmp     edi, 0Ch
0x180008c19  jl      short loc_180008BFA
0x180008c1b  mov     [rbp+2210h+var_2278], r15
0x180008c1f  mov     rdx, rsi; unsigned __int16 *
0x180008c22  lea     rcx, [rbp+2210h+var_2278]; this
0x180008c26  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180008c2b  xor     edi, edi
0x180008c2d  test    r14d, r14d
0x180008c30  jnz     short loc_180008C63
0x180008c32  mov     rdx, rsi; unsigned __int16 *
0x180008c35  mov     rcx, r13; this
0x180008c38  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008c3d  mov     edi, eax
0x180008c3f  test    eax, eax
0x180008c41  js      loc_18000920C
0x180008c47  mov     rdx, rsi; unsigned __int16 *
0x180008c4a  mov     rcx, r13; this
0x180008c4d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180008c52  mov     edi, eax
0x180008c54  xor     ecx, ecx
0x180008c56  test    eax, eax
0x180008c58  js      loc_18000920C
0x180008c5e  jmp     loc_180008F0A
0x180008c63  mov     r12d, 1
0x180008c69  lea     rdx, aNoremove; "NoRemove"
0x180008c70  mov     rcx, rsi; lpString1
0x180008c73  call    cs:__imp_lstrcmpiW
0x180008c79  test    eax, eax
0x180008c7b  jnz     short loc_180008C97
0x180008c7d  mov     r12d, edi
0x180008c80  mov     rdx, rsi; unsigned __int16 *
0x180008c83  mov     rcx, r13; this
0x180008c86  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008c8b  mov     edi, eax
0x180008c8d  test    eax, eax
0x180008c8f  js      loc_18000920C
0x180008c95  xor     edi, edi
0x180008c97  lea     rdx, aVal; "Val"
0x180008c9e  mov     rcx, rsi; lpString1
0x180008ca1  call    cs:__imp_lstrcmpiW
0x180008ca7  test    eax, eax
0x180008ca9  jnz     loc_180008D98
0x180008caf  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180008cb6  mov     rcx, r13; this
0x180008cb9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008cbe  mov     edi, eax
0x180008cc0  test    eax, eax
0x180008cc2  js      loc_18000920C
0x180008cc8  mov     rdx, rsi; unsigned __int16 *
0x180008ccb  mov     rcx, r13; this
0x180008cce  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008cd3  mov     edi, eax
0x180008cd5  test    eax, eax
0x180008cd7  js      loc_18000920C
0x180008cdd  cmp     word ptr [rsi], 3Dh ; '='
0x180008ce1  jnz     loc_180009258
0x180008ce7  xor     edi, edi
0x180008ce9  cmp     [rsp+2310h+var_22A8], edi
0x180008ced  jz      short loc_180008D18
0x180008cef  mov     [rbp+2210h+var_2270], rdi
0x180008cf3  mov     [rbp+2210h+var_2268], rdi
0x180008cf7  mov     [rbp+2210h+var_2278], r15
0x180008cfb  mov     r9, rsi; unsigned __int16 *
0x180008cfe  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180008d05  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180008d09  mov     rcx, r13; this
0x180008d0c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180008d11  mov     edi, eax
0x180008d13  jmp     loc_180008EFB
0x180008d18  cmp     [rbp+2210h+arg_20], edi
0x180008d1e  jnz     short loc_180008D7E
0x180008d20  test    r12d, r12d
0x180008d23  jz      short loc_180008D7E
0x180008d25  mov     [rsp+2310h+hKey], rdi
0x180008d2a  lea     rax, [rsp+2310h+hKey]
0x180008d2f  mov     [rsp+2310h+phkResult], rax; phkResult
0x180008d34  mov     r9d, 20006h; samDesired
0x180008d3a  xor     r8d, r8d; ulOptions
0x180008d3d  xor     edx, edx; lpSubKey
0x180008d3f  mov     rcx, r15; hKey
0x180008d42  call    cs:__imp_RegOpenKeyExW
0x180008d48  test    eax, eax
0x180008d4a  jnz     loc_180009203
0x180008d50  mov     r14, [rsp+2310h+hKey]
0x180008d55  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180008d5c  mov     rcx, r14; hKey
0x180008d5f  call    cs:__imp_RegDeleteValueW
0x180008d65  test    eax, 0FFFFFFFDh
0x180008d6a  jnz     loc_18000923F
0x180008d70  test    r14, r14
0x180008d73  jz      short loc_180008D7E
0x180008d75  mov     rcx, r14; hKey
0x180008d78  call    cs:__imp_RegCloseKey
0x180008d7e  mov     rdx, rsi; unsigned __int16 *
0x180008d81  mov     rcx, r13; this
0x180008d84  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180008d89  mov     edi, eax
0x180008d8b  test    eax, eax
0x180008d8d  js      loc_18000920C
0x180008d93  jmp     loc_1800090A5
0x180008d98  movzx   eax, word ptr [rsi]
0x180008d9b  test    ax, ax
0x180008d9e  jz      short loc_180008DC5
0x180008da0  mov     rcx, rsi; lpsz
0x180008da3  cmp     ax, 5Ch ; '\'
0x180008da7  jz      short loc_180008DBC
0x180008da9  call    cs:__imp_CharNextW
0x180008daf  mov     rcx, rax
0x180008db2  movzx   eax, word ptr [rax]
0x180008db5  test    ax, ax
0x180008db8  jnz     short loc_180008DA3
0x180008dba  jmp     short loc_180008DC5
0x180008dbc  test    rcx, rcx
0x180008dbf  jnz     loc_180009258
0x180008dc5  cmp     [rsp+2310h+var_22A8], edi
0x180008dc9  jz      loc_180008F5E
0x180008dcf  mov     [rsp+2310h+hKey], rdi
0x180008dd4  lea     rax, [rsp+2310h+hKey]
0x180008dd9  mov     [rsp+2310h+phkResult], rax; phkResult
0x180008dde  mov     r14d, 2001Fh
0x180008de4  mov     r9d, r14d; samDesired
0x180008de7  xor     r8d, r8d; ulOptions
0x180008dea  mov     rdx, rsi; lpSubKey
0x180008ded  mov     rcx, r15; hKey
0x180008df0  call    cs:__imp_RegOpenKeyExW
0x180008df6  test    eax, eax
0x180008df8  jnz     short loc_180008E1B
0x180008dfa  mov     eax, edi
0x180008dfc  test    rbx, rbx
0x180008dff  jz      short loc_180008E0A
0x180008e01  mov     rcx, rbx; hKey
0x180008e04  call    cs:__imp_RegCloseKey
0x180008e0a  mov     rbx, [rsp+2310h+hKey]
0x180008e0f  mov     [rbp+2210h+var_2290], rbx
0x180008e13  test    eax, eax
0x180008e15  jz      loc_180008EC6
0x180008e1b  mov     [rsp+2310h+hKey], rdi
0x180008e20  lea     rax, [rsp+2310h+hKey]
0x180008e25  mov     [rsp+2310h+phkResult], rax; phkResult
0x180008e2a  mov     r9d, 20019h; samDesired
0x180008e30  xor     r8d, r8d; ulOptions
0x180008e33  mov     rdx, rsi; lpSubKey
0x180008e36  mov     rcx, r15; hKey
0x180008e39  call    cs:__imp_RegOpenKeyExW
0x180008e3f  test    eax, eax
0x180008e41  jnz     short loc_180008E60
0x180008e43  mov     eax, edi
0x180008e45  test    rbx, rbx
0x180008e48  jz      short loc_180008E53
0x180008e4a  mov     rcx, rbx; hKey
0x180008e4d  call    cs:__imp_RegCloseKey
0x180008e53  mov     rbx, [rsp+2310h+hKey]
0x180008e58  mov     [rbp+2210h+var_2290], rbx
0x180008e5c  test    eax, eax
0x180008e5e  jz      short loc_180008EC6
0x180008e60  mov     dword ptr [rsp+2310h+hKey], edi
0x180008e64  mov     [rsp+2310h+var_2298], rdi
0x180008e69  lea     rax, [rsp+2310h+hKey]
0x180008e6e  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180008e73  lea     rax, [rsp+2310h+var_2298]
0x180008e78  mov     [rsp+2310h+var_22D8], rax; phkResult
0x180008e7d  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180008e82  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180008e87  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180008e8b  xor     r9d, r9d; lpClass
0x180008e8e  xor     r8d, r8d; Reserved
0x180008e91  mov     rdx, rsi; lpSubKey
0x180008e94  mov     rcx, r15; hKey
0x180008e97  call    cs:__imp_RegCreateKeyExW
0x180008e9d  test    eax, eax
0x180008e9f  jnz     loc_180009203
0x180008ea5  mov     eax, edi
0x180008ea7  test    rbx, rbx
0x180008eaa  jz      short loc_180008EB5
0x180008eac  mov     rcx, rbx; hKey
0x180008eaf  call    cs:__imp_RegCloseKey
0x180008eb5  mov     rbx, [rsp+2310h+var_2298]
0x180008eba  mov     [rbp+2210h+var_2290], rbx
0x180008ebe  test    eax, eax
0x180008ec0  jnz     loc_180009203
0x180008ec6  mov     rdx, rsi; unsigned __int16 *
0x180008ec9  mov     rcx, r13; this
0x180008ecc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008ed1  mov     edi, eax
0x180008ed3  xor     ecx, ecx
0x180008ed5  test    eax, eax
0x180008ed7  js      loc_18000920C
0x180008edd  cmp     word ptr [rsi], 3Dh ; '='
0x180008ee1  jnz     short loc_180008F05
0x180008ee3  mov     r9, rsi; unsigned __int16 *
0x180008ee6  xor     r8d, r8d; unsigned __int16 *
0x180008ee9  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180008eed  mov     rcx, r13; this
0x180008ef0  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180008ef5  mov     edi, eax
0x180008ef7  mov     rbx, [rbp+2210h+var_2290]
0x180008efb  test    eax, eax
0x180008efd  js      loc_18000920C
0x180008f03  xor     ecx, ecx
0x180008f05  mov     r12d, [rsp+2310h+var_22A8]
0x180008f0a  cmp     word ptr [rsi], 7Bh ; '{'
0x180008f0e  jnz     loc_1800090A5
0x180008f14  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008f18  inc     rax
0x180008f1b  cmp     [rsi+rax*2], cx
0x180008f1f  jnz     short loc_180008F18
0x180008f21  cmp     rax, 1
0x180008f25  jnz     loc_1800090A5
0x180008f2b  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x180008f33  mov     r9d, r12d; int
0x180008f36  mov     r8, rbx; HKEY
0x180008f39  mov     rdx, rsi; unsigned __int16 *
0x180008f3c  mov     rcx, r13; this
0x180008f3f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008f44  mov     edi, eax
0x180008f46  test    eax, eax
0x180008f48  js      loc_18000920C
0x180008f4e  mov     rdx, rsi; unsigned __int16 *
0x180008f51  mov     rcx, r13; this
0x180008f54  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008f59  jmp     loc_180008D89
  ... truncated ...
```
