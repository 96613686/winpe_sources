# generateSortTail

- ea: `0x180049a84`
- end: `0x18004a086`
- name: `generateSortTail`
- size: `1538`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18008b73c`

## callees

- `0x180049a84`
- `0x18007ca28`
- `0x180089d98`
- `0x1800923d8`
- `0x1800924d4`
- `0x1800927e0`
- `0x1800998c0`
- `0x18009a3b4`
- `0x18009c8f4`

## string_xrefs

- `0x180049b2a`: `USE TEMP B-TREE FOR %sORDER BY`
- `0x180049b02`: `USE TEMP B-TREE FOR LAST %d TERMS OF ORDER BY`

## pseudocode

```c
__int64 __fastcall generateSortTail(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, unsigned __int8 *a5)
{
  unsigned int v6; // eax
  __int64 v9; // rsi
  int v11; // ecx
  unsigned int v12; // r12d
  int v13; // ebp
  int v14; // eax
  const char *v15; // r9
  int v16; // r9d
  int v17; // r12d
  char v18; // al
  int *v19; // rbx
  char v20; // cl
  int v21; // r10d
  unsigned int TempRange; // ebp
  unsigned __int8 v23; // cl
  unsigned int v24; // r14d
  int v25; // r15d
  int v26; // r10d
  int v27; // r14d
  int v28; // eax
  int v29; // r8d
  unsigned int v30; // edx
  __int64 v31; // r9
  int v32; // r8d
  int i; // r14d
  int v34; // ecx
  int v35; // r15d
  int v36; // ecx
  int v37; // r9d
  int v38; // r8d
  unsigned int v39; // r9d
  int v40; // edx
  int v41; // r14d
  unsigned __int8 v42; // r9
  int v43; // r14d
  char v44; // al
  int v45; // ebx
  unsigned __int8 v46; // al
  __int64 v47; // rax
  __int64 v48; // rbx
  unsigned int v49; // eax
  int v50; // r8d
  int v52; // [rsp+30h] [rbp-68h]
  int v53; // [rsp+30h] [rbp-68h]
  unsigned int v54; // [rsp+34h] [rbp-64h]
  int v55; // [rsp+38h] [rbp-60h]
  int v56; // [rsp+3Ch] [rbp-5Ch]
  int v57; // [rsp+40h] [rbp-58h]
  __int64 v58; // [rsp+48h] [rbp-50h]
  int v59; // [rsp+A0h] [rbp+8h]
  unsigned int v60; // [rsp+A8h] [rbp+10h]
  int v62; // [rsp+B8h] [rbp+20h]

  v6 = --*(_DWORD *)(a1 + 68);
  v9 = *(_QWORD *)(a1 + 16);
  v11 = *(_DWORD *)(a3 + 8);
  v12 = *(_DWORD *)(a3 + 28);
  v13 = *a5;
  v54 = v6;
  v59 = *((_DWORD *)a5 + 1);
  v60 = v12;
  v58 = *(_QWORD *)(a2 + 32) + 8LL;
  v57 = v13;
  v14 = **(_DWORD **)a3 - v11;
  v52 = v14;
  if ( !v11 || v14 == 1 )
  {
    v15 = "LAST TERM OF ";
    if ( !v11 )
      v15 = (const char *)&Src;
    sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %sORDER BY", v15);
  }
  else
  {
    sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR LAST %d TERMS OF ORDER BY", v14);
  }
  v16 = *(_DWORD *)(a3 + 20);
  if ( v16 )
  {
    sqlite3VdbeAddOp3(v9, 10, *(_DWORD *)(a3 + 16), v16, 0);
    sqlite3VdbeAddOp3(v9, 9, 0, v12, 0);
    sqlite3VdbeResolveLabel(v9, *(unsigned int *)(a3 + 20));
  }
  v17 = *(_DWORD *)(a3 + 12);
  v56 = v17;
  if ( ((v13 - 9) & 0xFFFFFFFB) == 0 )
    goto LABEL_22;
  if ( v13 == 10 )
  {
    if ( *(_DWORD *)(a2 + 12) )
      sqlite3VdbeAddOp3(v9, 75, 0, *((_DWORD *)a5 + 3), 0);
LABEL_22:
    TempRange = *((_DWORD *)a5 + 3);
    v19 = (int *)(a1 + 56);
    v62 = 0;
    goto LABEL_23;
  }
  v18 = *(_BYTE *)(a1 + 31);
  v19 = (int *)(a1 + 56);
  if ( v18 )
  {
    v20 = v18 - 1;
    *(_BYTE *)(a1 + 31) = v18 - 1;
    v21 = *(_DWORD *)(a1 + 4LL * (unsigned __int8)(v18 - 1) + 232);
  }
  else
  {
    ++*v19;
    v20 = 0;
    v21 = *v19;
  }
  v62 = v21;
  if ( ((v13 - 12) & 0xFFFFFFFD) != 0 )
  {
    TempRange = sqlite3GetTempRange(a1, a4);
  }
  else
  {
    if ( v20 )
    {
      v23 = v20 - 1;
      *(_BYTE *)(a1 + 31) = v23;
      TempRange = *(_DWORD *)(a1 + 4LL * v23 + 232);
    }
    else
    {
      TempRange = ++*v19;
    }
    a4 = 0;
  }
LABEL_23:
  if ( (*(_BYTE *)(a3 + 36) & 1) != 0 )
  {
    v17 = *(_DWORD *)(a1 + 52);
    v24 = 0;
    v25 = ++*v19;
    *(_DWORD *)(a1 + 52) = v17 + 1;
    if ( *(_DWORD *)(a3 + 20) )
      v24 = sqlite3VdbeAddOp3(v9, 15, 0, 0, 0);
    sqlite3VdbeAddOp3(v9, 121, v17, v25, a4 + v52 + 1);
    v26 = 0;
    if ( v24 )
      sqlite3VdbeJumpHere(v9, v24);
    v55 = sqlite3VdbeAddOp3(v9, 34, v56, v60, v26) + 1;
    sqlite3VdbeAddOp3(v9, 133, v56, v25, v17);
    v27 = 0;
  }
  else
  {
    v28 = sqlite3VdbeAddOp3(v9, 35, v17, v60, 0);
    v29 = *(_DWORD *)(a2 + 12);
    v55 = v28 + 1;
    if ( v29 > 0 )
      sqlite3VdbeAddOp3(v9, 59, v29, v54, 1);
    v27 = 1;
    if ( *(int *)(a2 + 12) > 0 )
      sqlite3VdbeAddOp3(v9, 86, *(_DWORD *)(a2 + 8), -1, 0);
  }
  v30 = 0;
  v31 = v58;
  v32 = v27 + v52;
  v53 = v32;
  for ( i = v32 - 1; (int)v30 < (int)a4; i = v34 )
  {
    v34 = i + 1;
    if ( *(_WORD *)(32LL * v30 + v58 + 24) )
      v34 = i;
    ++v30;
  }
  v35 = a4 - 1;
  if ( (int)(a4 - 1) >= 0 )
  {
    do
    {
      v36 = *(unsigned __int16 *)(32LL * (unsigned int)v35 + v31 + 24);
      if ( (_WORD)v36 )
        v37 = v36 - 1;
      else
        v37 = i--;
      sqlite3VdbeAddOp3(v9, 94, v17, v37, v35 + TempRange);
      --v35;
      v31 = v58;
    }
    while ( v35 >= 0 );
    v32 = v53;
  }
  if ( v57 == 10 )
    goto LABEL_51;
  if ( v57 == 11 )
  {
    v41 = v62;
    v48 = *((_QWORD *)a5 + 3);
    v49 = sqlite3VdbeAddOp3(v9, 97, TempRange, a4, v62);
    sqlite3VdbeChangeP4(v9, v49, v48, a4);
    sqlite3VdbeAddOp4Int(v9, 138, v59, v62, TempRange, a4);
    goto LABEL_52;
  }
  if ( v57 != 12 && v57 != 14 )
  {
    if ( v57 == 15 )
    {
      v43 = *((_DWORD *)a5 + 2);
      v44 = *(_BYTE *)(a1 + 31);
      if ( v44 )
      {
        v46 = v44 - 1;
        *(_BYTE *)(a1 + 31) = v46;
        v45 = *(_DWORD *)(a1 + 4LL * v46 + 232);
      }
      else
      {
        v45 = ++*v19;
      }
      sqlite3VdbeAddOp3(v9, 97, ((unsigned int)v43 >> 31) + TempRange, a4 - ((unsigned int)v43 >> 31), v45);
      if ( v43 >= 0 )
        sqlite3VdbeAddOp4Int(v9, 138, v59, v45, TempRange, v43);
      else
        sqlite3VdbeAddOp3(v9, 128, v59, v45, TempRange);
    }
    else
    {
      if ( (_BYTE)v57 == 9 )
      {
        v38 = *((_DWORD *)a5 + 3);
        v39 = a4;
        v40 = 84;
      }
      else
      {
        v38 = *((_DWORD *)a5 + 1);
        v39 = 0;
        v40 = 12;
      }
      sqlite3VdbeAddOp3(v9, v40, v38, v39, 0);
    }
LABEL_51:
    v41 = v62;
LABEL_52:
    v42 = 8;
    goto LABEL_53;
  }
  sqlite3VdbeAddOp3(v9, 94, v17, v32, TempRange);
  v41 = v62;
  sqlite3VdbeAddOp3(v9, 127, v59, v62, 0);
  sqlite3VdbeAddOp3(v9, 128, v59, TempRange, v62);
  v47 = *(int *)(v9 + 144);
  if ( (int)v47 <= 0 )
    goto LABEL_52;
  v42 = 8;
  *(_WORD *)(*(_QWORD *)(v9 + 136) + 24 * v47 - 22) = 8;
LABEL_53:
  if ( !v41 )
    goto LABEL_71;
  if ( (_BYTE)v57 == 11 )
  {
    sqlite3ReleaseTempRange(a1, TempRange, a4);
  }
  else if ( TempRange )
  {
    if ( *(_BYTE *)(a1 + 31) >= 8u )
      goto LABEL_71;
    *(_DWORD *)(a1 + 4LL * (unsigned __int8)(*(_BYTE *)(a1 + 31))++ + 232) = TempRange;
  }
  if ( *(_BYTE *)(a1 + 31) < v42 )
    *(_DWORD *)(a1 + 4LL * (unsigned __int8)(*(_BYTE *)(a1 + 31))++ + 232) = v41;
LABEL_71:
  sqlite3VdbeResolveLabel(v9, v54);
  sqlite3VdbeAddOp3(v9, 2 * ((*(_BYTE *)(a3 + 36) & 1) == 0) + 37, v56, v55, 0);
  v50 = *(_DWORD *)(a3 + 16);
  if ( v50 )
    sqlite3VdbeAddOp3(v9, 67, v50, 0, 0);
  return sqlite3VdbeResolveLabel(v9, v60);
}

