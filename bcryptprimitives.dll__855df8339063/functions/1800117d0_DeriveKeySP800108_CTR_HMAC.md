# DeriveKeySP800108_CTR_HMAC

- ea: `0x1800117d0`
- end: `0x180012054`
- name: `DeriveKeySP800108_CTR_HMAC`
- size: `2180`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180012060`

## callees

- `0x18000ecb0`
- `0x18000ed00`
- `0x18000ee60`
- `0x18000ef70`
- `0x18000f810`
- `0x180010270`
- `0x1800102a0`
- `0x1800117d0`
- `0x180012a80`
- `0x1800139d4`
- `0x180013a50`
- `0x180013b70`
- `0x180017240`
- `0x1800173f0`
- `0x180063170`
- `0x180063180`

## string_xrefs

- `0x180011cf0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180011d2f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180011e1c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180011e5b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180011eaf`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180011edc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180011f0d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180011f44`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180011fa4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180011fcc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180012009`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18001202d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`

## pseudocode

```c
__int64 __fastcall DeriveKeySP800108_CTR_HMAC(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int *a5,
        int a6)
{
  PVOID v7; // r15
  _BYTE *v8; // r13
  unsigned int v9; // esi
  int v10; // edx
  int KeyBitLength; // ebx
  int v12; // r8d
  void *v13; // r12
  int ParameterList; // eax
  __int64 v15; // r14
  int v16; // eax
  int v17; // edx
  int v18; // r8d
  int v19; // eax
  int v20; // eax
  const wchar_t *v21; // rdx
  bool v22; // cf
  int v23; // edx
  int v24; // r8d
  int v25; // edx
  int v26; // r8d
  unsigned int HashProperty; // eax
  int v28; // edx
  int v29; // r8d
  _BYTE *v30; // rdi
  unsigned int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rax
  void *v34; // rdx
  _BYTE *v35; // rax
  unsigned int v36; // r14d
  char *v37; // rdi
  void *v38; // rcx
  unsigned int v39; // ebx
  void *v40; // rdx
  __int64 v41; // rcx
  size_t v42; // rbx
  char *v43; // rcx
  char *v44; // r8
  _BYTE *v45; // r12
  unsigned int v46; // edi
  int v47; // edx
  int v48; // r8d
  unsigned int v49; // r12d
  unsigned int i; // r15d
  int *v51; // rdx
  _BYTE *j; // rcx
  unsigned int v53; // eax
  unsigned int v54; // eax
  unsigned int v55; // ebx
  unsigned int v56; // edi
  size_t v57; // r8
  __int64 v58; // rax
  _BYTE *v59; // rcx
  __int64 v60; // rax
  _BYTE *v61; // rcx
  __int64 v62; // rcx
  _BYTE *v63; // rax
  __int64 v65; // rbx
  __int64 v66; // rax
  __int64 v67; // rbx
  size_t v68; // r14
  unsigned int v69; // ecx
  __int64 v70; // r9
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rax
  void *v74; // rdx
  _QWORD *v75; // rcx
  __int64 v76; // r9
  __int64 v77; // rax
  wchar_t *v78; // rax
  size_t v79; // [rsp+38h] [rbp-59h]
  char v80; // [rsp+38h] [rbp-59h]
  int v81[2]; // [rsp+48h] [rbp-49h]
  _BYTE *v82; // [rsp+50h] [rbp-41h]
  size_t v83; // [rsp+58h] [rbp-39h] BYREF
  int v84; // [rsp+60h] [rbp-31h] BYREF
  unsigned int v85; // [rsp+64h] [rbp-2Dh] BYREF
  PVOID P; // [rsp+68h] [rbp-29h] BYREF
  unsigned int v87; // [rsp+70h] [rbp-21h]
  unsigned int Size; // [rsp+74h] [rbp-1Dh]
  unsigned int Size_4; // [rsp+78h] [rbp-19h]
  int v90; // [rsp+7Ch] [rbp-15h]
  int v91[2]; // [rsp+80h] [rbp-11h] BYREF
  const wchar_t *v92; // [rsp+88h] [rbp-9h]
  void *Src; // [rsp+90h] [rbp-1h]
  void *v94; // [rsp+98h] [rbp+7h]

  v7 = 0;
  v8 = 0;
  P = 0;
  v9 = 0;
  *(_QWORD *)v91 = 0;
  v84 = 0;
  v83 = 0;
  v85 = 0;
  v92 = 0;
  if ( a6 )
  {
    v76 = 153;
LABEL_104:
    KeyBitLength = -1073741811;
    DebugTraceError(
      3221225485LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
      v76);
    goto LABEL_83;
  }
  *a5 = 0;
  v90 = *(_DWORD *)(a1 + 32);
  KeyBitLength = GetKeyBitLength(a2, a4, (char *)&v83 + 4);
  if ( KeyBitLength < 0 )
  {
    v75 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_83;
    v80 = -80;
LABEL_98:
    WPP_SF_sDsd(
      v75[2],
      v10,
      v12,
      (unsigned int)"Status",
      KeyBitLength,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
      v80);
    goto LABEL_83;
  }
  Src = 0;
  Size = 0;
  v87 = 0;
  v13 = 0;
  ParameterList = QueryParameterList(a2, 17, 0);
  v15 = ParameterList;
  a6 = ParameterList;
  if ( ParameterList >= 0 )
  {
    v77 = *(_QWORD *)(a2 + 8);
    v13 = *(void **)(v77 + 16 * v15 + 8);
    v87 = *(_DWORD *)(v77 + 16 * v15);
  }
  v16 = QueryParameterList(a2, 13, 0);
  if ( v16 >= 0 )
  {
    if ( v13 )
    {
      KeyBitLength = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v17,
          v18,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
          212);
      goto LABEL_83;
    }
    v32 = v16;
    v33 = *(_QWORD *)(a2 + 8);
    v32 *= 2;
    v34 = *(void **)(v33 + 8 * v32 + 8);
    LODWORD(v33) = *(_DWORD *)(v33 + 8 * v32);
    Src = v34;
    Size = v33;
  }
  v94 = 0;
  Size_4 = 0;
  v19 = QueryParameterList(a2, 14, 0);
  if ( v19 >= 0 )
  {
    if ( v13 )
    {
      v76 = 236;
      goto LABEL_104;
    }
    v72 = v19;
    v73 = *(_QWORD *)(a2 + 8);
    v72 *= 2;
    v74 = *(void **)(v73 + 8 * v72 + 8);
    LODWORD(v73) = *(_DWORD *)(v73 + 8 * v72);
    v94 = v74;
    Size_4 = v73;
  }
  v20 = QueryParameterList(a2, 0, 0);
  if ( v20 < 0 )
  {
    v21 = L"SHA256";
    goto LABEL_9;
  }
  _mm_lfence();
  v65 = v20;
  v66 = *(_QWORD *)(a2 + 8);
  v67 = 2 * v65;
  if ( (*(_BYTE *)(v66 + 8 * v67) & 1) != 0 || *(_DWORD *)(v66 + 8 * v67) < 2u )
  {
    v76 = 268;
    goto LABEL_104;
  }
  v68 = *(unsigned int *)(v66 + 8 * v67);
  v21 = *(const wchar_t **)(v66 + 8 * v67 + 8);
  if ( v21[(v68 >> 1) - 1] )
  {
    v78 = (wchar_t *)SafeAllocaAllocateFromHeap(v68 + 2);
    v92 = v78;
    if ( !v78 )
    {
      KeyBitLength = -1073741801;
      DebugTraceError(
        3221225495LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
        283);
LABEL_82:
      v7 = P;
LABEL_83:
      v30 = 0;
      v45 = 0;
      goto LABEL_44;
    }
    memcpy_0(v78, *(const void **)(*(_QWORD *)(a2 + 8) + 8 * v67 + 8), v68);
    v21 = v92;
    v92[v68 >> 1] = 0;
  }
  LODWORD(v15) = a6;
LABEL_9:
  v22 = v90 != 0;
  v90 = -v90;
  KeyBitLength = MSCryptOpenHashProvider(&P, v21, (unsigned int)v22 + 40);
  if ( KeyBitLength )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v23,
        v24,
        (unsigned int)"Status",
        KeyBitLength,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
        51);
    goto LABEL_82;
  }
  v7 = P;
  KeyBitLength = MSCryptGetHashProperty(P, L"ObjectLength", &v84, 4, &v85, 0);
  if ( KeyBitLength )
  {
    v75 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_83;
    v80 = 68;
    goto LABEL_98;
  }
  *(_QWORD *)v81 = SafeAllocaAllocateFromHeap((unsigned int)v84);
  if ( !*(_QWORD *)v81 )
  {
    KeyBitLength = -1073741801;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v25,
        v26,
        (unsigned int)"Status",
        23,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
        79);
    goto LABEL_87;
  }
  HashProperty = MSCryptGetHashProperty(v7, L"HashDigestLength", &v83, 4, &v85, 0);
  KeyBitLength = HashProperty;
  if ( HashProperty )
  {
    DebugTraceError(
      HashProperty,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
      352);
LABEL_87:
    v30 = 0;
    goto LABEL_43;
  }
  v82 = (_BYTE *)SafeAllocaAllocateFromHeap((unsigned int)v83);
  v30 = v82;
  if ( !v82 )
  {
    v70 = 363;
LABEL_111:
    KeyBitLength = -1073741801;
    v71 = 3221225495LL;
    goto LABEL_74;
  }
  if ( (int)v15 >= 0 )
  {
    v9 = v87 + 8;
    if ( v87 < 0xFFFFFFF8 )
      goto LABEL_22;
    v70 = 381;
LABEL_73:
    KeyBitLength = -1073741811;
    v9 = -1;
    v71 = 3221225485LL;
LABEL_74:
    DebugTraceError(v71, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", v70);
LABEL_43:
    v45 = *(_BYTE **)v81;
    goto LABEL_44;
  }
  v31 = Size + 8;
  if ( Size >= 0xFFFFFFF8 )
  {
    v9 = -1;
    KeyBitLength = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v28,
        v29,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
        137);
    goto LABEL_43;
  }
  v69 = v31 + Size_4;
  if ( v31 + Size_4 < v31 )
  {
    v70 = 403;
    goto LABEL_73;
  }
  v9 = v69 + 1;
  if ( v69 + 1 < v69 )
  {
    v9 = -1;
    KeyBitLength = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v28,
        v29,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
        157);
    goto LABEL_43;
  }
LABEL_22:
  v35 = (_BYTE *)SafeAllocaAllocateFromHeap(v9);
  v8 = v35;
  if ( !v35 )
  {
    v70 = 426;
    goto LABEL_111;
  }
  v36 = (unsigned int)(HIDWORD(v83) + 7) >> 3;
  memset_0(v35, 0, v9);
  v37 = v8 + 4;
  v38 = v8 + 4;
  if ( a6 >= 0 )
  {
    v42 = v87;
    v40 = v13;
  }
  else
  {
    v39 = Size;
    memcpy_0(v38, Src, Size);
    v40 = v94;
    v41 = v39 + 1;
    v42 = Size_4;
    v37 += v41;
    v38 = v37;
  }
  memcpy_0(v38, v40, v42);
  v43 = &v37[v42 + 3];
  v44 = (char *)&v83 + 4;
  while ( v43 >= &v37[v42] )
    *v43-- = *v44++;
  v45 = *(_BYTE **)v81;
  v46 = (v36 + (_DWORD)v83 - 1) / (unsigned int)v83;
  v85 = v46;
  LODWORD(v79) = *(_DWORD *)(a1 + 16);
  KeyBitLength = MSCryptCreateMultiHash((int)v7, (int)v91, 0, v81[0], v84, *(void **)(a1 + 24), v79, 0);
  if ( !KeyBitLength )
  {
    v49 = 0;
    for ( i = 1; ; ++i )
    {
      a6 = i;
      if ( i > v46 )
      {
        *(_BYTE *)(v36 - 1 + a3) &= -1 << (8 * v36 - BYTE4(v83));
        KeyBitLength = 0;
        *a5 = v36;
LABEL_42:
        v7 = P;
        v30 = v82;
        goto LABEL_43;
      }
      v51 = &a6;
      for ( j = v8 + 3; j >= v8; --j )
      {
        *j = *(_BYTE *)v51;
        v51 = (int *)((char *)v51 + 1);
      }
      v53 = MSCryptHashData(*(_QWORD *)v91, v8, v9, 0);
      KeyBitLength = v53;
      if ( v53 )
      {
        DebugTraceError(v53, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", 517);
        goto LABEL_42;
      }
      v30 = v82;
      v54 = MSCryptFinishHash(*(_QWORD *)v91, v82, (unsigned int)v83, 0);
      KeyBitLength = v54;
      if ( v54 )
        break;
      v55 = v83;
      v56 = v36 - v49;
      v57 = v36 - v49;
      if ( (unsigned int)v83 < v36 - v49 )
        v57 = (unsigned int)v83;
      memcpy_0((void *)(a3 + v49), v82, v57);
      if ( v55 < v56 )
        v56 = v55;
      v49 += v56;
      v46 = v85;
    }
    DebugTraceError(v54, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", 529);
    v7 = P;
    goto LABEL_43;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v47,
      v48,
      (unsigned int)"Status",
      KeyBitLength,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
      237);
  v30 = v82;
LABEL_44:
  if ( *(_QWORD *)v91 )
    MSCryptDestroyHash();
  if ( v7 )
    MSCryptCloseHashProvider(v7);
  if ( v30 )
  {
    v58 = (unsigned int)v83;
    v59 = v30;
    if ( (_DWORD)v83 )
    {
      do
      {
        *v59++ = 0;
        --v58;
      }
      while ( v58 );
    }
    MSCryptFree(v30);
  }
  if ( v45 )
  {
    v60 = (unsigned int)v84;
    v61 = v45;
    if ( v84 )
    {
      do
      {
        *v61++ = 0;
        --v60;
      }
      while ( v60 );
    }
    MSCryptFree(v45);
  }
  if ( v8 )
  {
    v62 = v9;
    v63 = v8;
    if ( v9 )
    {
      do
      {
        *v63++ = 0;
        --v62;
      }
      while ( v62 );
    }
    MSCryptFree(v8);
  }
  if ( v92 )
    MSCryptFree(v92);
  return (unsigned int)KeyBitLength;
}

```

