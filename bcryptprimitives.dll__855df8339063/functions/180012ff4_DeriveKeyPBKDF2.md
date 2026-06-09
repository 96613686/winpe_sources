# DeriveKeyPBKDF2

- ea: `0x180012ff4`
- end: `0x1800136b7`
- name: `DeriveKeyPBKDF2`
- size: `1731`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180012060`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18000ef70`
- `0x18000f810`
- `0x180010270`
- `0x1800102a0`
- `0x180012a80`
- `0x180012ff4`
- `0x1800139d4`
- `0x180013a50`
- `0x180016db0`
- `0x180063170`

## string_xrefs

- `0x1800134a0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x1800134f2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18001351b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180013576`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180013623`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180013675`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18001368a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180080909`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`

## pseudocode

```c
__int64 __fastcall DeriveKeyPBKDF2(__int64 a1, __int64 a2, void *a3, unsigned int a4, _DWORD *a5, int a6)
{
  void *v7; // rsi
  _WORD *v8; // r12
  int v9; // r15d
  int v10; // edx
  unsigned int KeyBitLength; // ebx
  int v12; // r8d
  __int64 v13; // rcx
  int ParameterList; // eax
  __int64 v15; // r11
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  int v19; // eax
  int v20; // edx
  int v21; // r8d
  __int64 *v22; // rbx
  int v23; // eax
  __int64 v24; // rdi
  __int64 v25; // rax
  __int64 v26; // rdi
  size_t v27; // r14
  _WORD *v28; // rdx
  int v29; // edx
  int v30; // r8d
  int HashProperty; // eax
  unsigned int v32; // r13d
  __int64 v33; // r15
  __int64 v34; // r14
  __int64 v35; // rax
  int v36; // edx
  int v37; // r8d
  char *v38; // rdi
  unsigned int i; // eax
  int v40; // edx
  int v41; // r8d
  _BYTE *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  _BYTE *v45; // rcx
  __int64 v46; // rax
  _BYTE *v47; // rcx
  __int64 v49; // r9
  __int64 v50; // rcx
  _QWORD *v51; // rcx
  int v52; // ebx
  _WORD *v53; // rax
  __int64 v54; // r9
  __int64 v55; // rcx
  char v56; // [rsp+38h] [rbp-49h]
  unsigned int v57; // [rsp+68h] [rbp-19h] BYREF
  unsigned int v58; // [rsp+6Ch] [rbp-15h] BYREF
  int v59; // [rsp+70h] [rbp-11h]
  int v60; // [rsp+74h] [rbp-Dh] BYREF
  size_t Size; // [rsp+78h] [rbp-9h] BYREF
  int v62; // [rsp+80h] [rbp-1h] BYREF
  __int64 v63; // [rsp+88h] [rbp+7h]
  __int64 v64; // [rsp+90h] [rbp+Fh]
  unsigned int v66; // [rsp+E0h] [rbp+5Fh] BYREF
  void *v67; // [rsp+E8h] [rbp+67h]

  v67 = a3;
  Size = 0;
  v62 = 0;
  v7 = 0;
  v58 = 0;
  v8 = 0;
  v66 = 0;
  v57 = 0;
  v60 = 0;
  if ( !a2 || a6 )
  {
    KeyBitLength = -1073741811;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return KeyBitLength;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
      113);
    goto LABEL_43;
  }
  *a5 = 0;
  v9 = *(_DWORD *)(a1 + 32);
  KeyBitLength = GetKeyBitLength(a2, a4, &v60);
  if ( (KeyBitLength & 0x80000000) == 0 )
  {
    QueryParameterList(a2, 17, 0);
    ParameterList = QueryParameterList(v13, 15, 0);
    if ( ParameterList >= 0 )
    {
      if ( (int)v15 >= 0 )
      {
        v49 = 938;
        goto LABEL_53;
      }
      v16 = ParameterList;
    }
    else
    {
      if ( (int)v15 < 0 )
      {
        v59 = 0;
        v63 = 0;
        goto LABEL_8;
      }
      v16 = v15;
    }
    v17 = *(_QWORD *)(a2 + 8);
    v18 = 2 * v16;
    v63 = *(_QWORD *)(v17 + 8 * v18 + 8);
    v59 = *(_DWORD *)(v17 + 8 * v18);
LABEL_8:
    v19 = QueryParameterList(a2, 16, 0);
    v22 = (__int64 *)(a2 + 8);
    if ( v19 < 0 )
    {
      v64 = 10000;
      goto LABEL_10;
    }
    if ( *(_DWORD *)(*v22 + 16LL * v19) != 8 )
    {
      KeyBitLength = -1073741811;
      v51 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return KeyBitLength;
      v56 = -56;
      goto LABEL_71;
    }
    _mm_lfence();
    v64 = **(_QWORD **)(*v22 + 16LL * v19 + 8);
    if ( v64 )
    {
LABEL_10:
      v23 = QueryParameterList(a2, 0, 0);
      if ( v23 < 0 )
      {
        KeyBitLength = -1073741811;
        v51 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return KeyBitLength;
        v56 = -20;
      }
      else
      {
        _mm_lfence();
        v24 = v23;
        v25 = *v22;
        v26 = 2 * v24;
        if ( (*(_BYTE *)(*v22 + 8 * v26) & 1) == 0 && *(_DWORD *)(v25 + 8 * v26) >= 2u )
        {
          v27 = *(unsigned int *)(v25 + 8 * v26);
          v28 = *(_WORD **)(v25 + 8 * v26 + 8);
          if ( !v28[(v27 >> 1) - 1] )
            goto LABEL_14;
          v53 = (_WORD *)SafeAllocaAllocateFromHeap(v27 + 2);
          v8 = v53;
          if ( v53 )
          {
            memcpy_0(v53, *(const void **)(*v22 + 8 * v26 + 8), v27);
            v28 = v8;
            v8[v27 >> 1] = 0;
LABEL_14:
            KeyBitLength = MSCryptOpenHashProvider(&Size, v28, (unsigned int)(v9 != 0) + 40);
            if ( KeyBitLength )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v29,
                  v30,
                  (unsigned int)"Status",
                  KeyBitLength,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                  31);
              }
              v7 = (void *)Size;
              goto LABEL_43;
            }
            v7 = (void *)Size;
            if ( (unsigned int)MSCryptGetHashProperty(Size, L"IsKeyedHash", &v62, 4, &v57, 0) || !v62 )
            {
              KeyBitLength = -1073741816;
              v54 = 1071;
              v55 = 3221225480LL;
            }
            else
            {
              HashProperty = MSCryptGetHashProperty(v7, L"HashDigestLength", &v66, 4, &v57, 0);
              KeyBitLength = HashProperty;
              if ( HashProperty )
              {
                v54 = 1084;
              }
              else
              {
                LODWORD(Size) = (unsigned int)(v60 + 7) >> 3;
                v32 = (v66 + (_DWORD)Size - 1) / v66;
                HashProperty = MSCryptGetHashProperty(v7, L"ObjectLength", &v58, 4, &v57, 0);
                KeyBitLength = HashProperty;
                if ( HashProperty >= 0 )
                {
                  v33 = SafeAllocaAllocateFromHeap(v66);
                  v34 = SafeAllocaAllocateFromHeap(v58);
                  v35 = SafeAllocaAllocateFromHeap(v66 * v32);
                  v38 = (char *)v35;
                  if ( v33 && v34 && v35 )
                  {
                    for ( i = 0; ; i = v57 )
                    {
                      if ( i >= v32 )
                      {
                        v52 = Size;
                        memcpy_0(v67, v38, (unsigned int)Size);
                        *((_BYTE *)v67 + (unsigned int)(v52 - 1)) &= -1 << (8 * v52 - v60);
                        *a5 = v52;
                        KeyBitLength = 0;
                        goto LABEL_28;
                      }
                      v57 = i + 1;
                      KeyBitLength = PBKDF2(
                                       v7,
                                       *(_QWORD *)(a1 + 24),
                                       *(unsigned int *)(a1 + 16),
                                       v63,
                                       v59,
                                       v64,
                                       i + 1,
                                       v34,
                                       v58,
                                       v33,
                                       &v38[v66 * i],
                                       v66);
                      if ( KeyBitLength )
                        break;
                    }
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_sDsd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        v40,
                        v41,
                        (unsigned int)"Status",
                        KeyBitLength,
                        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                        113);
                    }
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_sDsd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        v36,
                        v37,
                        (unsigned int)"Status",
                        23,
                        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                        92);
                    }
                    KeyBitLength = -1073741801;
                    if ( !v38 )
                      goto LABEL_35;
                  }
LABEL_28:
                  v42 = v38;
                  v43 = v66 * v32;
                  if ( v66 * v32 )
                  {
                    do
                    {
                      *v42++ = 0;
                      --v43;
                    }
                    while ( v43 );
                  }
                  MSCryptFree(v38);
LABEL_35:
                  if ( v34 )
                  {
                    v44 = v58;
                    v45 = (_BYTE *)v34;
                    if ( v58 )
                    {
                      do
                      {
                        *v45++ = 0;
                        --v44;
                      }
                      while ( v44 );
                    }
                    MSCryptFree(v34);
                  }
                  if ( v33 )
                  {
                    v46 = v66;
                    v47 = (_BYTE *)v33;
                    if ( v66 )
                    {
                      do
                      {
                        *v47++ = 0;
                        --v46;
                      }
                      while ( v46 );
                    }
                    MSCryptFree(v33);
                  }
                  goto LABEL_43;
                }
                v54 = 1103;
              }
              v55 = (unsigned int)HashProperty;
            }
            DebugTraceError(
              v55,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
              v54);
LABEL_43:
            if ( v7 )
              MSCryptCloseHashProvider(v7);
            if ( v8 )
              MSCryptFree(v8);
            return KeyBitLength;
          }
          KeyBitLength = -1073741801;
          v49 = 1030;
          v50 = 3221225495LL;
LABEL_85:
          DebugTraceError(v50, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", v49);
          return KeyBitLength;
        }
        KeyBitLength = -1073741811;
        v51 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return KeyBitLength;
        v56 = -9;
      }
LABEL_71:
      WPP_SF_sDsd(
        v51[2],
        v20,
        v21,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
        v56);
      return KeyBitLength;
    }
    v49 = 978;
LABEL_53:
    KeyBitLength = -1073741811;
    v50 = 3221225485LL;
    goto LABEL_85;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      v12,
      (unsigned int)"Status",
      KeyBitLength,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
      141);
  return KeyBitLength;
}

```

