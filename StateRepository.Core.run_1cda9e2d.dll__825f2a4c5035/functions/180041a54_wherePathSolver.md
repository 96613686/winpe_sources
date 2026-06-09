# wherePathSolver

- ea: `0x180041a54`
- end: `0x180042226`
- name: `wherePathSolver`
- size: `2002`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18003e944`

## callees

- `0x180010390`
- `0x180041a54`
- `0x180042230`
- `0x1800422a4`
- `0x180043834`
- `0x180043898`
- `0x180060ce8`
- `0x1800627d8`
- `0x18006910e`
- `0x180099814`

## pseudocode

```c
__int64 __fastcall wherePathSolver(__int64 a1, unsigned __int16 a2)
{
  __int64 v2; // r15
  unsigned int v3; // r14d
  __int64 *v4; // r8
  unsigned __int16 v5; // r13
  int v7; // ebx
  int *v8; // rcx
  int v9; // esi
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r12
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  char *v16; // rcx
  int v17; // eax
  __int16 v18; // ax
  int v19; // eax
  int v20; // ecx
  __int64 v21; // rsi
  unsigned int v22; // edx
  __int64 *v23; // r12
  int v24; // r8d
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rax
  char *v29; // rbx
  unsigned __int16 *v30; // r10
  __int16 v31; // r8
  char v32; // cl
  __int64 *v33; // rbx
  int v35; // edx
  int v36; // r10d
  __int64 v37; // r11
  int v38; // r15d
  __int64 v39; // r13
  __int64 v40; // rbx
  __int64 v41; // rcx
  unsigned __int16 v42; // ax
  __int16 v43; // ax
  __int64 v44; // r11
  unsigned __int8 v45; // r8
  __int64 v46; // r10
  __int64 v47; // rbx
  signed __int16 v48; // r12
  int v49; // r10d
  __int64 v50; // rbx
  unsigned __int16 v51; // ax
  __int16 v52; // ax
  __int16 v53; // dx
  __int16 v54; // r9
  unsigned __int16 *v55; // rdx
  char v56; // al
  int v57; // ecx
  __int64 v58; // rsi
  int v59; // eax
  __int16 v60; // dx
  __int64 v61; // rax
  __int16 v62; // r8
  int v63; // ecx
  int v64; // eax
  char v65; // al
  __int64 v66; // rax
  __int64 v67; // r8
  char v68; // al
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  int v72; // [rsp+40h] [rbp-59h]
  int v73; // [rsp+44h] [rbp-55h]
  __int64 v74; // [rsp+48h] [rbp-51h]
  unsigned int v75; // [rsp+50h] [rbp-49h]
  __int64 v76; // [rsp+58h] [rbp-41h]
  int v77; // [rsp+60h] [rbp-39h]
  __int16 v78; // [rsp+64h] [rbp-35h]
  __int16 v79; // [rsp+68h] [rbp-31h]
  int v80; // [rsp+6Ch] [rbp-2Dh]
  int v81; // [rsp+70h] [rbp-29h]
  __int64 *v82; // [rsp+78h] [rbp-21h]
  int v83; // [rsp+80h] [rbp-19h]
  char *v84; // [rsp+88h] [rbp-11h]
  __int64 v85; // [rsp+90h] [rbp-9h] BYREF
  __int64 v86; // [rsp+98h] [rbp-1h]
  __int64 v87; // [rsp+A0h] [rbp+7h]
  __int64 v88; // [rsp+A8h] [rbp+Fh]
  __int64 v89; // [rsp+100h] [rbp+67h] BYREF
  unsigned __int16 v90; // [rsp+108h] [rbp+6Fh]
  __int16 v91; // [rsp+110h] [rbp+77h]
  int v92; // [rsp+118h] [rbp+7Fh]

  v90 = a2;
  v2 = *(unsigned __int8 *)(a1 + 64);
  v3 = 1;
  v4 = *(__int64 **)a1;
  v5 = a2;
  v82 = *(__int64 **)a1;
  v83 = v2;
  if ( (unsigned int)v2 <= 1 )
  {
    v7 = 1;
    goto LABEL_4;
  }
  if ( (_DWORD)v2 == 2 )
  {
    v7 = 5;
LABEL_4:
    v72 = v7;
    goto LABEL_5;
  }
  v64 = computeMxChoice();
  v4 = v82;
  v7 = v64;
  v72 = v64;
LABEL_5:
  v8 = *(int **)(a1 + 16);
  if ( v8 && v5 )
    v9 = *v8;
  else
    v9 = 0;
  v92 = v9;
  v10 = sqlite3DbMallocRawNN(*v4, 2 * (v9 + 8 * v7 * ((int)v2 + 4)));
  v88 = v10;
  v11 = v10;
  if ( !v10 )
    return 7;
  v12 = v10;
  v76 = v10;
  v13 = 32LL * v7;
  v14 = v11;
  v77 = 0;
  v79 = 0;
  v78 = 0;
  v15 = v13 + v11;
  v84 = 0;
  v16 = (char *)(v13 + v13 + v11);
  v86 = v15;
  v17 = 2 * v7;
  *(_OWORD *)v15 = 0;
  for ( *(_OWORD *)(v15 + 16) = 0; v17 > 0; --v17 )
  {
    *(_QWORD *)(v14 + 24) = v16;
    v14 += 32;
    v16 += 8 * v2;
  }
  if ( v9 )
  {
    v84 = v16;
    memset_0(v16, 0, 2LL * v9);
    v15 = v86;
  }
  v18 = *((_WORD *)v82 + 112);
  if ( v18 >= 48 )
    v18 = 48;
  *(_WORD *)(v15 + 16) = v18;
  v19 = 1;
  v80 = 1;
  if ( v9 )
  {
    v65 = v9;
    if ( (_BYTE)v2 )
      v65 = -1;
    *(_BYTE *)(v15 + 22) = v65;
    v19 = 1;
  }
  v20 = 0;
  v75 = 0;
  if ( !(_BYTE)v2 )
    goto LABEL_16;
  do
  {
    v73 = 0;
    v74 = v15;
    v35 = 0;
    v81 = 0;
    v36 = 0;
    v37 = v15;
    if ( v19 <= 0 )
      goto LABEL_56;
    v38 = v72;
    v14 = 0;
    do
    {
      v39 = *(_QWORD *)(a1 + 88);
      if ( !v39 )
        goto LABEL_54;
      do
      {
        if ( (~*(_QWORD *)v37 & *(_QWORD *)v39) != 0
          || (v40 = *(_QWORD *)(v39 + 8), (v40 & *(_QWORD *)v37) != 0)
          || (*(_DWORD *)(v39 + 56) & 0x4000) != 0 && *(__int16 *)(v37 + 16) < 3 )
        {
          v36 = v73;
          goto LABEL_52;
        }
        v41 = *(unsigned __int16 *)(v39 + 18);
        v91 = *(_WORD *)(v37 + 16);
        v42 = *(_WORD *)(v39 + 20) + v91;
        if ( (_WORD)v41 )
          v42 = sqlite3LogEstAdd(v41, v42);
        v43 = sqlite3LogEstAdd(v42, *(unsigned __int16 *)(v37 + 20));
        v45 = *(_BYTE *)(v44 + 22);
        v47 = v46 | v40;
        v48 = v43;
        v87 = v47;
        v49 = 0;
        v91 += *(_WORD *)(v39 + 22);
        LOBYTE(v89) = v45;
        if ( (v45 & 0x80u) != 0 )
        {
          v54 = *(_WORD *)(a1 + 60);
          v55 = *(unsigned __int16 **)(a1 + 16);
          v85 = 0;
          v56 = wherePathSatisfiesOrderBy((__int64 **)a1, v55, v44, v54, v75, v39, &v85);
          v49 = 0;
          LOBYTE(v89) = v56;
          v45 = v56;
          if ( v56 < 0 )
          {
LABEL_60:
            v53 = v48;
            v48 -= 2;
            goto LABEL_61;
          }
        }
        else
        {
          v85 = *(_QWORD *)(v44 + 8);
        }
        if ( v45 >= v9 )
          goto LABEL_60;
        v50 = v45;
        v51 = *(_WORD *)&v84[2 * v45];
        if ( !v51 )
        {
          v51 = whereSortingCost(a1, v90, (unsigned int)v9);
          *(_WORD *)&v84[2 * v50] = v51;
        }
        v52 = sqlite3LogEstAdd((unsigned __int16)v48, v51);
        v47 = v87;
        v45 = v89;
        v53 = v52 + 3;
LABEL_61:
        v57 = v49;
        v36 = v73;
        v58 = v76;
        if ( v73 <= 0 )
        {
LABEL_65:
          if ( v73 >= v38 )
          {
            if ( v53 > v79 || v53 == v79 && v48 >= v78 )
              goto LABEL_85;
            v59 = v77;
          }
          else
          {
            v59 = v73++;
          }
          v58 = v76 + 32LL * v59;
        }
        else
        {
          while ( *(_QWORD *)v58 != v47 || ((*(_BYTE *)(v58 + 22) ^ v45) & 0x80u) != 0 )
          {
            ++v57;
            v58 += 32;
            if ( v57 >= v73 )
              goto LABEL_65;
          }
          if ( *(__int16 *)(v58 + 18) < v53
            || *(_WORD *)(v58 + 18) == v53
            && (*(__int16 *)(v58 + 16) < v91 || *(_WORD *)(v58 + 16) == v91 && *(__int16 *)(v58 + 20) <= v48) )
          {
LABEL_85:
            v9 = v92;
            v12 = v76;
            v37 = v74;
            goto LABEL_52;
          }
        }
        *(_QWORD *)v58 = *(_QWORD *)(v39 + 8) | *(_QWORD *)v74;
        *(_QWORD *)(v58 + 8) = v85;
        *(_WORD *)(v58 + 16) = v91;
        *(_BYTE *)(v58 + 22) = v45;
        *(_WORD *)(v58 + 18) = v53;
        *(_WORD *)(v58 + 20) = v48;
        memcpy_0(*(void **)(v58 + 24), *(const void **)(v74 + 24), 8LL * v75);
        v36 = v73;
        v12 = v76;
        *(_QWORD *)(8LL * v75 + *(_QWORD *)(v58 + 24)) = v39;
        if ( v73 >= v72 )
        {
          v60 = *(_WORD *)(v76 + 18);
          v61 = v76 + 32;
          v62 = *(_WORD *)(v76 + 16);
          v63 = 1;
          v79 = v60;
          v78 = v62;
          v77 = 0;
          if ( v72 > 1 )
          {
            do
            {
              if ( *(__int16 *)(v61 + 18) > v60 || *(_WORD *)(v61 + 18) == v60 && *(__int16 *)(v61 + 20) > v62 )
              {
                v60 = *(_WORD *)(v61 + 18);
                v62 = *(_WORD *)(v61 + 20);
                v77 = v63;
              }
              ++v63;
              v61 += 32;
            }
            while ( v63 < v72 );
            v78 = v62;
            v79 = v60;
          }
        }
        v9 = v92;
        v38 = v72;
        v37 = v74;
LABEL_52:
        v39 = *(_QWORD *)(v39 + 80);
        v14 = 0;
      }
      while ( v39 );
      v19 = v80;
      v35 = v81;
LABEL_54:
      ++v35;
      v37 += 32;
      v81 = v35;
      v74 = v37;
    }
    while ( v35 < v19 );
    LODWORD(v2) = v83;
    v15 = v86;
    v20 = v75;
LABEL_56:
    v76 = v15;
    ++v20;
    v86 = v12;
    v75 = v20;
    v12 = v15;
    v15 = v86;
    v19 = v36;
    v80 = v36;
  }
  while ( v20 < (int)v2 );
  if ( !v36 )
  {
    sqlite3ErrorMsg(v82, "no query solution", v14, v86);
    goto LABEL_27;
  }
  v5 = v90;
LABEL_16:
  v21 = v15;
  v22 = 1;
  if ( v19 > 1 )
  {
    do
    {
      if ( *(_WORD *)(v21 + 18) > *(_WORD *)(v15 + 32LL * v22 + 18) )
        v21 = v15 + 32LL * v22;
      ++v22;
    }
    while ( (int)v22 < v80 );
  }
  v23 = (__int64 *)(v21 + 24);
  v24 = 0;
  if ( (_BYTE)v2 )
  {
    do
    {
      v25 = (unsigned int)v24++;
      v26 = 112 * v25;
      v27 = *(_QWORD *)(*v23 + 8 * v25);
      *(_QWORD *)(v26 + a1 + 960) = v27;
      v28 = *(unsigned __int8 *)(v27 + 16);
      *(_BYTE *)(v26 + a1 + 928) = v28;
      *(_DWORD *)(v26 + a1 + 868) = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 80 * v28 + 40);
    }
    while ( v24 < (int)v2 );
  }
  v29 = (char *)(a1 + 60);
  if ( (*(_WORD *)(a1 + 60) & 0x100) != 0 && *v29 >= 0 && !*(_BYTE *)(a1 + 67) )
  {
    if ( v5 )
    {
      v66 = *v23;
      v89 = 0;
      if ( wherePathSatisfiesOrderBy(
             (__int64 **)a1,
             *(unsigned __int16 **)(a1 + 24),
             v21,
             128,
             v2 - 1,
             *(_QWORD *)(v66 + 8LL * (unsigned __int8)v2 - 8),
             &v89) == **(_DWORD **)(a1 + 24) )
      {
        *(_BYTE *)(a1 + 67) = 2;
        v29 = (char *)(a1 + 60);
      }
    }
  }
  *(_DWORD *)(a1 + 68) &= ~4u;
  v30 = *(unsigned __int16 **)(a1 + 16);
  if ( v30 )
  {
    v31 = *(_WORD *)v29;
    v32 = *(_BYTE *)(v21 + 22);
    *(_BYTE *)(a1 + 65) = v32;
    if ( (v31 & 0x80u) == 0 )
    {
      v33 = (__int64 *)(a1 + 104);
      *(_QWORD *)(a1 + 104) = *(_QWORD *)(v21 + 8);
      if ( v32 <= 0 )
      {
        *(_BYTE *)(a1 + 65) = 0;
        if ( (_BYTE)v2 )
        {
          v67 = *(_QWORD *)(*(_QWORD *)(v21 + 24) + 8LL * (unsigned __int8)v2 - 8);
          if ( (((*(_DWORD *)(v67 + 56) & 0x104) != 260) & !_bittest((const signed __int32 *)(v67 + 56), 0xCu)) != 0 )
          {
            v89 = 0;
            v68 = wherePathSatisfiesOrderBy((__int64 **)a1, v30, v21, 2048, v2 - 1, v67, &v89);
            v30 = *(unsigned __int16 **)(a1 + 16);
            if ( v68 == *(_DWORD *)v30 )
            {
              v69 = v89;
              *(_DWORD *)(a1 + 68) |= 4u;
              *v33 = v69;
            }
          }
        }
      }
      else if ( (_BYTE)v2 && v32 == 1 && (v31 & 3) != 0 )
      {
        *(_DWORD *)(a1 + 68) |= 4u;
      }
    }
    else
    {
      if ( *(char *)(v21 + 22) == *(_DWORD *)v30 )
        *(_BYTE *)(a1 + 67) = 2;
      v33 = (__int64 *)(a1 + 104);
    }
    if ( (*(_WORD *)(a1 + 60) & 0x200) != 0 && *(char *)(a1 + 65) == *(_DWORD *)v30 && (_BYTE)v2 )
    {
      v70 = *v23;
      v89 = 0;
      if ( wherePathSatisfiesOrderBy(
             (__int64 **)a1,
             v30,
             v21,
             0,
             v2 - 1,
             *(_QWORD *)(v70 + 8LL * (unsigned __int8)v2 - 8),
             &v89) == **(_DWORD **)(a1 + 16) )
      {
        v71 = v89;
        *(_DWORD *)(a1 + 68) |= 8u;
        *v33 = v71;
      }
    }
  }
  *(_WORD *)(a1 + 74) = *(_WORD *)(a1 + 72) + *(_WORD *)(v21 + 16);
  v3 = 0;
