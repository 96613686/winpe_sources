# _ReadPolicies(void *,ulong *,_tagEASPolicy * *)

- ea: `0x18009542c`
- end: `0x18009586a`
- name: `?_ReadPolicies@@YAJPEAXPEAKPEAPEAU_tagEASPolicy@@@Z`
- size: `1086`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned int *, struct _tagEASPolicy **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180094d5c`

## callees

- `0x1800680e4`
- `0x180095170`
- `0x18009542c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180095693`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180095693`
- `KERNEL32!LocalAlloc` at `0x180095534`
- `KERNEL32!LocalAlloc` at `0x180095584`
- `KERNEL32!LocalAlloc` at `0x1800955c7`
- `KERNEL32!LocalAlloc` at `0x180095534`
- `KERNEL32!LocalAlloc` at `0x180095584`
- `KERNEL32!LocalAlloc` at `0x1800955c7`
- `KERNEL32!LocalFree` at `0x18009582d`
- `KERNEL32!LocalFree` at `0x18009583b`
- `KERNEL32!LocalFree` at `0x18009582d`
- `KERNEL32!LocalFree` at `0x18009583b`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180095678`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180095678`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800954ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800954ca`

## string_xrefs

- `0x180095509`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x1800955fe`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x1800956b3`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18009570d`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x1800957c5`: `onecore\ds\security\eas\policyengine\common.cpp`

## pseudocode

```c
__int64 __fastcall _ReadPolicies(HKEY hKey, unsigned int *a2, struct _tagEASPolicy **a3)
{
  unsigned int v3; // r12d
  struct _tagEASPolicy *v4; // r14
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  __int64 v7; // r8
  SIZE_T v8; // rdx
  WCHAR *v9; // r15
  BYTE *v10; // r13
  __int64 v11; // xmm6_8
  DWORD i; // ecx
  LSTATUS v13; // eax
  int v14; // ecx
  int v15; // r12d
  __int16 v16; // ax
  __int64 v17; // rax
  LPDWORD lpcSubKeys; // [rsp+28h] [rbp-79h]
  LPDWORD lpcSubKeysa; // [rsp+28h] [rbp-79h]
  const wchar_t *lpcbMaxSubKeyLen; // [rsp+30h] [rbp-71h]
  unsigned int v22; // [rsp+68h] [rbp-39h]
  DWORD cValues; // [rsp+6Ch] [rbp-35h] BYREF
  DWORD cbMaxValueLen; // [rsp+70h] [rbp-31h] BYREF
  DWORD cchValueName; // [rsp+74h] [rbp-2Dh] BYREF
  DWORD cbData; // [rsp+78h] [rbp-29h] BYREF
  DWORD Type; // [rsp+7Ch] [rbp-25h] BYREF
  DWORD v28; // [rsp+80h] [rbp-21h]
  int v29; // [rsp+84h] [rbp-1Dh]
  __int128 v30; // [rsp+88h] [rbp-19h]
  __int64 v31; // [rsp+98h] [rbp-9h]
  DWORD cbMaxValueNameLen; // [rsp+120h] [rbp+7Fh] BYREF

  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v22 = 0;
  v3 = 0;
  v31 = 0;
  v4 = 0;
  *a2 = 0;
  *a3 = 0;
  v30 = 0;
  if ( !hKey )
    goto LABEL_2;
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  v5 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0xC0070000;
    v7 = v5;
    lpcbMaxSubKeyLen = L"RegQueryInfoKey";
    LODWORD(lpcSubKeys) = 496;
    goto LABEL_7;
  }
  if ( !cValues )
  {
LABEL_2:
    v5 = 0;
    goto LABEL_47;
  }
  v4 = (struct _tagEASPolicy *)LocalAlloc(0, 32LL * cValues);
  if ( !v4 )
  {
    v7 = 3221225495LL;
    lpcbMaxSubKeyLen = L"LocalAlloc";
    v5 = -1073741801;
    LODWORD(lpcSubKeys) = 510;
LABEL_7:
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      v7,
      L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
      lpcSubKeys,
      lpcbMaxSubKeyLen,
      &sourceString);
    goto LABEL_47;
  }
  v8 = 2LL * ++cbMaxValueNameLen;
  v9 = (WCHAR *)LocalAlloc(0x40u, v8);
  if ( !v9 )
  {
    v5 = -1073741801;
    LODWORD(lpcSubKeys) = 519;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221225495LL,
      L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
      lpcSubKeys,
      L"LocalAlloc",
      &sourceString);
    goto LABEL_47;
  }
  v10 = (BYTE *)LocalAlloc(0x40u, cbMaxValueLen);
  if ( !v10 )
  {
    v5 = -1073741801;
    LODWORD(lpcSubKeys) = 527;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221225495LL,
      L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
      lpcSubKeys,
      L"LocalAlloc",
      &sourceString);
    goto LABEL_45;
  }
  v11 = v31;
  for ( i = 0; ; i = v28 + 1 )
  {
    v28 = i;
    if ( i >= cValues )
    {
      *a2 = v3;
      *a3 = v4;
      v4 = 0;
      v5 = 0;
      goto LABEL_45;
    }
    Type = 0;
    LOWORD(v30) = 0;
    cchValueName = cbMaxValueNameLen;
    cbData = cbMaxValueLen;
    v13 = RegEnumValueW(hKey, i, v9, &cchValueName, 0, &Type, v10, &cbData);
    v5 = v13;
    if ( v13 )
      break;
    v9[cchValueName] = 0;
    v29 = _o__wtoi(v9);
    v14 = v29;
    if ( v29 <= 0 )
    {
      LODWORD(lpcSubKeysa) = 560;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        3221225485LL,
        L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
        lpcSubKeysa,
        L"Invalid policy id",
        v9);
      continue;
    }
    if ( cbData )
    {
      if ( Type != 4 )
      {
        v15 = -2147024809;
        LODWORD(lpcSubKeysa) = 433;
        DbgPrintfW(
          1u,
          L"(0x%08x) %ws:%u : %ws:%ws\n",
          2147942487LL,
          L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
          lpcSubKeysa,
          L"invalid type",
          &sourceString);
        v14 = v29;
        goto LABEL_27;
      }
      LOWORD(v30) = 19;
      DWORD2(v30) = *(_DWORD *)v10;
    }
    v15 = 0;
