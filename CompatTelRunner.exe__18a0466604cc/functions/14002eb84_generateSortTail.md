# generateSortTail

- ea: `0x14002eb84`
- end: `0x14002f174`
- name: `generateSortTail`
- size: `1520`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14006cd0c`

## callees

- `0x14002eb84`
- `0x14005ebd0`
- `0x14006b460`
- `0x1400738a0`
- `0x14007399c`
- `0x140073ca8`
- `0x14007aa84`
- `0x14007b574`
- `0x14007da70`

## string_xrefs

- `0x14002ebed`: `USE TEMP B-TREE FOR %sORDER BY`

## pseudocode

```c
__int64 __fastcall generateSortTail(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, unsigned __int8 *a5)
{
  const char *v6; // r9
  _DWORD *v8; // r12
  __int64 v10; // rdi
  __int64 v11; // rsi
  int v12; // ebp
  int v13; // r9d
  int v14; // r11d
  char v15; // al
  int *v16; // rbx
  char v17; // cl
  int v18; // r10d
  unsigned int TempRange; // ebp
  unsigned __int8 v20; // cl
  int v21; // r12d
  int v22; // eax
  unsigned int v23; // r14d
  int v24; // r15d
  int v25; // r10d
  int v26; // r14d
  int v27; // eax
  int v28; // r8d
  __int64 v29; // r8
  int v30; // r12d
  unsigned int v31; // edx
  int i; // r14d
  int v33; // ecx
  int v34; // r15d
  int v35; // ecx
  int v36; // r9d
  int v37; // r8d
  unsigned int v38; // r9d
  int v39; // edx
  int v40; // r14d
  unsigned __int8 v41; // r9
  int v42; // r14d
  char v43; // al
  int v44; // ebx
  unsigned __int8 v45; // al
  __int64 v46; // rax
  __int64 v47; // rbx
  unsigned int v48; // eax
  int v49; // r8d
  int v51; // [rsp+30h] [rbp-68h]
  int v52; // [rsp+34h] [rbp-64h]
  unsigned int v53; // [rsp+38h] [rbp-60h]
  unsigned int v54; // [rsp+3Ch] [rbp-5Ch]
  int v55; // [rsp+40h] [rbp-58h]
  int v56; // [rsp+44h] [rbp-54h]
  __int64 v57; // [rsp+48h] [rbp-50h]
  int v59; // [rsp+A8h] [rbp+10h]
  int v61; // [rsp+B8h] [rbp+20h]

  --*(_DWORD *)(a1 + 68);
  v6 = "RIGHT PART OF ";
  v8 = *(_DWORD **)a3;
  v10 = *(_QWORD *)(a1 + 16);
  v11 = a1;
  v53 = *(_DWORD *)(a3 + 28);
  v12 = *a5;
  v54 = *(_DWORD *)(a1 + 68);
  v51 = *((_DWORD *)a5 + 1);
  v56 = v12;
  v57 = *(_QWORD *)(a2 + 32) + 8LL;
  if ( *(int *)(a3 + 8) <= 0 )
    v6 = (const char *)&dword_1400ACDEC;
  sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %sORDER BY", v6);
  v13 = *(_DWORD *)(a3 + 20);
  if ( v13 )
  {
    sqlite3VdbeAddOp3(v10, 10, *(_DWORD *)(a3 + 16), v13, 0);
    sqlite3VdbeAddOp3(v10, 9, 0, v53, 0);
    sqlite3VdbeResolveLabel(v10, *(unsigned int *)(a3 + 20));
  }
  v14 = *(_DWORD *)(a3 + 12);
  v52 = v14;
  if ( ((v12 - 9) & 0xFFFFFFFB) == 0 )
    goto LABEL_18;
  if ( v12 == 10 )
  {
    if ( *(_DWORD *)(a2 + 12) )
    {
      sqlite3VdbeAddOp3(v10, 75, 0, *((_DWORD *)a5 + 3), 0);
      v14 = v52;
    }
LABEL_18:
    TempRange = *((_DWORD *)a5 + 3);
    v16 = (int *)(v11 + 56);
    v61 = 0;
    goto LABEL_19;
  }
  v15 = *(_BYTE *)(v11 + 31);
  v16 = (int *)(v11 + 56);
  if ( v15 )
  {
    v17 = v15 - 1;
    *(_BYTE *)(v11 + 31) = v15 - 1;
    v18 = *(_DWORD *)(v11 + 4LL * (unsigned __int8)(v15 - 1) + 224);
  }
  else
  {
    ++*v16;
    v17 = 0;
    v18 = *v16;
  }
  v61 = v18;
  if ( ((v12 - 12) & 0xFFFFFFFD) != 0 )
  {
    TempRange = sqlite3GetTempRange(v11, a4);
  }
  else
  {
    if ( v17 )
    {
      v20 = v17 - 1;
      *(_BYTE *)(v11 + 31) = v20;
      TempRange = *(_DWORD *)(v11 + 4LL * v20 + 224);
    }
    else
    {
      TempRange = ++*v16;
    }
    a4 = 0;
  }
LABEL_19:
  v21 = *v8 - *(_DWORD *)(a3 + 8);
  if ( (*(_BYTE *)(a3 + 36) & 1) != 0 )
  {
    v22 = *(_DWORD *)(v11 + 52);
    v23 = 0;
    v24 = ++*v16;
    v59 = v22;
    *(_DWORD *)(v11 + 52) = v22 + 1;
    if ( *(_DWORD *)(a3 + 20) )
      v23 = sqlite3VdbeAddOp3(v10, 15, 0, 0, 0);
    sqlite3VdbeAddOp3(v10, 121, v59, v24, a4 + v21 + 1);
    v25 = 0;
    if ( v23 )
      sqlite3VdbeJumpHere(v10, v23);
    v55 = sqlite3VdbeAddOp3(v10, 34, v52, v53, v25) + 1;
    sqlite3VdbeAddOp3(v10, 133, v52, v24, v59);
    v26 = 0;
  }
  else
  {
    v27 = sqlite3VdbeAddOp3(v10, 35, v14, v53, 0);
    v28 = *(_DWORD *)(a2 + 12);
    v55 = v27 + 1;
    if ( v28 > 0 )
      sqlite3VdbeAddOp3(v10, 59, v28, v54, 1);
    v26 = 1;
    v59 = v52;
    if ( *(int *)(a2 + 12) > 0 )
      sqlite3VdbeAddOp3(v10, 86, *(_DWORD *)(a2 + 8), -1, 0);
  }
  v29 = v57;
  v30 = v26 + v21;
  v31 = 0;
  for ( i = v30 - 1; (int)v31 < (int)a4; i = v33 )
  {
    v33 = i + 1;
    if ( *(_WORD *)(32LL * v31 + v57 + 24) )
      v33 = i;
    ++v31;
  }
  v34 = a4 - 1;
  if ( (int)(a4 - 1) >= 0 )
  {
    do
    {
      v35 = *(unsigned __int16 *)(32LL * (unsigned int)v34 + v29 + 24);
      if ( (_WORD)v35 )
        v36 = v35 - 1;
      else
        v36 = i--;
      sqlite3VdbeAddOp3(v10, 94, v59, v36, v34 + TempRange);
      --v34;
      v29 = v57;
    }
    while ( v34 >= 0 );
    v11 = a1;
  }
  if ( v56 == 10 )
    goto LABEL_47;
  if ( v56 == 11 )
  {
    v40 = v61;
    v47 = *((_QWORD *)a5 + 3);
    v48 = sqlite3VdbeAddOp3(v10, 97, TempRange, a4, v61);
    sqlite3VdbeChangeP4(v10, v48, v47, a4);
    sqlite3VdbeAddOp4Int(v10, 138, v51, v61, TempRange, a4);
    goto LABEL_48;
  }
  if ( v56 != 12 && v56 != 14 )
  {
    if ( v56 == 15 )
    {
      v42 = *((_DWORD *)a5 + 2);
      v43 = *(_BYTE *)(v11 + 31);
      if ( v43 )
      {
        v45 = v43 - 1;
        *(_BYTE *)(v11 + 31) = v45;
        v44 = *(_DWORD *)(v11 + 4LL * v45 + 224);
      }
      else
      {
        v44 = ++*v16;
      }
      sqlite3VdbeAddOp3(v10, 97, ((unsigned int)v42 >> 31) + TempRange, a4 - ((unsigned int)v42 >> 31), v44);
      if ( v42 >= 0 )
        sqlite3VdbeAddOp4Int(v10, 138, v51, v44, TempRange, v42);
      else
        sqlite3VdbeAddOp3(v10, 128, v51, v44, TempRange);
    }
    else
    {
      if ( (_BYTE)v56 == 9 )
      {
        v37 = *((_DWORD *)a5 + 3);
        v38 = a4;
        v39 = 84;
      }
      else
      {
        v37 = *((_DWORD *)a5 + 1);
        v38 = 0;
        v39 = 12;
      }
      sqlite3VdbeAddOp3(v10, v39, v37, v38, 0);
    }
LABEL_47:
    v40 = v61;
LABEL_48:
    v41 = 8;
    goto LABEL_49;
  }
  sqlite3VdbeAddOp3(v10, 94, v59, v30, TempRange);
  v40 = v61;
  sqlite3VdbeAddOp3(v10, 127, v51, v61, 0);
  sqlite3VdbeAddOp3(v10, 128, v51, TempRange, v61);
  v46 = *(int *)(v10 + 144);
  if ( (int)v46 <= 0 )
    goto LABEL_48;
  v41 = 8;
  *(_WORD *)(*(_QWORD *)(v10 + 136) + 24 * v46 - 22) = 8;
LABEL_49:
  if ( !v40 )
    goto LABEL_67;
  if ( (_BYTE)v56 == 11 )
  {
    sqlite3ReleaseTempRange(v11, TempRange, a4);
  }
  else if ( TempRange )
  {
    if ( *(_BYTE *)(v11 + 31) >= 8u )
      goto LABEL_67;
    *(_DWORD *)(v11 + 4LL * (unsigned __int8)(*(_BYTE *)(v11 + 31))++ + 224) = TempRange;
  }
  if ( *(_BYTE *)(v11 + 31) < v41 )
    *(_DWORD *)(v11 + 4LL * (unsigned __int8)(*(_BYTE *)(v11 + 31))++ + 224) = v40;
LABEL_67:
  sqlite3VdbeResolveLabel(v10, v54);
  sqlite3VdbeAddOp3(v10, 2 * ((*(_BYTE *)(a3 + 36) & 1) == 0) + 37, v52, v55, 0);
  v49 = *(_DWORD *)(a3 + 16);
  if ( v49 )
    sqlite3VdbeAddOp3(v10, 67, v49, 0, 0);
  return sqlite3VdbeResolveLabel(v10, v53);
}