```

## disassembly

```asm
0x180049a84  mov     [rsp+arg_10], r8
0x180049a89  push    rbx
0x180049a8a  push    rbp
0x180049a8b  push    rsi
0x180049a8c  push    rdi
0x180049a8d  push    r12
0x180049a8f  push    r13
0x180049a91  push    r14
0x180049a93  push    r15
0x180049a95  sub     rsp, 58h
0x180049a99  dec     dword ptr [rcx+44h]
0x180049a9c  mov     rdi, rcx
0x180049a9f  mov     eax, [rcx+44h]
0x180049aa2  mov     r15, rdx
0x180049aa5  mov     rbx, [rsp+98h+arg_20]
0x180049aad  mov     r13d, r9d
0x180049ab0  mov     rsi, [rcx+10h]
0x180049ab4  mov     r14, r8
0x180049ab7  mov     ecx, [r8+8]
0x180049abb  mov     r12d, [r8+1Ch]
0x180049abf  movzx   ebp, byte ptr [rbx]
0x180049ac2  mov     [rsp+98h+var_64], eax
0x180049ac6  mov     eax, [rbx+4]
0x180049ac9  mov     [rsp+98h+arg_0], eax
0x180049ad0  mov     rax, [rdx+20h]
0x180049ad4  xor     edx, edx
0x180049ad6  add     rax, 8
0x180049ada  mov     [rsp+98h+arg_8], r12d
0x180049ae2  mov     [rsp+98h+var_50], rax
0x180049ae7  mov     rax, [r8]
0x180049aea  mov     [rsp+98h+var_58], ebp
0x180049aee  mov     eax, [rax]
0x180049af0  sub     eax, ecx
0x180049af2  mov     [rsp+98h+var_68], eax
0x180049af6  test    ecx, ecx
0x180049af8  jz      short loc_180049B13
0x180049afa  cmp     eax, 1
0x180049afd  jz      short loc_180049B13
0x180049aff  mov     r9d, eax
0x180049b02  lea     r8, aUseTempBTreeFo; "USE TEMP B-TREE FOR LAST %d TERMS OF OR"...
0x180049b09  mov     rcx, rdi
0x180049b0c  call    sqlite3VdbeExplain
0x180049b11  jmp     short loc_180049B36
0x180049b13  test    ecx, ecx
0x180049b15  lea     rax, Src
0x180049b1c  lea     r9, aLastTermOf; "LAST TERM OF "
0x180049b23  mov     rcx, rdi
0x180049b26  cmovz   r9, rax
0x180049b2a  lea     r8, aUseTempBTreeFo_1; "USE TEMP B-TREE FOR %sORDER BY"
0x180049b31  call    sqlite3VdbeExplain
0x180049b36  mov     r9d, [r14+14h]
0x180049b3a  xor     edx, edx
0x180049b3c  test    r9d, r9d
0x180049b3f  jz      short loc_180049B7E
0x180049b41  mov     r8d, [r14+10h]
0x180049b45  mov     rcx, rsi
0x180049b48  mov     [rsp+98h+var_78], edx
0x180049b4c  mov     edx, 0Ah
0x180049b51  call    sqlite3VdbeAddOp3
0x180049b56  xor     r8d, r8d
0x180049b59  mov     [rsp+98h+var_78], 0
0x180049b61  mov     r9d, r12d
0x180049b64  mov     rcx, rsi
0x180049b67  lea     edx, [r8+9]
0x180049b6b  call    sqlite3VdbeAddOp3
0x180049b70  mov     edx, [r14+14h]
0x180049b74  mov     rcx, rsi
0x180049b77  call    sqlite3VdbeResolveLabel
0x180049b7c  xor     edx, edx
0x180049b7e  mov     r12d, [r14+0Ch]
0x180049b82  lea     eax, [rbp-9]
0x180049b85  mov     [rsp+98h+var_5C], r12d
0x180049b8a  test    eax, 0FFFFFFFBh
0x180049b8f  jz      loc_180049C1E
0x180049b95  cmp     ebp, 0Ah
0x180049b98  jz      short loc_180049BFF
0x180049b9a  mov     al, [rdi+1Fh]
0x180049b9d  lea     rbx, [rdi+38h]
0x180049ba1  test    al, al
0x180049ba3  jnz     short loc_180049BAE
0x180049ba5  inc     dword ptr [rbx]
0x180049ba7  mov     cl, dl
0x180049ba9  mov     r10d, [rbx]
0x180049bac  jmp     short loc_180049BBE
0x180049bae  dec     al
0x180049bb0  movzx   ecx, al
0x180049bb3  mov     [rdi+1Fh], cl
0x180049bb6  mov     r10d, [rdi+rcx*4+0E8h]
0x180049bbe  lea     eax, [rbp-0Ch]
0x180049bc1  mov     [rsp+98h+arg_18], r10d
0x180049bc9  test    eax, 0FFFFFFFDh
0x180049bce  jz      short loc_180049BE1
0x180049bd0  mov     edx, r13d
0x180049bd3  mov     rcx, rdi
0x180049bd6  call    sqlite3GetTempRange
0x180049bdb  mov     ebp, eax
0x180049bdd  xor     edx, edx
0x180049bdf  jmp     short loc_180049C2C
0x180049be1  test    cl, cl
0x180049be3  jnz     short loc_180049BEB
0x180049be5  inc     dword ptr [rbx]
0x180049be7  mov     ebp, [rbx]
0x180049be9  jmp     short loc_180049BFA
0x180049beb  dec     cl
0x180049bed  movzx   eax, cl
0x180049bf0  mov     [rdi+1Fh], al
0x180049bf3  mov     ebp, [rdi+rax*4+0E8h]
0x180049bfa  mov     r13d, edx
0x180049bfd  jmp     short loc_180049C2C
0x180049bff  cmp     [r15+0Ch], edx
0x180049c03  jz      short loc_180049C1E
0x180049c05  mov     r9d, [rbx+0Ch]
0x180049c09  xor     r8d, r8d
0x180049c0c  mov     [rsp+98h+var_78], edx
0x180049c10  mov     rcx, rsi
0x180049c13  lea     edx, [r8+4Bh]
0x180049c17  call    sqlite3VdbeAddOp3
0x180049c1c  xor     edx, edx
0x180049c1e  mov     ebp, [rbx+0Ch]
0x180049c21  lea     rbx, [rdi+38h]
0x180049c25  mov     [rsp+98h+arg_18], edx
0x180049c2c  test    byte ptr [r14+24h], 1
0x180049c31  jz      loc_180049CEB
0x180049c37  mov     r12d, [rdi+34h]
0x180049c3b  mov     r14d, edx
0x180049c3e  inc     dword ptr [rbx]
0x180049c40  mov     r15d, [rbx]
0x180049c43  lea     eax, [r12+1]
0x180049c48  mov     [rdi+34h], eax
0x180049c4b  mov     rax, [rsp+98h+arg_10]
0x180049c53  cmp     [rax+14h], edx
0x180049c56  jz      short loc_180049C71
0x180049c58  xor     r9d, r9d
0x180049c5b  mov     [rsp+98h+var_78], edx
0x180049c5f  xor     r8d, r8d
0x180049c62  mov     rcx, rsi
0x180049c65  lea     edx, [r9+0Fh]
0x180049c69  call    sqlite3VdbeAddOp3
0x180049c6e  mov     r14d, eax
0x180049c71  mov     ecx, [rsp+98h+var_68]
0x180049c75  mov     r9d, r15d
0x180049c78  inc     ecx
0x180049c7a  mov     r8d, r12d
0x180049c7d  add     ecx, r13d
0x180049c80  mov     edx, 79h ; 'y'
0x180049c85  mov     [rsp+98h+var_78], ecx
0x180049c89  mov     rcx, rsi
0x180049c8c  call    sqlite3VdbeAddOp3
0x180049c91  xor     r10d, r10d
0x180049c94  test    r14d, r14d
0x180049c97  jz      short loc_180049CA4
0x180049c99  mov     edx, r14d
0x180049c9c  mov     rcx, rsi
0x180049c9f  call    sqlite3VdbeJumpHere
0x180049ca4  mov     r9d, [rsp+98h+arg_8]
0x180049cac  mov     edx, 22h ; '"'
0x180049cb1  mov     r8d, [rsp+98h+var_5C]
0x180049cb6  mov     rcx, rsi
0x180049cb9  mov     [rsp+98h+var_78], r10d
0x180049cbe  call    sqlite3VdbeAddOp3
0x180049cc3  mov     r8d, [rsp+98h+var_5C]
0x180049cc8  inc     eax
0x180049cca  mov     r9d, r15d
0x180049ccd  mov     [rsp+98h+var_60], eax
0x180049cd1  mov     edx, 85h
0x180049cd6  mov     [rsp+98h+var_78], r12d
0x180049cdb  mov     rcx, rsi
0x180049cde  call    sqlite3VdbeAddOp3
0x180049ce3  xor     r10d, r10d
0x180049ce6  mov     r14d, r10d
0x180049ce9  jmp     short loc_180049D5D
0x180049ceb  mov     r9d, [rsp+98h+arg_8]
0x180049cf3  mov     r8d, r12d
0x180049cf6  mov     [rsp+98h+var_78], edx
0x180049cfa  mov     rcx, rsi
0x180049cfd  mov     edx, 23h ; '#'
0x180049d02  call    sqlite3VdbeAddOp3
0x180049d07  mov     r8d, [r15+0Ch]
0x180049d0b  inc     eax
0x180049d0d  xor     r10d, r10d
0x180049d10  mov     [rsp+98h+var_60], eax
0x180049d14  test    r8d, r8d
0x180049d17  jle     short loc_180049D35
0x180049d19  mov     r9d, [rsp+98h+var_64]
0x180049d1e  lea     edx, [r10+3Bh]
0x180049d22  mov     rcx, rsi
0x180049d25  mov     [rsp+98h+var_78], 1
0x180049d2d  call    sqlite3VdbeAddOp3
0x180049d32  xor     r10d, r10d
0x180049d35  mov     r14d, 1
0x180049d3b  cmp     [r15+0Ch], r10d
0x180049d3f  jle     short loc_180049D5D
0x180049d41  mov     r8d, [r15+8]
0x180049d45  lea     edx, [r14+55h]
0x180049d49  or      r9d, 0FFFFFFFFh
0x180049d4d  mov     [rsp+98h+var_78], r10d
0x180049d52  mov     rcx, rsi
0x180049d55  call    sqlite3VdbeAddOp3
0x180049d5a  xor     r10d, r10d
0x180049d5d  mov     r8d, [rsp+98h+var_68]
0x180049d62  mov     edx, r10d
0x180049d65  mov     r9, [rsp+98h+var_50]
0x180049d6a  add     r8d, r14d
0x180049d6d  mov     [rsp+98h+var_68], r8d
0x180049d72  lea     r14d, [r8-1]
0x180049d76  test    r13d, r13d
0x180049d79  jle     short loc_180049D99
0x180049d7b  mov     eax, edx
0x180049d7d  lea     ecx, [r14+1]
0x180049d81  shl     rax, 5
0x180049d85  cmp     [rax+r9+18h], r10w
0x180049d8b  cmovnz  ecx, r14d
0x180049d8f  inc     edx
0x180049d91  mov     r14d, ecx
0x180049d94  cmp     edx, r13d
0x180049d97  jl      short loc_180049D7B
0x180049d99  lea     r15d, [r13-1]
0x180049d9d  test    r15d, r15d
0x180049da0  js      short loc_180049DEE
0x180049da2  mov     eax, r15d
0x180049da5  shl     rax, 5
0x180049da9  movzx   ecx, word ptr [rax+r9+18h]
0x180049daf  test    cx, cx
0x180049db2  jz      short loc_180049DBA
0x180049db4  lea     r9d, [rcx-1]
0x180049db8  jmp     short loc_180049DC0
0x180049dba  mov     r9d, r14d
0x180049dbd  dec     r14d
0x180049dc0  lea     eax, [r15+rbp]
0x180049dc4  mov     r8d, r12d
0x180049dc7  mov     edx, 5Eh ; '^'
0x180049dcc  mov     [rsp+98h+var_78], eax
0x180049dd0  mov     rcx, rsi
0x180049dd3  call    sqlite3VdbeAddOp3
0x180049dd8  sub     r15d, 1
0x180049ddc  mov     r9, [rsp+98h+var_50]
0x180049de1  mov     r10d, 0
0x180049de7  jns     short loc_180049DA2
0x180049de9  mov     r8d, [rsp+98h+var_68]
0x180049dee  mov     r15d, [rsp+98h+var_58]
0x180049df3  mov     ecx, r15d
0x180049df6  sub     ecx, 0Ah
0x180049df9  jz      short loc_180049E42
0x180049dfb  sub     ecx, 1
0x180049dfe  jz      loc_180049F82
0x180049e04  sub     ecx, 1
0x180049e07  jz      loc_180049EFC
0x180049e0d  sub     ecx, 2
0x180049e10  jz      loc_180049EFC
0x180049e16  mov     rax, [rsp+98h+arg_20]
0x180049e1e  cmp     ecx, 1
0x180049e21  jz      short loc_180049E82
0x180049e23  mov     [rsp+98h+var_78], r10d
0x180049e28  mov     rcx, rsi
0x180049e2b  cmp     r15b, 9
0x180049e2f  jnz     short loc_180049E75
0x180049e31  mov     r8d, [rax+0Ch]
0x180049e35  mov     r9d, r13d
0x180049e38  mov     edx, 54h ; 'T'
0x180049e3d  call    sqlite3VdbeAddOp3
0x180049e42  mov     r14d, [rsp+98h+arg_18]
0x180049e4a  mov     r9d, 8
0x180049e50  test    r14d, r14d
0x180049e53  jz      loc_18004A011
0x180049e59  cmp     r15b, 0Bh
0x180049e5d  jnz     loc_180049FE4
0x180049e63  mov     r8d, r13d
0x180049e66  mov     edx, ebp
0x180049e68  mov     rcx, rdi
0x180049e6b  call    sqlite3ReleaseTempRange
0x180049e70  jmp     loc_180049FFC
0x180049e75  mov     r8d, [rax+4]
0x180049e79  xor     r9d, r9d
0x180049e7c  lea     edx, [r9+0Ch]
0x180049e80  jmp     short loc_180049E3D
0x180049e82  mov     r14d, [rax+8]
0x180049e86  mov     al, [rdi+1Fh]
0x180049e89  test    al, al
0x180049e8b  jnz     short loc_180049E93
0x180049e8d  inc     dword ptr [rbx]
0x180049e8f  mov     ebx, [rbx]
0x180049e91  jmp     short loc_180049EA2
0x180049e93  dec     al
0x180049e95  movzx   eax, al
0x180049e98  mov     [rdi+1Fh], al
0x180049e9b  mov     ebx, [rdi+rax*4+0E8h]
0x180049ea2  mov     eax, r14d
0x180049ea5  mov     [rsp+98h+var_78], ebx
0x180049ea9  shr     eax, 1Fh
0x180049eac  mov     r9d, r13d
0x180049eaf  sub     r9d, eax
0x180049eb2  mov     edx, 61h ; 'a'
0x180049eb7  mov     rcx, rsi
0x180049eba  lea     r8d, [rax+rbp]
0x180049ebe  call    sqlite3VdbeAddOp3
0x180049ec3  mov     r8d, [rsp+98h+arg_0]
0x180049ecb  mov     r9d, ebx
0x180049ece  mov     rcx, rsi
0x180049ed1  test    r14d, r14d
0x180049ed4  jns     short loc_180049EE4
  ... truncated ...
```
