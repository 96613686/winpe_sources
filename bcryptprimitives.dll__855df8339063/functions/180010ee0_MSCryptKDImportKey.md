# MSCryptKDImportKey

- ea: `0x180010ee0`
- end: `0x18001162d`
- name: `MSCryptKDImportKey`
- size: `1869`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18006c410`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180010270`
- `0x1800102a0`
- `0x180010ee0`
- `0x180011640`
- `0x180011740`
- `0x1800469e0`
- `0x180063170`
- `0x18007f765`
- `0x180083010`

## string_xrefs

- `0x180011021`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18001128d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18001137b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800113c2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180080788`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDImportKey(
        __int64 a1,
        unsigned int a2,
        const wchar_t *a3,
        _QWORD *a4,
        __int64 a5,
        unsigned int a6,
        _DWORD *a7,
        unsigned int a8,
        int a9)
{
  unsigned int v9; // r12d
  const wchar_t *v11; // rdi
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rsi
  __int64 v16; // rdi
  char *v17; // r13
  char *v18; // rcx
  char v19; // al
  void *v20; // rbx
  int v21; // eax
  int v22; // ebp
  __int64 v23; // rcx
  void *v24; // rax
  _QWORD *v25; // rcx
  void *v26; // rax
  int v27; // edx
  int v28; // r8d
  wchar_t *v29; // rcx
  unsigned int (__fastcall **SymCryptMacAlgorithm)(__int64, __int64, __int64); // rax
  __int64 v31; // r8
  __int64 v32; // rdx
  int v33; // edx
  int v34; // r8d
  __int64 v36; // rcx
  _QWORD *v37; // rcx
  __int64 v38; // r9
  __int64 v39; // rcx
  char v40; // [rsp+30h] [rbp-78h]
  size_t Size; // [rsp+40h] [rbp-68h] BYREF
  __int64 v42; // [rsp+48h] [rbp-60h] BYREF
  void *Src; // [rsp+50h] [rbp-58h]

  v9 = 0;
  v42 = 0;
  v11 = a3;
  LODWORD(Size) = 0;
  if ( a9 )
  {
    v14 = -1073741811;
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v14;
    v40 = -58;
LABEL_64:
    WPP_SF_sDsd(
      v37[2],
      a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v40);
    return v14;
  }
  v13 = ValidateKeyDerivationAlgorithm(a1, &v42);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        v13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        208);
    return v14;
  }
  v15 = v42;
  if ( !v42 )
  {
    v14 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        215);
    return v14;
  }
  if ( !a5 || !a7 )
  {
    v14 = -1073741811;
    v38 = 2014;
    v39 = 3221225485LL;
    goto LABEL_97;
  }
  if ( !v11 )
  {
    v14 = -1073741811;
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v14;
    v40 = -27;
    goto LABEL_64;
  }
  if ( !a4 )
  {
    v14 = -1073741811;
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v14;
    v40 = -20;
    goto LABEL_64;
  }
  if ( wcscmp_0(v11, L"KeyDataBlob") )
  {
    v14 = -1073741637;
    v38 = 2137;
    v39 = 3221225659LL;
LABEL_97:
    DebugTraceError(
      v39,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v38);
    return v14;
  }
  if ( a8 < 0xC || (v16 = (unsigned int)a7[2], a8 < (unsigned __int64)(v16 + 12)) )
  {
    v14 = -1073741811;
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v14;
    v40 = -3;
    goto LABEL_64;
  }
  if ( *a7 != 1296188491 || a7[1] != 1 )
  {
    v14 = -1073741811;
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v14;
    v40 = 5;
    goto LABEL_64;
  }
  v17 = (char *)(a7 + 3);
  if ( *(_DWORD *)(v15 + 8) != 393223 )
  {
    v20 = 0;
    goto LABEL_18;
  }
  v18 = (char *)&Size + 3;
  do
  {
    v19 = *v17++;
    *v18-- = v19;
  }
  while ( v18 >= (char *)&Size );
  v9 = Size;
  if ( (unsigned int)Size > (unsigned __int64)(v16 - 4) )
  {
    v14 = -1073741811;
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v14;
    v40 = 26;
    goto LABEL_64;
  }
  v20 = a7 + 4;
  LODWORD(v16) = -4 - Size + v16;
  v17 = (char *)a7 + (unsigned int)Size + 16;
LABEL_18:
  Src = v20;
  v42 = 0;
  if ( !v17 )
  {
    v14 = -1073741811;
    LOBYTE(v22) = 13;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v14;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_31;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      98);
    goto LABEL_46;
  }
  v21 = ValidateKeyDerivationAlgorithm(a1, &v42);
  v22 = v21;
  if ( v21 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        v21,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        110);
      v25 = WPP_GLOBAL_Control;
    }
    v14 = v22;
    goto LABEL_31;
  }
  if ( a6 < 0x280 )
  {
    v14 = -1073741789;
    LOBYTE(v22) = 35;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v14;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_31;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      35,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      118);
    goto LABEL_46;
  }
  v23 = v42;
  a2 = 0;
  *(_DWORD *)a5 = *(_DWORD *)(v42 + 12);
  *(_DWORD *)(a5 + 4) = 1297304409;
  *(_DWORD *)(a5 + 8) = *(_DWORD *)(v23 + 8);
  *(_DWORD *)(a5 + 32) = *(_DWORD *)(v23 + 16);
  *(_QWORD *)(a5 + 40) = v23;
  *(_DWORD *)(a5 + 48) = 0;
  *(_QWORD *)(a5 + 72) = 0;
  *(_QWORD *)(a5 + 56) = 0;
  *(_DWORD *)(a5 + 64) = 0;
  *(_DWORD *)(a5 + 16) = v16;
  LODWORD(a3) = *(_DWORD *)(v23 + 8) - 393217;
  if ( *(_DWORD *)(v23 + 8) == 393217
    || (LODWORD(a3) = *(_DWORD *)(v23 + 8) - 393218, *(_DWORD *)(v23 + 8) == 393218)
    || (LODWORD(a3) = *(_DWORD *)(v23 + 8) - 393219, *(_DWORD *)(v23 + 8) == 393219)
    || (LODWORD(a3) = *(_DWORD *)(v23 + 8) - 393220, *(_DWORD *)(v23 + 8) == 393220)
    || (LODWORD(a3) = *(_DWORD *)(v23 + 8) - 393221, *(_DWORD *)(v23 + 8) == 393221)
    || (LODWORD(a3) = *(_DWORD *)(v23 + 8) - 393222, (unsigned int)a3 < 2) )
  {
    a2 = 2048;
  }
  if ( (unsigned int)v16 > a2 )
  {
    v14 = -1073741811;
    LOBYTE(v22) = 13;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v14;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_31;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      194);
    goto LABEL_46;
  }
  *(_DWORD *)(a5 + 12) = 8 * v16;
  v24 = (void *)SafeAllocaAllocateFromHeap((unsigned int)v16);
  *(_QWORD *)(a5 + 24) = v24;
  if ( !v24 )
  {
    v14 = -1073741801;
    LOBYTE(v22) = 23;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v14;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_31;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      23,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      213);
LABEL_46:
    v25 = WPP_GLOBAL_Control;
LABEL_31:
    if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        v25[2],
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        v22,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        41);
    return v14;
  }
  memcpy_0(v24, v17, *(unsigned int *)(a5 + 16));
  if ( !v20 || !v9 )
  {
LABEL_41:
    v14 = 0;
    *a4 = a5;
    return v14;
  }
  v26 = (void *)SafeAllocaAllocateFromHeap(v9);
  *(_QWORD *)(a5 + 56) = v26;
  if ( v26 )
  {
    memcpy_0(v26, Src, v9);
    v29 = *(wchar_t **)(a5 + 56);
    *(_DWORD *)(a5 + 64) = v9;
    SymCryptMacAlgorithm = (unsigned int (__fastcall **)(__int64, __int64, __int64))GetSymCryptMacAlgorithm(v29);
    *(_QWORD *)(a5 + 72) = SymCryptMacAlgorithm;
    if ( SymCryptMacAlgorithm )
    {
      v31 = *(unsigned int *)(a5 + 16);
      v32 = *(_QWORD *)(a5 + 24);
      *(_QWORD *)(a5 + 624) = SymCryptMacAlgorithm;
      if ( !(*SymCryptMacAlgorithm)(a5 + 80, v32, v31) )
      {
        *(_DWORD *)(a5 + 48) = 1;
        goto LABEL_41;
      }
      v14 = -1073741823;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v33,
          v34,
          (unsigned int)"Status",
          1,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
          79);
    }
    else
    {
      v14 = -1073741637;
      DebugTraceError(
        3221225659LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        2115);
    }
  }
  else
  {
    v14 = -1073741801;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v27,
        v28,
        (unsigned int)"Status",
        23,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        54);
  }
  v36 = *(_QWORD *)(a5 + 56);
  if ( v36 )
  {
    MSCryptFree(v36);
    *(_QWORD *)(a5 + 56) = 0;
  }
  MSCryptKDDestroyKey(a5);
  return v14;
}

```

