# ATL::CRegParser::RegisterSubkeys(char *,HKEY__ *,int,int)

- ea: `0x180005408`
- end: `0x180005b92`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEADPEAUHKEY__@@HH@Z`
- size: `1930`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, char *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180004f3c`
- `0x180005408`

## callees

- `0x180002e4c`
- `0x180003738`
- `0x1800037f4`
- `0x180003de8`
- `0x1800048d0`
- `0x180004df8`
- `0x180005408`
- `0x18000640c`
- `0x18000b640`
- `0x18000b700`

## import_xrefs

- `msvcrt!strncpy_s` at `0x1800058ca`
- `msvcrt!strncpy_s` at `0x1800058ca`
- `ADVAPI32!RegDeleteValueA` at `0x18000565f`
- `ADVAPI32!RegDeleteValueA` at `0x18000565f`
- `ADVAPI32!RegCreateKeyExA` at `0x180005791`
- `ADVAPI32!RegCreateKeyExA` at `0x180005791`
- `ADVAPI32!RegOpenKeyExA` at `0x180005642`
- `ADVAPI32!RegOpenKeyExA` at `0x1800056ea`
- `ADVAPI32!RegOpenKeyExA` at `0x180005733`
- `ADVAPI32!RegOpenKeyExA` at `0x18000587e`
- `ADVAPI32!RegOpenKeyExA` at `0x180005642`
- `ADVAPI32!RegOpenKeyExA` at `0x1800056ea`
- `ADVAPI32!RegOpenKeyExA` at `0x180005733`
- `ADVAPI32!RegOpenKeyExA` at `0x18000587e`
- `ADVAPI32!RegQueryInfoKeyA` at `0x1800059f1`
- `ADVAPI32!RegQueryInfoKeyA` at `0x180005a87`
- `ADVAPI32!RegQueryInfoKeyA` at `0x1800059f1`
- `ADVAPI32!RegQueryInfoKeyA` at `0x180005a87`
- `ADVAPI32!RegCloseKey` at `0x180005678`
- `ADVAPI32!RegCloseKey` at `0x1800056fe`
- `ADVAPI32!RegCloseKey` at `0x180005747`
- `ADVAPI32!RegCloseKey` at `0x1800057a9`
- `ADVAPI32!RegCloseKey` at `0x180005893`
- `ADVAPI32!RegCloseKey` at `0x180005aa2`
- `ADVAPI32!RegCloseKey` at `0x180005b07`
- `ADVAPI32!RegCloseKey` at `0x180005b43`
- `ADVAPI32!RegCloseKey` at `0x180005b53`
- `ADVAPI32!RegCloseKey` at `0x180005678`
- `ADVAPI32!RegCloseKey` at `0x1800056fe`
- `ADVAPI32!RegCloseKey` at `0x180005747`
- `ADVAPI32!RegCloseKey` at `0x1800057a9`
- `ADVAPI32!RegCloseKey` at `0x180005893`
- `ADVAPI32!RegCloseKey` at `0x180005aa2`
- `ADVAPI32!RegCloseKey` at `0x180005b07`
- `ADVAPI32!RegCloseKey` at `0x180005b43`
- `ADVAPI32!RegCloseKey` at `0x180005b53`
- `KERNEL32!lstrcmpiA` at `0x180005482`
- `KERNEL32!lstrcmpiA` at `0x180005495`
- `KERNEL32!lstrcmpiA` at `0x18000550d`
- `KERNEL32!lstrcmpiA` at `0x180005574`
- `KERNEL32!lstrcmpiA` at `0x1800055a2`
- `KERNEL32!lstrcmpiA` at `0x180005a14`
- `KERNEL32!lstrcmpiA` at `0x180005482`
- `KERNEL32!lstrcmpiA` at `0x180005495`
- `KERNEL32!lstrcmpiA` at `0x18000550d`
- `KERNEL32!lstrcmpiA` at `0x180005574`
- `KERNEL32!lstrcmpiA` at `0x1800055a2`
- `KERNEL32!lstrcmpiA` at `0x180005a14`
- `USER32!CharNextA` at `0x1800054e3`
- `USER32!CharNextA` at `0x1800056a5`
- `USER32!CharNextA` at `0x1800054e3`
- `USER32!CharNextA` at `0x1800056a5`

