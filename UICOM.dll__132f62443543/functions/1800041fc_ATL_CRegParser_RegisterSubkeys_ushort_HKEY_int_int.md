# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800041fc`
- end: `0x180004999`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1949`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180003ea8`
- `0x1800041fc`

## callees

- `0x1800026a4`
- `0x180002cfc`
- `0x180003558`
- `0x180003640`
- `0x1800038f4`
- `0x180003d58`
- `0x1800041fc`
- `0x1800049ac`
- `0x180005f60`
- `0x180005ff0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800046d3`
- `msvcrt!wcsncpy_s` at `0x1800046d3`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800047fa`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004893`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800047fa`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004893`
- `ADVAPI32!RegCreateKeyExW` at `0x180004594`
- `ADVAPI32!RegCreateKeyExW` at `0x180004594`
- `ADVAPI32!RegOpenKeyExW` at `0x18000443f`
- `ADVAPI32!RegOpenKeyExW` at `0x1800044ed`
- `ADVAPI32!RegOpenKeyExW` at `0x180004536`
- `ADVAPI32!RegOpenKeyExW` at `0x180004681`
- `ADVAPI32!RegOpenKeyExW` at `0x18000443f`
- `ADVAPI32!RegOpenKeyExW` at `0x1800044ed`
- `ADVAPI32!RegOpenKeyExW` at `0x180004536`
- `ADVAPI32!RegOpenKeyExW` at `0x180004681`
- `ADVAPI32!RegDeleteValueW` at `0x18000445c`
- `ADVAPI32!RegDeleteValueW` at `0x18000445c`
- `ADVAPI32!RegCloseKey` at `0x180004475`
- `ADVAPI32!RegCloseKey` at `0x180004501`
- `ADVAPI32!RegCloseKey` at `0x18000454a`
- `ADVAPI32!RegCloseKey` at `0x1800045ac`
- `ADVAPI32!RegCloseKey` at `0x18000469c`
- `ADVAPI32!RegCloseKey` at `0x1800048b2`
- `ADVAPI32!RegCloseKey` at `0x180004911`
- `ADVAPI32!RegCloseKey` at `0x18000494d`
- `ADVAPI32!RegCloseKey` at `0x18000495d`
- `ADVAPI32!RegCloseKey` at `0x180004475`
- `ADVAPI32!RegCloseKey` at `0x180004501`
- `ADVAPI32!RegCloseKey` at `0x18000454a`
- `ADVAPI32!RegCloseKey` at `0x1800045ac`
- `ADVAPI32!RegCloseKey` at `0x18000469c`
- `ADVAPI32!RegCloseKey` at `0x1800048b2`
- `ADVAPI32!RegCloseKey` at `0x180004911`
- `ADVAPI32!RegCloseKey` at `0x18000494d`
- `ADVAPI32!RegCloseKey` at `0x18000495d`
- `KERNEL32!lstrcmpiW` at `0x18000427a`
- `KERNEL32!lstrcmpiW` at `0x18000428d`
- `KERNEL32!lstrcmpiW` at `0x18000430b`
- `KERNEL32!lstrcmpiW` at `0x180004374`
- `KERNEL32!lstrcmpiW` at `0x1800043a2`
- `KERNEL32!lstrcmpiW` at `0x180004821`
- `KERNEL32!lstrcmpiW` at `0x18000427a`
- `KERNEL32!lstrcmpiW` at `0x18000428d`
- `KERNEL32!lstrcmpiW` at `0x18000430b`
- `KERNEL32!lstrcmpiW` at `0x180004374`
- `KERNEL32!lstrcmpiW` at `0x1800043a2`
- `KERNEL32!lstrcmpiW` at `0x180004821`
- `USER32!CharNextW` at `0x1800042df`
- `USER32!CharNextW` at `0x1800044a6`
- `USER32!CharNextW` at `0x1800042df`
- `USER32!CharNextW` at `0x1800044a6`

## string_xrefs

