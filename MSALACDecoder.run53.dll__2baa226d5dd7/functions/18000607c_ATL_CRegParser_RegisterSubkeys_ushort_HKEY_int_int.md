# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000607c`
- end: `0x180006813`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1943`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180005d08`
- `0x18000607c`

## callees

- `0x180001550`
- `0x18000462c`
- `0x180004e28`
- `0x180004e40`
- `0x180005348`
- `0x180005630`
- `0x180005bb8`
- `0x18000607c`
- `0x180006a18`
- `0x180009f10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000655a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000655a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180006686`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000671c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180006686`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000671c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800062f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006384`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800063cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000642f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006523`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000673a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006794`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800067d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800067e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800062f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006384`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800063cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000642f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006523`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000673a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006794`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800067d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800067e0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006417`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006417`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800062df`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800062df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800062c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006370`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800063b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006508`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800062c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006370`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800063b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006508`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000615e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006329`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000615e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006329`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800060f9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000610c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000618a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800061f3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006221`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800066a9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800060f9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000610c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000618a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800061f3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006221`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800066a9`

## string_xrefs

- `0x180006102`: `ForceRemove`
- `0x1800061e9`: `NoRemove`
- `0x1800060ef`: `Delete`

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
0x18000607c  push    rbp
0x18000607e  push    rbx
0x18000607f  push    rsi
0x180006080  push    rdi
0x180006081  push    r12
0x180006083  push    r13
0x180006085  push    r14
0x180006087  push    r15
0x180006089  lea     rbp, [rsp-21D8h]
0x180006091  mov     eax, 22D8h
0x180006096  call    _alloca_probe
0x18000609b  sub     rsp, rax
0x18000609e  mov     rax, cs:__security_cookie
0x1800060a5  xor     rax, rsp
0x1800060a8  mov     [rbp+2210h+var_50], rax
0x1800060af  mov     r12d, r9d
0x1800060b2  mov     [rsp+2310h+var_22A8], r9d
0x1800060b7  mov     r15, r8
0x1800060ba  mov     [rsp+2310h+var_22A0], r8
0x1800060bf  mov     rsi, rdx
0x1800060c2  mov     r13, rcx
0x1800060c5  xor     eax, eax
0x1800060c7  mov     ebx, eax
0x1800060c9  mov     [rbp+2210h+var_2290], rax
0x1800060cd  mov     [rbp+2210h+var_2288], rax
0x1800060d1  mov     [rbp+2210h+var_2280], rax
0x1800060d5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800060da  mov     edi, eax
0x1800060dc  test    eax, eax
0x1800060de  jns     short loc_1800060E5
0x1800060e0  jmp     loc_18000679C
0x1800060e5  cmp     word ptr [rsi], 7Dh ; '}'
0x1800060e9  jz      loc_18000678C
0x1800060ef  lea     rdx, String2; "Delete"
0x1800060f6  mov     rcx, rsi; lpString1
0x1800060f9  call    cs:__imp_lstrcmpiW
0x1800060ff  mov     r14d, eax
0x180006102  lea     rdx, aForceremove; "ForceRemove"
0x180006109  mov     rcx, rsi; lpString1
0x18000610c  call    cs:__imp_lstrcmpiW
0x180006112  xor     edi, edi
0x180006114  test    eax, eax
0x180006116  jz      short loc_180006121
0x180006118  test    r14d, r14d
0x18000611b  jnz     loc_1800061E3
0x180006121  mov     rdx, rsi; unsigned __int16 *
0x180006124  mov     rcx, r13; this
0x180006127  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000612c  mov     edi, eax
0x18000612e  test    eax, eax
0x180006130  js      loc_18000678C
0x180006136  xor     edi, edi
0x180006138  test    r12d, r12d
0x18000613b  jz      loc_1800061E3
0x180006141  mov     [rbp+2210h+var_2278], rdi
0x180006145  mov     [rbp+2210h+var_2270], rdi
0x180006149  mov     [rbp+2210h+var_2268], rdi
0x18000614d  movzx   eax, word ptr [rsi]
0x180006150  test    ax, ax
0x180006153  jz      short loc_18000617A
0x180006155  mov     rcx, rsi; lpsz
0x180006158  cmp     ax, 5Ch ; '\'
0x18000615c  jz      short loc_180006171
0x18000615e  call    cs:__imp_CharNextW
0x180006164  mov     rcx, rax
0x180006167  movzx   eax, word ptr [rax]
0x18000616a  test    ax, ax
0x18000616d  jnz     short loc_180006158
0x18000616f  jmp     short loc_18000617A
0x180006171  test    rcx, rcx
0x180006174  jnz     loc_1800067D8
0x18000617a  mov     edx, edi
0x18000617c  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180006183  mov     rdx, [rax+rdx*8]; lpString2
0x180006187  mov     rcx, rsi; lpString1
0x18000618a  call    cs:__imp_lstrcmpiW
0x180006190  test    eax, eax
0x180006192  jz      short loc_1800061AB
0x180006194  inc     edi
0x180006196  cmp     edi, 0Ch
0x180006199  jl      short loc_18000617A
0x18000619b  mov     [rbp+2210h+var_2278], r15
0x18000619f  mov     rdx, rsi; unsigned __int16 *
0x1800061a2  lea     rcx, [rbp+2210h+var_2278]; this
0x1800061a6  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800061ab  xor     edi, edi
0x1800061ad  test    r14d, r14d
0x1800061b0  jnz     short loc_1800061E3
0x1800061b2  mov     rdx, rsi; unsigned __int16 *
0x1800061b5  mov     rcx, r13; this
0x1800061b8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800061bd  mov     edi, eax
0x1800061bf  test    eax, eax
0x1800061c1  js      loc_18000678C
0x1800061c7  mov     rdx, rsi; unsigned __int16 *
0x1800061ca  mov     rcx, r13; this
0x1800061cd  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800061d2  mov     edi, eax
0x1800061d4  xor     ecx, ecx
0x1800061d6  test    eax, eax
0x1800061d8  js      loc_18000678C
0x1800061de  jmp     loc_18000648A
0x1800061e3  mov     r12d, 1
0x1800061e9  lea     rdx, aNoremove; "NoRemove"
0x1800061f0  mov     rcx, rsi; lpString1
0x1800061f3  call    cs:__imp_lstrcmpiW
0x1800061f9  test    eax, eax
0x1800061fb  jnz     short loc_180006217
0x1800061fd  mov     r12d, edi
0x180006200  mov     rdx, rsi; unsigned __int16 *
0x180006203  mov     rcx, r13; this
0x180006206  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000620b  mov     edi, eax
0x18000620d  test    eax, eax
0x18000620f  js      loc_18000678C
0x180006215  xor     edi, edi
0x180006217  lea     rdx, aVal; "Val"
0x18000621e  mov     rcx, rsi; lpString1
0x180006221  call    cs:__imp_lstrcmpiW
0x180006227  test    eax, eax
0x180006229  jnz     loc_180006318
0x18000622f  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180006236  mov     rcx, r13; this
0x180006239  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000623e  mov     edi, eax
0x180006240  test    eax, eax
0x180006242  js      loc_18000678C
0x180006248  mov     rdx, rsi; unsigned __int16 *
0x18000624b  mov     rcx, r13; this
0x18000624e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006253  mov     edi, eax
0x180006255  test    eax, eax
0x180006257  js      loc_18000678C
0x18000625d  cmp     word ptr [rsi], 3Dh ; '='
0x180006261  jnz     loc_1800067D8
0x180006267  xor     edi, edi
0x180006269  cmp     [rsp+2310h+var_22A8], edi
0x18000626d  jz      short loc_180006298
0x18000626f  mov     [rbp+2210h+var_2270], rdi
0x180006273  mov     [rbp+2210h+var_2268], rdi
0x180006277  mov     [rbp+2210h+var_2278], r15
0x18000627b  mov     r9, rsi; unsigned __int16 *
0x18000627e  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180006285  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180006289  mov     rcx, r13; this
0x18000628c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180006291  mov     edi, eax
0x180006293  jmp     loc_18000647B
0x180006298  cmp     [rbp+2210h+arg_20], edi
0x18000629e  jnz     short loc_1800062FE
0x1800062a0  test    r12d, r12d
0x1800062a3  jz      short loc_1800062FE
0x1800062a5  mov     [rsp+2310h+hKey], rdi
0x1800062aa  lea     rax, [rsp+2310h+hKey]
0x1800062af  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800062b4  mov     r9d, 20006h; samDesired
0x1800062ba  xor     r8d, r8d; ulOptions
0x1800062bd  xor     edx, edx; lpSubKey
0x1800062bf  mov     rcx, r15; hKey
0x1800062c2  call    cs:__imp_RegOpenKeyExW
0x1800062c8  test    eax, eax
0x1800062ca  jnz     loc_180006783
0x1800062d0  mov     r14, [rsp+2310h+hKey]
0x1800062d5  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x1800062dc  mov     rcx, r14; hKey
0x1800062df  call    cs:__imp_RegDeleteValueW
0x1800062e5  test    eax, 0FFFFFFFDh
0x1800062ea  jnz     loc_1800067BF
0x1800062f0  test    r14, r14
0x1800062f3  jz      short loc_1800062FE
0x1800062f5  mov     rcx, r14; hKey
0x1800062f8  call    cs:__imp_RegCloseKey
0x1800062fe  mov     rdx, rsi; unsigned __int16 *
0x180006301  mov     rcx, r13; this
0x180006304  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180006309  mov     edi, eax
0x18000630b  test    eax, eax
0x18000630d  js      loc_18000678C
0x180006313  jmp     loc_180006625
0x180006318  movzx   eax, word ptr [rsi]
0x18000631b  test    ax, ax
0x18000631e  jz      short loc_180006345
0x180006320  mov     rcx, rsi; lpsz
0x180006323  cmp     ax, 5Ch ; '\'
0x180006327  jz      short loc_18000633C
0x180006329  call    cs:__imp_CharNextW
0x18000632f  mov     rcx, rax
0x180006332  movzx   eax, word ptr [rax]
0x180006335  test    ax, ax
0x180006338  jnz     short loc_180006323
0x18000633a  jmp     short loc_180006345
0x18000633c  test    rcx, rcx
0x18000633f  jnz     loc_1800067D8
0x180006345  cmp     [rsp+2310h+var_22A8], edi
0x180006349  jz      loc_1800064DE
0x18000634f  mov     [rsp+2310h+hKey], rdi
0x180006354  lea     rax, [rsp+2310h+hKey]
0x180006359  mov     [rsp+2310h+phkResult], rax; phkResult
0x18000635e  mov     r14d, 2001Fh
0x180006364  mov     r9d, r14d; samDesired
0x180006367  xor     r8d, r8d; ulOptions
0x18000636a  mov     rdx, rsi; lpSubKey
0x18000636d  mov     rcx, r15; hKey
0x180006370  call    cs:__imp_RegOpenKeyExW
0x180006376  test    eax, eax
0x180006378  jnz     short loc_18000639B
0x18000637a  mov     eax, edi
0x18000637c  test    rbx, rbx
0x18000637f  jz      short loc_18000638A
0x180006381  mov     rcx, rbx; hKey
0x180006384  call    cs:__imp_RegCloseKey
0x18000638a  mov     rbx, [rsp+2310h+hKey]
0x18000638f  mov     [rbp+2210h+var_2290], rbx
0x180006393  test    eax, eax
0x180006395  jz      loc_180006446
0x18000639b  mov     [rsp+2310h+hKey], rdi
0x1800063a0  lea     rax, [rsp+2310h+hKey]
0x1800063a5  mov     [rsp+2310h+phkResult], rax; phkResult
0x1800063aa  mov     r9d, 20019h; samDesired
0x1800063b0  xor     r8d, r8d; ulOptions
0x1800063b3  mov     rdx, rsi; lpSubKey
0x1800063b6  mov     rcx, r15; hKey
0x1800063b9  call    cs:__imp_RegOpenKeyExW
0x1800063bf  test    eax, eax
0x1800063c1  jnz     short loc_1800063E0
0x1800063c3  mov     eax, edi
0x1800063c5  test    rbx, rbx
0x1800063c8  jz      short loc_1800063D3
0x1800063ca  mov     rcx, rbx; hKey
0x1800063cd  call    cs:__imp_RegCloseKey
0x1800063d3  mov     rbx, [rsp+2310h+hKey]
0x1800063d8  mov     [rbp+2210h+var_2290], rbx
0x1800063dc  test    eax, eax
0x1800063de  jz      short loc_180006446
0x1800063e0  mov     dword ptr [rsp+2310h+hKey], edi
0x1800063e4  mov     [rsp+2310h+var_2298], rdi
0x1800063e9  lea     rax, [rsp+2310h+hKey]
0x1800063ee  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x1800063f3  lea     rax, [rsp+2310h+var_2298]
0x1800063f8  mov     [rsp+2310h+var_22D8], rax; phkResult
0x1800063fd  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180006402  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180006407  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x18000640b  xor     r9d, r9d; lpClass
0x18000640e  xor     r8d, r8d; Reserved
0x180006411  mov     rdx, rsi; lpSubKey
0x180006414  mov     rcx, r15; hKey
0x180006417  call    cs:__imp_RegCreateKeyExW
0x18000641d  test    eax, eax
0x18000641f  jnz     loc_180006783
0x180006425  mov     eax, edi
0x180006427  test    rbx, rbx
0x18000642a  jz      short loc_180006435
0x18000642c  mov     rcx, rbx; hKey
0x18000642f  call    cs:__imp_RegCloseKey
0x180006435  mov     rbx, [rsp+2310h+var_2298]
0x18000643a  mov     [rbp+2210h+var_2290], rbx
0x18000643e  test    eax, eax
0x180006440  jnz     loc_180006783
0x180006446  mov     rdx, rsi; unsigned __int16 *
0x180006449  mov     rcx, r13; this
0x18000644c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006451  mov     edi, eax
0x180006453  xor     ecx, ecx
0x180006455  test    eax, eax
0x180006457  js      loc_18000678C
0x18000645d  cmp     word ptr [rsi], 3Dh ; '='
0x180006461  jnz     short loc_180006485
0x180006463  mov     r9, rsi; unsigned __int16 *
0x180006466  xor     r8d, r8d; unsigned __int16 *
0x180006469  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x18000646d  mov     rcx, r13; this
0x180006470  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180006475  mov     edi, eax
0x180006477  mov     rbx, [rbp+2210h+var_2290]
0x18000647b  test    eax, eax
0x18000647d  js      loc_18000678C
0x180006483  xor     ecx, ecx
0x180006485  mov     r12d, [rsp+2310h+var_22A8]
0x18000648a  cmp     word ptr [rsi], 7Bh ; '{'
0x18000648e  jnz     loc_180006625
0x180006494  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006498  inc     rax
0x18000649b  cmp     [rsi+rax*2], cx
0x18000649f  jnz     short loc_180006498
0x1800064a1  cmp     rax, 1
0x1800064a5  jnz     loc_180006625
0x1800064ab  mov     dword ptr [rsp+2310h+phkResult], 0; int
0x1800064b3  mov     r9d, r12d; int
0x1800064b6  mov     r8, rbx; HKEY
0x1800064b9  mov     rdx, rsi; unsigned __int16 *
0x1800064bc  mov     rcx, r13; this
0x1800064bf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800064c4  mov     edi, eax
0x1800064c6  test    eax, eax
0x1800064c8  js      loc_18000678C
0x1800064ce  mov     rdx, rsi; unsigned __int16 *
0x1800064d1  mov     rcx, r13; this
0x1800064d4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800064d9  jmp     loc_180006309
  ... truncated ...
```
