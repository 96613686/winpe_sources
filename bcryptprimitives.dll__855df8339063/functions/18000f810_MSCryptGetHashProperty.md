# MSCryptGetHashProperty

- ea: `0x18000f810`
- end: `0x18000fdee`
- name: `MSCryptGetHashProperty`
- size: `1502`
- prototype: ``
- caller_count: `8`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000f450`
- `0x1800117d0`
- `0x180012ff4`
- `0x180053de4`
- `0x180058a04`
- `0x18006c5c4`
- `0x18007dd2c`
- `0x18007ebb4`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18000f810`
- `0x180014240`
- `0x1800185c0`
- `0x180063170`
- `0x18007f765`

## string_xrefs

- `0x18000f9ba`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000fa07`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000fb4b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000fba2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000fc2a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x1800805a1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x180080601`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptGetHashProperty(
        __int64 a1,
        const wchar_t *a2,
        _QWORD *a3,
        unsigned int a4,
        unsigned int *a5,
        int a6)
{
  int v10; // ebp
  int v11; // edx
  int v12; // r8d
  unsigned int v13; // ebx
  int v15; // edx
  int v16; // r8d
  _QWORD *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 *v20; // rbp
  __int64 v21; // rdi
  unsigned int v22; // edx
  unsigned int v23; // ecx
  __int64 v24; // rax
  _QWORD *v25; // rdx
  unsigned int v26; // r15d
  char *v27; // rsi
  __int64 v28; // r12
  __int64 v29; // rbx
  char *v30; // rcx
  const void *v31; // rdx
  __int64 v32; // rax
  int v33; // edx
  int v34; // r8d
  __int64 v35; // rax
  __int64 *v36; // rdx
  __int64 v37; // rax
  unsigned int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // r8
  int v42; // eax
  BOOL v43; // eax
  __int64 v44; // r9
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // r8
  char v48; // [rsp+30h] [rbp-38h]

  if ( a6 )
  {
    v13 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        184);
    return v13;
  }
  if ( !a1 || (v10 = *(_DWORD *)(a1 + 4), v10 != 1297303617) && v10 != 1297303624 )
  {
    v13 = -1073741816;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v48 = -63;
LABEL_28:
      WPP_SF_sDsd(
        v17[2],
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        v48);
      return v13;
    }
    return v13;
  }
  if ( !a5 )
  {
    v44 = 3528;
LABEL_89:
    v13 = -1073741811;
    v45 = 3221225485LL;
    goto LABEL_90;
  }
  if ( !wcscmp_0(a2, L"AlgorithmName") )
  {
    v35 = (unsigned int)*(unsigned __int16 *)(a1 + 8) - 1;
    if ( (unsigned int)v35 < 0x1A )
    {
      v36 = &rgHashAlgorithmDefaults[12 * v35];
      v37 = -1;
      while ( *(_WORD *)(v36[7] + 2 * v37++ + 2) != 0 )
        ;
      v39 = 2 * v37 + 2;
      *a5 = v39;
      if ( !a3 )
        return 0;
      if ( a4 >= v39 )
      {
        memcpy_0(a3, (const void *)v36[7], v39);
        return 0;
      }
      return (unsigned int)-1073741789;
    }
    v13 = -1073741816;
    v44 = 3539;
    v45 = 3221225480LL;
LABEL_90:
    DebugTraceError(v45, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v44);
    return v13;
  }
  if ( !wcscmp_0(a2, L"HashDigestLength") )
  {
    *a5 = 4;
    if ( !a3 )
      return 0;
    if ( a4 >= 4 )
    {
      *(_DWORD *)a3 = *(_DWORD *)(a1 + 12);
      return 0;
    }
    return (unsigned int)-1073741789;
  }
  if ( !wcscmp_0(a2, L"ObjectLength") )
  {
    if ( v10 != 1297303617 )
    {
      v13 = -1073741637;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          v12,
          (unsigned int)"Status",
          187,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
          2);
      return v13;
    }
    *a5 = 4;
    if ( a3 )
    {
      if ( a4 >= 4 )
      {
        *(_DWORD *)a3 = *(_DWORD *)(a1 + 16);
        return 0;
      }
      return (unsigned int)-1073741789;
    }
    return 0;
  }
  if ( !wcscmp_0(a2, L"MultiObjectLength") )
  {
    v32 = validateMSCryptHashAlgorithm(a1);
    if ( !v32 )
    {
      v13 = -1073741637;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v33,
          v34,
          (unsigned int)"Status",
          187,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
          32);
      return v13;
    }
    *a5 = 8;
    if ( a3 )
    {
      if ( a4 >= 8 )
      {
        *a3 = __PAIR64__(*(_DWORD *)(v32 + 24), *(_DWORD *)(v32 + 20) - *(_DWORD *)(v32 + 24));
        return 0;
      }
      return (unsigned int)-1073741789;
    }
    return 0;
  }
  if ( wcscmp_0(a2, L"HashOIDList") )
  {
    if ( !wcscmp_0(a2, L"HashBlockLength") )
    {
      if ( v10 != 1297303617 )
      {
        v13 = -1073741637;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v15,
            v16,
            (unsigned int)"Status",
            187,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            120);
        return v13;
      }
      *a5 = 4;
      if ( a3 )
      {
        if ( a4 >= 4 )
        {
          *(_DWORD *)a3 = *(_DWORD *)(a1 + 28);
          return 0;
        }
        return (unsigned int)-1073741789;
      }
      return 0;
    }
    if ( !wcscmp_0(a2, L"IsKeyedHash") )
    {
      v41 = validateMSCryptHash(a1, 0);
      if ( v41 || (v40 = validateMSCryptHashAlgorithm(a1)) != 0 )
      {
        v42 = *(_DWORD *)(a1 + 8);
        *a5 = 4;
        if ( !a3 )
          return 0;
        if ( a4 >= 4 )
        {
          v43 = LODWORD(rgHashAlgorithmDefaults[12 * (unsigned int)(unsigned __int16)v42 - 8])
             || v41 && *(_DWORD *)(v41 + 28) == 1
             || v40 && *(_DWORD *)(v40 + 52) == 1;
          *(_DWORD *)a3 = v43;
          return 0;
        }
        return (unsigned int)-1073741789;
      }
      v44 = 3737;
    }
    else
    {
      if ( wcscmp_0(a2, L"IsReusableHash") )
      {
        v13 = -1073741637;
        DebugTraceError(3221225659LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", 3812);
        return v13;
      }
      v47 = validateMSCryptHash(a1, 0);
      if ( v47 || (v46 = validateMSCryptHashAlgorithm(a1)) != 0 )
      {
        *a5 = 4;
        if ( !a3 )
          return 0;
        if ( a4 >= 4 )
        {
          *(_DWORD *)a3 = v47 && *(_DWORD *)(v47 + 24) == 1 || v46 && *(_DWORD *)(v46 + 40) == 1;
          return 0;
        }
        return (unsigned int)-1073741789;
      }
      v44 = 3780;
    }
    goto LABEL_89;
  }
  v18 = (unsigned int)*(unsigned __int16 *)(a1 + 8) - 1;
  if ( (unsigned int)v18 < 0x1A )
  {
    _mm_lfence();
    v19 = rgHashAlgorithmDefaults[12 * v18 + 10];
    v20 = &rgHashAlgorithmDefaults[12 * v18];
    v21 = *((unsigned int *)v20 + 18);
    v22 = 16 * (v21 + 1);
    *a5 = v22;
    if ( (_DWORD)v21 )
    {
      v23 = 0;
      do
      {
        v24 = v23++;
        v22 += *(_DWORD *)(16 * v24 + v19);
        *a5 = v22;
      }
      while ( v23 < (unsigned int)v21 );
    }
    if ( !a3 )
      return 0;
    if ( a4 >= v22 )
    {
      *(_DWORD *)a3 = v21;
      v25 = a3 + 2;
      a3[1] = a3 + 2;
      if ( (_DWORD)v21 )
      {
        v26 = 0;
        v27 = (char *)&a3[2 * v21 + 2];
        v28 = 0;
        do
        {
          v29 = 2 * v28;
          LODWORD(v25[2 * v28]) = *(_DWORD *)(v20[10] + 16 * v28);
          v30 = v27;
          v31 = *(const void **)(v20[10] + 16 * v28 + 8);
          if ( !v31 )
            v30 = 0;
          *(_QWORD *)(a3[1] + 16 * v28 + 8) = v30;
          memcpy_0(v27, v31, *(unsigned int *)(a3[1] + 16 * v28));
          v25 = (_QWORD *)a3[1];
          ++v26;
          ++v28;
          v27 += LODWORD(v25[v29]);
        }
        while ( v26 < (unsigned int)v21 );
      }
      return 0;
    }
    return (unsigned int)-1073741789;
  }
  v13 = -1073741816;
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v48 = 66;
    goto LABEL_28;
  }
  return v13;
}

