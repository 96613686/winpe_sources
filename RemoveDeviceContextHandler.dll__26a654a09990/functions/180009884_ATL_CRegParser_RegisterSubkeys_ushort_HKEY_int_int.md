# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180009884`
- end: `0x18000a021`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1949`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180009538`
- `0x180009884`

## callees

- `0x180006784`
- `0x180006ddc`
- `0x180006df4`
- `0x180007948`
- `0x180008930`
- `0x1800093e8`
- `0x180009884`
- `0x18000abe0`
- `0x18000c990`
- `0x18000ca20`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180009d5b`
- `msvcrt!wcsncpy_s` at `0x180009d5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009afd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009b89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009bd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009d24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009f3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009f99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009fd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009fe5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009afd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009b89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009bd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009d24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009f3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009f99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009fd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009fe5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009e82`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009f1b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009e82`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009f1b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180009ae4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180009ae4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009ac7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009b75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009bbe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009d09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009ac7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009b75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009bbe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009d09`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009c1c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009c1c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009967`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009b2e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009967`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009b2e`
- `KERNEL32!lstrcmpiW` at `0x180009902`
- `KERNEL32!lstrcmpiW` at `0x180009915`
- `KERNEL32!lstrcmpiW` at `0x180009993`
- `KERNEL32!lstrcmpiW` at `0x1800099fc`
- `KERNEL32!lstrcmpiW` at `0x180009a2a`
- `KERNEL32!lstrcmpiW` at `0x180009ea9`
- `KERNEL32!lstrcmpiW` at `0x180009902`
- `KERNEL32!lstrcmpiW` at `0x180009915`
- `KERNEL32!lstrcmpiW` at `0x180009993`
- `KERNEL32!lstrcmpiW` at `0x1800099fc`
- `KERNEL32!lstrcmpiW` at `0x180009a2a`
- `KERNEL32!lstrcmpiW` at `0x180009ea9`

## string_xrefs