## disassembly

```asm
0x180010ee0  mov     rax, rsp
0x180010ee3  mov     [rax+20h], r9
0x180010ee7  push    rbx
0x180010ee8  push    rbp
0x180010ee9  push    rsi
0x180010eea  push    rdi
0x180010eeb  push    r12
0x180010eed  push    r13
0x180010eef  push    r14
0x180010ef1  push    r15
0x180010ef3  sub     rsp, 68h
0x180010ef7  xor     r12d, r12d
0x180010efa  mov     qword ptr [rax-60h], 0
0x180010f02  mov     r15, r9
0x180010f05  mov     rdi, r8
0x180010f08  mov     rbp, rcx
0x180010f0b  mov     [rax-68h], r12d
0x180010f0f  cmp     [rsp+0A8h+arg_40], r12d
0x180010f17  jnz     loc_180011438
0x180010f1d  lea     rdx, [rax-60h]
0x180010f21  call    ValidateKeyDerivationAlgorithm
0x180010f26  mov     ebx, eax
0x180010f28  test    eax, eax
0x180010f2a  js      loc_180011264
0x180010f30  mov     rsi, [rsp+0A8h+var_60]
0x180010f35  test    rsi, rsi
0x180010f38  jz      loc_180011394
0x180010f3e  mov     r14, [rsp+0A8h+arg_20]
0x180010f46  test    r14, r14
0x180010f49  jz      loc_180011618
0x180010f4f  mov     rbx, [rsp+0A8h+arg_30]
0x180010f57  test    rbx, rbx
0x180010f5a  jz      loc_180011618
0x180010f60  test    rdi, rdi
0x180010f63  jz      loc_18001146B
0x180010f69  test    r15, r15
0x180010f6c  jz      loc_18001149E
0x180010f72  lea     rdx, aKeydatablob; "KeyDataBlob"
0x180010f79  mov     rcx, rdi; String1
0x180010f7c  call    wcscmp_0
0x180010f81  test    eax, eax
0x180010f83  jnz     loc_180011603
0x180010f89  cmp     [rsp+0A8h+arg_38], 0Ch
0x180010f91  jb      loc_18001134D
0x180010f97  mov     edi, [rbx+8]
0x180010f9a  mov     eax, [rsp+0A8h+arg_38]
0x180010fa1  lea     rcx, [rdi+0Ch]
0x180010fa5  cmp     rax, rcx
0x180010fa8  jb      loc_18001134D
0x180010fae  cmp     dword ptr [rbx], 4D42444Bh
0x180010fb4  jnz     loc_1800113DB
0x180010fba  cmp     dword ptr [rbx+4], 1
0x180010fbe  jnz     loc_1800113DB
0x180010fc4  cmp     dword ptr [rsi+8], 60007h
0x180010fcb  lea     r13, [rbx+0Ch]
0x180010fcf  jnz     loc_1800112B2
0x180010fd5  lea     rcx, [rsp+0A8h+Size+3]
0x180010fda  mov     al, [r13+0]
0x180010fde  inc     r13
0x180010fe1  mov     [rcx], al
0x180010fe3  dec     rcx
0x180010fe6  lea     rax, [rsp+0A8h+Size]
0x180010feb  cmp     rcx, rax
0x180010fee  jnb     short loc_180010FDA
0x180010ff0  mov     r12d, dword ptr [rsp+0A8h+Size]
0x180010ff5  lea     rax, [rdi-4]
0x180010ff9  cmp     r12, rax
0x180010ffc  ja      loc_1800114D1
0x180011002  add     rbx, 10h
0x180011006  mov     eax, 0FFFFFFFCh
0x18001100b  sub     eax, r12d
0x18001100e  add     edi, eax
0x180011010  lea     r13, [rbx+r12]
0x180011014  xor     r15d, r15d
0x180011017  mov     [rsp+0A8h+Src], rbx
0x18001101c  mov     [rsp+0A8h+var_60], r15
0x180011021  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011028  test    r13, r13
0x18001102b  jz      loc_1800111E7
0x180011031  lea     rdx, [rsp+0A8h+var_60]
0x180011036  mov     rcx, rbp
0x180011039  call    ValidateKeyDerivationAlgorithm
0x18001103e  mov     ebp, eax
0x180011040  test    eax, eax
0x180011042  js      loc_180011240
0x180011048  cmp     [rsp+0A8h+arg_28], 280h
0x180011053  jb      loc_180011579
0x180011059  mov     rcx, [rsp+0A8h+var_60]
0x18001105e  xor     ebp, ebp
0x180011060  mov     edx, ebp
0x180011062  mov     eax, [rcx+0Ch]
0x180011065  mov     [r14], eax
0x180011068  mov     dword ptr [r14+4], 4D534B59h
0x180011070  mov     eax, [rcx+8]
0x180011073  mov     [r14+8], eax
0x180011077  mov     eax, [rcx+10h]
0x18001107a  mov     [r14+20h], eax
0x18001107e  mov     [r14+28h], rcx
0x180011082  mov     [r14+30h], ebp
0x180011086  mov     [r14+48h], rbp
0x18001108a  mov     [r14+38h], rbp
0x18001108e  mov     [r14+40h], ebp
0x180011092  mov     [r14+10h], edi
0x180011096  mov     r8d, [rcx+8]
0x18001109a  sub     r8d, 60001h
0x1800110a1  jz      loc_1800115BB
0x1800110a7  sub     r8d, 1
0x1800110ab  jz      loc_1800115BB
0x1800110b1  sub     r8d, 1
0x1800110b5  jz      loc_1800115BB
0x1800110bb  sub     r8d, 1
0x1800110bf  jz      loc_1800115BB
0x1800110c5  sub     r8d, 1
0x1800110c9  jz      loc_1800115BB
0x1800110cf  sub     r8d, 1
0x1800110d3  jz      loc_1800115BB
0x1800110d9  cmp     r8d, 1
0x1800110dd  jz      loc_1800115BB
0x1800110e3  cmp     edi, edx
0x1800110e5  ja      loc_180011504
0x1800110eb  lea     eax, ds:0[rdi*8]
0x1800110f2  mov     ecx, edi
0x1800110f4  mov     [r14+0Ch], eax
0x1800110f8  call    SafeAllocaAllocateFromHeap
0x1800110fd  mov     [r14+18h], rax
0x180011101  test    rax, rax
0x180011104  jnz     short loc_180011140
0x180011106  mov     ebx, 0C0000017h
0x18001110b  mov     ebp, ebx
0x18001110d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011114  lea     rdi, WPP_GLOBAL_Control
0x18001111b  cmp     rcx, rdi
0x18001111e  jz      short loc_180011139
0x180011120  test    byte ptr [rcx+1Ch], 1
0x180011124  jnz     loc_1800115C5
0x18001112a  cmp     rcx, rdi
0x18001112d  jz      short loc_180011139
0x18001112f  test    byte ptr [rcx+1Ch], 1
0x180011133  jnz     loc_1800112FA
0x180011139  xor     ebp, ebp
0x18001113b  jmp     loc_1800111D3
0x180011140  mov     r8d, [r14+10h]; Size
0x180011144  mov     rdx, r13; Src
0x180011147  mov     rcx, rax; void *
0x18001114a  call    memcpy_0
0x18001114f  test    rbx, rbx
0x180011152  jz      short loc_1800111C6
0x180011154  test    r12d, r12d
0x180011157  jz      short loc_1800111C6
0x180011159  mov     ecx, r12d
0x18001115c  mov     ebx, r12d
0x18001115f  call    SafeAllocaAllocateFromHeap
0x180011164  mov     [r14+38h], rax
0x180011168  test    rax, rax
0x18001116b  jz      loc_180011539
0x180011171  mov     rdx, [rsp+0A8h+Src]; Src
0x180011176  mov     r8d, ebx; Size
0x180011179  mov     rcx, rax; void *
0x18001117c  call    memcpy_0
0x180011181  mov     rcx, [r14+38h]; String1
0x180011185  mov     [r14+40h], r12d
0x180011189  call    GetSymCryptMacAlgorithm
0x18001118e  mov     [r14+48h], rax
0x180011192  test    rax, rax
0x180011195  jz      loc_1800115DF
0x18001119b  mov     r8d, [r14+10h]
0x18001119f  lea     rcx, [r14+50h]
0x1800111a3  mov     rdx, [r14+18h]
0x1800111a7  mov     [rcx+220h], rax
0x1800111ae  mov     rax, [rax]
0x1800111b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111b6  test    eax, eax
0x1800111b8  jnz     loc_1800112B9
0x1800111be  mov     dword ptr [r14+30h], 1
0x1800111c6  mov     rax, [rsp+0A8h+arg_18]
0x1800111ce  mov     ebx, ebp
0x1800111d0  mov     [rax], r14
0x1800111d3  mov     eax, ebx
0x1800111d5  add     rsp, 68h
0x1800111d9  pop     r15
0x1800111db  pop     r14
0x1800111dd  pop     r13
0x1800111df  pop     r12
0x1800111e1  pop     rdi
0x1800111e2  pop     rsi
0x1800111e3  pop     rbp
0x1800111e4  pop     rbx
0x1800111e5  retn
0x1800111e7  mov     ebx, 0C000000Dh
0x1800111ec  mov     ebp, ebx
0x1800111ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111f5  lea     rdi, WPP_GLOBAL_Control
0x1800111fc  cmp     rcx, rdi
0x1800111ff  jz      loc_180011139
0x180011205  test    byte ptr [rcx+1Ch], 1
0x180011209  jz      loc_18001112A
0x18001120f  mov     dword ptr [rsp+0A8h+var_78], 562h
0x180011217  mov     [rsp+0A8h+var_80], rsi
0x18001121c  mov     [rsp+0A8h+var_88], 0C000000Dh
0x180011224  mov     rcx, [rcx+10h]
0x180011228  lea     r9, aStatus; "Status"
0x18001122f  call    WPP_SF_sDsd
0x180011234  mov     rcx, cs:WPP_GLOBAL_Control
0x18001123b  jmp     loc_18001112A
0x180011240  mov     rcx, cs:WPP_GLOBAL_Control
0x180011247  lea     rdi, WPP_GLOBAL_Control
0x18001124e  cmp     rcx, rdi
0x180011251  jz      short loc_18001125D
0x180011253  test    byte ptr [rcx+1Ch], 1
0x180011257  jnz     loc_180011320
0x18001125d  mov     ebx, ebp
0x18001125f  jmp     loc_18001112A
0x180011264  mov     rcx, cs:WPP_GLOBAL_Control
0x18001126b  lea     rdi, WPP_GLOBAL_Control
0x180011272  cmp     rcx, rdi
0x180011275  jz      loc_1800111D3
0x18001127b  test    byte ptr [rcx+1Ch], 1
0x18001127f  jz      loc_1800111D3
0x180011285  mov     dword ptr [rsp+0A8h+var_78], 7D0h
0x18001128d  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011294  mov     [rsp+0A8h+var_80], rsi
0x180011299  mov     [rsp+0A8h+var_88], eax
0x18001129d  mov     rcx, [rcx+10h]
0x1800112a1  lea     r9, aStatus; "Status"
0x1800112a8  call    WPP_SF_sDsd
0x1800112ad  jmp     loc_1800111D3
0x1800112b2  xor     ebx, ebx
0x1800112b4  jmp     loc_180011014
0x1800112b9  mov     ebx, 0C0000001h
0x1800112be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800112c5  lea     rdi, WPP_GLOBAL_Control
0x1800112cc  cmp     rcx, rdi
0x1800112cf  jz      short loc_1800112DB
0x1800112d1  test    byte ptr [rcx+1Ch], 1
0x1800112d5  jnz     loc_18001140E
0x1800112db  mov     rcx, [r14+38h]
0x1800112df  test    rcx, rcx
0x1800112e2  jz      short loc_1800112ED
0x1800112e4  call    MSCryptFree
0x1800112e9  mov     [r14+38h], rbp
0x1800112ed  mov     rcx, r14
0x1800112f0  call    MSCryptKDDestroyKey
0x1800112f5  jmp     loc_1800111D3
0x1800112fa  mov     rcx, [rcx+10h]
0x1800112fe  lea     r9, aStatus; "Status"
0x180011305  mov     dword ptr [rsp+0A8h+var_78], 829h
0x18001130d  mov     [rsp+0A8h+var_80], rsi
0x180011312  mov     [rsp+0A8h+var_88], ebp
0x180011316  call    WPP_SF_sDsd
0x18001131b  jmp     loc_180011139
0x180011320  mov     rcx, [rcx+10h]
0x180011324  lea     r9, aStatus; "Status"
0x18001132b  mov     dword ptr [rsp+0A8h+var_78], 56Eh
0x180011333  mov     [rsp+0A8h+var_80], rsi
0x180011338  mov     [rsp+0A8h+var_88], ebp
0x18001133c  call    WPP_SF_sDsd
0x180011341  mov     rcx, cs:WPP_GLOBAL_Control
0x180011348  jmp     loc_18001125D
0x18001134d  mov     ebx, 0C000000Dh
0x180011352  mov     rcx, cs:WPP_GLOBAL_Control
0x180011359  lea     rdi, WPP_GLOBAL_Control
0x180011360  cmp     rcx, rdi
0x180011363  jz      loc_1800111D3
0x180011369  test    byte ptr [rcx+1Ch], 1
0x18001136d  jz      loc_1800111D3
0x180011373  mov     dword ptr [rsp+0A8h+var_78], 7FDh
0x18001137b  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011382  mov     [rsp+0A8h+var_80], rsi
0x180011387  mov     [rsp+0A8h+var_88], 0C000000Dh
0x18001138f  jmp     loc_18001129D
0x180011394  mov     ebx, 0C0000008h
0x180011399  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113a0  lea     rdi, WPP_GLOBAL_Control
0x1800113a7  cmp     rcx, rdi
0x1800113aa  jz      loc_1800111D3
0x1800113b0  test    byte ptr [rcx+1Ch], 1
0x1800113b4  jz      loc_1800111D3
0x1800113ba  mov     dword ptr [rsp+0A8h+var_78], 7D7h
0x1800113c2  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800113c9  mov     [rsp+0A8h+var_80], rsi
0x1800113ce  mov     [rsp+0A8h+var_88], 0C0000008h
0x1800113d6  jmp     loc_18001129D
0x1800113db  mov     ebx, 0C000000Dh
0x1800113e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113e7  lea     rdi, WPP_GLOBAL_Control
0x1800113ee  cmp     rcx, rdi
0x1800113f1  jz      loc_1800111D3
0x1800113f7  test    byte ptr [rcx+1Ch], 1
0x1800113fb  jz      loc_1800111D3
0x180011401  mov     dword ptr [rsp+0A8h+var_78], 805h
0x180011409  jmp     loc_18001137B
0x18001140e  mov     dword ptr [rsp+0A8h+var_78], 84Fh
0x180011416  mov     [rsp+0A8h+var_80], rsi
0x18001141b  mov     [rsp+0A8h+var_88], 0C0000001h
0x180011423  mov     rcx, [rcx+10h]
0x180011427  lea     r9, aStatus; "Status"
0x18001142e  call    WPP_SF_sDsd
0x180011433  jmp     loc_1800112DB
0x180011438  mov     ebx, 0C000000Dh
0x18001143d  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