## disassembly

```asm
0x180012ff4  mov     rax, rsp
0x180012ff7  mov     [rax+20h], rbx
0x180012ffb  mov     [rax+18h], r8
0x180012fff  mov     [rax+8], rcx
0x180013003  push    rbp
0x180013004  push    rsi
0x180013005  push    rdi
0x180013006  push    r12
0x180013008  push    r13
0x18001300a  push    r14
0x18001300c  push    r15
0x18001300e  lea     rbp, [rax-4Fh]
0x180013012  sub     rsp, 90h
0x180013019  xor     r13d, r13d
0x18001301c  mov     rdi, rdx
0x18001301f  mov     [rbp+47h+Size], r13
0x180013023  mov     rax, rcx
0x180013026  mov     [rbp+47h+var_48], r13d
0x18001302a  mov     esi, r13d
0x18001302d  mov     [rbp+47h+var_5C], r13d
0x180013031  mov     r12d, r13d
0x180013034  mov     [rbp+47h+arg_8], r13d
0x180013038  mov     [rbp+47h+var_60], r13d
0x18001303c  mov     [rbp+47h+var_54], r13d
0x180013040  test    rdx, rdx
0x180013043  jz      loc_180013385
0x180013049  cmp     [rbp+47h+arg_28], r13d
0x18001304d  jnz     loc_180013385
0x180013053  mov     rcx, [rbp+47h+arg_20]
0x180013057  lea     r8, [rbp+47h+var_54]
0x18001305b  mov     edx, r9d
0x18001305e  mov     [rcx], r13d
0x180013061  mov     rcx, rdi
0x180013064  mov     r15d, [rax+20h]
0x180013068  call    GetKeyBitLength
0x18001306d  mov     ebx, eax
0x18001306f  test    eax, eax
0x180013071  js      loc_1800134C9
0x180013077  xor     r8d, r8d
0x18001307a  lea     edx, [r13+11h]
0x18001307e  mov     rcx, rdi
0x180013081  call    QueryParameterList
0x180013086  xor     r8d, r8d
0x180013089  movsxd  r11, eax
0x18001308c  lea     edx, [r13+0Fh]
0x180013090  call    QueryParameterList
0x180013095  test    eax, eax
0x180013097  jns     loc_1800135C9
0x18001309d  test    r11d, r11d
0x1800130a0  js      loc_1800135DD
0x1800130a6  mov     rcx, r11
0x1800130a9  mov     rax, [rdi+8]
0x1800130ad  add     rcx, rcx
0x1800130b0  mov     r11, [rax+rcx*8+8]
0x1800130b5  mov     [rbp+47h+var_40], r11
0x1800130b9  mov     r11d, [rax+rcx*8]
0x1800130bd  mov     [rbp+47h+var_58], r11d
0x1800130c1  xor     r8d, r8d
0x1800130c4  mov     rcx, rdi
0x1800130c7  lea     edx, [r8+10h]
0x1800130cb  call    QueryParameterList
0x1800130d0  lea     rbx, [rdi+8]
0x1800130d4  test    eax, eax
0x1800130d6  jns     loc_1800133C5
0x1800130dc  mov     [rbp+47h+var_38], 2710h
0x1800130e4  xor     r8d, r8d
0x1800130e7  xor     edx, edx
0x1800130e9  mov     rcx, rdi
0x1800130ec  call    QueryParameterList
0x1800130f1  test    eax, eax
0x1800130f3  js      loc_180013469
0x1800130f9  lfence
0x1800130fc  movsxd  rdi, eax
0x1800130ff  mov     rax, [rbx]
0x180013102  add     rdi, rdi
0x180013105  test    byte ptr [rax+rdi*8], 1
0x180013109  jnz     loc_180013436
0x18001310f  cmp     dword ptr [rax+rdi*8], 2
0x180013113  jb      loc_180013436
0x180013119  mov     r14d, [rax+rdi*8]
0x18001311d  mov     rdx, [rax+rdi*8+8]
0x180013122  mov     esi, r14d
0x180013125  shr     rsi, 1
0x180013128  cmp     r13w, [rdx+rsi*2-2]
0x18001312e  jnz     loc_1800135EA
0x180013134  neg     r15d
0x180013137  lea     rcx, [rbp+47h+Size]
0x18001313b  sbb     r8d, r8d
0x18001313e  neg     r8d
0x180013141  add     r8d, 28h ; '('
0x180013145  call    MSCryptOpenHashProvider
0x18001314a  mov     ebx, eax
0x18001314c  test    eax, eax
0x18001314e  jnz     loc_180013408
0x180013154  mov     rsi, [rbp+47h+Size]
0x180013158  lea     rax, [rbp+47h+var_60]
0x18001315c  lea     edi, [rbx+4]
0x18001315f  mov     [rsp+0C0h+var_98], r13d
0x180013164  mov     r9d, edi
0x180013167  mov     [rsp+0C0h+var_A0], rax
0x18001316c  mov     rcx, rsi
0x18001316f  lea     r8, [rbp+47h+var_48]
0x180013173  lea     rdx, aIskeyedhash; "IsKeyedHash"
0x18001317a  call    MSCryptGetHashProperty
0x18001317f  test    eax, eax
0x180013181  jnz     loc_18001365E
0x180013187  cmp     [rbp+47h+var_48], r13d
0x18001318b  jz      loc_18001365E
0x180013191  lea     rax, [rbp+47h+var_60]
0x180013195  mov     [rsp+0C0h+var_98], r13d
0x18001319a  mov     r9d, edi
0x18001319d  mov     [rsp+0C0h+var_A0], rax
0x1800131a2  lea     r8, [rbp+47h+arg_8]
0x1800131a6  mov     rcx, rsi
0x1800131a9  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800131b0  call    MSCryptGetHashProperty
0x1800131b5  mov     ebx, eax
0x1800131b7  test    eax, eax
0x1800131b9  jnz     loc_18001364C
0x1800131bf  mov     eax, [rbp+47h+var_54]
0x1800131c2  lea     r8, [rbp+47h+var_5C]
0x1800131c6  add     eax, 7
0x1800131c9  mov     [rsp+0C0h+var_98], ebx
0x1800131cd  shr     eax, 3
0x1800131d0  xor     edx, edx
0x1800131d2  mov     dword ptr [rbp+47h+Size], eax
0x1800131d5  mov     r9d, edi
0x1800131d8  dec     eax
0x1800131da  mov     rcx, rsi
0x1800131dd  add     eax, [rbp+47h+arg_8]
0x1800131e0  div     [rbp+47h+arg_8]
0x1800131e3  lea     rdx, aObjectlength; "ObjectLength"
0x1800131ea  mov     r13d, eax
0x1800131ed  lea     rax, [rbp+47h+var_60]
0x1800131f1  mov     [rsp+0C0h+var_A0], rax
0x1800131f6  call    MSCryptGetHashProperty
0x1800131fb  mov     ebx, eax
0x1800131fd  test    eax, eax
0x1800131ff  js      loc_180013654
0x180013205  mov     ecx, [rbp+47h+arg_8]
0x180013208  call    SafeAllocaAllocateFromHeap
0x18001320d  mov     ecx, [rbp+47h+var_5C]
0x180013210  mov     r15, rax
0x180013213  call    SafeAllocaAllocateFromHeap
0x180013218  mov     ecx, r13d
0x18001321b  mov     r14, rax
0x18001321e  imul    ecx, [rbp+47h+arg_8]
0x180013222  call    SafeAllocaAllocateFromHeap
0x180013227  mov     rdi, rax
0x18001322a  test    r15, r15
0x18001322d  jz      loc_1800132F5
0x180013233  test    r14, r14
0x180013236  jz      loc_1800132F5
0x18001323c  test    rax, rax
0x18001323f  jz      loc_1800132F5
0x180013245  xor     eax, eax
0x180013247  cmp     eax, r13d
0x18001324a  jnb     loc_18001358F
0x180013250  mov     ecx, [rbp+47h+arg_8]
0x180013253  lea     edx, [rax+1]
0x180013256  mov     r9, [rbp+47h+var_40]
0x18001325a  mov     [rsp+58h], ecx
0x18001325e  imul    eax, ecx
0x180013261  mov     rcx, rsi
0x180013264  mov     [rbp+47h+var_60], edx
0x180013267  add     rax, rdi
0x18001326a  mov     qword ptr [rsp+0C0h+var_70], rax
0x18001326f  mov     eax, [rbp+47h+var_5C]
0x180013272  mov     [rsp+0C0h+var_78], r15
0x180013277  mov     dword ptr [rsp+0C0h+var_80], eax
0x18001327b  mov     rax, [rbp+47h+var_38]
0x18001327f  mov     qword ptr [rsp+0C0h+var_88], r14
0x180013284  mov     dword ptr [rsp+0C0h+var_90], edx
0x180013288  mov     qword ptr [rsp+0C0h+var_98], rax
0x18001328d  mov     eax, [rbp+47h+var_58]
0x180013290  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180013294  mov     rax, [rbp+47h+arg_0]
0x180013298  mov     r8d, [rax+10h]
0x18001329c  mov     rdx, [rax+18h]
0x1800132a0  call    _PBKDF2
0x1800132a5  mov     ebx, eax
0x1800132a7  test    eax, eax
0x1800132a9  jz      loc_18001342E
0x1800132af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132b6  lea     rax, WPP_GLOBAL_Control
0x1800132bd  cmp     rcx, rax
0x1800132c0  jz      short loc_1800132CC
0x1800132c2  test    byte ptr [rcx+1Ch], 1
0x1800132c6  jnz     loc_18001349C
0x1800132cc  imul    r13d, [rbp+47h+arg_8]
0x1800132d1  mov     rax, rdi
0x1800132d4  mov     ecx, r13d
0x1800132d7  xor     r13d, r13d
0x1800132da  test    rcx, rcx
0x1800132dd  jz      short loc_1800132EB
0x1800132df  mov     [rax], r13b
0x1800132e2  inc     rax
0x1800132e5  sub     rcx, 1
0x1800132e9  jnz     short loc_1800132DF
0x1800132eb  mov     rcx, rdi
0x1800132ee  call    MSCryptFree
0x1800132f3  jmp     short loc_18001331F
0x1800132f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132fc  lea     rax, WPP_GLOBAL_Control
0x180013303  cmp     rcx, rax
0x180013306  jz      short loc_180013312
0x180013308  test    byte ptr [rcx+1Ch], 1
0x18001330c  jnz     loc_180013517
0x180013312  mov     ebx, 0C0000017h
0x180013317  test    rdi, rdi
0x18001331a  jnz     short loc_1800132CC
0x18001331c  xor     r13d, r13d
0x18001331f  test    r14, r14
0x180013322  jz      short loc_180013343
0x180013324  mov     eax, [rbp+47h+var_5C]
0x180013327  mov     rcx, r14
0x18001332a  test    rax, rax
0x18001332d  jz      short loc_18001333B
0x18001332f  mov     [rcx], r13b
0x180013332  inc     rcx
0x180013335  sub     rax, 1
0x180013339  jnz     short loc_18001332F
0x18001333b  mov     rcx, r14
0x18001333e  call    MSCryptFree
0x180013343  test    r15, r15
0x180013346  jz      short loc_180013367
0x180013348  mov     eax, [rbp+47h+arg_8]
0x18001334b  mov     rcx, r15
0x18001334e  test    rax, rax
0x180013351  jz      short loc_18001335F
0x180013353  mov     [rcx], r13b
0x180013356  inc     rcx
0x180013359  sub     rax, 1
0x18001335d  jnz     short loc_180013353
0x18001335f  mov     rcx, r15
0x180013362  call    MSCryptFree
0x180013367  test    rsi, rsi
0x18001336a  jz      short loc_180013376
0x18001336c  xor     edx, edx
0x18001336e  mov     rcx, rsi; P
0x180013371  call    MSCryptCloseHashProvider
0x180013376  test    r12, r12
0x180013379  jz      short loc_1800133A7
0x18001337b  mov     rcx, r12
0x18001337e  call    MSCryptFree
0x180013383  jmp     short loc_1800133A7
0x180013385  mov     ebx, 0C000000Dh
0x18001338a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013391  lea     rax, WPP_GLOBAL_Control
0x180013398  cmp     rcx, rax
0x18001339b  jz      short loc_1800133A7
0x18001339d  test    byte ptr [rcx+1Ch], 1
0x1800133a1  jnz     loc_180013686
0x1800133a7  mov     eax, ebx
0x1800133a9  mov     rbx, [rsp+0C0h+arg_18]
0x1800133b1  add     rsp, 90h
0x1800133b8  pop     r15
0x1800133ba  pop     r14
0x1800133bc  pop     r13
0x1800133be  pop     r12
0x1800133c0  pop     rdi
0x1800133c1  pop     rsi
0x1800133c2  pop     rbp
0x1800133c3  retn
0x1800133c5  movsxd  rcx, eax
0x1800133c8  mov     rax, [rbx]
0x1800133cb  add     rcx, rcx
0x1800133ce  cmp     dword ptr [rax+rcx*8], 8
0x1800133d2  jnz     loc_180013548
0x1800133d8  lfence
0x1800133db  mov     rax, [rbx]
0x1800133de  mov     rcx, [rax+rcx*8+8]
0x1800133e3  mov     r11, [rcx]
0x1800133e6  mov     [rbp+47h+var_38], r11
0x1800133ea  test    r11, r11
0x1800133ed  jnz     loc_1800130E4
0x1800133f3  mov     r9d, 3D2h
0x1800133f9  mov     ebx, 0C000000Dh
0x1800133fe  mov     ecx, 0C000000Dh
0x180013403  jmp     loc_180080902
0x180013408  mov     rcx, cs:WPP_GLOBAL_Control
0x18001340f  lea     rax, WPP_GLOBAL_Control
0x180013416  cmp     rcx, rax
0x180013419  jz      short loc_180013425
0x18001341b  test    byte ptr [rcx+1Ch], 1
0x18001341f  jnz     loc_18001361F
0x180013425  mov     rsi, [rbp+47h+Size]
0x180013429  jmp     loc_180013367
0x18001342e  mov     eax, [rbp+47h+var_60]
0x180013431  jmp     loc_180013247
0x180013436  mov     ebx, 0C000000Dh
0x18001343b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013442  lea     rax, WPP_GLOBAL_Control
0x180013449  cmp     rcx, rax
0x18001344c  jz      loc_1800133A7
0x180013452  test    byte ptr [rcx+1Ch], 1
0x180013456  jz      loc_1800133A7
0x18001345c  mov     dword ptr [rsp+0C0h+var_90], 3F7h
0x180013464  jmp     loc_180013576
0x180013469  mov     ebx, 0C000000Dh
  ... truncated ...
```