- `0x180004280`: `ForceRemove`
- `0x180004364`: `NoRemove`
- `0x180004270`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  HKEY v5; // rbx
  int v6; // r12d
  HKEY v7; // r15
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
  int v32; // r14d
  LSTATUS v33; // eax
  unsigned int v34; // ecx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+68h] [rbp-98h]
  HKEY v37; // [rsp+70h] [rbp-90h]
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v39[3]; // [rsp+80h] [rbp-80h] BYREF
  HKEY v40; // [rsp+98h] [rbp-68h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-60h]
  __int64 v42; // [rsp+A8h] [rbp-58h]
  wchar_t Destination[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v36 = a4;
  v5 = 0;
  v37 = a3;
  memset(v39, 0, sizeof(v39));
  v6 = a4;
  v7 = a3;
  result = ATL::CRegParser::NextToken(this, a2);
  Token = result;
  if ( (int)result < 0 )
    return result;
  if ( *a2 == 125 )
    return (unsigned int)Token;
  while ( 1 )
  {
    v12 = lstrcmpiW(a2, L"Delete");
    if ( !lstrcmpiW(a2, L"ForceRemove") || !v12 )
    {
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
      v13 = 0;
      if ( v6 )
      {
        v14 = *a2;
        v40 = 0;
        v41 = 0;
        v42 = 0;
        if ( !v14 )
          goto LABEL_13;
        v15 = a2;
        do
        {
          if ( v14 == 92 )
          {
            if ( !v15 )
              break;
            goto LABEL_118;
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
            v40 = v7;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v40, a2);
            break;
          }
        }
        if ( !v12 )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_112;
          Token = ATL::CRegParser::SkipAssignment(this, a2);
          if ( Token < 0 )
            goto LABEL_112;
LABEL_61:
          if ( *a2 != 123 )
            goto LABEL_93;
          v26 = -1;
          do
            ++v26;
          while ( a2[v26] );
          if ( v26 != 1 )
            goto LABEL_93;
          Token = ATL::CRegParser::RegisterSubkeys(this, a2, v5, v6, 0);
          if ( Token < 0 )
            goto LABEL_112;
          v21 = ATL::CRegParser::NextToken(this, a2);
          goto LABEL_35;
        }
      }
    }
    v16 = 1;
    if ( !lstrcmpiW(a2, L"NoRemove") )
    {
      v16 = 0;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
    }
    if ( !lstrcmpiW(a2, L"Val") )
    {
      Token = ATL::CRegParser::NextToken(this, ValueName);
      if ( Token < 0 )
        goto LABEL_112;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
      if ( *a2 != 61 )
        break;
      if ( v36 )
      {
        v41 = 0;
        v42 = 0;
        v40 = v7;
        v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)&v40, ValueName, a2);
LABEL_59:
        Token = v17;
        if ( v17 < 0 )
          goto LABEL_112;
        goto LABEL_60;
      }
      if ( !a5 && v16 )
      {
        hKey = 0;
        v18 = RegOpenKeyExW(v7, 0, 0, 0x20006u, &hKey);
        if ( v18 )
          goto LABEL_110;
        v19 = hKey;
        v20 = RegDeleteValueW(hKey, ValueName);
        if ( (v20 & 0xFFFFFFFD) != 0 )
        {
          Token = ATL::AtlHresultFromWin32(v20);
          if ( v19 )
            RegCloseKey(v19);
          goto LABEL_112;
        }
        if ( v19 )
          RegCloseKey(v19);
      }
      v21 = ATL::CRegParser::SkipAssignment(this, a2);
LABEL_35:
      Token = v21;
      if ( v21 < 0 )
        goto LABEL_112;
      goto LABEL_93;
    }
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
        break;
    }
LABEL_43:
    if ( v36 )
    {
      hKey = 0;
      if ( RegOpenKeyExW(v7, a2, 0, 0x2001Fu, &hKey) )
        goto LABEL_128;
      v24 = 0;
      if ( v5 )
        v24 = RegCloseKey(v5);
      v5 = hKey;
      v39[0] = hKey;
      if ( v24 )
      {
LABEL_128:
        hKey = 0;
        if ( RegOpenKeyExW(v7, a2, 0, 0x20019u, &hKey) )
          goto LABEL_129;
        v25 = 0;
        if ( v5 )
          v25 = RegCloseKey(v5);
        v5 = hKey;
        v39[0] = hKey;
        if ( v25 )
        {
LABEL_129:
          LODWORD(hKey) = 0;
          phkResult = 0;
          v18 = RegCreateKeyExW(v7, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, (LPDWORD)&hKey);
          if ( v18 )
            goto LABEL_110;
          v18 = 0;
          if ( v5 )
            v18 = RegCloseKey(v5);
          v5 = phkResult;
          v39[0] = phkResult;
          if ( v18 )
          {
LABEL_110:
            v34 = v18;
            goto LABEL_111;
          }
        }
      }
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_112;
      if ( *a2 == 61 )
      {
        v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)v39, 0, a2);
        v5 = (HKEY)v39[0];
        goto LABEL_59;
      }