LABEL_27:
    v5 = 0;
    if ( v15 )
      v5 = v15 | 0x40000000;
    if ( v5 == -1073282985 )
    {
      v3 = v22;
    }
    else
    {
      if ( v5 )
      {
        LODWORD(lpcSubKeysa) = 574;
        DbgPrintfW(
          1u,
          L"(0x%08x) %ws:%u : %ws:%ws\n",
          v5,
          L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
          lpcSubKeysa,
          L"_RegValueToVariant",
          v9);
        v3 = v22;
        goto LABEL_45;
      }
      if ( v14 == 5 || v14 == 8 )
      {
        LOWORD(v30) = 11;
        if ( DWORD2(v30) )
          v16 = -1;
        else
          v16 = 0;
        WORD4(v30) = v16;
      }
      v17 = 32LL * v22;
      *(_OWORD *)((char *)v4 + v17 + 8) = v30;
      *(_DWORD *)((char *)v4 + v17) = v14;
      *(_QWORD *)((char *)v4 + v17 + 24) = v11;
      v3 = v22 + 1;
      LOWORD(v30) = 0;
      ++v22;
    }
  }
  if ( v13 > 0 )
    v5 = (unsigned __int16)v13 | 0xC0070000;
  LODWORD(lpcSubKeysa) = 552;
  DbgPrintfW(
    1u,
    L"(0x%08x) %ws:%u : %ws:%ws\n",
    v5,
    L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
    lpcSubKeysa,
    L"RegEnumValue",
    &sourceString);
LABEL_45:
  LocalFree(v9);
  if ( v10 )
    LocalFree(v10);
LABEL_47:
  _FreePolicies(v3, v4);
  return v5;
}