## string_xrefs

- `0x18000548b`: `ForceRemove`
- `0x18000556a`: `NoRemove`
- `0x180005478`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(ATL::CRegParser *this, char *a2, HKEY a3, int a4, int a5)
{
  int v5; // r12d
  HKEY v6; // r15
  HKEY v9; // rbx
  __int64 result; // rax
  int Token; // edi
  int v12; // r14d
  int v13; // edi
  CHAR v14; // al
  const CHAR *v15; // rcx
  int v16; // r12d
  int v17; // eax
  LSTATUS v18; // eax
  HKEY v19; // r14
  LSTATUS v20; // eax
  int v21; // eax
  CHAR v22; // al
  const CHAR *v23; // rcx
  LSTATUS v24; // eax
  LSTATUS v25; // eax
  __int64 v26; // rax
  LSTATUS v27; // r14d
  int v28; // r15d
  errno_t v29; // eax
  __int64 v30; // rax
  int v31; // r14d
  LSTATUS v32; // eax
  unsigned int v33; // ecx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+68h] [rbp-98h]
  HKEY v36; // [rsp+70h] [rbp-90h]
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v38[3]; // [rsp+80h] [rbp-80h] BYREF
  HKEY v39; // [rsp+98h] [rbp-68h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-60h]
  __int64 v41; // [rsp+A8h] [rbp-58h]
  char Destination[272]; // [rsp+B0h] [rbp-50h] BYREF
  CHAR ValueName[4096]; // [rsp+1C0h] [rbp+C0h] BYREF

  v5 = a4;
  v35 = a4;
  v6 = a3;
  v36 = a3;
  v9 = 0;
  memset(v38, 0, sizeof(v38));
  result = ATL::CRegParser::NextToken(this, a2);
  Token = result;
  if ( (int)result < 0 )
    return result;
  if ( *a2 == 125 )
    goto LABEL_111;
  while ( 1 )
  {
    v12 = lstrcmpiA(a2, "Delete");
    if ( !lstrcmpiA(a2, "ForceRemove") || !v12 )
    {
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
      v13 = 0;
      if ( v5 )
      {
        v39 = 0;
        v40 = 0;
        v41 = 0;
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
            goto LABEL_116;
          }
          v15 = CharNextA(v15);
          v14 = *v15;
        }
        while ( *v15 );
LABEL_13:
        while ( lstrcmpiA(a2, (LPCSTR)(&ATL::CRegParser::rgszNeverDelete)[v13]) )
        {
          if ( ++v13 >= 12 )
          {
            v39 = v6;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v39, a2);
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
    if ( !lstrcmpiA(a2, "NoRemove") )
    {
      v16 = 0;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
    }
    if ( !lstrcmpiA(a2, "Val") )
      break;
    v22 = *a2;
    if ( *a2 )
    {
      v23 = a2;
      while ( v22 != 92 )
      {
        v23 = CharNextA(v23);
        v22 = *v23;
        if ( !*v23 )
          goto LABEL_43;
      }
      if ( v23 )
        goto LABEL_116;
    }
LABEL_43:
    if ( v35 )
    {
      hKey = 0;
      if ( RegOpenKeyExA(v6, a2, 0, 0x2001Fu, &hKey) )
        goto LABEL_126;
      v24 = 0;
      if ( v9 )
        v24 = RegCloseKey(v9);
      v9 = hKey;
      v38[0] = hKey;
      if ( v24 )
      {
LABEL_126:
        hKey = 0;
        if ( RegOpenKeyExA(v6, a2, 0, 0x20019u, &hKey) )
          goto LABEL_127;
        v25 = 0;
        if ( v9 )
          v25 = RegCloseKey(v9);
        v9 = hKey;
        v38[0] = hKey;
        if ( v25 )
        {
LABEL_127:
          LODWORD(hKey) = 0;
          phkResult = 0;
          v18 = RegCreateKeyExA(v6, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, (LPDWORD)&hKey);
          if ( v18 )
            goto LABEL_109;
          v18 = 0;
          if ( v9 )
            v18 = RegCloseKey(v9);
          v9 = phkResult;
          v38[0] = phkResult;
          if ( v18 )
          {
LABEL_109:
            v33 = v18;
            goto LABEL_110;
          }
        }
      }
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_111;
      if ( *a2 == 61 )
      {
        v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)v38, 0, a2);
        Token = v17;
        v9 = (HKEY)v38[0];
        goto LABEL_59;
      }
LABEL_60:
      v5 = v35;
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
      v27 = RegOpenKeyExA(v6, a2, 0, 0x20019u, &phkResult);
      if ( !v27 )
      {
        if ( v9 )
          v27 = RegCloseKey(v9);
        v9 = phkResult;
        v38[0] = phkResult;
      }
    }
    v28 = 1;
    if ( !v27 )
      v28 = a5;
    v29 = strncpy_s(Destination, 0x104u, a2, 0xFFFFFFFFFFFFFFFFuLL);
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
        v6 = v36;
        goto LABEL_93;
      }
      v33 = v27;