- `0x180009908`: `ForceRemove`
- `0x1800099ec`: `NoRemove`
- `0x1800098f8`: `Delete`

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
0x180009884  push    rbp
0x180009886  push    rbx
0x180009887  push    rsi
0x180009888  push    rdi
0x180009889  push    r12
0x18000988b  push    r13
0x18000988d  push    r14
0x18000988f  push    r15
0x180009891  lea     rbp, [rsp-21D8h]
0x180009899  mov     eax, 22D8h
0x18000989e  call    _alloca_probe
0x1800098a3  sub     rsp, rax
0x1800098a6  mov     rax, cs:__security_cookie
0x1800098ad  xor     rax, rsp
0x1800098b0  mov     [rbp+2210h+var_50], rax
0x1800098b7  xor     r14d, r14d
0x1800098ba  mov     [rsp+2310h+var_22A8], r9d
0x1800098bf  mov     ebx, r14d
0x1800098c2  mov     [rsp+2310h+var_22A0], r8
0x1800098c7  mov     [rbp+2210h+var_2290], rbx
0x1800098cb  mov     r12d, r9d
0x1800098ce  mov     r15, r8
0x1800098d1  mov     [rbp+2210h+var_2288], r14
0x1800098d5  mov     rsi, rdx
0x1800098d8  mov     [rbp+2210h+var_2280], r14
0x1800098dc  mov     r13, rcx
0x1800098df  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800098e4  mov     edi, eax
0x1800098e6  test    eax, eax
0x1800098e8  js      loc_180009FA1
0x1800098ee  cmp     word ptr [rsi], 7Dh ; '}'
0x1800098f2  jz      loc_180009F9F
0x1800098f8  lea     rdx, aDelete; "Delete"
0x1800098ff  mov     rcx, rsi; lpString1
0x180009902  call    cs:__imp_lstrcmpiW
0x180009908  lea     rdx, aForceremove; "ForceRemove"
0x18000990f  mov     rcx, rsi; lpString1
0x180009912  mov     r14d, eax
0x180009915  call    cs:__imp_lstrcmpiW
0x18000991b  xor     edi, edi
0x18000991d  test    eax, eax
0x18000991f  jz      short loc_18000992A
0x180009921  test    r14d, r14d
0x180009924  jnz     loc_1800099EC
0x18000992a  mov     rdx, rsi; unsigned __int16 *
0x18000992d  mov     rcx, r13; this
0x180009930  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009935  mov     edi, eax
0x180009937  test    eax, eax
0x180009939  js      loc_180009F91
0x18000993f  xor     edi, edi
0x180009941  test    r12d, r12d
0x180009944  jz      loc_1800099EC
0x18000994a  movzx   eax, word ptr [rsi]
0x18000994d  mov     [rbp+2210h+var_2278], rdi
0x180009951  mov     [rbp+2210h+var_2270], rdi
0x180009955  mov     [rbp+2210h+var_2268], rdi
0x180009959  test    ax, ax
0x18000995c  jz      short loc_180009983
0x18000995e  mov     rcx, rsi; lpsz
0x180009961  cmp     ax, 5Ch ; '\'
0x180009965  jz      short loc_18000997A
0x180009967  call    cs:__imp_CharNextW
0x18000996d  mov     rcx, rax
0x180009970  movzx   eax, word ptr [rax]
0x180009973  test    ax, ax
0x180009976  jnz     short loc_180009961
0x180009978  jmp     short loc_180009983
0x18000997a  test    rcx, rcx
0x18000997d  jnz     loc_180009FDD
0x180009983  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x18000998a  mov     edx, edi
0x18000998c  mov     rcx, rsi; lpString1
0x18000998f  mov     rdx, [rax+rdx*8]; lpString2
0x180009993  call    cs:__imp_lstrcmpiW
0x180009999  test    eax, eax
0x18000999b  jz      short loc_1800099B4
0x18000999d  inc     edi
0x18000999f  cmp     edi, 0Ch
0x1800099a2  jl      short loc_180009983
0x1800099a4  mov     rdx, rsi; unsigned __int16 *
0x1800099a7  mov     [rbp+2210h+var_2278], r15
0x1800099ab  lea     rcx, [rbp+2210h+var_2278]; this
0x1800099af  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800099b4  xor     edi, edi
0x1800099b6  test    r14d, r14d
0x1800099b9  jnz     short loc_1800099EC
0x1800099bb  mov     rdx, rsi; unsigned __int16 *
0x1800099be  mov     rcx, r13; this
0x1800099c1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800099c6  mov     edi, eax
0x1800099c8  test    eax, eax
0x1800099ca  js      loc_180009F91
0x1800099d0  mov     rdx, rsi; unsigned __int16 *
0x1800099d3  mov     rcx, r13; this
0x1800099d6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800099db  xor     edx, edx
0x1800099dd  mov     edi, eax
0x1800099df  test    eax, eax
0x1800099e1  js      loc_180009F91
0x1800099e7  jmp     loc_180009C8F
0x1800099ec  lea     rdx, aNoremove; "NoRemove"
0x1800099f3  mov     rcx, rsi; lpString1
0x1800099f6  mov     r12d, 1
0x1800099fc  call    cs:__imp_lstrcmpiW
0x180009a02  test    eax, eax
0x180009a04  jnz     short loc_180009A20
0x180009a06  mov     rdx, rsi; unsigned __int16 *
0x180009a09  mov     rcx, r13; this
0x180009a0c  mov     r12d, edi
0x180009a0f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009a14  mov     edi, eax
0x180009a16  test    eax, eax
0x180009a18  js      loc_180009F91
0x180009a1e  xor     edi, edi
0x180009a20  lea     rdx, aVal; "Val"
0x180009a27  mov     rcx, rsi; lpString1
0x180009a2a  call    cs:__imp_lstrcmpiW
0x180009a30  test    eax, eax
0x180009a32  jnz     loc_180009B1D
0x180009a38  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x180009a3f  mov     rcx, r13; this
0x180009a42  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009a47  mov     edi, eax
0x180009a49  test    eax, eax
0x180009a4b  js      loc_180009F91
0x180009a51  mov     rdx, rsi; unsigned __int16 *
0x180009a54  mov     rcx, r13; this
0x180009a57  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009a5c  xor     edx, edx; lpSubKey
0x180009a5e  mov     edi, eax
0x180009a60  test    eax, eax
0x180009a62  js      loc_180009F91
0x180009a68  cmp     word ptr [rsi], 3Dh ; '='
0x180009a6c  jnz     loc_180009FDD
0x180009a72  cmp     [rsp+2310h+var_22A8], edx
0x180009a76  jz      short loc_180009A9F
0x180009a78  mov     [rbp+2210h+var_2270], rdx
0x180009a7c  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x180009a83  mov     [rbp+2210h+var_2268], rdx
0x180009a87  mov     r9, rsi; unsigned __int16 *
0x180009a8a  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x180009a8e  mov     [rbp+2210h+var_2278], r15
0x180009a92  mov     rcx, r13; this
0x180009a95  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180009a9a  jmp     loc_180009C7E
0x180009a9f  cmp     [rbp+2210h+arg_20], edx
0x180009aa5  jnz     short loc_180009B03
0x180009aa7  test    r12d, r12d
0x180009aaa  jz      short loc_180009B03
0x180009aac  lea     rax, [rsp+2310h+hKey]
0x180009ab1  mov     [rsp+2310h+hKey], rdx
0x180009ab6  mov     r9d, 20006h; samDesired
0x180009abc  mov     [rsp+2310h+phkResult], rax; phkResult
0x180009ac1  xor     r8d, r8d; ulOptions
0x180009ac4  mov     rcx, r15; hKey
0x180009ac7  call    cs:__imp_RegOpenKeyExW
0x180009acd  test    eax, eax
0x180009acf  jnz     loc_180009F88
0x180009ad5  mov     r14, [rsp+2310h+hKey]
0x180009ada  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x180009ae1  mov     rcx, r14; hKey
0x180009ae4  call    cs:__imp_RegDeleteValueW
0x180009aea  test    eax, 0FFFFFFFDh
0x180009aef  jnz     loc_180009FC4
0x180009af5  test    r14, r14
0x180009af8  jz      short loc_180009B03
0x180009afa  mov     rcx, r14; hKey
0x180009afd  call    cs:__imp_RegCloseKey
0x180009b03  mov     rdx, rsi; unsigned __int16 *
0x180009b06  mov     rcx, r13; this
0x180009b09  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180009b0e  mov     edi, eax
0x180009b10  test    eax, eax
0x180009b12  js      loc_180009F91
0x180009b18  jmp     loc_180009E26
0x180009b1d  movzx   eax, word ptr [rsi]
0x180009b20  test    ax, ax
0x180009b23  jz      short loc_180009B4A
0x180009b25  mov     rcx, rsi; lpsz
0x180009b28  cmp     ax, 5Ch ; '\'
0x180009b2c  jz      short loc_180009B41
0x180009b2e  call    cs:__imp_CharNextW
0x180009b34  mov     rcx, rax
0x180009b37  movzx   eax, word ptr [rax]
0x180009b3a  test    ax, ax
0x180009b3d  jnz     short loc_180009B28
0x180009b3f  jmp     short loc_180009B4A
0x180009b41  test    rcx, rcx
0x180009b44  jnz     loc_180009FDD
0x180009b4a  cmp     [rsp+2310h+var_22A8], edi
0x180009b4e  jz      loc_180009CDF
0x180009b54  lea     rax, [rsp+2310h+hKey]
0x180009b59  mov     [rsp+2310h+hKey], rdi
0x180009b5e  mov     r14d, 2001Fh
0x180009b64  mov     [rsp+2310h+phkResult], rax; phkResult
0x180009b69  mov     r9d, r14d; samDesired
0x180009b6c  xor     r8d, r8d; ulOptions
0x180009b6f  mov     rdx, rsi; lpSubKey
0x180009b72  mov     rcx, r15; hKey
0x180009b75  call    cs:__imp_RegOpenKeyExW
0x180009b7b  test    eax, eax
0x180009b7d  jnz     short loc_180009BA0
0x180009b7f  mov     eax, edi
0x180009b81  test    rbx, rbx
0x180009b84  jz      short loc_180009B8F
0x180009b86  mov     rcx, rbx; hKey
0x180009b89  call    cs:__imp_RegCloseKey
0x180009b8f  mov     rbx, [rsp+2310h+hKey]
0x180009b94  mov     [rbp+2210h+var_2290], rbx
0x180009b98  test    eax, eax
0x180009b9a  jz      loc_180009C4B
0x180009ba0  lea     rax, [rsp+2310h+hKey]
0x180009ba5  mov     [rsp+2310h+hKey], rdi
0x180009baa  mov     r9d, 20019h; samDesired
0x180009bb0  mov     [rsp+2310h+phkResult], rax; phkResult
0x180009bb5  xor     r8d, r8d; ulOptions
0x180009bb8  mov     rdx, rsi; lpSubKey
0x180009bbb  mov     rcx, r15; hKey
0x180009bbe  call    cs:__imp_RegOpenKeyExW
0x180009bc4  test    eax, eax
0x180009bc6  jnz     short loc_180009BE5
0x180009bc8  mov     eax, edi
0x180009bca  test    rbx, rbx
0x180009bcd  jz      short loc_180009BD8
0x180009bcf  mov     rcx, rbx; hKey
0x180009bd2  call    cs:__imp_RegCloseKey
0x180009bd8  mov     rbx, [rsp+2310h+hKey]
0x180009bdd  mov     [rbp+2210h+var_2290], rbx
0x180009be1  test    eax, eax
0x180009be3  jz      short loc_180009C4B
0x180009be5  lea     rax, [rsp+2310h+hKey]
0x180009bea  mov     dword ptr [rsp+2310h+hKey], edi
0x180009bee  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x180009bf3  xor     r9d, r9d; lpClass
0x180009bf6  lea     rax, [rsp+2310h+var_2298]
0x180009bfb  mov     [rsp+2310h+var_2298], rdi
0x180009c00  mov     [rsp+2310h+var_22D8], rax; phkResult
0x180009c05  xor     r8d, r8d; Reserved
0x180009c08  mov     [rsp+2310h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180009c0d  mov     rdx, rsi; lpSubKey
0x180009c10  mov     [rsp+2310h+samDesired], r14d; samDesired
0x180009c15  mov     rcx, r15; hKey
0x180009c18  mov     dword ptr [rsp+2310h+phkResult], edi; dwOptions
0x180009c1c  call    cs:__imp_RegCreateKeyExW
0x180009c22  test    eax, eax
0x180009c24  jnz     loc_180009F88
0x180009c2a  mov     eax, edi
0x180009c2c  test    rbx, rbx
0x180009c2f  jz      short loc_180009C3A
0x180009c31  mov     rcx, rbx; hKey
0x180009c34  call    cs:__imp_RegCloseKey
0x180009c3a  mov     rbx, [rsp+2310h+var_2298]
0x180009c3f  mov     [rbp+2210h+var_2290], rbx
0x180009c43  test    eax, eax
0x180009c45  jnz     loc_180009F88
0x180009c4b  mov     rdx, rsi; unsigned __int16 *
0x180009c4e  mov     rcx, r13; this
0x180009c51  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009c56  xor     edx, edx
0x180009c58  mov     edi, eax
0x180009c5a  test    eax, eax
0x180009c5c  js      loc_180009F91
0x180009c62  cmp     word ptr [rsi], 3Dh ; '='
0x180009c66  jnz     short loc_180009C8A
0x180009c68  mov     r9, rsi; unsigned __int16 *
0x180009c6b  lea     rdx, [rbp+2210h+var_2290]; struct ATL::CRegKey *
0x180009c6f  xor     r8d, r8d; unsigned __int16 *
0x180009c72  mov     rcx, r13; this
0x180009c75  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180009c7a  mov     rbx, [rbp+2210h+var_2290]
0x180009c7e  xor     edx, edx
0x180009c80  mov     edi, eax
0x180009c82  test    eax, eax
0x180009c84  js      loc_180009F91
0x180009c8a  mov     r12d, [rsp+2310h+var_22A8]
0x180009c8f  cmp     word ptr [rsi], 7Bh ; '{'
0x180009c93  jnz     loc_180009E26
0x180009c99  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009c9d  inc     rax
0x180009ca0  cmp     [rsi+rax*2], dx
0x180009ca4  jnz     short loc_180009C9D
0x180009ca6  cmp     rax, 1
0x180009caa  jnz     loc_180009E26
0x180009cb0  mov     dword ptr [rsp+2310h+phkResult], edx; int
0x180009cb4  mov     r9d, r12d; int
0x180009cb7  mov     rdx, rsi; unsigned __int16 *
0x180009cba  mov     r8, rbx; HKEY
0x180009cbd  mov     rcx, r13; this
0x180009cc0  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180009cc5  mov     edi, eax
0x180009cc7  test    eax, eax
0x180009cc9  js      loc_180009F91
0x180009ccf  mov     rdx, rsi; unsigned __int16 *
0x180009cd2  mov     rcx, r13; this
0x180009cd5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009cda  jmp     loc_180009B0E
0x180009cdf  mov     edi, [rbp+2210h+arg_20]
0x180009ce5  xor     eax, eax
0x180009ce7  test    edi, edi
  ... truncated ...
```