```

## disassembly

```asm
0x14002eb84  mov     [rsp+arg_10], r8
0x14002eb89  mov     [rsp+arg_0], rcx
0x14002eb8e  push    rbx
0x14002eb8f  push    rbp
0x14002eb90  push    rsi
0x14002eb91  push    rdi
0x14002eb92  push    r12
0x14002eb94  push    r13
0x14002eb96  push    r14
0x14002eb98  push    r15
0x14002eb9a  sub     rsp, 58h
0x14002eb9e  dec     dword ptr [rcx+44h]
0x14002eba1  mov     r13d, r9d
0x14002eba4  mov     eax, [r8+1Ch]
0x14002eba8  lea     r9, aRightPartOf; "RIGHT PART OF "
0x14002ebaf  mov     rbx, [rsp+98h+arg_20]
0x14002ebb7  mov     r14, r8
0x14002ebba  mov     r12, [r8]
0x14002ebbd  mov     r15, rdx
0x14002ebc0  mov     rdi, [rcx+10h]
0x14002ebc4  mov     rsi, rcx
0x14002ebc7  mov     [rsp+98h+var_60], eax
0x14002ebcb  mov     eax, [rcx+44h]
0x14002ebce  movzx   ebp, byte ptr [rbx]
0x14002ebd1  mov     [rsp+98h+var_5C], eax
0x14002ebd5  mov     eax, [rbx+4]
0x14002ebd8  mov     [rsp+98h+var_68], eax
0x14002ebdc  mov     rax, [rdx+20h]
0x14002ebe0  add     rax, 8
0x14002ebe4  mov     [rsp+98h+var_54], ebp
0x14002ebe8  cmp     dword ptr [r8+8], 0
0x14002ebed  lea     r8, aUseTempBTreeFo_0; "USE TEMP B-TREE FOR %sORDER BY"
0x14002ebf4  mov     [rsp+98h+var_50], rax
0x14002ebf9  lea     rax, dword_1400ACDEC
0x14002ec00  cmovle  r9, rax
0x14002ec04  xor     edx, edx
0x14002ec06  call    sqlite3VdbeExplain
0x14002ec0b  mov     r9d, [r14+14h]
0x14002ec0f  xor     edx, edx
0x14002ec11  test    r9d, r9d
0x14002ec14  jz      short loc_14002EC55
0x14002ec16  mov     r8d, [r14+10h]
0x14002ec1a  mov     rcx, rdi
0x14002ec1d  mov     [rsp+98h+var_78], edx
0x14002ec21  mov     edx, 0Ah
0x14002ec26  call    sqlite3VdbeAddOp3
0x14002ec2b  mov     r9d, [rsp+98h+var_60]
0x14002ec30  xor     r8d, r8d
0x14002ec33  mov     rcx, rdi
0x14002ec36  mov     [rsp+98h+var_78], 0
0x14002ec3e  lea     edx, [r8+9]
0x14002ec42  call    sqlite3VdbeAddOp3
0x14002ec47  mov     edx, [r14+14h]
0x14002ec4b  mov     rcx, rdi
0x14002ec4e  call    sqlite3VdbeResolveLabel
0x14002ec53  xor     edx, edx
0x14002ec55  mov     r11d, [r14+0Ch]
0x14002ec59  lea     eax, [rbp-9]
0x14002ec5c  mov     [rsp+98h+var_64], r11d
0x14002ec61  test    eax, 0FFFFFFFBh
0x14002ec66  jz      loc_14002ECFA
0x14002ec6c  cmp     ebp, 0Ah
0x14002ec6f  jz      short loc_14002ECD6
0x14002ec71  mov     al, [rsi+1Fh]
0x14002ec74  lea     rbx, [rsi+38h]
0x14002ec78  test    al, al
0x14002ec7a  jnz     short loc_14002EC85
0x14002ec7c  inc     dword ptr [rbx]
0x14002ec7e  mov     cl, dl
0x14002ec80  mov     r10d, [rbx]
0x14002ec83  jmp     short loc_14002EC95
0x14002ec85  dec     al
0x14002ec87  movzx   ecx, al
0x14002ec8a  mov     [rsi+1Fh], cl
0x14002ec8d  mov     r10d, [rsi+rcx*4+0E0h]
0x14002ec95  lea     eax, [rbp-0Ch]
0x14002ec98  mov     [rsp+98h+arg_18], r10d
0x14002eca0  test    eax, 0FFFFFFFDh
0x14002eca5  jz      short loc_14002ECB8
0x14002eca7  mov     edx, r13d
0x14002ecaa  mov     rcx, rsi
0x14002ecad  call    sqlite3GetTempRange
0x14002ecb2  mov     ebp, eax
0x14002ecb4  xor     edx, edx
0x14002ecb6  jmp     short loc_14002ED08
0x14002ecb8  test    cl, cl
0x14002ecba  jnz     short loc_14002ECC2
0x14002ecbc  inc     dword ptr [rbx]
0x14002ecbe  mov     ebp, [rbx]
0x14002ecc0  jmp     short loc_14002ECD1
0x14002ecc2  dec     cl
0x14002ecc4  movzx   eax, cl
0x14002ecc7  mov     [rsi+1Fh], al
0x14002ecca  mov     ebp, [rsi+rax*4+0E0h]
0x14002ecd1  mov     r13d, edx
0x14002ecd4  jmp     short loc_14002ED08
0x14002ecd6  cmp     [r15+0Ch], edx
0x14002ecda  jz      short loc_14002ECFA
0x14002ecdc  mov     r9d, [rbx+0Ch]
0x14002ece0  xor     r8d, r8d
0x14002ece3  mov     [rsp+98h+var_78], edx
0x14002ece7  mov     rcx, rdi
0x14002ecea  lea     edx, [r8+4Bh]
0x14002ecee  call    sqlite3VdbeAddOp3
0x14002ecf3  mov     r11d, [rsp+98h+var_64]
0x14002ecf8  xor     edx, edx
0x14002ecfa  mov     ebp, [rbx+0Ch]
0x14002ecfd  lea     rbx, [rsi+38h]
0x14002ed01  mov     [rsp+98h+arg_18], edx
0x14002ed08  mov     r12d, [r12]
0x14002ed0c  sub     r12d, [r14+8]
0x14002ed10  test    byte ptr [r14+24h], 1
0x14002ed15  jz      loc_14002EDD9
0x14002ed1b  mov     eax, [rsi+34h]
0x14002ed1e  mov     r14d, edx
0x14002ed21  inc     dword ptr [rbx]
0x14002ed23  mov     r15d, [rbx]
0x14002ed26  mov     [rsp+98h+arg_8], eax
0x14002ed2d  inc     eax
0x14002ed2f  mov     [rsi+34h], eax
0x14002ed32  mov     rax, [rsp+98h+arg_10]
0x14002ed3a  cmp     [rax+14h], edx
0x14002ed3d  jz      short loc_14002ED58
0x14002ed3f  xor     r9d, r9d
0x14002ed42  mov     [rsp+98h+var_78], edx
0x14002ed46  xor     r8d, r8d
0x14002ed49  mov     rcx, rdi
0x14002ed4c  lea     edx, [r9+0Fh]
0x14002ed50  call    sqlite3VdbeAddOp3
0x14002ed55  mov     r14d, eax
0x14002ed58  mov     r8d, [rsp+98h+arg_8]
0x14002ed60  lea     ecx, [r12+1]
0x14002ed65  add     ecx, r13d
0x14002ed68  mov     r9d, r15d
0x14002ed6b  mov     [rsp+98h+var_78], ecx
0x14002ed6f  mov     edx, 79h ; 'y'
0x14002ed74  mov     rcx, rdi
0x14002ed77  call    sqlite3VdbeAddOp3
0x14002ed7c  xor     r10d, r10d
0x14002ed7f  test    r14d, r14d
0x14002ed82  jz      short loc_14002ED8F
0x14002ed84  mov     edx, r14d
0x14002ed87  mov     rcx, rdi
0x14002ed8a  call    sqlite3VdbeJumpHere
0x14002ed8f  mov     r9d, [rsp+98h+var_60]
0x14002ed94  mov     edx, 22h ; '"'
0x14002ed99  mov     r8d, [rsp+98h+var_64]
0x14002ed9e  mov     rcx, rdi
0x14002eda1  mov     [rsp+98h+var_78], r10d
0x14002eda6  call    sqlite3VdbeAddOp3
0x14002edab  mov     r8d, [rsp+98h+var_64]
0x14002edb0  inc     eax
0x14002edb2  mov     [rsp+98h+var_58], eax
0x14002edb6  mov     r9d, r15d
0x14002edb9  mov     eax, [rsp+98h+arg_8]
0x14002edc0  mov     edx, 85h
0x14002edc5  mov     rcx, rdi
0x14002edc8  mov     [rsp+98h+var_78], eax
0x14002edcc  call    sqlite3VdbeAddOp3
0x14002edd1  xor     r9d, r9d
0x14002edd4  mov     r14d, r9d
0x14002edd7  jmp     short loc_14002EE54
0x14002edd9  mov     r9d, [rsp+98h+var_60]
0x14002edde  mov     r8d, r11d
0x14002ede1  mov     [rsp+98h+var_78], edx
0x14002ede5  mov     rcx, rdi
0x14002ede8  mov     edx, 23h ; '#'
0x14002eded  call    sqlite3VdbeAddOp3
0x14002edf2  mov     r8d, [r15+0Ch]
0x14002edf6  inc     eax
0x14002edf8  xor     r9d, r9d
0x14002edfb  mov     [rsp+98h+var_58], eax
0x14002edff  test    r8d, r8d
0x14002ee02  jle     short loc_14002EE21
0x14002ee04  mov     r9d, [rsp+98h+var_5C]
0x14002ee09  mov     edx, 3Bh ; ';'
0x14002ee0e  mov     rcx, rdi
0x14002ee11  mov     [rsp+98h+var_78], 1
0x14002ee19  call    sqlite3VdbeAddOp3
0x14002ee1e  xor     r9d, r9d
0x14002ee21  mov     r14d, 1
0x14002ee27  mov     eax, [rsp+98h+var_64]
0x14002ee2b  mov     [rsp+98h+arg_8], eax
0x14002ee32  cmp     [r15+0Ch], r9d
0x14002ee36  jle     short loc_14002EE54
0x14002ee38  mov     r8d, [r15+8]
0x14002ee3c  lea     edx, [r14+55h]
0x14002ee40  mov     [rsp+98h+var_78], r9d
0x14002ee45  mov     rcx, rdi
0x14002ee48  or      r9d, 0FFFFFFFFh
0x14002ee4c  call    sqlite3VdbeAddOp3
0x14002ee51  xor     r9d, r9d
0x14002ee54  mov     r8, [rsp+98h+var_50]
0x14002ee59  add     r12d, r14d
0x14002ee5c  mov     edx, r9d
0x14002ee5f  lea     r14d, [r12-1]
0x14002ee64  test    r13d, r13d
0x14002ee67  jle     short loc_14002EE87
0x14002ee69  mov     eax, edx
0x14002ee6b  lea     ecx, [r14+1]
0x14002ee6f  shl     rax, 5
0x14002ee73  cmp     [rax+r8+18h], r9w
0x14002ee79  cmovnz  ecx, r14d
0x14002ee7d  inc     edx
0x14002ee7f  mov     r14d, ecx
0x14002ee82  cmp     edx, r13d
0x14002ee85  jl      short loc_14002EE69
0x14002ee87  lea     r15d, [r13-1]
0x14002ee8b  test    r15d, r15d
0x14002ee8e  js      short loc_14002EEE6
0x14002ee90  mov     esi, [rsp+98h+arg_8]
0x14002ee97  mov     eax, r15d
0x14002ee9a  shl     rax, 5
0x14002ee9e  movzx   ecx, word ptr [rax+r8+18h]
0x14002eea4  test    cx, cx
0x14002eea7  jz      short loc_14002EEAF
0x14002eea9  lea     r9d, [rcx-1]
0x14002eead  jmp     short loc_14002EEB5
0x14002eeaf  mov     r9d, r14d
0x14002eeb2  dec     r14d
0x14002eeb5  lea     eax, [r15+rbp]
0x14002eeb9  mov     r8d, esi
0x14002eebc  mov     edx, 5Eh ; '^'
0x14002eec1  mov     [rsp+98h+var_78], eax
0x14002eec5  mov     rcx, rdi
0x14002eec8  call    sqlite3VdbeAddOp3
0x14002eecd  sub     r15d, 1
0x14002eed1  mov     r8, [rsp+98h+var_50]
0x14002eed6  mov     r9d, 0
0x14002eedc  jns     short loc_14002EE97
0x14002eede  mov     rsi, [rsp+98h+arg_0]
0x14002eee6  mov     r15d, [rsp+98h+var_54]
0x14002eeeb  mov     ecx, r15d
0x14002eeee  sub     ecx, 0Ah
0x14002eef1  jz      short loc_14002EF3A
0x14002eef3  sub     ecx, 1
0x14002eef6  jz      loc_14002F076
0x14002eefc  sub     ecx, 1
0x14002eeff  jz      loc_14002EFF1
0x14002ef05  sub     ecx, 2
0x14002ef08  jz      loc_14002EFF1
0x14002ef0e  mov     rax, [rsp+98h+arg_20]
0x14002ef16  cmp     ecx, 1
0x14002ef19  jz      short loc_14002EF7A
0x14002ef1b  mov     [rsp+98h+var_78], r9d
0x14002ef20  mov     rcx, rdi
0x14002ef23  cmp     r15b, 9
0x14002ef27  jnz     short loc_14002EF6D
0x14002ef29  mov     r8d, [rax+0Ch]
0x14002ef2d  mov     r9d, r13d
0x14002ef30  mov     edx, 54h ; 'T'
0x14002ef35  call    sqlite3VdbeAddOp3
0x14002ef3a  mov     r14d, [rsp+98h+arg_18]
0x14002ef42  mov     r9d, 8
0x14002ef48  test    r14d, r14d
0x14002ef4b  jz      loc_14002F102
0x14002ef51  cmp     r15b, 0Bh
0x14002ef55  jnz     loc_14002F0D5
0x14002ef5b  mov     r8d, r13d
0x14002ef5e  mov     edx, ebp
0x14002ef60  mov     rcx, rsi
0x14002ef63  call    sqlite3ReleaseTempRange
0x14002ef68  jmp     loc_14002F0ED
0x14002ef6d  mov     r8d, [rax+4]
0x14002ef71  xor     r9d, r9d
0x14002ef74  lea     edx, [r9+0Ch]
0x14002ef78  jmp     short loc_14002EF35
0x14002ef7a  mov     r14d, [rax+8]
0x14002ef7e  mov     al, [rsi+1Fh]
0x14002ef81  test    al, al
0x14002ef83  jnz     short loc_14002EF8B
0x14002ef85  inc     dword ptr [rbx]
0x14002ef87  mov     ebx, [rbx]
0x14002ef89  jmp     short loc_14002EF9A
0x14002ef8b  dec     al
0x14002ef8d  movzx   eax, al
0x14002ef90  mov     [rsi+1Fh], al
0x14002ef93  mov     ebx, [rsi+rax*4+0E0h]
0x14002ef9a  mov     eax, r14d
0x14002ef9d  mov     [rsp+98h+var_78], ebx
0x14002efa1  shr     eax, 1Fh
0x14002efa4  mov     r9d, r13d
0x14002efa7  sub     r9d, eax
0x14002efaa  mov     edx, 61h ; 'a'
0x14002efaf  mov     rcx, rdi
0x14002efb2  lea     r8d, [rax+rbp]
0x14002efb6  call    sqlite3VdbeAddOp3
0x14002efbb  mov     r8d, [rsp+98h+var_68]
0x14002efc0  mov     r9d, ebx
0x14002efc3  mov     rcx, rdi
0x14002efc6  test    r14d, r14d
0x14002efc9  jns     short loc_14002EFD9
0x14002efcb  mov     [rsp+98h+var_78], ebp
0x14002efcf  mov     edx, 80h
0x14002efd4  jmp     loc_14002EF35
0x14002efd9  mov     [rsp+98h+var_70], r14d
0x14002efde  mov     edx, 8Ah
0x14002efe3  mov     [rsp+98h+var_78], ebp
0x14002efe7  call    sqlite3VdbeAddOp4Int
0x14002efec  jmp     loc_14002EF3A
  ... truncated ...
```