LABEL_110:
      Token = ATL::AtlHresultFromWin32(v33);
      goto LABEL_111;
    }
    v31 = 0;
    if ( a5 )
    {
      LODWORD(hKey) = 0;
      if ( !RegQueryInfoKeyA(v9, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      {
        if ( (_DWORD)hKey )
        {
          while ( lstrcmpiA(Destination, (LPCSTR)(&ATL::CRegParser::rgszNeverDelete)[v31]) )
          {
            if ( ++v31 >= 12 )
            {
              if ( v16 )
              {
                ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v38, Destination);
                v9 = (HKEY)v38[0];
              }
              goto LABEL_92;
            }
          }
          goto LABEL_92;
        }
      }
    }
    LODWORD(hKey) = 0;
    if ( !RegQueryInfoKeyA(v9, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0) )
      LOBYTE(v31) = (_DWORD)hKey != 0;
    if ( v9 )
    {
      v32 = RegCloseKey(v9);
      v9 = 0;
      v38[0] = 0;
      if ( v32 )
        return ATL::AtlHresultFromWin32(v32);
    }
    if ( !v16 )
      goto LABEL_92;
    v6 = v36;
    if ( !v31 )
    {
      v40 = 0;
      v41 = 0;
      v39 = v36;
      v18 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&v39, Destination);
      if ( v18 )
        goto LABEL_109;
    }
