# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x140005098`
- end: `0x14000582f`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x140004d28`
- `0x140005098`

## callees

- `0x140002bec`
- `0x14000331c`
- `0x140003b88`
- `0x140003ca4`
- `0x140004070`
- `0x140004bd8`
- `0x140005098`
- `0x140005af0`
- `0x140011e10`
- `0x140011ed0`

## import_xrefs

- `USER32!CharNextW` at `0x14000517a`
- `USER32!CharNextW` at `0x140005345`
- `USER32!CharNextW` at `0x14000517a`
- `USER32!CharNextW` at `0x140005345`
- `msvcrt!wcsncpy_s` at `0x140005576`
- `msvcrt!wcsncpy_s` at `0x140005576`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400052de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000538c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400053d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140005524`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400052de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000538c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400053d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140005524`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400056a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140005738`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400056a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140005738`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005314`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400053a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400053e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000544b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000553f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005756`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400057b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400057ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400057fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005314`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400053a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400053e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000544b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000553f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005756`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400057b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400057ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400057fc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140005433`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140005433`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400052fb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400052fb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140005115`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140005128`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400051a6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14000520f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14000523d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400056c5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140005115`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140005128`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400051a6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14000520f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14000523d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400056c5`

## string_xrefs

- `0x14000511e`: `ForceRemove`
- `0x140005205`: `NoRemove`
- `0x14000510b`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(LPCWSTR *this, unsigned __int16 *a2, HKEY a3, int a4, int a5)
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
  errno_t v29; // eax
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
            ATL::CRegKey::RecurseDeleteKey(&v38, a2);
            break;
          }
        }
        if ( !v12 )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_111;
          Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
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
        v17 = ATL::CRegParser::AddValue(this, v37, 0, a2);
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
      Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v9, v5, 0);
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
    Token = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
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
        Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, a2, v9, 0, v28);
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
                ATL::CRegKey::RecurseDeleteKey(v37, Destination);
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
    v17 = ATL::CRegParser::AddValue(this, &v38, ValueName, a2);
    Token = v17;