```

## disassembly

```asm
0x18009542c  mov     rax, rsp
0x18009542f  mov     [rax+18h], r8
0x180095433  mov     [rax+10h], rdx
0x180095437  mov     [rax+8], rcx
0x18009543b  push    rbp
0x18009543c  push    rbx
0x18009543d  push    rsi
0x18009543e  push    rdi
0x18009543f  push    r12
0x180095441  push    r13
0x180095443  push    r14
0x180095445  push    r15
0x180095447  lea     rbp, [rax-5Fh]
0x18009544b  sub     rsp, 0B8h
0x180095452  xor     esi, esi
0x180095454  movaps  xmmword ptr [rax-58h], xmm6
0x180095458  mov     rax, rcx
0x18009545b  mov     [rbp+57h+cValues], esi
0x18009545e  xor     ecx, ecx
0x180095460  mov     [rbp+57h+cbMaxValueNameLen], esi
0x180095463  mov     [rbp+57h+cbMaxValueLen], esi
0x180095466  xorps   xmm0, xmm0
0x180095469  mov     [rbp+57h+var_90], esi
0x18009546c  mov     r12d, esi
0x18009546f  mov     [rbp+57h+var_60], rcx
0x180095473  mov     r14d, esi
0x180095476  mov     [rdx], esi
0x180095478  mov     [r8], rsi
0x18009547b  movups  [rbp+57h+var_70], xmm0
0x18009547f  test    rax, rax
0x180095482  jnz     short loc_18009548B
0x180095484  mov     ebx, esi
0x180095486  jmp     loc_180095841
0x18009548b  mov     [rsp+58h], rsi; lpftLastWriteTime
0x180095490  lea     rcx, [rbp+57h+cbMaxValueLen]
0x180095494  mov     [rsp+0F0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180095499  xor     r9d, r9d; lpReserved
0x18009549c  mov     [rsp+0F0h+lpcbMaxValueLen], rcx; lpcbMaxValueLen
0x1800954a1  xor     r8d, r8d; lpcchClass
0x1800954a4  lea     rcx, [rbp+57h+cbMaxValueNameLen]
0x1800954a8  xor     edx, edx; lpClass
0x1800954aa  mov     [rsp+0F0h+lpcbMaxValueNameLen], rcx; lpcbMaxValueNameLen
0x1800954af  lea     rcx, [rbp+57h+cValues]
0x1800954b3  mov     [rsp+0F0h+lpcValues], rcx; lpcValues
0x1800954b8  mov     rcx, rax; hKey
0x1800954bb  mov     [rsp+0F0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1800954c0  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x1800954c5  mov     [rsp+0F0h+lpcSubKeys], rsi; lpcSubKeys
0x1800954ca  call    cs:__imp_RegQueryInfoKeyW
0x1800954d0  mov     ebx, eax
0x1800954d2  test    eax, eax
0x1800954d4  jz      short loc_180095521
0x1800954d6  jle     short loc_1800954E1
0x1800954d8  movzx   ebx, ax
0x1800954db  or      ebx, 0C0070000h
0x1800954e1  lea     rsi, sourceString
0x1800954e8  mov     r8d, ebx
0x1800954eb  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x1800954f0  lea     rax, aRegqueryinfoke; "RegQueryInfoKey"
0x1800954f7  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax
0x1800954fc  mov     dword ptr [rsp+0F0h+lpcSubKeys], 1F0h
0x180095504  mov     ecx, 1; unsigned int
0x180095509  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x180095510  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180095517  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18009551c  jmp     loc_180095841
0x180095521  mov     eax, [rbp+57h+cValues]
0x180095524  test    eax, eax
0x180095526  jz      loc_180095484
0x18009552c  mov     edx, eax
0x18009552e  xor     ecx, ecx; uFlags
0x180095530  shl     rdx, 5; uBytes
0x180095534  call    cs:__imp_LocalAlloc
0x18009553a  mov     r14, rax
0x18009553d  test    rax, rax
0x180095540  jnz     short loc_18009556D
0x180095542  lea     rsi, sourceString
0x180095549  mov     r8d, 0C0000017h
0x18009554f  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x180095554  lea     rcx, aLocalalloc; "LocalAlloc"
0x18009555b  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rcx
0x180095560  mov     ebx, r8d
0x180095563  mov     dword ptr [rsp+0F0h+lpcSubKeys], 1FEh
0x18009556b  jmp     short loc_180095504
0x18009556d  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x180095570  mov     edi, 1
0x180095575  add     eax, edi
0x180095577  mov     edx, eax
0x180095579  add     rdx, rdx; uBytes
0x18009557c  mov     [rbp+57h+cbMaxValueNameLen], eax
0x18009557f  lea     ebx, [rdi+3Fh]
0x180095582  mov     ecx, ebx; uFlags
0x180095584  call    cs:__imp_LocalAlloc
0x18009558a  mov     r15, rax
0x18009558d  test    rax, rax
0x180095590  jnz     short loc_1800955C2
0x180095592  lea     rcx, aLocalalloc; "LocalAlloc"
0x180095599  mov     r8d, 0C0000017h
0x18009559f  lea     rsi, sourceString
0x1800955a6  mov     ebx, r8d
0x1800955a9  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x1800955ae  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rcx
0x1800955b3  mov     ecx, edi
0x1800955b5  mov     dword ptr [rsp+0F0h+lpcSubKeys], 207h
0x1800955bd  jmp     loc_180095509
0x1800955c2  mov     edx, [rbp+57h+cbMaxValueLen]; uBytes
0x1800955c5  mov     ecx, ebx; uFlags
0x1800955c7  call    cs:__imp_LocalAlloc
0x1800955cd  mov     r13, rax
0x1800955d0  test    rax, rax
0x1800955d3  jnz     short loc_180095618
0x1800955d5  lea     rsi, sourceString
0x1800955dc  mov     r8d, 0C0000017h
0x1800955e2  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x1800955e7  lea     rcx, aLocalalloc; "LocalAlloc"
0x1800955ee  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rcx
0x1800955f3  mov     ebx, r8d
0x1800955f6  mov     dword ptr [rsp+0F0h+lpcSubKeys], 20Fh
0x1800955fe  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x180095605  mov     ecx, edi; unsigned int
0x180095607  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18009560e  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180095613  jmp     loc_18009582A
0x180095618  movsd   xmm6, [rbp+57h+var_60]
0x18009561d  mov     ecx, esi
0x18009561f  lea     rsi, sourceString
0x180095626  mov     [rbp+57h+var_78], ecx
0x180095629  cmp     ecx, [rbp+57h+cValues]
0x18009562c  jnb     loc_180095817
0x180095632  xor     eax, eax
0x180095634  mov     [rbp+57h+Type], 0
0x18009563b  mov     word ptr [rbp+57h+var_70], ax
0x18009563f  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180095643  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x180095646  mov     edx, ecx; dwIndex
0x180095648  mov     rcx, [rbp+57h+hKey]; hKey
0x18009564c  mov     r8, r15; lpValueName
0x18009564f  mov     [rbp+57h+cchValueName], eax
0x180095652  mov     eax, [rbp+57h+cbMaxValueLen]
0x180095655  mov     [rbp+57h+cbData], eax
0x180095658  lea     rax, [rbp+57h+cbData]
0x18009565c  mov     [rsp+0F0h+lpcValues], rax; lpcbData
0x180095661  lea     rax, [rbp+57h+Type]
0x180095665  mov     [rsp+0F0h+lpcbMaxClassLen], r13; lpData
0x18009566a  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax; lpType
0x18009566f  mov     [rsp+0F0h+lpcSubKeys], 0; lpReserved
0x180095678  call    cs:__imp_RegEnumValueW
0x18009567e  mov     ebx, eax
0x180095680  test    eax, eax
0x180095682  jnz     loc_1800957EB
0x180095688  mov     ecx, [rbp+57h+cchValueName]
0x18009568b  mov     [r15+rcx*2], ax
0x180095690  mov     rcx, r15
0x180095693  call    cs:__imp__o__wtoi
0x180095699  mov     [rbp+57h+var_74], eax
0x18009569c  mov     ecx, eax
0x18009569e  test    eax, eax
0x1800956a0  jg      short loc_1800956DB
0x1800956a2  lea     rax, aInvalidPolicyI; "Invalid policy id"
0x1800956a9  mov     [rsp+0F0h+lpcbMaxClassLen], r15
0x1800956ae  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax
0x1800956b3  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x1800956ba  mov     r8d, 0C000000Dh
0x1800956c0  mov     dword ptr [rsp+0F0h+lpcSubKeys], 230h
0x1800956c8  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x1800956cf  mov     ecx, edi; unsigned int
0x1800956d1  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x1800956d6  jmp     loc_1800957AA
0x1800956db  cmp     [rbp+57h+cbData], 0
0x1800956df  jz      short loc_180095735
0x1800956e1  cmp     [rbp+57h+Type], 4
0x1800956e5  jz      short loc_180095725
0x1800956e7  mov     ecx, 80070057h
0x1800956ec  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x1800956f1  lea     rax, aInvalidType; "invalid type"
0x1800956f8  mov     r12d, ecx
0x1800956fb  mov     r8d, ecx
0x1800956fe  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax
0x180095703  mov     ecx, edi; unsigned int
0x180095705  mov     dword ptr [rsp+0F0h+lpcSubKeys], 1B1h
0x18009570d  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x180095714  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18009571b  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180095720  mov     ecx, [rbp+57h+var_74]
0x180095723  jmp     short loc_180095738
0x180095725  mov     eax, 13h
0x18009572a  mov     word ptr [rbp+57h+var_70], ax
0x18009572e  mov     eax, [r13+0]
0x180095732  mov     dword ptr [rbp+57h+var_70+8], eax
0x180095735  xor     r12d, r12d
0x180095738  xor     ebx, ebx
0x18009573a  mov     eax, r12d
0x18009573d  bts     eax, 1Eh
0x180095741  test    r12d, r12d
0x180095744  cmovnz  ebx, eax
0x180095747  cmp     ebx, 0C0070057h
0x18009574d  jz      short loc_1800957A6
0x18009574f  test    ebx, ebx
0x180095751  jnz     short loc_1800957B4
0x180095753  cmp     ecx, 5
0x180095756  jz      short loc_18009575D
0x180095758  cmp     ecx, 8
0x18009575b  jnz     short loc_180095777
0x18009575d  cmp     dword ptr [rbp+57h+var_70+8], 0
0x180095761  mov     eax, 0Bh
0x180095766  mov     word ptr [rbp+57h+var_70], ax
0x18009576a  jz      short loc_180095771
0x18009576c  or      eax, 0FFFFFFFFh
0x18009576f  jmp     short loc_180095773
0x180095771  xor     eax, eax
0x180095773  mov     word ptr [rbp+57h+var_70+8], ax
0x180095777  mov     r12d, [rbp+57h+var_90]
0x18009577b  movups  xmm0, [rbp+57h+var_70]
0x18009577f  mov     eax, r12d
0x180095782  shl     rax, 5
0x180095786  movups  xmmword ptr [rax+r14+8], xmm0
0x18009578c  mov     [rax+r14], ecx
0x180095790  movsd   qword ptr [rax+r14+18h], xmm6
0x180095797  xor     eax, eax
0x180095799  add     r12d, edi
0x18009579c  mov     word ptr [rbp+57h+var_70], ax
0x1800957a0  mov     [rbp+57h+var_90], r12d
0x1800957a4  jmp     short loc_1800957AA
0x1800957a6  mov     r12d, [rbp+57h+var_90]
0x1800957aa  mov     ecx, [rbp+57h+var_78]
0x1800957ad  add     ecx, edi
0x1800957af  jmp     loc_180095626
0x1800957b4  lea     rax, aRegvaluetovari; "_RegValueToVariant"
0x1800957bb  mov     [rsp+0F0h+lpcbMaxClassLen], r15
0x1800957c0  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax
0x1800957c5  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x1800957cc  mov     r8d, ebx
0x1800957cf  mov     dword ptr [rsp+0F0h+lpcSubKeys], 23Eh
0x1800957d7  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x1800957de  mov     ecx, edi; unsigned int
0x1800957e0  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x1800957e5  mov     r12d, [rbp+57h+var_90]
0x1800957e9  jmp     short loc_18009582A
0x1800957eb  jle     short loc_1800957F6
0x1800957ed  movzx   ebx, ax
0x1800957f0  or      ebx, 0C0070000h
0x1800957f6  mov     [rsp+0F0h+lpcbMaxClassLen], rsi
0x1800957fb  lea     rax, aRegenumvalue; "RegEnumValue"
0x180095802  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax
0x180095807  mov     r8d, ebx
0x18009580a  mov     dword ptr [rsp+0F0h+lpcSubKeys], 228h
0x180095812  jmp     loc_1800955FE
0x180095817  mov     rax, [rbp+57h+arg_8]
0x18009581b  mov     [rax], r12d
0x18009581e  mov     rax, [rbp+57h+arg_10]
0x180095822  mov     [rax], r14
0x180095825  xor     r14d, r14d
0x180095828  xor     ebx, ebx
0x18009582a  mov     rcx, r15; hMem
0x18009582d  call    cs:__imp_LocalFree
0x180095833  test    r13, r13
0x180095836  jz      short loc_180095841
0x180095838  mov     rcx, r13; hMem
0x18009583b  call    cs:__imp_LocalFree
0x180095841  mov     rdx, r14; struct _tagEASPolicy *
0x180095844  mov     ecx, r12d; unsigned int
0x180095847  call    ?_FreePolicies@@YAXKPEAU_tagEASPolicy@@@Z; _FreePolicies(ulong,_tagEASPolicy *)
0x18009584c  movaps  xmm6, [rsp+0F0h+var_58+8]
0x180095854  mov     eax, ebx
0x180095856  add     rsp, 0B8h
0x18009585d  pop     r15
0x18009585f  pop     r14
0x180095861  pop     r13
0x180095863  pop     r12
0x180095865  pop     rdi
0x180095866  pop     rsi
0x180095867  pop     rbx
0x180095868  pop     rbp
0x180095869  retn
```