LABEL_93:
    if ( *a2 == 125 )
      goto LABEL_111;
    v5 = v35;
  }
  Token = ATL::CRegParser::NextToken(this, ValueName);
  if ( Token < 0 )
    goto LABEL_111;
  Token = ATL::CRegParser::NextToken(this, a2);
  if ( Token < 0 )
    goto LABEL_111;
  if ( *a2 != 61 )
  {
LABEL_116:
    if ( v9 )
      RegCloseKey(v9);
    return 2147614729LL;
  }
  if ( v35 )
  {
    v40 = 0;
    v41 = 0;
    v39 = v6;
    v17 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)&v39, ValueName, a2);
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
  v18 = RegOpenKeyExA(v6, 0, 0, 0x20006u, &hKey);
  if ( v18 )
    goto LABEL_109;
  v19 = hKey;
  v20 = RegDeleteValueA(hKey, ValueName);
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
0x180005408  push    rbp
0x18000540a  push    rbx
0x18000540b  push    rsi
0x18000540c  push    rdi
0x18000540d  push    r12
0x18000540f  push    r13
0x180005411  push    r14
0x180005413  push    r15
0x180005415  lea     rbp, [rsp-10D8h]
0x18000541d  mov     eax, 11D8h
0x180005422  call    _alloca_probe
0x180005427  sub     rsp, rax
0x18000542a  mov     rax, cs:__security_cookie
0x180005431  xor     rax, rsp
0x180005434  mov     [rbp+1110h+var_50], rax
0x18000543b  mov     r12d, r9d
0x18000543e  mov     [rsp+1210h+var_11A8], r9d
0x180005443  mov     r15, r8
0x180005446  mov     [rsp+1210h+var_11A0], r8
0x18000544b  mov     rsi, rdx
0x18000544e  mov     r13, rcx
0x180005451  xor     ebx, ebx
0x180005453  mov     [rbp+1110h+var_1190], rbx
0x180005457  mov     [rbp+1110h+var_1188], rbx
0x18000545b  mov     [rbp+1110h+var_1180], rbx
0x18000545f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x180005464  mov     edi, eax
0x180005466  test    eax, eax
0x180005468  jns     short loc_18000546F
0x18000546a  jmp     loc_180005B0F
0x18000546f  cmp     byte ptr [rsi], 7Dh ; '}'
0x180005472  jz      loc_180005AFF
0x180005478  lea     rdx, String2; "Delete"
0x18000547f  mov     rcx, rsi; lpString1
0x180005482  call    cs:__imp_lstrcmpiA
0x180005488  mov     r14d, eax
0x18000548b  lea     rdx, aForceremove; "ForceRemove"
0x180005492  mov     rcx, rsi; lpString1
0x180005495  call    cs:__imp_lstrcmpiA
0x18000549b  xor     edi, edi
0x18000549d  test    eax, eax
0x18000549f  jz      short loc_1800054AA
0x1800054a1  test    r14d, r14d
0x1800054a4  jnz     loc_180005564
0x1800054aa  mov     rdx, rsi; char *
0x1800054ad  mov     rcx, r13; this
0x1800054b0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x1800054b5  mov     edi, eax
0x1800054b7  test    eax, eax
0x1800054b9  js      loc_180005AFF
0x1800054bf  xor     edi, edi
0x1800054c1  test    r12d, r12d
0x1800054c4  jz      loc_180005564
0x1800054ca  mov     [rbp+1110h+var_1178], rdi
0x1800054ce  mov     [rbp+1110h+var_1170], rdi
0x1800054d2  mov     [rbp+1110h+var_1168], rdi
0x1800054d6  mov     al, [rsi]
0x1800054d8  test    al, al
0x1800054da  jz      short loc_1800054FD
0x1800054dc  mov     rcx, rsi; lpsz
0x1800054df  cmp     al, 5Ch ; '\'
0x1800054e1  jz      short loc_1800054F4
0x1800054e3  call    cs:__imp_CharNextA
0x1800054e9  mov     rcx, rax
0x1800054ec  mov     al, [rax]
0x1800054ee  test    al, al
0x1800054f0  jnz     short loc_1800054DF
0x1800054f2  jmp     short loc_1800054FD
0x1800054f4  test    rcx, rcx
0x1800054f7  jnz     loc_180005B4B
0x1800054fd  mov     edx, edi
0x1800054ff  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBDB; char const * const near * const ATL::CRegParser::rgszNeverDelete
0x180005506  mov     rdx, [rax+rdx*8]; lpString2
0x18000550a  mov     rcx, rsi; lpString1
0x18000550d  call    cs:__imp_lstrcmpiA
0x180005513  test    eax, eax
0x180005515  jz      short loc_18000552E
0x180005517  inc     edi
0x180005519  cmp     edi, 0Ch
0x18000551c  jl      short loc_1800054FD
0x18000551e  mov     [rbp+1110h+var_1178], r15
0x180005522  mov     rdx, rsi; char *
0x180005525  lea     rcx, [rbp+1110h+var_1178]; this
0x180005529  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBD@Z; ATL::CRegKey::RecurseDeleteKey(char const *)
0x18000552e  xor     edi, edi
0x180005530  test    r14d, r14d
0x180005533  jnz     short loc_180005564
0x180005535  mov     rdx, rsi; char *
0x180005538  mov     rcx, r13; this
0x18000553b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x180005540  mov     edi, eax
0x180005542  test    eax, eax
0x180005544  js      loc_180005AFF
0x18000554a  mov     rdx, rsi; char *
0x18000554d  mov     rcx, r13; this
0x180005550  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::SkipAssignment(char *)
0x180005555  mov     edi, eax
0x180005557  test    eax, eax
0x180005559  js      loc_180005AFF
0x18000555f  jmp     loc_1800057FF
0x180005564  mov     r12d, 1
0x18000556a  lea     rdx, aNoremove; "NoRemove"
0x180005571  mov     rcx, rsi; lpString1
0x180005574  call    cs:__imp_lstrcmpiA
0x18000557a  test    eax, eax
0x18000557c  jnz     short loc_180005598
0x18000557e  mov     r12d, edi
0x180005581  mov     rdx, rsi; char *
0x180005584  mov     rcx, r13; this
0x180005587  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x18000558c  mov     edi, eax
0x18000558e  test    eax, eax
0x180005590  js      loc_180005AFF
0x180005596  xor     edi, edi
0x180005598  lea     rdx, aVal; "Val"
0x18000559f  mov     rcx, rsi; lpString1
0x1800055a2  call    cs:__imp_lstrcmpiA
0x1800055a8  test    eax, eax
0x1800055aa  jnz     loc_180005698
0x1800055b0  lea     rdx, [rbp+1110h+ValueName]; char *
0x1800055b7  mov     rcx, r13; this
0x1800055ba  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x1800055bf  mov     edi, eax
0x1800055c1  test    eax, eax
0x1800055c3  js      loc_180005AFF
0x1800055c9  mov     rdx, rsi; char *
0x1800055cc  mov     rcx, r13; this
0x1800055cf  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x1800055d4  mov     edi, eax
0x1800055d6  test    eax, eax
0x1800055d8  js      loc_180005AFF
0x1800055de  cmp     byte ptr [rsi], 3Dh ; '='
0x1800055e1  jnz     loc_180005B4B
0x1800055e7  xor     edi, edi
0x1800055e9  cmp     [rsp+1210h+var_11A8], edi
0x1800055ed  jz      short loc_180005618
0x1800055ef  mov     [rbp+1110h+var_1170], rdi
0x1800055f3  mov     [rbp+1110h+var_1168], rdi
0x1800055f7  mov     [rbp+1110h+var_1178], r15
0x1800055fb  mov     r9, rsi; char *
0x1800055fe  lea     r8, [rbp+1110h+ValueName]; char *
0x180005605  lea     rdx, [rbp+1110h+var_1178]; struct ATL::CRegKey *
0x180005609  mov     rcx, r13; this
0x18000560c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBDPEAD@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,char const *,char *)
0x180005611  mov     edi, eax
0x180005613  jmp     loc_1800057F2
0x180005618  cmp     [rbp+1110h+arg_20], edi
0x18000561e  jnz     short loc_18000567E
0x180005620  test    r12d, r12d
0x180005623  jz      short loc_18000567E
0x180005625  mov     [rsp+1210h+hKey], rdi
0x18000562a  lea     rax, [rsp+1210h+hKey]
0x18000562f  mov     [rsp+1210h+phkResult], rax; phkResult
0x180005634  mov     r9d, 20006h; samDesired
0x18000563a  xor     r8d, r8d; ulOptions
0x18000563d  xor     edx, edx; lpSubKey
0x18000563f  mov     rcx, r15; hKey
0x180005642  call    cs:__imp_RegOpenKeyExA
0x180005648  test    eax, eax
0x18000564a  jnz     loc_180005AF6
0x180005650  mov     r14, [rsp+1210h+hKey]
0x180005655  lea     rdx, [rbp+1110h+ValueName]; lpValueName
0x18000565c  mov     rcx, r14; hKey
0x18000565f  call    cs:__imp_RegDeleteValueA
0x180005665  test    eax, 0FFFFFFFDh
0x18000566a  jnz     loc_180005B32
0x180005670  test    r14, r14
0x180005673  jz      short loc_18000567E
0x180005675  mov     rcx, r14; hKey
0x180005678  call    cs:__imp_RegCloseKey
0x18000567e  mov     rdx, rsi; char *
0x180005681  mov     rcx, r13; this
0x180005684  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::SkipAssignment(char *)
0x180005689  mov     edi, eax
0x18000568b  test    eax, eax
0x18000568d  js      loc_180005AFF
0x180005693  jmp     loc_180005991
0x180005698  mov     al, [rsi]
0x18000569a  test    al, al
0x18000569c  jz      short loc_1800056BF
0x18000569e  mov     rcx, rsi; lpsz
0x1800056a1  cmp     al, 5Ch ; '\'
0x1800056a3  jz      short loc_1800056B6
0x1800056a5  call    cs:__imp_CharNextA
0x1800056ab  mov     rcx, rax
0x1800056ae  mov     al, [rax]
0x1800056b0  test    al, al
0x1800056b2  jnz     short loc_1800056A1
0x1800056b4  jmp     short loc_1800056BF
0x1800056b6  test    rcx, rcx
0x1800056b9  jnz     loc_180005B4B
0x1800056bf  cmp     [rsp+1210h+var_11A8], edi
0x1800056c3  jz      loc_180005852
0x1800056c9  mov     [rsp+1210h+hKey], rdi
0x1800056ce  lea     rax, [rsp+1210h+hKey]
0x1800056d3  mov     [rsp+1210h+phkResult], rax; phkResult
0x1800056d8  mov     r14d, 2001Fh
0x1800056de  mov     r9d, r14d; samDesired
0x1800056e1  xor     r8d, r8d; ulOptions
0x1800056e4  mov     rdx, rsi; lpSubKey
0x1800056e7  mov     rcx, r15; hKey
0x1800056ea  call    cs:__imp_RegOpenKeyExA
0x1800056f0  test    eax, eax
0x1800056f2  jnz     short loc_180005715
0x1800056f4  mov     eax, edi
0x1800056f6  test    rbx, rbx
0x1800056f9  jz      short loc_180005704
0x1800056fb  mov     rcx, rbx; hKey
0x1800056fe  call    cs:__imp_RegCloseKey
0x180005704  mov     rbx, [rsp+1210h+hKey]
0x180005709  mov     [rbp+1110h+var_1190], rbx
0x18000570d  test    eax, eax
0x18000570f  jz      loc_1800057C0
0x180005715  mov     [rsp+1210h+hKey], rdi
0x18000571a  lea     rax, [rsp+1210h+hKey]
0x18000571f  mov     [rsp+1210h+phkResult], rax; phkResult
0x180005724  mov     r9d, 20019h; samDesired
0x18000572a  xor     r8d, r8d; ulOptions
0x18000572d  mov     rdx, rsi; lpSubKey
0x180005730  mov     rcx, r15; hKey
0x180005733  call    cs:__imp_RegOpenKeyExA
0x180005739  test    eax, eax
0x18000573b  jnz     short loc_18000575A
0x18000573d  mov     eax, edi
0x18000573f  test    rbx, rbx
0x180005742  jz      short loc_18000574D
0x180005744  mov     rcx, rbx; hKey
0x180005747  call    cs:__imp_RegCloseKey
0x18000574d  mov     rbx, [rsp+1210h+hKey]
0x180005752  mov     [rbp+1110h+var_1190], rbx
0x180005756  test    eax, eax
0x180005758  jz      short loc_1800057C0
0x18000575a  mov     dword ptr [rsp+1210h+hKey], edi
0x18000575e  mov     [rsp+1210h+var_1198], rdi
0x180005763  lea     rax, [rsp+1210h+hKey]
0x180005768  mov     [rsp+1210h+lpdwDisposition], rax; lpdwDisposition
0x18000576d  lea     rax, [rsp+1210h+var_1198]
0x180005772  mov     [rsp+1210h+var_11D8], rax; phkResult
0x180005777  mov     [rsp+1210h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000577c  mov     [rsp+1210h+samDesired], r14d; samDesired
0x180005781  mov     dword ptr [rsp+1210h+phkResult], edi; dwOptions
0x180005785  xor     r9d, r9d; lpClass
0x180005788  xor     r8d, r8d; Reserved
0x18000578b  mov     rdx, rsi; lpSubKey
0x18000578e  mov     rcx, r15; hKey
0x180005791  call    cs:__imp_RegCreateKeyExA
0x180005797  test    eax, eax
0x180005799  jnz     loc_180005AF6
0x18000579f  mov     eax, edi
0x1800057a1  test    rbx, rbx
0x1800057a4  jz      short loc_1800057AF
0x1800057a6  mov     rcx, rbx; hKey
0x1800057a9  call    cs:__imp_RegCloseKey
0x1800057af  mov     rbx, [rsp+1210h+var_1198]
0x1800057b4  mov     [rbp+1110h+var_1190], rbx
0x1800057b8  test    eax, eax
0x1800057ba  jnz     loc_180005AF6
0x1800057c0  mov     rdx, rsi; char *
0x1800057c3  mov     rcx, r13; this
0x1800057c6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x1800057cb  mov     edi, eax
0x1800057cd  test    eax, eax
0x1800057cf  js      loc_180005AFF
0x1800057d5  cmp     byte ptr [rsi], 3Dh ; '='
0x1800057d8  jnz     short loc_1800057FA
0x1800057da  mov     r9, rsi; char *
0x1800057dd  xor     r8d, r8d; char *
0x1800057e0  lea     rdx, [rbp+1110h+var_1190]; struct ATL::CRegKey *
0x1800057e4  mov     rcx, r13; this
0x1800057e7  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBDPEAD@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,char const *,char *)
0x1800057ec  mov     edi, eax
0x1800057ee  mov     rbx, [rbp+1110h+var_1190]
0x1800057f2  test    eax, eax
0x1800057f4  js      loc_180005AFF
0x1800057fa  mov     r12d, [rsp+1210h+var_11A8]
0x1800057ff  cmp     byte ptr [rsi], 7Bh ; '{'
0x180005802  jnz     loc_180005991
0x180005808  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000580c  inc     rax
0x18000580f  cmp     byte ptr [rsi+rax], 0
0x180005813  jnz     short loc_18000580C
0x180005815  cmp     rax, 1
0x180005819  jnz     loc_180005991
0x18000581f  mov     dword ptr [rsp+1210h+phkResult], 0; int
0x180005827  mov     r9d, r12d; int
0x18000582a  mov     r8, rbx; HKEY
0x18000582d  mov     rdx, rsi; char *
0x180005830  mov     rcx, r13; this
0x180005833  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEADPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(char *,HKEY__ *,int,int)
0x180005838  mov     edi, eax
0x18000583a  test    eax, eax
0x18000583c  js      loc_180005AFF
0x180005842  mov     rdx, rsi; char *
0x180005845  mov     rcx, r13; this
0x180005848  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x18000584d  jmp     loc_180005689
0x180005852  mov     edi, [rbp+1110h+arg_20]
0x180005858  test    edi, edi
0x18000585a  jnz     short loc_1800058A7
0x18000585c  mov     [rsp+1210h+var_1198], 0
  ... truncated ...
```