LABEL_59:
    if ( v17 < 0 )
      goto LABEL_111;
    goto LABEL_60;
  }
  if ( a5 || !v16 )
  {
LABEL_34:
    v21 = ATL::CRegParser::SkipAssignment((ATL::CRegParser *)this, a2);
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
0x140005098  push    rbp
0x14000509a  push    rbx
0x14000509b  push    rsi
0x14000509c  push    rdi
0x14000509d  push    r12
0x14000509f  push    r13
0x1400050a1  push    r14
0x1400050a3  push    r15
0x1400050a5  lea     rbp, [rsp-21D8h]
0x1400050ad  mov     eax, 22D8h
0x1400050b2  call    _alloca_probe
0x1400050b7  sub     rsp, rax
0x1400050ba  mov     rax, cs:__security_cookie
0x1400050c1  xor     rax, rsp
0x1400050c4  mov     [rbp+2210h+var_50], rax
0x1400050cb  mov     r12d, r9d
0x1400050ce  mov     [rsp+2310h+var_22A8], r9d
0x1400050d3  mov     r15, r8
0x1400050d6  mov     [rsp+2310h+var_22A0], r8
0x1400050db  mov     rsi, rdx
0x1400050de  mov     r13, rcx
0x1400050e1  xor     eax, eax
0x1400050e3  mov     ebx, eax
0x1400050e5  mov     [rbp+2210h+var_2290], rax
0x1400050e9  mov     [rbp+2210h+var_2288], rax
0x1400050ed  mov     [rbp+2210h+var_2280], rax
0x1400050f1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400050f6  mov     edi, eax
0x1400050f8  test    eax, eax
0x1400050fa  jns     short loc_140005101
0x1400050fc  jmp     loc_1400057B8
0x140005101  cmp     word ptr [rsi], 7Dh ; '}'
0x140005105  jz      loc_1400057A8
0x14000510b  lea     rdx, String2; "Delete"
0x140005112  mov     rcx, rsi; lpString1
0x140005115  call    cs:__imp_lstrcmpiW
0x14000511b  mov     r14d, eax
0x14000511e  lea     rdx, aForceremove; "ForceRemove"
0x140005125  mov     rcx, rsi; lpString1
0x140005128  call    cs:__imp_lstrcmpiW
0x14000512e  xor     edi, edi
0x140005130  test    eax, eax
0x140005132  jz      short loc_14000513D
0x140005134  test    r14d, r14d
0x140005137  jnz     loc_1400051FF
0x14000513d  mov     rdx, rsi; unsigned __int16 *
0x140005140  mov     rcx, r13; this
0x140005143  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140005148  mov     edi, eax
0x14000514a  test    eax, eax
0x14000514c  js      loc_1400057A8
0x140005152  xor     edi, edi
0x140005154  test    r12d, r12d
0x140005157  jz      loc_1400051FF
0x14000515d  mov     [rbp+2210h+var_2278], rdi
0x140005161  mov     [rbp+2210h+var_2270], rdi
0x140005165  mov     [rbp+2210h+var_2268], rdi
0x140005169  movzx   eax, word ptr [rsi]
0x14000516c  test    ax, ax
0x14000516f  jz      short loc_140005196
0x140005171  mov     rcx, rsi; lpsz
0x140005174  cmp     ax, 5Ch ; '\'
0x140005178  jz      short loc_14000518D
0x14000517a  call    cs:__imp_CharNextW
0x140005180  mov     rcx, rax
0x140005183  movzx   eax, word ptr [rax]
0x140005186  test    ax, ax
0x140005189  jnz     short loc_140005174
0x14000518b  jmp     short loc_140005196
0x14000518d  test    rcx, rcx
0x140005190  jnz     loc_1400057F4
0x140005196  mov     edx, edi
0x140005198  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x14000519f  mov     rdx, [rax+rdx*8]; lpString2
0x1400051a3  mov     rcx, rsi; lpString1
0x1400051a6  call    cs:__imp_lstrcmpiW
0x1400051ac  test    eax, eax
0x1400051ae  jz      short loc_1400051C7
0x1400051b0  inc     edi
0x1400051b2  cmp     edi, 0Ch
0x1400051b5  jl      short loc_140005196
0x1400051b7  mov     [rbp+2210h+var_2278], r15
0x1400051bb  mov     rdx, rsi; unsigned __int16 *
0x1400051be  lea     rcx, [rbp+2210h+var_2278]; this
0x1400051c2  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1400051c7  xor     edi, edi
0x1400051c9  test    r14d, r14d
0x1400051cc  jnz     short loc_1400051FF
0x1400051ce  mov     rdx, rsi; unsigned __int16 *
0x1400051d1  mov     rcx, r13; this
0x1400051d4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400051d9  mov     edi, eax
0x1400051db  test    eax, eax
0x1400051dd  js      loc_1400057A8
0x1400051e3  mov     rdx, rsi; unsigned __int16 *
0x1400051e6  mov     rcx, r13; this
0x1400051e9  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1400051ee  mov     edi, eax
0x1400051f0  xor     ecx, ecx
0x1400051f2  test    eax, eax
0x1400051f4  js      loc_1400057A8
0x1400051fa  jmp     loc_1400054A6
0x1400051ff  mov     r12d, 1
0x140005205  lea     rdx, aNoremove; "NoRemove"
0x14000520c  mov     rcx, rsi; lpString1
0x14000520f  call    cs:__imp_lstrcmpiW
0x140005215  test    eax, eax
0x140005217  jnz     short loc_140005233
0x140005219  mov     r12d, edi
0x14000521c  mov     rdx, rsi; unsigned __int16 *
0x14000521f  mov     rcx, r13; this
0x140005222  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140005227  mov     edi, eax
0x140005229  test    eax, eax
0x14000522b  js      loc_1400057A8
0x140005231  xor     edi, edi
0x140005233  lea     rdx, aVal; "Val"
0x14000523a  mov     rcx, rsi; lpString1
0x14000523d  call    cs:__imp_lstrcmpiW
0x140005243  test    eax, eax
0x140005245  jnz     loc_140005334
0x14000524b  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x140005252  mov     rcx, r13; this
0x140005255  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000525a  mov     edi, eax
0x14000525c  test    eax, eax
0x14000525e  js      loc_1400057A8
0x140005264  mov     rdx, rsi; unsigned __int16 *
0x140005267  mov     rcx, r13; this
0x14000526a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000526f  mov     edi, eax
0x140005271  test    eax, eax
0x140005273  js      loc_1400057A8
0x140005279  cmp     word ptr [rsi], 3Dh ; '='
0x14000527d  jnz     loc_1400057F4
0x140005283  xor     edi, edi
0x140005285  cmp     [rsp+2310h+var_22A8], edi
0x140005289  jz      short loc_1400052B4
0x14000528b  mov     [rbp+2210h+var_2270], rdi
0x14000528f  mov     [rbp+2210h+var_2268], rdi
0x140005293  mov     [rbp+2210h+var_2278], r15
0x140005297  mov     r9, rsi; unsigned __int16 *
0x14000529a  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x1400052a1  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x1400052a5  mov     rcx, r13; this
0x1400052a8  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1400052ad  mov     edi, eax
0x1400052af  jmp     loc_140005497
0x1400052b4  cmp     [rbp+2210h+arg_20], edi
0x1400052ba  jnz     short loc_14000531A
0x1400052bc  test    r12d, r12d
0x1400052bf  jz      short loc_14000531A
0x1400052c1  mov     [rsp+2310h+hKey], rdi
0x1400052c6  lea     rax, [rsp+2310h+hKey]
0x1400052cb  mov     [rsp+2310h+phkResult], rax; phkResult
0x1400052d0  mov     r9d, 20006h; samDesired
0x1400052d6  xor     r8d, r8d; ulOptions
0x1400052d9  xor     edx, edx; lpSubKey
0x1400052db  mov     rcx, r15; hKey
0x1400052de  call    cs:__imp_RegOpenKeyExW
0x1400052e4  test    eax, eax
0x1400052e6  jnz     loc_14000579F
0x1400052ec  mov     r14, [rsp+2310h+hKey]
0x1400052f1  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x1400052f8  mov     rcx, r14; hKey
0x1400052fb  call    cs:__imp_RegDeleteValueW
0x140005301  test    eax, 0FFFFFFFDh
0x140005306  jnz     loc_1400057DB
0x14000530c  test    r14, r14
0x14000530f  jz      short loc_14000531A
0x140005311  mov     rcx, r14; hKey
0x140005314  call    cs:__imp_RegCloseKey
0x14000531a  mov     rdx, rsi; unsigned __int16 *
0x14000531d  mov     rcx, r13; this
0x140005320  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x140005325  mov     edi, eax
0x140005327  test    eax, eax
0x140005329  js      loc_1400057A8
0x14000532f  jmp     loc_140005641
0x140005334  movzx   eax, word ptr [rsi]
0x140005337  test    ax, ax
0x14000533a  jz      short loc_140005361
0x14000533c  mov     rcx, rsi; lpsz
0x14000533f  cmp     ax, 5Ch ; '\'
0x140005343  jz      short loc_140005358
0x140005345  call    cs:__imp_CharNextW
0x14000534b  mov     rcx, rax
0x14000534e  movzx   eax, word ptr [rax]
0x140005351  test    ax, ax
0x140005354  jnz     short loc_14000533F
0x140005356  jmp     short loc_140005361
0x140005358  test    rcx, rcx
0x14000535b  jnz     loc_1400057F4
0x140005361  cmp     [rsp+2310h+var_22A8], edi
0x140005365  jz      loc_1400054FA
0x14000536b  mov     [rsp+2310h+hKey], rdi
0x140005370  lea     rax, [rsp+2310h+hKey]
0x140005375  mov     [rsp+2310h+phkResult], rax; phkResult
0x14000537a  mov     r14d, 2001Fh
0x140005380  mov     r9d, r14d; samDesired
0x140005383  xor     r8d, r8d; ulOptions
0x140005386  mov     rdx, rsi; lpSubKey
0x140005389  mov     rcx, r15; hKey
0x14000538c  call    cs:__imp_RegOpenKeyExW
0x140005392  test    eax, eax
0x140005394  jnz     short loc_1400053B7
0x140005396  mov     eax, edi
0x140005398  test    rbx, rbx
0x14000539b  jz      short loc_1400053A6
0x14000539d  mov     rcx, rbx; hKey
0x1400053a0  call    cs:__imp_RegCloseKey
0x1400053a6  mov     rbx, [rsp+2310h+hKey]
0x1400053ab  mov     [rbp+2210h+var_2290], rbx
0x1400053af  test    eax, eax
0x1400053b1  jz      loc_140005462
0x1400053b7  mov     [rsp+2310h+hKey], rdi
0x1400053bc  lea     rax, [rsp+2310h+hKey]
0x1400053c1  mov     [rsp+2310h+phkResult], rax; phkResult
0x1400053c6  mov     r9d, 20019h; samDesired
0x1400053cc  xor     r8d, r8d; ulOptions
0x1400053cf  mov     rdx, rsi; lpSubKey
0x1400053d2  mov     rcx, r15; hKey
0x1400053d5  call    cs:__imp_RegOpenKeyExW
0x1400053db  test    eax, eax
0x1400053dd  jnz     short loc_1400053FC
0x1400053df  mov     eax, edi
0x1400053e1  test    rbx, rbx
0x1400053e4  jz      short loc_1400053EF
0x1400053e6  mov     rcx, rbx; hKey
0x1400053e9  call    cs:__imp_RegCloseKey
0x1400053ef  mov     rbx, [rsp+2310h+hKey]
0x1400053f4  mov     [rbp+2210h+var_2290], rbx
0x1400053f8  test    eax, eax
0x1400053fa  jz      short loc_140005462
0x1400053fc  mov     dword ptr [rsp+2310h+hKey], edi
0x140005400  mov     [rsp+2310h+var_2298], rdi
0x140005405  lea     rax, [rsp+2310h+hKey]
0x14000540a  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x14000540f  lea     rax, [rsp+2310h+var_2298]
0x140005414  mov     [rsp+2310h+var_22D8], rax; phkResult
0x140005419  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x14000541e  mov     [rsp+2310h+samDesired], r14d; samDesired
0x140005423  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x140005427  xor     r9d, r9d; lpClass
0x14000542a  xor     r8d, r8d; Reserved
0x14000542d  mov     rdx, rsi; lpSubKey
0x140005430  mov     rcx, r15; hKey
0x140005433  call    cs:__imp_RegCreateKeyExW
0x140005439  test    eax, eax
0x14000543b  jnz     loc_14000579F
0x140005441  mov     eax, edi
0x140005443  test    rbx, rbx
0x140005446  jz      short loc_140005451
0x140005448  mov     rcx, rbx; hKey
0x14000544b  call    cs:__imp_RegCloseKey
0x140005451  mov     rbx, [rsp+2310h+var_2298]
0x140005456  mov     [rbp+2210h+var_2290], rbx
0x14000545a  test    eax, eax
0x14000545c  jnz     loc_14000579F
0x140005462  mov     rdx, rsi; unsigned __int16 *
0x140005465  mov     rcx, r13; this
0x140005468  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000546d  mov     edi, eax
0x14000546f  xor     ecx, ecx
0x140005471  test    eax, eax
0x140005473  js      loc_1400057A8
0x140005479  cmp     word ptr [rsi], 3Dh ; '='
0x14000547d  jnz     short loc_1400054A1
0x14000547f  mov     r9, rsi; unsigned __int16 *
0x140005482  xor     r8d, r8d; unsigned __int16 *
0x140005485  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x140005489  mov     rcx, r13; this
0x14000548c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x140005491  mov     edi, eax
0x140005493  mov     rbx, [rbp+2210h+var_2290]
0x140005497  test    eax, eax
0x140005499  js      loc_1400057A8
0x14000549f  xor     ecx, ecx
0x1400054a1  mov     r12d, [rsp+2310h+var_22A8]
0x1400054a6  cmp     word ptr [rsi], 7Bh ; '{'
0x1400054aa  jnz     loc_140005641
0x1400054b0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400054b4  inc     rax
0x1400054b7  cmp     [rsi+rax*2], cx
0x1400054bb  jnz     short loc_1400054B4
0x1400054bd  cmp     rax, 1
0x1400054c1  jnz     loc_140005641
0x1400054c7  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x1400054cf  mov     r9d, r12d; int
0x1400054d2  mov     r8, rbx; HKEY
0x1400054d5  mov     rdx, rsi; unsigned __int16 *
0x1400054d8  mov     rcx, r13; this
0x1400054db  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1400054e0  mov     edi, eax
0x1400054e2  test    eax, eax
0x1400054e4  js      loc_1400057A8
0x1400054ea  mov     rdx, rsi; unsigned __int16 *
0x1400054ed  mov     rcx, r13; this
0x1400054f0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400054f5  jmp     loc_140005325
  ... truncated ...
```