LABEL_60:
      v6 = v36;
      goto LABEL_61;
    }
    if ( a5 )
    {
      v27 = 2;
    }
    else
    {
      phkResult = 0;
      v27 = RegOpenKeyExW(v7, a2, 0, 0x20019u, &phkResult);
      if ( !v27 )
      {
        v27 = 0;
        if ( v5 )
          v27 = RegCloseKey(v5);
        v5 = phkResult;
        v39[0] = phkResult;
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
      goto LABEL_112;
    Token = ATL::CRegParser::SkipAssignment(this, a2);
    if ( Token < 0 )
      goto LABEL_112;
    if ( *a2 == 123 )
    {
      v30 = -1;
      do
        ++v30;
      while ( a2[v30] );
      if ( v30 == 1 )
      {
        Token = ATL::CRegParser::RegisterSubkeys(this, a2, v5, 0, v28);
        if ( Token < 0 && !v28 )
          goto LABEL_112;
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_112;
      }
    }
    if ( v27 == 2 )
      goto LABEL_92;
    if ( v27 )
    {
      if ( a5 )
      {
LABEL_92:
        v7 = v37;
        goto LABEL_93;
      }
      v34 = v27;
LABEL_111:
      Token = ATL::AtlHresultFromWin32(v34);
LABEL_112:
      if ( v5 )
        RegCloseKey(v5);
      return (unsigned int)Token;
    }
    if ( a5 )
    {
      LODWORD(hKey) = 0;
      if ( !RegQueryInfoKeyW(v5, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      {
        if ( (_DWORD)hKey )
        {
          v31 = 0;
          while ( lstrcmpiW(Destination, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v31]) )
          {
            if ( ++v31 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v39, Destination);
                v5 = (HKEY)v39[0];
              }
              goto LABEL_92;
            }
          }
          goto LABEL_92;
        }
      }
    }
    LODWORD(hKey) = 0;
    v32 = 0;
    if ( !RegQueryInfoKeyW(v5, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      LOBYTE(v32) = (_DWORD)hKey != 0;
    if ( v5 )
    {
      v33 = RegCloseKey(v5);
      v39[0] = 0;
      v5 = 0;
      if ( v33 )
        return ATL::AtlHresultFromWin32(v33);
    }
    if ( !v16 )
      goto LABEL_92;
    v7 = v37;
    if ( !v32 )
    {
      v41 = 0;
      v42 = 0;
      v40 = v37;
      v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v40, Destination);
      if ( v18 )
        goto LABEL_110;
    }
LABEL_93:
    if ( *a2 == 125 )
      goto LABEL_112;
    v6 = v36;
  }
LABEL_118:
  if ( v5 )
    RegCloseKey(v5);
  return 2147614729LL;
}