```

## disassembly

```asm
0x18000f810  mov     [rsp+arg_10], rbx
0x18000f815  mov     [rsp+arg_18], rsi
0x18000f81a  push    rdi
0x18000f81b  push    r14
0x18000f81d  push    r15
0x18000f81f  sub     rsp, 50h
0x18000f823  cmp     [rsp+68h+arg_28], 0
0x18000f82b  mov     r15d, r9d
0x18000f82e  mov     r14, r8
0x18000f831  mov     rdi, rdx
0x18000f834  mov     rbx, rcx
0x18000f837  jnz     loc_18000F9DD
0x18000f83d  mov     [rsp+68h+arg_0], rbp
0x18000f842  test    rcx, rcx
0x18000f845  jz      loc_18000F98C
0x18000f84b  mov     ebp, [rcx+4]
0x18000f84e  cmp     ebp, 4D534841h
0x18000f854  jnz     loc_18000F980
0x18000f85a  mov     rsi, [rsp+68h+arg_20]
0x18000f862  test    rsi, rsi
0x18000f865  jz      loc_18000FD2C
0x18000f86b  lea     rdx, aAlgorithmname; "AlgorithmName"
0x18000f872  mov     rcx, rdi; String1
0x18000f875  call    wcscmp_0
0x18000f87a  test    eax, eax
0x18000f87c  jz      loc_18000FC43
0x18000f882  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18000f889  mov     rcx, rdi; String1
0x18000f88c  call    wcscmp_0
0x18000f891  test    eax, eax
0x18000f893  jz      loc_18000F960
0x18000f899  lea     rdx, aObjectlength; "ObjectLength"
0x18000f8a0  mov     rcx, rdi; String1
0x18000f8a3  call    wcscmp_0
0x18000f8a8  test    eax, eax
0x18000f8aa  jnz     short loc_18000F8F3
0x18000f8ac  cmp     ebp, 4D534841h
0x18000f8b2  jnz     loc_18000FB1D
0x18000f8b8  mov     dword ptr [rsi], 4
0x18000f8be  test    r14, r14
0x18000f8c1  jz      short loc_18000F8D3
0x18000f8c3  cmp     r15d, 4
0x18000f8c7  jb      loc_18000F9D3
0x18000f8cd  mov     eax, [rbx+10h]
0x18000f8d0  mov     [r14], eax
0x18000f8d3  xor     ebx, ebx
0x18000f8d5  mov     rbp, [rsp+68h+arg_0]
0x18000f8da  lea     r11, [rsp+68h+var_18]
0x18000f8df  mov     eax, ebx
0x18000f8e1  mov     rbx, [r11+30h]
0x18000f8e5  mov     rsi, [r11+38h]
0x18000f8e9  mov     rsp, r11
0x18000f8ec  pop     r15
0x18000f8ee  pop     r14
0x18000f8f0  pop     rdi
0x18000f8f1  retn
0x18000f8f3  lea     rdx, aMultiobjectlen; "MultiObjectLength"
0x18000f8fa  mov     rcx, rdi; String1
0x18000f8fd  call    wcscmp_0
0x18000f902  test    eax, eax
0x18000f904  jz      loc_18000FBEB
0x18000f90a  lea     rdx, aHashoidlist; "HashOIDList"
0x18000f911  mov     rcx, rdi; String1
0x18000f914  call    wcscmp_0
0x18000f919  test    eax, eax
0x18000f91b  jz      loc_18000FA34
0x18000f921  lea     rdx, aHashblocklengt; "HashBlockLength"
0x18000f928  mov     rcx, rdi; String1
0x18000f92b  call    wcscmp_0
0x18000f930  test    eax, eax
0x18000f932  jnz     loc_18000FCAB
0x18000f938  cmp     ebp, 4D534841h
0x18000f93e  jnz     loc_18000FB74
0x18000f944  mov     dword ptr [rsi], 4
0x18000f94a  test    r14, r14
0x18000f94d  jz      short loc_18000F8D3
0x18000f94f  cmp     r15d, 4
0x18000f953  jb      short loc_18000F9D3
0x18000f955  mov     eax, [rbx+1Ch]
0x18000f958  mov     [r14], eax
0x18000f95b  jmp     loc_18000F8D3
0x18000f960  mov     dword ptr [rsi], 4
0x18000f966  test    r14, r14
0x18000f969  jz      loc_18000F8D3
0x18000f96f  cmp     r15d, 4
0x18000f973  jb      short loc_18000F9D3
0x18000f975  mov     eax, [rbx+0Ch]
0x18000f978  mov     [r14], eax
0x18000f97b  jmp     loc_18000F8D3
0x18000f980  cmp     ebp, 4D534848h
0x18000f986  jz      loc_18000F85A
0x18000f98c  mov     ebx, 0C0000008h
0x18000f991  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f998  lea     rax, WPP_GLOBAL_Control
0x18000f99f  cmp     rcx, rax
0x18000f9a2  jz      loc_18000F8D5
0x18000f9a8  test    byte ptr [rcx+1Ch], 1
0x18000f9ac  jz      loc_18000F8D5
0x18000f9b2  mov     dword ptr [rsp+68h+var_38], 0DC1h
0x18000f9ba  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f9c1  mov     [rsp+68h+var_40], rax
0x18000f9c6  mov     [rsp+68h+var_48], 0C0000008h
0x18000f9ce  jmp     loc_18000FB5F
0x18000f9d3  mov     ebx, 0C0000023h
0x18000f9d8  jmp     loc_18000F8D5
0x18000f9dd  mov     ebx, 0C000000Dh
0x18000f9e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9e9  lea     rax, WPP_GLOBAL_Control
0x18000f9f0  cmp     rcx, rax
0x18000f9f3  jz      loc_18000F8DA
0x18000f9f9  test    byte ptr [rcx+1Ch], 1
0x18000f9fd  jz      loc_18000F8DA
0x18000fa03  mov     rcx, [rcx+10h]
0x18000fa07  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fa0e  mov     dword ptr [rsp+68h+var_38], 0DB8h
0x18000fa16  lea     r9, aStatus; "Status"
0x18000fa1d  mov     [rsp+68h+var_40], rax
0x18000fa22  mov     [rsp+68h+var_48], 0C000000Dh
0x18000fa2a  call    WPP_SF_sDsd
0x18000fa2f  jmp     loc_18000F8DA
0x18000fa34  movzx   eax, word ptr [rbx+8]
0x18000fa38  dec     eax
0x18000fa3a  cmp     eax, 1Ah
0x18000fa3d  jnb     loc_18000FBB8
0x18000fa43  lfence
0x18000fa46  lea     rcx, [rax+rax*2]
0x18000fa4a  shl     rcx, 5
0x18000fa4e  lea     rax, rgHashAlgorithmDefaults
0x18000fa55  mov     r8, [rcx+rax+50h]
0x18000fa5a  lea     rbp, [rcx+rax]
0x18000fa5e  mov     edi, [rcx+rax+48h]
0x18000fa62  lea     edx, [rdi+1]
0x18000fa65  shl     edx, 4
0x18000fa68  mov     [rsi], edx
0x18000fa6a  test    edi, edi
0x18000fa6c  jz      short loc_18000FA82
0x18000fa6e  xor     ecx, ecx
0x18000fa70  mov     eax, ecx
0x18000fa72  inc     ecx
0x18000fa74  shl     rax, 4
0x18000fa78  add     edx, [rax+r8]
0x18000fa7c  mov     [rsi], edx
0x18000fa7e  cmp     ecx, edi
0x18000fa80  jb      short loc_18000FA70
0x18000fa82  test    r14, r14
0x18000fa85  jz      loc_18000F8D3
0x18000fa8b  cmp     r15d, edx
0x18000fa8e  jb      loc_18000F9D3
0x18000fa94  mov     [r14], edi
0x18000fa97  lea     rdx, [r14+10h]
0x18000fa9b  mov     [r14+8], rdx
0x18000fa9f  test    edi, edi
0x18000faa1  jz      loc_18000F8D3
0x18000faa7  lea     rsi, [rdi+1]
0x18000faab  mov     [rsp+68h+arg_8], r12
0x18000fab0  shl     rsi, 4
0x18000fab4  xor     r15d, r15d
0x18000fab7  add     rsi, r14
0x18000faba  xor     r12d, r12d
0x18000fabd  nop     dword ptr [rax]
0x18000fac0  mov     rax, [rbp+50h]
0x18000fac4  mov     rbx, r12
0x18000fac7  add     rbx, rbx
0x18000faca  mov     ecx, [rax+rbx*8]
0x18000facd  mov     [rdx+rbx*8], ecx
0x18000fad0  mov     rcx, rsi
0x18000fad3  mov     rax, [rbp+50h]
0x18000fad7  mov     rdx, [rax+rbx*8+8]; Src
0x18000fadc  xor     eax, eax
0x18000fade  test    rdx, rdx
0x18000fae1  cmovz   rcx, rax
0x18000fae5  mov     rax, [r14+8]
0x18000fae9  mov     [rax+rbx*8+8], rcx
0x18000faee  mov     rcx, rsi; void *
0x18000faf1  mov     rax, [r14+8]
0x18000faf5  mov     r8d, [rax+rbx*8]; Size
0x18000faf9  call    memcpy_0
0x18000fafe  mov     rdx, [r14+8]
0x18000fb02  inc     r15d
0x18000fb05  inc     r12
0x18000fb08  mov     eax, [rdx+rbx*8]
0x18000fb0b  add     rsi, rax
0x18000fb0e  cmp     r15d, edi
0x18000fb11  jb      short loc_18000FAC0
0x18000fb13  mov     r12, [rsp+68h+arg_8]
0x18000fb18  jmp     loc_18000F8D3
0x18000fb1d  mov     ebx, 0C00000BBh
0x18000fb22  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb29  lea     rax, WPP_GLOBAL_Control
0x18000fb30  cmp     rcx, rax
0x18000fb33  jz      loc_18000F8D5
0x18000fb39  test    byte ptr [rcx+1Ch], 1
0x18000fb3d  jz      loc_18000F8D5
0x18000fb43  mov     dword ptr [rsp+68h+var_38], 0E02h
0x18000fb4b  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fb52  mov     [rsp+68h+var_40], rax
0x18000fb57  mov     [rsp+68h+var_48], 0C00000BBh
0x18000fb5f  mov     rcx, [rcx+10h]
0x18000fb63  lea     r9, aStatus; "Status"
0x18000fb6a  call    WPP_SF_sDsd
0x18000fb6f  jmp     loc_18000F8D5
0x18000fb74  mov     ebx, 0C00000BBh
0x18000fb79  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb80  lea     rax, WPP_GLOBAL_Control
0x18000fb87  cmp     rcx, rax
0x18000fb8a  jz      loc_18000F8D5
0x18000fb90  test    byte ptr [rcx+1Ch], 1
0x18000fb94  jz      loc_18000F8D5
0x18000fb9a  mov     dword ptr [rsp+68h+var_38], 0E78h
0x18000fba2  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fba9  mov     [rsp+68h+var_40], rax
0x18000fbae  mov     [rsp+68h+var_48], 0C00000BBh
0x18000fbb6  jmp     short loc_18000FB5F
0x18000fbb8  mov     ebx, 0C0000008h
0x18000fbbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbc4  lea     rax, WPP_GLOBAL_Control
0x18000fbcb  cmp     rcx, rax
0x18000fbce  jz      loc_18000F8D5
0x18000fbd4  test    byte ptr [rcx+1Ch], 1
0x18000fbd8  jz      loc_18000F8D5
0x18000fbde  mov     dword ptr [rsp+68h+var_38], 0E42h
0x18000fbe6  jmp     loc_18000F9BA
0x18000fbeb  mov     rcx, rbx
0x18000fbee  call    validateMSCryptHashAlgorithm
0x18000fbf3  test    rax, rax
0x18000fbf6  jnz     loc_18000FD4C
0x18000fbfc  mov     ebx, 0C00000BBh
0x18000fc01  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc08  lea     rax, WPP_GLOBAL_Control
0x18000fc0f  cmp     rcx, rax
0x18000fc12  jz      loc_18000F8D5
0x18000fc18  test    byte ptr [rcx+1Ch], 1
0x18000fc1c  jz      loc_18000F8D5
0x18000fc22  mov     dword ptr [rsp+68h+var_38], 0E20h
0x18000fc2a  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fc31  mov     [rsp+68h+var_40], rax
0x18000fc36  mov     [rsp+68h+var_48], 0C00000BBh
0x18000fc3e  jmp     loc_18000FB5F
0x18000fc43  movzx   eax, word ptr [rbx+8]
0x18000fc47  dec     eax
0x18000fc49  cmp     eax, 1Ah
0x18000fc4c  jnb     loc_18000FD37
0x18000fc52  lea     rdx, [rax+rax*2]
0x18000fc56  lea     rax, rgHashAlgorithmDefaults
0x18000fc5d  shl     rdx, 5
0x18000fc61  add     rdx, rax
0x18000fc64  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000fc6b  mov     rcx, [rdx+38h]
0x18000fc6f  nop
0x18000fc70  cmp     word ptr [rcx+rax*2+2], 0
0x18000fc76  lea     rax, [rax+1]
0x18000fc7a  jnz     short loc_18000FC70
0x18000fc7c  lea     eax, ds:2[rax*2]
0x18000fc83  mov     [rsi], eax
0x18000fc85  test    r14, r14
0x18000fc88  jz      loc_18000F8D3
0x18000fc8e  cmp     r15d, eax
0x18000fc91  jb      loc_18000F9D3
0x18000fc97  mov     rdx, [rdx+38h]; Src
0x18000fc9b  mov     rcx, r14; void *
0x18000fc9e  mov     r8d, eax; Size
0x18000fca1  call    memcpy_0
0x18000fca6  jmp     loc_18000F8D3
0x18000fcab  lea     rdx, aIskeyedhash; "IsKeyedHash"
0x18000fcb2  mov     rcx, rdi; String1
0x18000fcb5  call    wcscmp_0
0x18000fcba  test    eax, eax
0x18000fcbc  jnz     loc_18000FDA2
0x18000fcc2  mov     rcx, rbx
0x18000fcc5  xor     edx, edx
0x18000fcc7  call    validateMSCryptHash
0x18000fccc  mov     r8, rax
0x18000fccf  test    rax, rax
0x18000fcd2  jnz     short loc_18000FCE8
0x18000fcd4  mov     rcx, rbx
0x18000fcd7  call    validateMSCryptHashAlgorithm
0x18000fcdc  mov     rdx, rax
0x18000fcdf  test    rax, rax
0x18000fce2  jz      loc_18000FD82
0x18000fce8  mov     eax, [rbx+8]
0x18000fceb  mov     dword ptr [rsi], 4
0x18000fcf1  test    r14, r14
0x18000fcf4  jz      loc_18000F8D3
0x18000fcfa  cmp     r15d, 4
0x18000fcfe  jb      loc_18000F9D3
0x18000fd04  movzx   eax, ax
0x18000fd07  dec     eax
0x18000fd09  lea     rcx, [rax+rax*2]
0x18000fd0d  shl     rcx, 5
0x18000fd11  lea     rax, rgHashAlgorithmDefaults
0x18000fd18  cmp     dword ptr [rcx+rax+20h], 0
0x18000fd1d  jz      short loc_18000FD8D
0x18000fd1f  mov     eax, 1
0x18000fd24  mov     [r14], eax
0x18000fd27  jmp     loc_18000F8D3
0x18000fd2c  mov     r9d, 0DC8h
0x18000fd32  jmp     loc_180080590
0x18000fd37  mov     ebx, 0C0000008h
0x18000fd3c  mov     r9d, 0DD3h
0x18000fd42  mov     ecx, 0C0000008h
  ... truncated ...
```
