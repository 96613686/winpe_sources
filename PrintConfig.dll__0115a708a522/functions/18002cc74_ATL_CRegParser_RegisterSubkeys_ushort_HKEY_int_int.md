# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18002cc74`
- end: `0x18002d4b0`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `2108`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18002c8bc`
- `0x18002cc74`

## callees

- `0x180003400`
- `0x1800109e8`
- `0x1800284d4`
- `0x180028e6c`
- `0x18002a2ac`
- `0x18002c188`
- `0x18002c74c`
- `0x18002cc74`
- `0x18002d9c8`
- `0x1801b5620`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002d1c6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002d1c6`
- `KERNEL32!lstrcmpiW` at `0x18002ccf9`
- `KERNEL32!lstrcmpiW` at `0x18002cd12`
- `KERNEL32!lstrcmpiW` at `0x18002cd9c`
- `KERNEL32!lstrcmpiW` at `0x18002ce0b`
- `KERNEL32!lstrcmpiW` at `0x18002ce3f`
- `KERNEL32!lstrcmpiW` at `0x18002d321`
- `KERNEL32!lstrcmpiW` at `0x18002ccf9`
- `KERNEL32!lstrcmpiW` at `0x18002cd12`
- `KERNEL32!lstrcmpiW` at `0x18002cd9c`
- `KERNEL32!lstrcmpiW` at `0x18002ce0b`
- `KERNEL32!lstrcmpiW` at `0x18002ce3f`
- `KERNEL32!lstrcmpiW` at `0x18002d321`
- `ADVAPI32!RegCloseKey` at `0x18002cf28`
- `ADVAPI32!RegCloseKey` at `0x18002cfc6`
- `ADVAPI32!RegCloseKey` at `0x18002d01b`
- `ADVAPI32!RegCloseKey` at `0x18002d089`
- `ADVAPI32!RegCloseKey` at `0x18002d189`
- `ADVAPI32!RegCloseKey` at `0x18002d3be`
- `ADVAPI32!RegCloseKey` at `0x18002d41e`
- `ADVAPI32!RegCloseKey` at `0x18002d461`
- `ADVAPI32!RegCloseKey` at `0x18002d477`
- `ADVAPI32!RegCloseKey` at `0x18002cf28`
- `ADVAPI32!RegCloseKey` at `0x18002cfc6`
- `ADVAPI32!RegCloseKey` at `0x18002d01b`
- `ADVAPI32!RegCloseKey` at `0x18002d089`
- `ADVAPI32!RegCloseKey` at `0x18002d189`
- `ADVAPI32!RegCloseKey` at `0x18002d3be`
- `ADVAPI32!RegCloseKey` at `0x18002d41e`
- `ADVAPI32!RegCloseKey` at `0x18002d461`
- `ADVAPI32!RegCloseKey` at `0x18002d477`
- `ADVAPI32!RegCreateKeyExW` at `0x18002d06b`
- `ADVAPI32!RegCreateKeyExW` at `0x18002d06b`
- `ADVAPI32!RegOpenKeyExW` at `0x18002cee6`
- `ADVAPI32!RegOpenKeyExW` at `0x18002cfac`
- `ADVAPI32!RegOpenKeyExW` at `0x18002d001`
- `ADVAPI32!RegOpenKeyExW` at `0x18002d168`
- `ADVAPI32!RegOpenKeyExW` at `0x18002cee6`
- `ADVAPI32!RegOpenKeyExW` at `0x18002cfac`
- `ADVAPI32!RegOpenKeyExW` at `0x18002d001`
- `ADVAPI32!RegOpenKeyExW` at `0x18002d168`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002d2f8`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002d39a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002d2f8`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002d39a`
- `ADVAPI32!RegDeleteValueW` at `0x18002cf09`
- `ADVAPI32!RegDeleteValueW` at `0x18002cf09`
- `USER32!CharNextW` at `0x18002cd6a`
- `USER32!CharNextW` at `0x18002cf5f`
- `USER32!CharNextW` at `0x18002cd6a`
- `USER32!CharNextW` at `0x18002cf5f`

## string_xrefs

- `0x18002cd08`: `ForceRemove`
- `0x18002ce01`: `NoRemove`
- `0x18002ccef`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  int v29; // eax
  __int64 v30; // rax
  int v31; // r14d
  int v32; // ecx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+68h] [rbp-98h]
  HKEY v35; // [rsp+70h] [rbp-90h]
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  HKEY v37[3]; // [rsp+80h] [rbp-80h] BYREF
  HKEY v38; // [rsp+98h] [rbp-68h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+A8h] [rbp-58h]
  __int64 v41; // [rsp+B0h] [rbp-50h]
  WCHAR String1[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR ValueName[4096]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v41 = -2;
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
                ATL::CRegKey::RecurseDeleteKey(v37, String1);
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
0x18002cc74  push    rbp
0x18002cc76  push    rbx
0x18002cc77  push    rsi
0x18002cc78  push    rdi
0x18002cc79  push    r12
0x18002cc7b  push    r13
0x18002cc7d  push    r14
0x18002cc7f  push    r15
0x18002cc81  lea     rbp, [rsp-21E8h]
0x18002cc89  mov     eax, 22E8h
0x18002cc8e  call    _alloca_probe
0x18002cc93  sub     rsp, rax
0x18002cc96  mov     [rbp+2220h+var_2270], 0FFFFFFFFFFFFFFFEh
0x18002cc9e  mov     rax, cs:__security_cookie
0x18002cca5  xor     rax, rsp
0x18002cca8  mov     [rbp+2220h+var_50], rax
0x18002ccaf  mov     r12d, r9d
0x18002ccb2  mov     [rsp+2320h+var_22B8], r9d
0x18002ccb7  mov     r15, r8
0x18002ccba  mov     [rsp+2320h+var_22B0], r8
0x18002ccbf  mov     rsi, rdx
0x18002ccc2  mov     r13, rcx
0x18002ccc5  xor     eax, eax
0x18002ccc7  mov     ebx, eax
0x18002ccc9  mov     [rbp+2220h+var_22A0], rax
0x18002cccd  mov     [rbp+2220h+var_2298], rax
0x18002ccd1  mov     [rbp+2220h+var_2290], rax
0x18002ccd5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002ccda  mov     edi, eax
0x18002ccdc  test    eax, eax
0x18002ccde  jns     short loc_18002CCE5
0x18002cce0  jmp     loc_18002D42C
0x18002cce5  cmp     word ptr [rsi], 7Dh ; '}'
0x18002cce9  jz      loc_18002D416
0x18002ccef  lea     rdx, aDelete; "Delete"
0x18002ccf6  mov     rcx, rsi; lpString1
0x18002ccf9  call    cs:__imp_lstrcmpiW
0x18002cd00  nop     dword ptr [rax+rax+00h]
0x18002cd05  mov     r14d, eax
0x18002cd08  lea     rdx, aForceremove; "ForceRemove"
0x18002cd0f  mov     rcx, rsi; lpString1
0x18002cd12  call    cs:__imp_lstrcmpiW
0x18002cd19  nop     dword ptr [rax+rax+00h]
0x18002cd1e  xor     edi, edi
0x18002cd20  test    eax, eax
0x18002cd22  jz      short loc_18002CD2D
0x18002cd24  test    r14d, r14d
0x18002cd27  jnz     loc_18002CDFB
0x18002cd2d  mov     rdx, rsi; unsigned __int16 *
0x18002cd30  mov     rcx, r13; this
0x18002cd33  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002cd38  mov     edi, eax
0x18002cd3a  test    eax, eax
0x18002cd3c  js      loc_18002D416
0x18002cd42  xor     edi, edi
0x18002cd44  test    r12d, r12d
0x18002cd47  jz      loc_18002CDFB
0x18002cd4d  mov     [rbp+2220h+var_2288], rdi
0x18002cd51  mov     [rbp+2220h+var_2280], rdi
0x18002cd55  mov     [rbp+2220h+var_2278], rdi
0x18002cd59  movzx   eax, word ptr [rsi]
0x18002cd5c  test    ax, ax
0x18002cd5f  jz      short loc_18002CD8C
0x18002cd61  mov     rcx, rsi; lpsz
0x18002cd64  cmp     ax, 5Ch ; '\'
0x18002cd68  jz      short loc_18002CD83
0x18002cd6a  call    cs:__imp_CharNextW
0x18002cd71  nop     dword ptr [rax+rax+00h]
0x18002cd76  mov     rcx, rax
0x18002cd79  movzx   eax, word ptr [rax]
0x18002cd7c  test    ax, ax
0x18002cd7f  jnz     short loc_18002CD64
0x18002cd81  jmp     short loc_18002CD8C
0x18002cd83  test    rcx, rcx
0x18002cd86  jnz     loc_18002D46F
0x18002cd8c  mov     edx, edi
0x18002cd8e  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x18002cd95  mov     rdx, [rax+rdx*8]; lpString2
0x18002cd99  mov     rcx, rsi; lpString1
0x18002cd9c  call    cs:__imp_lstrcmpiW
0x18002cda3  nop     dword ptr [rax+rax+00h]
0x18002cda8  test    eax, eax
0x18002cdaa  jz      short loc_18002CDC3
0x18002cdac  inc     edi
0x18002cdae  cmp     edi, 0Ch
0x18002cdb1  jl      short loc_18002CD8C
0x18002cdb3  mov     [rbp+2220h+var_2288], r15
0x18002cdb7  mov     rdx, rsi; unsigned __int16 *
0x18002cdba  lea     rcx, [rbp+2220h+var_2288]; this
0x18002cdbe  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18002cdc3  xor     edi, edi
0x18002cdc5  test    r14d, r14d
0x18002cdc8  jnz     short loc_18002CDFB
0x18002cdca  mov     rdx, rsi; unsigned __int16 *
0x18002cdcd  mov     rcx, r13; this
0x18002cdd0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002cdd5  mov     edi, eax
0x18002cdd7  test    eax, eax
0x18002cdd9  js      loc_18002D416
0x18002cddf  mov     rdx, rsi; unsigned __int16 *
0x18002cde2  mov     rcx, r13; this
0x18002cde5  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18002cdea  mov     edi, eax
0x18002cdec  xor     ecx, ecx
0x18002cdee  test    eax, eax
0x18002cdf0  js      loc_18002D416
0x18002cdf6  jmp     loc_18002D0EA
0x18002cdfb  mov     r12d, 1
0x18002ce01  lea     rdx, aNoremove; "NoRemove"
0x18002ce08  mov     rcx, rsi; lpString1
0x18002ce0b  call    cs:__imp_lstrcmpiW
0x18002ce12  nop     dword ptr [rax+rax+00h]
0x18002ce17  test    eax, eax
0x18002ce19  jnz     short loc_18002CE35
0x18002ce1b  mov     r12d, edi
0x18002ce1e  mov     rdx, rsi; unsigned __int16 *
0x18002ce21  mov     rcx, r13; this
0x18002ce24  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002ce29  mov     edi, eax
0x18002ce2b  test    eax, eax
0x18002ce2d  js      loc_18002D416
0x18002ce33  xor     edi, edi
0x18002ce35  lea     rdx, aVal; "Val"
0x18002ce3c  mov     rcx, rsi; lpString1
0x18002ce3f  call    cs:__imp_lstrcmpiW
0x18002ce46  nop     dword ptr [rax+rax+00h]
0x18002ce4b  test    eax, eax
0x18002ce4d  jnz     loc_18002CF4E
0x18002ce53  lea     rdx, [rbp+2220h+ValueName]; unsigned __int16 *
0x18002ce5a  mov     rcx, r13; this
0x18002ce5d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002ce62  mov     edi, eax
0x18002ce64  test    eax, eax
0x18002ce66  js      loc_18002D416
0x18002ce6c  mov     rdx, rsi; unsigned __int16 *
0x18002ce6f  mov     rcx, r13; this
0x18002ce72  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002ce77  mov     edi, eax
0x18002ce79  test    eax, eax
0x18002ce7b  js      loc_18002D416
0x18002ce81  cmp     word ptr [rsi], 3Dh ; '='
0x18002ce85  jnz     loc_18002D46F
0x18002ce8b  xor     edi, edi
0x18002ce8d  cmp     [rsp+2320h+var_22B8], edi
0x18002ce91  jz      short loc_18002CEBC
0x18002ce93  mov     [rbp+2220h+var_2280], rdi
0x18002ce97  mov     [rbp+2220h+var_2278], rdi
0x18002ce9b  mov     [rbp+2220h+var_2288], r15
0x18002ce9f  mov     r9, rsi; unsigned __int16 *
0x18002cea2  lea     r8, [rbp+2220h+ValueName]; unsigned __int16 *
0x18002cea9  lea     rdx, [rbp+2220h+var_2288]; struct ATL::CRegKey *
0x18002cead  mov     rcx, r13; this
0x18002ceb0  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18002ceb5  mov     edi, eax
0x18002ceb7  jmp     loc_18002D0DB
0x18002cebc  cmp     [rbp+2220h+arg_20], edi
0x18002cec2  jnz     short loc_18002CF34
0x18002cec4  test    r12d, r12d
0x18002cec7  jz      short loc_18002CF34
0x18002cec9  mov     [rsp+2320h+hKey], rdi
0x18002cece  lea     rax, [rsp+2320h+hKey]
0x18002ced3  mov     [rsp+2320h+phkResult], rax; phkResult
0x18002ced8  mov     r9d, 20006h; samDesired
0x18002cede  xor     r8d, r8d; ulOptions
0x18002cee1  xor     edx, edx; lpSubKey
0x18002cee3  mov     rcx, r15; hKey
0x18002cee6  call    cs:__imp_RegOpenKeyExW
0x18002ceed  nop     dword ptr [rax+rax+00h]
0x18002cef2  test    eax, eax
0x18002cef4  jnz     loc_18002D40D
0x18002cefa  mov     r14, [rsp+2320h+hKey]
0x18002ceff  lea     rdx, [rbp+2220h+ValueName]; lpValueName
0x18002cf06  mov     rcx, r14; hKey
0x18002cf09  call    cs:__imp_RegDeleteValueW
0x18002cf10  nop     dword ptr [rax+rax+00h]
0x18002cf15  test    eax, 0FFFFFFFDh
0x18002cf1a  jnz     loc_18002D450
0x18002cf20  test    r14, r14
0x18002cf23  jz      short loc_18002CF34
0x18002cf25  mov     rcx, r14; hKey
0x18002cf28  call    cs:__imp_RegCloseKey
0x18002cf2f  nop     dword ptr [rax+rax+00h]
0x18002cf34  mov     rdx, rsi; unsigned __int16 *
0x18002cf37  mov     rcx, r13; this
0x18002cf3a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18002cf3f  mov     edi, eax
0x18002cf41  test    eax, eax
0x18002cf43  js      loc_18002D416
0x18002cf49  jmp     loc_18002D297
0x18002cf4e  movzx   eax, word ptr [rsi]
0x18002cf51  test    ax, ax
0x18002cf54  jz      short loc_18002CF81
0x18002cf56  mov     rcx, rsi; lpsz
0x18002cf59  cmp     ax, 5Ch ; '\'
0x18002cf5d  jz      short loc_18002CF78
0x18002cf5f  call    cs:__imp_CharNextW
0x18002cf66  nop     dword ptr [rax+rax+00h]
0x18002cf6b  mov     rcx, rax
0x18002cf6e  movzx   eax, word ptr [rax]
0x18002cf71  test    ax, ax
0x18002cf74  jnz     short loc_18002CF59
0x18002cf76  jmp     short loc_18002CF81
0x18002cf78  test    rcx, rcx
0x18002cf7b  jnz     loc_18002D46F
0x18002cf81  cmp     [rsp+2320h+var_22B8], edi
0x18002cf85  jz      loc_18002D13E
0x18002cf8b  mov     [rsp+2320h+hKey], rdi
0x18002cf90  lea     rax, [rsp+2320h+hKey]
0x18002cf95  mov     [rsp+2320h+phkResult], rax; phkResult
0x18002cf9a  mov     r14d, 2001Fh
0x18002cfa0  mov     r9d, r14d; samDesired
0x18002cfa3  xor     r8d, r8d; ulOptions
0x18002cfa6  mov     rdx, rsi; lpSubKey
0x18002cfa9  mov     rcx, r15; hKey
0x18002cfac  call    cs:__imp_RegOpenKeyExW
0x18002cfb3  nop     dword ptr [rax+rax+00h]
0x18002cfb8  test    eax, eax
0x18002cfba  jnz     short loc_18002CFE3
0x18002cfbc  mov     eax, edi
0x18002cfbe  test    rbx, rbx
0x18002cfc1  jz      short loc_18002CFD2
0x18002cfc3  mov     rcx, rbx; hKey
0x18002cfc6  call    cs:__imp_RegCloseKey
0x18002cfcd  nop     dword ptr [rax+rax+00h]
0x18002cfd2  mov     rbx, [rsp+2320h+hKey]
0x18002cfd7  mov     [rbp+2220h+var_22A0], rbx
0x18002cfdb  test    eax, eax
0x18002cfdd  jz      loc_18002D0A6
0x18002cfe3  mov     [rsp+2320h+hKey], rdi
0x18002cfe8  lea     rax, [rsp+2320h+hKey]
0x18002cfed  mov     [rsp+2320h+phkResult], rax; phkResult
0x18002cff2  mov     r9d, 20019h; samDesired
0x18002cff8  xor     r8d, r8d; ulOptions
0x18002cffb  mov     rdx, rsi; lpSubKey
0x18002cffe  mov     rcx, r15; hKey
0x18002d001  call    cs:__imp_RegOpenKeyExW
0x18002d008  nop     dword ptr [rax+rax+00h]
0x18002d00d  test    eax, eax
0x18002d00f  jnz     short loc_18002D034
0x18002d011  mov     eax, edi
0x18002d013  test    rbx, rbx
0x18002d016  jz      short loc_18002D027
0x18002d018  mov     rcx, rbx; hKey
0x18002d01b  call    cs:__imp_RegCloseKey
0x18002d022  nop     dword ptr [rax+rax+00h]
0x18002d027  mov     rbx, [rsp+2320h+hKey]
0x18002d02c  mov     [rbp+2220h+var_22A0], rbx
0x18002d030  test    eax, eax
0x18002d032  jz      short loc_18002D0A6
0x18002d034  mov     dword ptr [rsp+2320h+hKey], edi
0x18002d038  mov     [rsp+2320h+var_22A8], rdi
0x18002d03d  lea     rax, [rsp+2320h+hKey]
0x18002d042  mov     [rsp+2320h+lpdwDisposition], rax; lpdwDisposition
0x18002d047  lea     rax, [rsp+2320h+var_22A8]
0x18002d04c  mov     [rsp+2320h+var_22E8], rax; phkResult
0x18002d051  mov     [rsp+2320h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18002d056  mov     [rsp+2320h+samDesired], r14d; samDesired
0x18002d05b  mov     dword ptr [rsp+2320h+phkResult], edi; dwOptions
0x18002d05f  xor     r9d, r9d; lpClass
0x18002d062  xor     r8d, r8d; Reserved
0x18002d065  mov     rdx, rsi; lpSubKey
0x18002d068  mov     rcx, r15; hKey
0x18002d06b  call    cs:__imp_RegCreateKeyExW
0x18002d072  nop     dword ptr [rax+rax+00h]
0x18002d077  test    eax, eax
0x18002d079  jnz     loc_18002D40D
0x18002d07f  mov     eax, edi
0x18002d081  test    rbx, rbx
0x18002d084  jz      short loc_18002D095
0x18002d086  mov     rcx, rbx; hKey
0x18002d089  call    cs:__imp_RegCloseKey
0x18002d090  nop     dword ptr [rax+rax+00h]
0x18002d095  mov     rbx, [rsp+2320h+var_22A8]
0x18002d09a  mov     [rbp+2220h+var_22A0], rbx
0x18002d09e  test    eax, eax
0x18002d0a0  jnz     loc_18002D40D
0x18002d0a6  mov     rdx, rsi; unsigned __int16 *
0x18002d0a9  mov     rcx, r13; this
0x18002d0ac  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002d0b1  mov     edi, eax
0x18002d0b3  xor     ecx, ecx
0x18002d0b5  test    eax, eax
0x18002d0b7  js      loc_18002D416
0x18002d0bd  cmp     word ptr [rsi], 3Dh ; '='
0x18002d0c1  jnz     short loc_18002D0E5
0x18002d0c3  mov     r9, rsi; unsigned __int16 *
0x18002d0c6  xor     r8d, r8d; unsigned __int16 *
0x18002d0c9  lea     rdx, [rbp+2220h+var_22A0]; struct ATL::CRegKey *
0x18002d0cd  mov     rcx, r13; this
0x18002d0d0  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18002d0d5  mov     edi, eax
0x18002d0d7  mov     rbx, [rbp+2220h+var_22A0]
0x18002d0db  test    eax, eax
0x18002d0dd  js      loc_18002D416
0x18002d0e3  xor     ecx, ecx
0x18002d0e5  mov     r12d, [rsp+2320h+var_22B8]
0x18002d0ea  cmp     word ptr [rsi], 7Bh ; '{'
0x18002d0ee  jnz     loc_18002D297
0x18002d0f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d0f8  inc     rax
  ... truncated ...
```