## disassembly

```asm
0x1800117d0  mov     rax, rsp
0x1800117d3  mov     [rax+10h], rbx
0x1800117d7  mov     [rax+18h], r8
0x1800117db  mov     [rax+8], rcx
0x1800117df  push    rbp
0x1800117e0  push    rsi
0x1800117e1  push    rdi
0x1800117e2  push    r12
0x1800117e4  push    r13
0x1800117e6  push    r14
0x1800117e8  push    r15
0x1800117ea  lea     rbp, [rax-4Fh]
0x1800117ee  sub     rsp, 0A0h
0x1800117f5  xor     r14d, r14d
0x1800117f8  mov     rdi, rdx
0x1800117fb  mov     rax, rcx
0x1800117fe  mov     r15d, r14d
0x180011801  mov     r13d, r14d
0x180011804  mov     [rbp+47h+P], r14
0x180011808  mov     esi, r14d
0x18001180b  mov     qword ptr [rbp+47h+var_58], r14
0x18001180f  mov     [rbp+47h+var_78], r14d
0x180011813  mov     dword ptr [rbp+47h+var_80], r14d
0x180011817  mov     [rbp+47h+var_74], r14d
0x18001181b  mov     [rbp+47h+var_50], r14
0x18001181f  mov     dword ptr [rbp+47h+var_80+4], r14d
0x180011823  cmp     [rbp+47h+arg_28], r14d
0x180011827  jnz     loc_180011F36
0x18001182d  mov     rcx, [rbp+47h+arg_20]
0x180011831  lea     r8, [rbp+47h+var_80+4]
0x180011835  mov     edx, r9d
0x180011838  mov     [rcx], r14d
0x18001183b  mov     rcx, rdi
0x18001183e  mov     eax, [rax+20h]
0x180011841  mov     [rbp+47h+var_5C], eax
0x180011844  call    GetKeyBitLength
0x180011849  mov     ebx, eax
0x18001184b  test    eax, eax
0x18001184d  js      loc_180011E32
0x180011853  xor     r8d, r8d
0x180011856  mov     [rbp+47h+Src], r14
0x18001185a  lea     edx, [r14+11h]
0x18001185e  mov     dword ptr [rbp+47h+Size], r14d
0x180011862  mov     rcx, rdi
0x180011865  mov     [rbp+47h+var_68], r14d
0x180011869  mov     r12d, r14d
0x18001186c  call    QueryParameterList
0x180011871  movsxd  r14, eax
0x180011874  mov     [rbp+47h+arg_28], r14d
0x180011878  test    eax, eax
0x18001187a  jns     loc_180011F66
0x180011880  xor     r8d, r8d
0x180011883  mov     rcx, rdi
0x180011886  lea     edx, [r8+0Dh]
0x18001188a  call    QueryParameterList
0x18001188f  test    eax, eax
0x180011891  jns     loc_1800119C9
0x180011897  xor     r8d, r8d
0x18001189a  mov     [rbp+47h+var_40], rsi
0x18001189e  mov     rcx, rdi
0x1800118a1  mov     dword ptr [rbp+47h+Size+4], esi
0x1800118a4  lea     edx, [r8+0Eh]
0x1800118a8  call    QueryParameterList
0x1800118ad  test    eax, eax
0x1800118af  jns     loc_180011D48
0x1800118b5  xor     r8d, r8d
0x1800118b8  xor     edx, edx
0x1800118ba  mov     rcx, rdi
0x1800118bd  call    QueryParameterList
0x1800118c2  test    eax, eax
0x1800118c4  jns     loc_180011C60
0x1800118ca  lea     rdx, aSha256; "SHA256"
0x1800118d1  neg     [rbp+47h+var_5C]
0x1800118d4  lea     rcx, [rbp+47h+P]
0x1800118d8  sbb     r8d, r8d
0x1800118db  neg     r8d
0x1800118de  add     r8d, 28h ; '('
0x1800118e2  call    MSCryptOpenHashProvider
0x1800118e7  mov     ebx, eax
0x1800118e9  test    eax, eax
0x1800118eb  jnz     loc_180011D7A
0x1800118f1  mov     r15, [rbp+47h+P]
0x1800118f5  lea     rax, [rbp+47h+var_74]
0x1800118f9  lea     edi, [rbx+4]
0x1800118fc  mov     dword ptr [rsp+0D0h+var_A8], esi
0x180011900  mov     r9d, edi
0x180011903  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180011908  mov     rcx, r15
0x18001190b  lea     r8, [rbp+47h+var_78]
0x18001190f  lea     rdx, aObjectlength; "ObjectLength"
0x180011916  call    MSCryptGetHashProperty
0x18001191b  mov     ebx, eax
0x18001191d  test    eax, eax
0x18001191f  jnz     loc_180011E80
0x180011925  mov     ecx, [rbp+47h+var_78]
0x180011928  call    SafeAllocaAllocateFromHeap
0x18001192d  mov     qword ptr [rbp+47h+var_90], rax
0x180011931  test    rax, rax
0x180011934  jz      loc_180011DA6
0x18001193a  lea     rax, [rbp+47h+var_74]
0x18001193e  mov     dword ptr [rsp+0D0h+var_A8], esi
0x180011942  mov     r9d, edi
0x180011945  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18001194a  lea     r8, [rbp+47h+var_80]
0x18001194e  mov     rcx, r15
0x180011951  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180011958  call    MSCryptGetHashProperty
0x18001195d  mov     ebx, eax
0x18001195f  test    eax, eax
0x180011961  jnz     loc_180011FC6
0x180011967  mov     ecx, dword ptr [rbp+47h+var_80]
0x18001196a  call    SafeAllocaAllocateFromHeap
0x18001196f  mov     [rbp+47h+var_88], rax
0x180011973  mov     rdi, rax
0x180011976  test    rax, rax
0x180011979  jz      loc_180011FE6
0x18001197f  test    r14d, r14d
0x180011982  jns     short loc_1800119F0
0x180011984  mov     eax, dword ptr [rbp+47h+Size]
0x180011987  add     eax, 8
0x18001198a  cmp     eax, 8
0x18001198d  jnb     loc_180011CA7
0x180011993  or      esi, 0FFFFFFFFh
0x180011996  mov     ebx, 0C000000Dh
0x18001199b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119a2  lea     rax, WPP_GLOBAL_Control
0x1800119a9  cmp     rcx, rax
0x1800119ac  jz      loc_180011BA7
0x1800119b2  test    byte ptr [rcx+1Ch], 1
0x1800119b6  jz      loc_180011BA7
0x1800119bc  mov     dword ptr [rsp+0D0h+var_A0], 189h
0x1800119c4  jmp     loc_180011CEC
0x1800119c9  test    r12, r12
0x1800119cc  jnz     loc_180011DF6
0x1800119d2  movsxd  rcx, eax
0x1800119d5  mov     rax, [rdi+8]
0x1800119d9  add     rcx, rcx
0x1800119dc  mov     rdx, [rax+rcx*8+8]
0x1800119e1  mov     eax, [rax+rcx*8]
0x1800119e4  mov     [rbp+47h+Src], rdx
0x1800119e8  mov     dword ptr [rbp+47h+Size], eax
0x1800119eb  jmp     loc_180011897
0x1800119f0  mov     esi, [rbp+47h+var_68]
0x1800119f3  add     esi, 8
0x1800119f6  cmp     esi, 8
0x1800119f9  jb      loc_180011D40
0x1800119ff  mov     ecx, esi
0x180011a01  mov     ebx, esi
0x180011a03  call    SafeAllocaAllocateFromHeap
0x180011a08  mov     r13, rax
0x180011a0b  test    rax, rax
0x180011a0e  jz      loc_180011FEE
0x180011a14  mov     r14d, dword ptr [rbp+47h+var_80+4]
0x180011a18  mov     r8d, ebx; Size
0x180011a1b  add     r14d, 7
0x180011a1f  xor     edx, edx; Val
0x180011a21  mov     rcx, rax; void *
0x180011a24  shr     r14d, 3
0x180011a28  call    memset_0
0x180011a2d  cmp     [rbp+47h+arg_28], 0
0x180011a31  lea     rdi, [r13+4]
0x180011a35  mov     rcx, rdi; void *
0x180011a38  jge     loc_180011D6F
0x180011a3e  mov     ebx, dword ptr [rbp+47h+Size]
0x180011a41  mov     rdx, [rbp+47h+Src]; Src
0x180011a45  mov     r8d, ebx; Size
0x180011a48  call    memcpy_0
0x180011a4d  mov     rdx, [rbp+47h+var_40]; Src
0x180011a51  lea     ecx, [rbx+1]
0x180011a54  mov     ebx, dword ptr [rbp+47h+Size+4]
0x180011a57  add     rdi, rcx
0x180011a5a  mov     rcx, rdi; void *
0x180011a5d  mov     r8, rbx; Size
0x180011a60  call    memcpy_0
0x180011a65  lea     rdx, [rbx+rdi]
0x180011a69  lea     rcx, [rdx+3]
0x180011a6d  lea     r8, [rbp+47h+var_80+4]
0x180011a71  jmp     short loc_180011A7E
0x180011a73  mov     al, [r8]
0x180011a76  mov     [rcx], al
0x180011a78  dec     rcx
0x180011a7b  inc     r8
0x180011a7e  cmp     rcx, rdx
0x180011a81  jnb     short loc_180011A73
0x180011a83  mov     ecx, dword ptr [rbp+47h+var_80]
0x180011a86  xor     edx, edx
0x180011a88  mov     r12, qword ptr [rbp+47h+var_90]
0x180011a8c  xor     r8d, r8d; int
0x180011a8f  mov     dword ptr [rsp+38h], 0; int
0x180011a97  mov     r9, r12; int
0x180011a9a  lea     eax, [rcx-1]
0x180011a9d  add     eax, r14d
0x180011aa0  div     ecx
0x180011aa2  mov     edx, [rbp+47h+var_78]
0x180011aa5  mov     edi, eax
0x180011aa7  mov     [rbp+47h+var_74], eax
0x180011aaa  mov     rax, [rbp+47h+arg_0]
0x180011aae  mov     ecx, [rax+10h]
0x180011ab1  mov     dword ptr [rsp+0D0h+var_A0], ecx; Size
0x180011ab5  mov     rcx, [rax+18h]
0x180011ab9  mov     [rsp+0D0h+var_A8], rcx; Src
0x180011abe  mov     rcx, r15; int
0x180011ac1  mov     [rsp+0D0h+var_B0], edx; int
0x180011ac5  lea     rdx, [rbp+47h+var_58]; int
0x180011ac9  call    MSCryptCreateMultiHash
0x180011ace  mov     ebx, eax
0x180011ad0  test    eax, eax
0x180011ad2  jnz     loc_180011DD0
0x180011ad8  xor     r12d, r12d
0x180011adb  lea     r15d, [rax+1]
0x180011adf  mov     eax, r15d
0x180011ae2  mov     [rbp+47h+arg_28], r15d
0x180011ae6  cmp     eax, edi
0x180011ae8  ja      loc_180011B79
0x180011aee  lea     rdx, [rbp+47h+arg_28]
0x180011af2  lea     rcx, [r13+3]
0x180011af6  jmp     short loc_180011B02
0x180011af8  mov     al, [rdx]
0x180011afa  mov     [rcx], al
0x180011afc  dec     rcx
0x180011aff  inc     rdx
0x180011b02  cmp     rcx, r13
0x180011b05  jnb     short loc_180011AF8
0x180011b07  mov     rcx, qword ptr [rbp+47h+var_58]
0x180011b0b  xor     r9d, r9d
0x180011b0e  mov     r8d, esi
0x180011b11  mov     rdx, r13
0x180011b14  call    MSCryptHashData
0x180011b19  mov     ebx, eax
0x180011b1b  test    eax, eax
0x180011b1d  jnz     loc_180012027
0x180011b23  mov     rdi, [rbp+47h+var_88]
0x180011b27  xor     r9d, r9d
0x180011b2a  mov     r8d, dword ptr [rbp+47h+var_80]
0x180011b2e  mov     rdx, rdi
0x180011b31  mov     rcx, qword ptr [rbp+47h+var_58]
0x180011b35  call    MSCryptFinishHash
0x180011b3a  mov     ebx, eax
0x180011b3c  test    eax, eax
0x180011b3e  jnz     loc_180012003
0x180011b44  mov     ebx, dword ptr [rbp+47h+var_80]
0x180011b47  mov     edi, r14d
0x180011b4a  mov     rdx, [rbp+47h+var_88]; Src
0x180011b4e  sub     edi, r12d
0x180011b51  mov     r8d, edi
0x180011b54  mov     ecx, r12d
0x180011b57  cmp     ebx, edi
0x180011b59  cmovb   r8d, ebx; Size
0x180011b5d  add     rcx, [rbp+47h+arg_10]; void *
0x180011b61  call    memcpy_0
0x180011b66  cmp     ebx, edi
0x180011b68  cmovb   edi, ebx
0x180011b6b  add     r12d, edi
0x180011b6e  mov     edi, [rbp+47h+var_74]
0x180011b71  inc     r15d
0x180011b74  jmp     loc_180011ADF
0x180011b79  lea     ecx, ds:0[r14*8]
0x180011b81  mov     eax, 0FFh
0x180011b86  sub     ecx, dword ptr [rbp+47h+var_80+4]
0x180011b89  lea     edx, [r14-1]
0x180011b8d  shl     al, cl
0x180011b8f  mov     rcx, [rbp+47h+arg_10]
0x180011b93  and     [rdx+rcx], al
0x180011b96  mov     rax, [rbp+47h+arg_20]
0x180011b9a  xor     ebx, ebx
0x180011b9c  mov     [rax], r14d
0x180011b9f  mov     r15, [rbp+47h+P]
0x180011ba3  mov     rdi, [rbp+47h+var_88]
0x180011ba7  mov     r12, qword ptr [rbp+47h+var_90]
0x180011bab  mov     rcx, qword ptr [rbp+47h+var_58]
0x180011baf  test    rcx, rcx
0x180011bb2  jz      short loc_180011BB9
0x180011bb4  call    MSCryptDestroyHash
0x180011bb9  test    r15, r15
0x180011bbc  jz      short loc_180011BC8
0x180011bbe  xor     edx, edx
0x180011bc0  mov     rcx, r15; P
0x180011bc3  call    MSCryptCloseHashProvider
0x180011bc8  xor     r15d, r15d
0x180011bcb  test    rdi, rdi
0x180011bce  jz      short loc_180011BEF
0x180011bd0  mov     eax, dword ptr [rbp+47h+var_80]
0x180011bd3  mov     rcx, rdi
0x180011bd6  test    rax, rax
0x180011bd9  jz      short loc_180011BE7
0x180011bdb  mov     [rcx], r15b
0x180011bde  inc     rcx
0x180011be1  sub     rax, 1
0x180011be5  jnz     short loc_180011BDB
0x180011be7  mov     rcx, rdi
0x180011bea  call    MSCryptFree
0x180011bef  test    r12, r12
0x180011bf2  jz      short loc_180011C13
0x180011bf4  mov     eax, [rbp+47h+var_78]
0x180011bf7  mov     rcx, r12
0x180011bfa  test    rax, rax
0x180011bfd  jz      short loc_180011C0B
0x180011bff  mov     [rcx], r15b
0x180011c02  inc     rcx
0x180011c05  sub     rax, 1
  ... truncated ...
```