```

## disassembly

```asm
0x1800041fc  push    rbp
0x1800041fe  push    rbx
0x1800041ff  push    rsi
0x180004200  push    rdi
0x180004201  push    r12
0x180004203  push    r13
0x180004205  push    r14
0x180004207  push    r15
0x180004209  lea     rbp, [rsp-21D8h]
0x180004211  mov     eax, 22D8h
0x180004216  call    _alloca_probe
0x18000421b  sub     rsp, rax
0x18000421e  mov     rax, cs:__security_cookie
0x180004225  xor     rax, rsp
0x180004228  mov     [rbp+2210h+var_50], rax
0x18000422f  xor     r14d, r14d
0x180004232  mov     [rsp+2310h+var_22A8], r9d
0x180004237  mov     ebx, r14d
0x18000423a  mov     [rsp+2310h+var_22A0], r8
0x18000423f  mov     [rbp+2210h+var_2290], rbx
0x180004243  mov     r12d, r9d
0x180004246  mov     r15, r8
0x180004249  mov     [rbp+2210h+var_2288], r14
0x18000424d  mov     rsi, rdx
0x180004250  mov     [rbp+2210h+var_2280], r14
0x180004254  mov     r13, rcx
0x180004257  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000425c  mov     edi, eax
0x18000425e  test    eax, eax
0x180004260  js      loc_180004919
0x180004266  cmp     word ptr [rsi], 7Dh ; '}'
0x18000426a  jz      loc_180004917
0x180004270  lea     rdx, String2; "Delete"
0x180004277  mov     rcx, rsi; lpString1
0x18000427a  call    cs:__imp_lstrcmpiW
0x180004280  lea     rdx, aForceremove; "ForceRemove"
0x180004287  mov     rcx, rsi; lpString1
0x18000428a  mov     r14d, eax
0x18000428d  call    cs:__imp_lstrcmpiW
0x180004293  xor     edi, edi
0x180004295  test    eax, eax
0x180004297  jz      short loc_1800042A2
0x180004299  test    r14d, r14d
0x18000429c  jnz     loc_180004364
0x1800042a2  mov     rdx, rsi; unsigned __int16 *
0x1800042a5  mov     rcx, r13; this
0x1800042a8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800042ad  mov     edi, eax
0x1800042af  test    eax, eax
0x1800042b1  js      loc_180004909
0x1800042b7  xor     edi, edi
0x1800042b9  test    r12d, r12d
0x1800042bc  jz      loc_180004364
0x1800042c2  movzx   eax, word ptr [rsi]
0x1800042c5  mov     [rbp+2210h+var_2278], rdi
0x1800042c9  mov     [rbp+2210h+var_2270], rdi
0x1800042cd  mov     [rbp+2210h+var_2268], rdi
0x1800042d1  test    ax, ax
0x1800042d4  jz      short loc_1800042FB
0x1800042d6  mov     rcx, rsi; lpsz
0x1800042d9  cmp     ax, 5Ch ; '\'
0x1800042dd  jz      short loc_1800042F2
0x1800042df  call    cs:__imp_CharNextW
0x1800042e5  mov     rcx, rax
0x1800042e8  movzx   eax, word ptr [rax]
0x1800042eb  test    ax, ax
0x1800042ee  jnz     short loc_1800042D9
0x1800042f0  jmp     short loc_1800042FB
0x1800042f2  test    rcx, rcx
0x1800042f5  jnz     loc_180004955
0x1800042fb  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180004302  mov     edx, edi
0x180004304  mov     rcx, rsi; lpString1
0x180004307  mov     rdx, [rax+rdx*8]; lpString2
0x18000430b  call    cs:__imp_lstrcmpiW
0x180004311  test    eax, eax
0x180004313  jz      short loc_18000432C
0x180004315  inc     edi
0x180004317  cmp     edi, 0Ch
0x18000431a  jl      short loc_1800042FB
0x18000431c  mov     rdx, rsi; unsigned __int16 *
0x18000431f  mov     [rbp+2210h+var_2278], r15
0x180004323  lea     rcx, [rbp+2210h+var_2278]; this
0x180004327  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000432c  xor     edi, edi
0x18000432e  test    r14d, r14d
0x180004331  jnz     short loc_180004364
0x180004333  mov     rdx, rsi; unsigned __int16 *
0x180004336  mov     rcx, r13; this
0x180004339  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000433e  mov     edi, eax
0x180004340  test    eax, eax
0x180004342  js      loc_180004909
0x180004348  mov     rdx, rsi; unsigned __int16 *
0x18000434b  mov     rcx, r13; this
0x18000434e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180004353  xor     edx, edx
0x180004355  mov     edi, eax
0x180004357  test    eax, eax
0x180004359  js      loc_180004909
0x18000435f  jmp     loc_180004607
0x180004364  lea     rdx, aNoremove; "NoRemove"
0x18000436b  mov     rcx, rsi; lpString1
0x18000436e  mov     r12d, 1
0x180004374  call    cs:__imp_lstrcmpiW
0x18000437a  test    eax, eax
0x18000437c  jnz     short loc_180004398
0x18000437e  mov     rdx, rsi; unsigned __int16 *
0x180004381  mov     rcx, r13; this
0x180004384  mov     r12d, edi
0x180004387  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000438c  mov     edi, eax
0x18000438e  test    eax, eax
0x180004390  js      loc_180004909
0x180004396  xor     edi, edi
0x180004398  lea     rdx, aVal; "Val"
0x18000439f  mov     rcx, rsi; lpString1
0x1800043a2  call    cs:__imp_lstrcmpiW
0x1800043a8  test    eax, eax
0x1800043aa  jnz     loc_180004495
0x1800043b0  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x1800043b7  mov     rcx, r13; this
0x1800043ba  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800043bf  mov     edi, eax
0x1800043c1  test    eax, eax
0x1800043c3  js      loc_180004909
0x1800043c9  mov     rdx, rsi; unsigned __int16 *
0x1800043cc  mov     rcx, r13; this
0x1800043cf  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800043d4  xor     edx, edx; lpSubKey
0x1800043d6  mov     edi, eax
0x1800043d8  test    eax, eax
0x1800043da  js      loc_180004909
0x1800043e0  cmp     word ptr [rsi], 3Dh ; '='
0x1800043e4  jnz     loc_180004955
0x1800043ea  cmp     [rsp+2310h+var_22A8], edx
0x1800043ee  jz      short loc_180004417
0x1800043f0  mov     [rbp+2210h+var_2270], rdx
0x1800043f4  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x1800043fb  mov     [rbp+2210h+var_2268], rdx
0x1800043ff  mov     r9, rsi; unsigned __int16 *
0x180004402  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180004406  mov     [rbp+2210h+var_2278], r15
0x18000440a  mov     rcx, r13; this
0x18000440d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180004412  jmp     loc_1800045F6
0x180004417  cmp     [rbp+2210h+arg_20], edx
0x18000441d  jnz     short loc_18000447B
0x18000441f  test    r12d, r12d
0x180004422  jz      short loc_18000447B
0x180004424  lea     rax, [rsp+2310h+hKey]
0x180004429  mov     [rsp+2310h+hKey], rdx
0x18000442e  mov     r9d, 20006h; samDesired
0x180004434  mov     [rsp+2310h+phkResult], rax; phkResult
0x180004439  xor     r8d, r8d; ulOptions
0x18000443c  mov     rcx, r15; hKey
0x18000443f  call    cs:__imp_RegOpenKeyExW
0x180004445  test    eax, eax
0x180004447  jnz     loc_180004900
0x18000444d  mov     r14, [rsp+2310h+hKey]
0x180004452  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180004459  mov     rcx, r14; hKey
0x18000445c  call    cs:__imp_RegDeleteValueW
0x180004462  test    eax, 0FFFFFFFDh
0x180004467  jnz     loc_18000493C
0x18000446d  test    r14, r14
0x180004470  jz      short loc_18000447B
0x180004472  mov     rcx, r14; hKey
0x180004475  call    cs:__imp_RegCloseKey
0x18000447b  mov     rdx, rsi; unsigned __int16 *
0x18000447e  mov     rcx, r13; this
0x180004481  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180004486  mov     edi, eax
0x180004488  test    eax, eax
0x18000448a  js      loc_180004909
0x180004490  jmp     loc_18000479E
0x180004495  movzx   eax, word ptr [rsi]
0x180004498  test    ax, ax
0x18000449b  jz      short loc_1800044C2
0x18000449d  mov     rcx, rsi; lpsz
0x1800044a0  cmp     ax, 5Ch ; '\'
0x1800044a4  jz      short loc_1800044B9
0x1800044a6  call    cs:__imp_CharNextW
0x1800044ac  mov     rcx, rax
0x1800044af  movzx   eax, word ptr [rax]
0x1800044b2  test    ax, ax
0x1800044b5  jnz     short loc_1800044A0
0x1800044b7  jmp     short loc_1800044C2
0x1800044b9  test    rcx, rcx
0x1800044bc  jnz     loc_180004955
0x1800044c2  cmp     [rsp+2310h+var_22A8], edi
0x1800044c6  jz      loc_180004657
0x1800044cc  lea     rax, [rsp+2310h+hKey]
0x1800044d1  mov     [rsp+2310h+hKey], rdi
0x1800044d6  mov     r14d, 2001Fh
0x1800044dc  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800044e1  mov     r9d, r14d; samDesired
0x1800044e4  xor     r8d, r8d; ulOptions
0x1800044e7  mov     rdx, rsi; lpSubKey
0x1800044ea  mov     rcx, r15; hKey
0x1800044ed  call    cs:__imp_RegOpenKeyExW
0x1800044f3  test    eax, eax
0x1800044f5  jnz     short loc_180004518
0x1800044f7  mov     eax, edi
0x1800044f9  test    rbx, rbx
0x1800044fc  jz      short loc_180004507
0x1800044fe  mov     rcx, rbx; hKey
0x180004501  call    cs:__imp_RegCloseKey
0x180004507  mov     rbx, [rsp+2310h+hKey]
0x18000450c  mov     [rbp+2210h+var_2290], rbx
0x180004510  test    eax, eax
0x180004512  jz      loc_1800045C3
0x180004518  lea     rax, [rsp+2310h+hKey]
0x18000451d  mov     [rsp+2310h+hKey], rdi
0x180004522  mov     r9d, 20019h; samDesired
0x180004528  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000452d  xor     r8d, r8d; ulOptions
0x180004530  mov     rdx, rsi; lpSubKey
0x180004533  mov     rcx, r15; hKey
0x180004536  call    cs:__imp_RegOpenKeyExW
0x18000453c  test    eax, eax
0x18000453e  jnz     short loc_18000455D
0x180004540  mov     eax, edi
0x180004542  test    rbx, rbx
0x180004545  jz      short loc_180004550
0x180004547  mov     rcx, rbx; hKey
0x18000454a  call    cs:__imp_RegCloseKey
0x180004550  mov     rbx, [rsp+2310h+hKey]
0x180004555  mov     [rbp+2210h+var_2290], rbx
0x180004559  test    eax, eax
0x18000455b  jz      short loc_1800045C3
0x18000455d  lea     rax, [rsp+2310h+hKey]
0x180004562  mov     dword ptr [rsp+2310h+hKey], edi
0x180004566  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x18000456b  xor     r9d, r9d; lpClass
0x18000456e  lea     rax, [rsp+2310h+var_2298]
0x180004573  mov     [rsp+2310h+var_2298], rdi
0x180004578  mov     [rsp+2310h+var_22D8], rax; phkResult
0x18000457d  xor     r8d, r8d; Reserved
0x180004580  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180004585  mov     rdx, rsi; lpSubKey
0x180004588  mov     [rsp+2310h+samDesired], r14d; samDesired
0x18000458d  mov     rcx, r15; hKey
0x180004590  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180004594  call    cs:__imp_RegCreateKeyExW
0x18000459a  test    eax, eax
0x18000459c  jnz     loc_180004900
0x1800045a2  mov     eax, edi
0x1800045a4  test    rbx, rbx
0x1800045a7  jz      short loc_1800045B2
0x1800045a9  mov     rcx, rbx; hKey
0x1800045ac  call    cs:__imp_RegCloseKey
0x1800045b2  mov     rbx, [rsp+2310h+var_2298]
0x1800045b7  mov     [rbp+2210h+var_2290], rbx
0x1800045bb  test    eax, eax
0x1800045bd  jnz     loc_180004900
0x1800045c3  mov     rdx, rsi; unsigned __int16 *
0x1800045c6  mov     rcx, r13; this
0x1800045c9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800045ce  xor     edx, edx
0x1800045d0  mov     edi, eax
0x1800045d2  test    eax, eax
0x1800045d4  js      loc_180004909
0x1800045da  cmp     word ptr [rsi], 3Dh ; '='
0x1800045de  jnz     short loc_180004602
0x1800045e0  mov     r9, rsi; unsigned __int16 *
0x1800045e3  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x1800045e7  xor     r8d, r8d; unsigned __int16 *
0x1800045ea  mov     rcx, r13; this
0x1800045ed  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800045f2  mov     rbx, [rbp+2210h+var_2290]
0x1800045f6  xor     edx, edx
0x1800045f8  mov     edi, eax
0x1800045fa  test    eax, eax
0x1800045fc  js      loc_180004909
0x180004602  mov     r12d, [rsp+2310h+var_22A8]
0x180004607  cmp     word ptr [rsi], 7Bh ; '{'
0x18000460b  jnz     loc_18000479E
0x180004611  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004615  inc     rax
0x180004618  cmp     [rsi+rax*2], dx
0x18000461c  jnz     short loc_180004615
0x18000461e  cmp     rax, 1
0x180004622  jnz     loc_18000479E
0x180004628  mov     dword ptr [rsp+2310h+phkResult], edx; int
0x18000462c  mov     r9d, r12d; int
0x18000462f  mov     rdx, rsi; unsigned __int16 *
0x180004632  mov     r8, rbx; HKEY
0x180004635  mov     rcx, r13; this
0x180004638  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000463d  mov     edi, eax
0x18000463f  test    eax, eax
0x180004641  js      loc_180004909
0x180004647  mov     rdx, rsi; unsigned __int16 *
0x18000464a  mov     rcx, r13; this
0x18000464d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004652  jmp     loc_180004486
0x180004657  mov     edi, [rbp+2210h+arg_20]
0x18000465d  xor     eax, eax
0x18000465f  test    edi, edi
  ... truncated ...
```