LABEL_27:
  sqlite3DbFreeNN(*v82, v88);
  return v3;
}

```

## disassembly

```asm
0x180041a54  mov     [rsp-8+arg_8], dx
0x180041a59  push    rbp
0x180041a5a  push    rbx
0x180041a5b  push    rsi
0x180041a5c  push    rdi
0x180041a5d  push    r12
0x180041a5f  push    r13
0x180041a61  push    r14
0x180041a63  push    r15
0x180041a65  lea     rbp, [rsp-1Fh]
0x180041a6a  sub     rsp, 0B8h
0x180041a71  movzx   r15d, byte ptr [rcx+40h]
0x180041a76  mov     r14d, 1
0x180041a7c  mov     r8, [rcx]
0x180041a7f  movzx   r13d, dx
0x180041a83  mov     [rbp+57h+var_78], r8
0x180041a87  mov     rdi, rcx
0x180041a8a  mov     [rbp+57h+var_70], r15d
0x180041a8e  cmp     r15d, r14d
0x180041a91  jbe     loc_180041C72
0x180041a97  cmp     r15d, 2
0x180041a9b  jnz     loc_180042003
0x180041aa1  lea     ebx, [r15+3]
0x180041aa5  mov     [rbp+57h+var_B0], ebx
0x180041aa8  mov     rcx, [rcx+10h]
0x180041aac  xor     eax, eax
0x180041aae  test    rcx, rcx
0x180041ab1  jnz     loc_180041C61
0x180041ab7  mov     esi, eax
0x180041ab9  lea     eax, [r15+4]
0x180041abd  mov     [rbp+57h+arg_18], esi
0x180041ac0  imul    eax, ebx
0x180041ac3  lea     ecx, [rsi+rax*8]
0x180041ac6  add     ecx, ecx
0x180041ac8  movsxd  rdx, ecx
0x180041acb  mov     rcx, [r8]
0x180041ace  call    sqlite3DbMallocRawNN
0x180041ad3  xor     r11d, r11d
0x180041ad6  mov     [rbp+57h+var_48], rax
0x180041ada  mov     rdx, rax
0x180041add  test    rax, rax
0x180041ae0  jz      loc_180042016
0x180041ae6  mov     r12, rax
0x180041ae9  mov     [rbp+57h+var_98], rax
0x180041aed  xorps   xmm0, xmm0
0x180041af0  movsxd  rax, ebx
0x180041af3  shl     rax, 5
0x180041af7  mov     r8, rdx
0x180041afa  mov     [rbp+57h+var_90], r11d
0x180041afe  mov     [rbp+57h+var_88], r11d
0x180041b02  mov     [rbp+57h+var_8C], r11d
0x180041b06  lea     r9, [rax+rdx]
0x180041b0a  mov     [rbp+57h+var_68], r11
0x180041b0e  lea     rcx, [rax+r9]
0x180041b12  mov     [rbp+57h+var_58], r9
0x180041b16  lea     eax, [rbx+rbx]
0x180041b19  movups  xmmword ptr [r9], xmm0
0x180041b1d  movups  xmmword ptr [r9+10h], xmm0
0x180041b22  test    eax, eax
0x180041b24  jle     short loc_180041B3F
0x180041b26  mov     rdx, r15
0x180041b29  shl     rdx, 3
0x180041b2d  mov     [r8+18h], rcx
0x180041b31  lea     r8, [r8+20h]
0x180041b35  add     rcx, rdx; void *
0x180041b38  sub     eax, r14d
0x180041b3b  test    eax, eax
0x180041b3d  jg      short loc_180041B2D
0x180041b3f  test    esi, esi
0x180041b41  jnz     loc_180042020
0x180041b47  mov     rax, [rbp+57h+var_78]
0x180041b4b  mov     ecx, 30h ; '0'
0x180041b50  movzx   eax, word ptr [rax+0E0h]
0x180041b57  cmp     ax, cx
0x180041b5a  jge     loc_18004203D
0x180041b60  mov     [r9+10h], ax
0x180041b65  mov     eax, r14d
0x180041b68  mov     [rbp+57h+var_84], eax
0x180041b6b  test    esi, esi
0x180041b6d  jnz     loc_180042044
0x180041b73  mov     ecx, r11d
0x180041b76  mov     [rbp+57h+var_A0], ecx
0x180041b79  test    r15b, r15b
0x180041b7c  jnz     loc_180041CAA
0x180041b82  mov     rsi, r9
0x180041b85  mov     edx, r14d
0x180041b88  cmp     eax, r14d
0x180041b8b  jg      loc_18004207E
0x180041b91  lea     r12, [rsi+18h]
0x180041b95  mov     r8d, r11d
0x180041b98  test    r15b, r15b
0x180041b9b  jz      short loc_180041BDD
0x180041b9d  mov     rax, [r12]
0x180041ba1  mov     ecx, r8d
0x180041ba4  add     r8d, r14d
0x180041ba7  imul    rdx, rcx, 70h ; 'p'
0x180041bab  mov     rax, [rax+rcx*8]
0x180041baf  mov     [rdx+rdi+3C0h], rax
0x180041bb7  movzx   eax, byte ptr [rax+10h]
0x180041bbb  mov     [rdx+rdi+3A0h], al
0x180041bc2  lea     rcx, [rax+rax*4]
0x180041bc6  mov     rax, [rdi+8]
0x180041bca  add     rcx, rcx
0x180041bcd  mov     ecx, [rax+rcx*8+28h]
0x180041bd1  mov     [rdx+rdi+364h], ecx
0x180041bd8  cmp     r8d, r15d
0x180041bdb  jl      short loc_180041B9D
0x180041bdd  lea     rbx, [rdi+3Ch]
0x180041be1  mov     eax, 100h
0x180041be6  test    [rbx], ax
0x180041be9  jnz     loc_1800420A4
0x180041bef  and     dword ptr [rdi+44h], 0FFFFFFFBh
0x180041bf3  mov     r10, [rdi+10h]
0x180041bf7  test    r10, r10
0x180041bfa  jz      short loc_180041C2B
0x180041bfc  movzx   r8d, word ptr [rbx]
0x180041c00  mov     cl, [rsi+16h]
0x180041c03  mov     [rdi+41h], cl
0x180041c06  test    r8b, r8b
0x180041c09  jns     short loc_180041C7A
0x180041c0b  movsx   eax, byte ptr [rsi+16h]
0x180041c0f  cmp     eax, [r10]
0x180041c12  jz      loc_180042121
0x180041c18  lea     rbx, [rdi+68h]
0x180041c1c  mov     eax, 200h
0x180041c21  test    [rdi+3Ch], ax
0x180041c25  jnz     loc_1800421B7
0x180041c2b  movzx   eax, word ptr [rsi+10h]
0x180041c2f  add     ax, [rdi+48h]
0x180041c33  mov     [rdi+4Ah], ax
0x180041c37  xor     r14d, r14d
0x180041c3a  mov     rax, [rbp+57h+var_78]
0x180041c3e  mov     rdx, [rbp+57h+var_48]
0x180041c42  mov     rcx, [rax]
0x180041c45  call    sqlite3DbFreeNN
0x180041c4a  mov     eax, r14d
0x180041c4d  add     rsp, 0B8h
0x180041c54  pop     r15
0x180041c56  pop     r14
0x180041c58  pop     r13
0x180041c5a  pop     r12
0x180041c5c  pop     rdi
0x180041c5d  pop     rsi
0x180041c5e  pop     rbx
0x180041c5f  pop     rbp
0x180041c60  retn
0x180041c61  test    r13w, r13w
0x180041c65  jz      loc_180041AB7
0x180041c6b  mov     esi, [rcx]
0x180041c6d  jmp     loc_180041AB9
0x180041c72  mov     ebx, r14d
0x180041c75  jmp     loc_180041AA5
0x180041c7a  mov     rax, [rsi+8]
0x180041c7e  lea     rbx, [rdi+68h]
0x180041c82  mov     [rbx], rax
0x180041c85  test    cl, cl
0x180041c87  jle     loc_18004212A
0x180041c8d  test    r15b, r15b
0x180041c90  jz      short loc_180041C1C
0x180041c92  cmp     cl, r14b
0x180041c95  jnz     short loc_180041C1C
0x180041c97  test    r8b, 3
0x180041c9b  jz      loc_180041C1C
0x180041ca1  or      dword ptr [rdi+44h], 4
0x180041ca5  jmp     loc_180041C1C
0x180041caa  xor     r13d, r13d
0x180041cad  mov     [rbp+57h+var_AC], r11d
0x180041cb1  mov     [rbp+57h+var_A8], r9
0x180041cb5  mov     edx, r13d
0x180041cb8  mov     [rbp+57h+var_80], edx
0x180041cbb  mov     r10d, r11d
0x180041cbe  mov     r11, r9
0x180041cc1  test    eax, eax
0x180041cc3  jle     loc_180041DF0
0x180041cc9  mov     r15d, [rbp+57h+var_B0]
0x180041ccd  xor     r8d, r8d
0x180041cd0  mov     r13, [rdi+58h]
0x180041cd4  test    r13, r13
0x180041cd7  jz      loc_180041DCF
0x180041cdd  mov     r10, [r11]
0x180041ce0  mov     rax, r10
0x180041ce3  not     rax
0x180041ce6  test    [r13+0], rax
0x180041cea  jnz     loc_180041DB2
0x180041cf0  mov     rbx, [r13+8]
0x180041cf4  test    r10, rbx
0x180041cf7  jnz     loc_180041DB2
0x180041cfd  test    dword ptr [r13+38h], 4000h
0x180041d05  jnz     loc_180041DA6
0x180041d0b  movzx   eax, word ptr [r11+10h]
0x180041d10  movzx   ecx, word ptr [r13+12h]
0x180041d15  mov     [rbp+57h+arg_10], ax
0x180041d19  add     ax, [r13+14h]
0x180041d1e  test    cx, cx
0x180041d21  jnz     loc_18004205B
0x180041d27  movzx   edx, word ptr [r11+14h]
0x180041d2c  movzx   ecx, ax
0x180041d2f  call    sqlite3LogEstAdd
0x180041d34  mov     r8b, [r11+16h]
0x180041d38  or      rbx, r10
0x180041d3b  movzx   r12d, ax
0x180041d3f  mov     [rbp+57h+var_50], rbx
0x180041d43  movzx   eax, [rbp+57h+arg_10]
0x180041d47  xor     r10d, r10d
0x180041d4a  add     ax, [r13+16h]
0x180041d4f  mov     [rbp+57h+arg_10], ax
0x180041d53  mov     byte ptr [rbp+57h+arg_0], r8b
0x180041d57  test    r8b, r8b
0x180041d5a  js      loc_180041E3A
0x180041d60  mov     rax, [r11+8]
0x180041d64  mov     [rbp+57h+var_60], rax
0x180041d68  movzx   r9d, r8b
0x180041d6c  cmp     r9d, esi
0x180041d6f  jge     loc_180041E79
0x180041d75  mov     rax, [rbp+57h+var_68]
0x180041d79  movzx   ebx, r8b
0x180041d7d  movzx   eax, word ptr [rax+rbx*2]
0x180041d81  test    ax, ax
0x180041d84  jz      loc_180041FAE
0x180041d8a  movzx   edx, ax
0x180041d8d  movzx   ecx, r12w
0x180041d91  call    sqlite3LogEstAdd
0x180041d96  mov     rbx, [rbp+57h+var_50]
0x180041d9a  mov     r8b, byte ptr [rbp+57h+arg_0]
0x180041d9e  lea     edx, [rax+3]
0x180041da1  jmp     loc_180041E82
0x180041da6  cmp     word ptr [r11+10h], 3
0x180041dac  jge     loc_180041D0B
0x180041db2  mov     r10d, [rbp+57h+var_AC]
0x180041db6  mov     r13, [r13+50h]
0x180041dba  mov     r8d, 0
0x180041dc0  test    r13, r13
0x180041dc3  jnz     loc_180041CDD
0x180041dc9  mov     eax, [rbp+57h+var_84]
0x180041dcc  mov     edx, [rbp+57h+var_80]
0x180041dcf  add     edx, r14d
0x180041dd2  add     r11, 20h ; ' '
0x180041dd6  mov     [rbp+57h+var_80], edx
0x180041dd9  mov     [rbp+57h+var_A8], r11
0x180041ddd  cmp     edx, eax
0x180041ddf  jl      loc_180041CD0
0x180041de5  mov     r15d, [rbp+57h+var_70]
0x180041de9  mov     r9, [rbp+57h+var_58]
0x180041ded  mov     ecx, [rbp+57h+var_A0]
0x180041df0  mov     rax, r12
0x180041df3  mov     [rbp+57h+var_98], r9
0x180041df7  add     ecx, r14d
0x180041dfa  mov     [rbp+57h+var_58], rax
0x180041dfe  mov     [rbp+57h+var_A0], ecx
0x180041e01  mov     r12, r9
0x180041e04  mov     r9, rax
0x180041e07  mov     eax, r10d
0x180041e0a  mov     [rbp+57h+var_84], eax
0x180041e0d  mov     r11d, 0
0x180041e13  cmp     ecx, r15d
0x180041e16  jl      loc_180041CAA
0x180041e1c  test    r10d, r10d
0x180041e1f  jnz     loc_180042074
0x180041e25  mov     rcx, [rbp+57h+var_78]
0x180041e29  lea     rdx, aNoQuerySolutio; "no query solution"
0x180041e30  call    sqlite3ErrorMsg
0x180041e35  jmp     loc_180041C3A
0x180041e3a  movzx   r9d, word ptr [rdi+3Ch]
0x180041e3f  lea     rax, [rbp+57h+var_60]
0x180041e43  mov     rdx, [rdi+10h]
0x180041e47  mov     r8, r11
0x180041e4a  mov     [rsp+0F0h+var_C0], rax
0x180041e4f  mov     rcx, rdi
0x180041e52  mov     eax, [rbp+57h+var_A0]
0x180041e55  mov     [rsp+0F0h+var_C8], r13
0x180041e5a  mov     [rsp+0F0h+var_D0], ax
0x180041e5f  mov     [rbp+57h+var_60], r10
0x180041e63  call    wherePathSatisfiesOrderBy
0x180041e68  xor     r10d, r10d
0x180041e6b  mov     byte ptr [rbp+57h+arg_0], al
0x180041e6e  mov     r8b, al
0x180041e71  test    al, al
0x180041e73  jns     loc_180041D68
0x180041e79  movzx   edx, r12w
0x180041e7d  sub     r12w, 2
0x180041e82  mov     r9, [rbp+57h+var_98]
0x180041e86  mov     ecx, r10d
0x180041e89  mov     r10d, [rbp+57h+var_AC]
0x180041e8d  mov     rsi, r9
0x180041e90  test    r10d, r10d
0x180041e93  jle     short loc_180041EB2
0x180041e95  cmp     [rsi], rbx
0x180041e98  jnz     short loc_180041EA6
0x180041e9a  mov     al, r8b
0x180041e9d  xor     al, [rsi+16h]
0x180041ea0  jge     loc_180041FCD
0x180041ea6  add     ecx, r14d
0x180041ea9  add     rsi, 20h ; ' '
0x180041ead  cmp     ecx, r10d
0x180041eb0  jl      short loc_180041E95
0x180041eb2  cmp     r10d, r15d
0x180041eb5  jge     loc_180041F3C
0x180041ebb  mov     eax, r10d
0x180041ebe  add     r10d, r14d
0x180041ec1  mov     [rbp+57h+var_AC], r10d
  ... truncated ...
```
