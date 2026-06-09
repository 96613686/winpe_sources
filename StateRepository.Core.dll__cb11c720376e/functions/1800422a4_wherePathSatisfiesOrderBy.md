# wherePathSatisfiesOrderBy

- ea: `0x1800422a4`
- end: `0x180042ade`
- name: `wherePathSatisfiesOrderBy`
- size: `2106`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180041a54`

## callees

- `0x18000e4d4`
- `0x1800127ac`
- `0x1800143f0`
- `0x18003dde0`
- `0x1800422a4`
- `0x180042af0`
- `0x18006244c`
- `0x180062c90`
- `0x180067cd4`
- `0x1800964d0`

## pseudocode

```c
char __fastcall wherePathSatisfiesOrderBy(
        __int64 **a1,
        unsigned __int16 *a2,
        __int64 a3,
        __int16 a4,
        unsigned __int16 a5,
        __int64 a6,
        __int64 *a7)
{
  __int64 v7; // rbp
  __int64 *v8; // rax
  __int64 v9; // rsi
  __int64 **v10; // r11
  unsigned __int64 v11; // rdi
  __int64 v12; // rbx
  unsigned __int16 v13; // r10
  unsigned __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // r14
  int v17; // r13d
  unsigned __int16 v18; // r15
  bool v19; // zf
  unsigned int v20; // r10d
  unsigned int v21; // esi
  __int64 v22; // rbp
  __int64 v23; // rax
  __int64 v24; // rbx
  __int64 Term; // rax
  _QWORD *v26; // r15
  int v27; // edx
  unsigned int v28; // ecx
  __int64 *v29; // rbx
  _QWORD *v30; // rbp
  _QWORD *v31; // rax
  int matched; // eax
  int v33; // eax
  __int64 v34; // r13
  char v35; // r11
  int v36; // ebx
  int v37; // r10d
  char v38; // r8
  __int64 v39; // r8
  __int64 v40; // rcx
  unsigned __int16 v41; // ax
  int i; // edx
  int v43; // r12d
  unsigned int j; // esi
  __int64 v45; // r15
  char v46; // dl
  __int64 v47; // rcx
  unsigned __int16 *v48; // r10
  __int16 v49; // r11
  char v50; // r9
  _QWORD *v51; // rax
  int v52; // eax
  unsigned __int8 v53; // al
  char v54; // al
  __int64 v55; // rcx
  unsigned int v56; // ebx
  __int64 v57; // rsi
  __int64 v58; // rbp
  int k; // ecx
  __int64 v61; // rdx
  char v62; // [rsp+40h] [rbp-B8h]
  unsigned __int16 v63; // [rsp+42h] [rbp-B6h]
  unsigned __int8 v64; // [rsp+44h] [rbp-B4h]
  int v65; // [rsp+48h] [rbp-B0h]
  unsigned __int8 v66; // [rsp+4Ch] [rbp-ACh]
  char v67; // [rsp+4Dh] [rbp-ABh]
  unsigned int v68; // [rsp+50h] [rbp-A8h]
  int v69; // [rsp+54h] [rbp-A4h]
  int v70; // [rsp+58h] [rbp-A0h]
  char v71; // [rsp+5Ch] [rbp-9Ch]
  unsigned __int16 v72; // [rsp+60h] [rbp-98h]
  unsigned __int64 v73; // [rsp+68h] [rbp-90h] BYREF
  int v74; // [rsp+70h] [rbp-88h]
  __int64 v75; // [rsp+78h] [rbp-80h]
  __int16 v76; // [rsp+80h] [rbp-78h]
  int v77; // [rsp+84h] [rbp-74h]
  __int64 v78; // [rsp+88h] [rbp-70h]
  unsigned __int64 v79; // [rsp+90h] [rbp-68h]
  __int64 v80; // [rsp+98h] [rbp-60h]
  __int64 v81; // [rsp+A0h] [rbp-58h]
  __int64 v82; // [rsp+A8h] [rbp-50h]
  unsigned __int16 *v84; // [rsp+108h] [rbp+10h]
  __int16 v86; // [rsp+118h] [rbp+20h]

  v86 = a4;
  v84 = a2;
  v8 = *a1;
  v9 = a3;
  v10 = a1;
  v11 = 0;
  v73 = 0;
  v12 = *v8;
  v75 = *v8;
  if ( !a5 || (*(_BYTE *)(v12 + 96) & 0x40) == 0 )
  {
    v72 = *a2;
    v13 = *a2;
    if ( *a2 <= 0x3Fu )
    {
      v70 = *a2;
      v78 = 0;
      LOBYTE(v7) = 1;
      v14 = (1LL << v13) - 1;
      v65 = v7;
      v79 = v14;
      v15 = 0;
      v80 = 0;
      v16 = 0;
      v17 = 0;
      v18 = ((a4 & 0x803) != 0) + 386;
      v63 = v18;
LABEL_5:
      v69 = v17;
      if ( (_BYTE)v7 )
      {
        v19 = v11 == v14;
        if ( v11 >= v14 )
          goto LABEL_135;
        if ( v17 <= a5 )
        {
          if ( v17 > 0 )
            v80 = *(_QWORD *)(v16 + 8) | v15;
          if ( v17 >= a5 )
          {
            v16 = a6;
            v81 = a6;
          }
          else
          {
            v16 = *(_QWORD *)(*(_QWORD *)(v9 + 24) + 8LL * v17);
            v81 = v16;
            if ( (a4 & 0x800) != 0 )
              goto LABEL_130;
          }
          if ( (*(_DWORD *)(v16 + 56) & 0x400) == 0 )
          {
            v76 = a4 & 0x80;
            if ( (a4 & 0x80) != 0 )
              *(_WORD *)(v16 + 30) = 0;
            v20 = v10[1][10 * *(unsigned __int8 *)(v16 + 16) + 5];
            v68 = v20;
            if ( v70 )
            {
              v21 = 0;
              while ( 1 )
              {
                if ( _bittest64((const __int64 *)&v11, v21) )
                  goto LABEL_35;
                v22 = 16LL * v21;
                v23 = sqlite3ExprSkipCollateAndLikely(*(_QWORD *)&a2[v22 + 4]);
                v24 = v23;
                if ( !v23 || ((*(_BYTE *)v23 + 88) & 0xFD) != 0 || *(_DWORD *)(v23 + 44) != v20 )
                  goto LABEL_35;
                Term = sqlite3WhereFindTerm((int)v10 + 112, v20, *(__int16 *)(v23 + 48), ~(_DWORD)v80, v18, 0);
                v26 = (_QWORD *)Term;
                if ( Term )
                {
                  if ( *(_WORD *)(Term + 20) != 1 )
                    goto LABEL_29;
                  v27 = *(unsigned __int16 *)(v16 + 60);
                  v28 = 0;
                  if ( *(_WORD *)(v16 + 60) )
                  {
                    while ( Term != *(_QWORD *)(*(_QWORD *)(v16 + 72) + 8LL * v28) )
                    {
                      if ( (int)++v28 >= v27 )
                        goto LABEL_28;
                    }
LABEL_33:
                    _bittestandset64((__int64 *)&v11, v21);
                    v73 = v11;
                    goto LABEL_34;
                  }
LABEL_28:
                  if ( (int)v28 < v27 )
                  {
LABEL_29:
                    if ( (*(_BYTE *)(Term + 20) & 0x82) != 0 && *(__int16 *)(v24 + 48) >= 0 )
                    {
                      v29 = *a1;
                      v30 = (_QWORD *)sqlite3ExprNNCollSeq(*a1, *(_QWORD *)&v84[v22 + 4]);
                      v31 = (_QWORD *)sqlite3ExprCompareCollSeq(v29, *v26);
                      if ( !v31 || (unsigned int)sqlite3StrICmp(*v30, *v31) )
                        goto LABEL_34;
                    }
                    goto LABEL_33;
                  }
                }
LABEL_34:
                a2 = v84;
                v20 = v68;
                LODWORD(v10) = (_DWORD)a1;
                v18 = v63;
LABEL_35:
                if ( (int)++v21 >= v70 )
                {
                  LODWORD(v7) = v65;
                  v12 = v75;
                  break;
                }
              }
            }
            if ( (*(_DWORD *)(v16 + 56) & 0x1000) != 0 )
              goto LABEL_120;
            if ( (*(_DWORD *)(v16 + 56) & 0x100) != 0 )
            {
              if ( *(_QWORD *)(v16 + 40)
                && (*(_DWORD *)(v12 + 96) & 0x10000000) == 0
                && (matched = wherePathMatchSubqueryOB(
                                (_DWORD)v10,
                                v16,
                                v17,
                                v20,
                                (__int64)a2,
                                (__int64)a7,
                                (__int64)&v73),
                    v11 = v73,
                    matched) )
              {
                LOBYTE(v7) = 0;
                LOWORD(v33) = 0;
                v65 = v7;
              }
              else
              {
                LOWORD(v33) = 1;
              }
              v34 = 0;
              v74 = 0;
              goto LABEL_51;
            }
            v34 = *(_QWORD *)(v16 + 32);
            if ( v34 && (*(_BYTE *)(v34 + 100) & 4) == 0 )
            {
              v74 = *(unsigned __int16 *)(v34 + 94);
              LOWORD(v33) = *(_WORD *)(v34 + 96);
              if ( !*(_BYTE *)(v34 + 98) || (*(_DWORD *)(v16 + 56) & 0x8000) != 0 )
              {
                LOBYTE(v7) = 0;
                v65 = v7;
              }
              else
              {
                LOBYTE(v7) = 1;
                v65 = v7;
              }
LABEL_51:
              v35 = 0;
              v33 = (unsigned __int16)v33;
              v71 = 0;
              v36 = 0;
              v77 = (unsigned __int16)v33;
              v67 = 0;
              v66 = 0;
              while ( 1 )
              {
                if ( v36 >= v33 )
                {
                  v54 = v65;
LABEL_116:
                  if ( v35 )
                  {
                    LOBYTE(v7) = 1;
                    v65 = v7;
                    goto LABEL_119;
                  }
                  LOBYTE(v7) = v54;
                  v65 = v7;
                  if ( v54 )
                  {
LABEL_119:
                    v17 = v69;
LABEL_120:
                    v56 = 0;
                    v78 |= *(_QWORD *)(v16 + 8);
                    if ( v70 )
                    {
                      do
                      {
                        if ( !_bittest64((const __int64 *)&v11, v56) )
                        {
                          v57 = *(_QWORD *)&v84[16 * v56 + 4];
                          v58 = sqlite3WhereExprUsage(a1 + 75, v57);
                          if ( (v58 || (unsigned int)exprIsConst(0, v57, 1)) && (~v78 & v58) == 0 )
                          {
                            _bittestandset64((__int64 *)&v11, v56);
                            v73 = v11;
                          }
                        }
                        ++v56;
                      }
                      while ( (int)v56 < v70 );
                      v16 = v81;
                      LODWORD(v7) = v65;
                      goto LABEL_128;
                    }
                  }
                  else
                  {
LABEL_128:
                    v17 = v69;
                  }
                  a4 = v86;
                  a2 = v84;
                  v14 = v79;
                  v10 = a1;
                  v18 = v63;
                  v12 = v75;
                  v9 = a3;
LABEL_130:
                  v15 = v80;
                  ++v17;
                  goto LABEL_5;
                }
                v37 = *(unsigned __int16 *)(v16 + 24);
                v38 = 1;
                if ( v36 < v37 && v36 >= *(unsigned __int16 *)(v16 + 62) )
                {
                  v39 = *(_QWORD *)(v16 + 72);
                  v40 = *(_QWORD *)(v39 + 8LL * v36);
                  v41 = *(_WORD *)(v40 + 20);
                  if ( (v18 & v41) != 0 )
                  {
                    if ( (v41 & 0x180) != 0 )
                    {
                      LOBYTE(v7) = 0;
                      v65 = v7;
                    }
                    goto LABEL_112;
                  }
                  if ( (v41 & 1) != 0 )
                  {
                    for ( i = v36 + 1; i < v37; ++i )
                    {
                      if ( **(_QWORD **)(v39 + 8LL * i) == *(_QWORD *)v40 )
                      {
                        v38 = 0;
                        goto LABEL_65;
                      }
                    }
                  }
                  v38 = 1;
                }
LABEL_65:
                if ( v34 )
                {
                  v43 = *(__int16 *)(*(_QWORD *)(v34 + 8) + 2LL * v36);
                  v64 = *(_BYTE *)(v36 + *(_QWORD *)(v34 + 56)) & 1;
                  if ( v43 == *(__int16 *)(*(_QWORD *)(v34 + 24) + 52LL) )
                    v43 = -1;
                }
                else
                {
                  v43 = -1;
                  v64 = 0;
                }
                if ( (_BYTE)v7 )
                {
                  if ( v43 < 0 )
                  {
                    LODWORD(v7) = (unsigned __int8)v7;
                    if ( v43 == -2 )
                      LODWORD(v7) = 0;
                    v65 = v7;
                  }
                  else if ( v36 >= v37
                         && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v34 + 24) + 8LL) + 24LL * v43 + 8) & 0xF) == 0 )
                  {
                    LOBYTE(v65) = 0;
                  }
                }
                for ( j = 0; ; ++j )
                {
                  if ( !v38 || (int)j >= v70 )
                    goto LABEL_100;
                  if ( !_bittest64((const __int64 *)&v11, j) )
                  {
                    v82 = (int)j;
                    v45 = 16LL * (int)j;
                    v47 = sqlite3ExprSkipCollateAndLikely(*(_QWORD *)&v84[v45 + 4]);
                    if ( v47 )
                    {
                      v50 = v86;
                      LODWORD(v7) = -1;
                      v62 = (v86 & 0xC0) != 0 ? v38 : 0;
                      v38 = v62;
                      if ( v43 < -1 )
                      {
                        v7 = v36;
                        if ( !(unsigned int)sqlite3ExprCompareSkip(
                                              v47,
                                              *(_QWORD *)(32LL * v36 + *(_QWORD *)(v34 + 80) + 8),
                                              v68) )
                        {
                          v48 = v84;
                          goto LABEL_91;
                        }
LABEL_92:
                        v38 = v62;
                        continue;
                      }
                      if ( ((*(_BYTE *)v47 + 88) & 0xFD) == 0
                        && *(_DWORD *)(v47 + 44) == v68
                        && *(__int16 *)(v47 + 48) == v43 )
                      {
                        break;
                      }
                    }
                  }
                }
                if ( v43 == -1 )
                  goto LABEL_95;
                v7 = v36;
LABEL_91:
                v51 = (_QWORD *)sqlite3ExprNNCollSeq(*a1, *(_QWORD *)&v48[v45 + 4]);
                v52 = sqlite3StrICmp(*v51, *(_QWORD *)(*(_QWORD *)(v34 + 64) + 8 * v7));
                v49 = 0;
                if ( v52 )
                  goto LABEL_92;
                v46 = v82;
                LODWORD(v7) = -1;
                v50 = v86;
                v48 = v84;
LABEL_95:
                if ( v76 != v49 )
                  *(_WORD *)(v16 + 30) = v36 + 1;
                if ( (v50 & 0x40) == 0 )
                {
                  v53 = v48[v45 + 12] & 1;
                  if ( v67 == (_BYTE)v49 )
                  {
                    v66 = v64 ^ v53;
                    if ( v64 != v53 )
                    {
                      v55 = *a7;
                      _bittestandset64(&v55, v69);
                      *a7 = v55;
                    }
                    v67 = 1;
                  }
                  else if ( (v66 ^ v64) != v53 )
                  {
                    goto LABEL_100;
                  }
                }
                if ( (v48[v45 + 12] & 2) != 0 )
                {
                  if ( v36 != *(unsigned __int16 *)(v16 + 24) )
                  {
LABEL_100:
                    if ( v36 && v36 >= (unsigned __int16)v74 )
                      v54 = v65;
                    else
                      v54 = 0;
                    v35 = v71;
                    goto LABEL_116;
                  }
                  *(_DWORD *)(v16 + 56) |= 0x80000u;
                }
                LODWORD(v7) = v65;
                v18 = v63;
                v35 = v71;
                if ( v43 == -1 )
                  v35 = 1;
                v11 |= 1LL << v46;
                v73 = v11;
                v71 = v35;
LABEL_112:
                v33 = v77;
                ++v36;
              }
            }
            return 0;
          }
          if ( *(_BYTE *)(v16 + 32) && (a4 & 0x280) != 0x80 )
            v11 = v14;
        }
      }
      v19 = v11 == v14;
LABEL_135:
      if ( v19 )
        return v72;
      if ( (_BYTE)v7 )
        return -1;
      for ( k = v70 - 1; k > 0; --k )
      {
        if ( k >= 64 )
          v61 = 0;
        else
          v61 = (1LL << k) - 1;
        if ( (v11 & v61) == v61 )
          return k;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800422a4  mov     rax, rsp
0x1800422a7  mov     [rax+20h], r9w
0x1800422ac  mov     [rax+18h], r8
0x1800422b0  mov     [rax+10h], rdx
0x1800422b4  mov     [rax+8], rcx
0x1800422b8  push    rbx
0x1800422b9  push    rbp
0x1800422ba  push    rsi
0x1800422bb  push    rdi
0x1800422bc  push    r12
0x1800422be  push    r13
0x1800422c0  push    r14
0x1800422c2  push    r15
0x1800422c4  sub     rsp, 0B8h
0x1800422cb  mov     rax, [rcx]
0x1800422ce  xor     r12d, r12d
0x1800422d1  mov     rsi, r8
0x1800422d4  mov     r11, rcx
0x1800422d7  mov     edi, r12d
0x1800422da  mov     [rsp+0F8h+var_90], r12
0x1800422df  mov     rbx, [rax]
0x1800422e2  mov     [rsp+0F8h+var_80], rbx
0x1800422e7  cmp     [rsp+0F8h+arg_20], r12w
0x1800422f0  jz      short loc_1800422FC
0x1800422f2  test    byte ptr [rbx+60h], 40h
0x1800422f6  jnz     loc_180042AC8
0x1800422fc  movzx   r10d, word ptr [rdx]
0x180042300  mov     [rsp+0F8h+var_98], r10w
0x180042306  cmp     r10d, 3Fh ; '?'
0x18004230a  ja      loc_180042AC8
0x180042310  mov     r15d, 1
0x180042316  mov     [rsp+0F8h+var_A0], r10d
0x18004231b  mov     r8d, r15d
0x18004231e  mov     [rsp+0F8h+var_70], r12
0x180042326  mov     ecx, r10d
0x180042329  mov     bpl, r15b
0x18004232c  shl     r8, cl
0x18004232f  mov     r10d, 803h
0x180042335  sub     r8, r15
0x180042338  mov     [rsp+0F8h+var_B0], ebp
0x18004233c  movzx   eax, r9w
0x180042340  mov     [rsp+0F8h+var_68], r8
0x180042348  and     ax, r10w
0x18004234c  mov     rcx, r12
0x18004234f  neg     ax
0x180042352  mov     [rsp+0F8h+var_60], rcx
0x18004235a  mov     r14, r12
0x18004235d  mov     r13d, r12d
0x180042360  sbb     r15w, r15w
0x180042364  mov     r10d, 80h
0x18004236a  neg     r15w
0x18004236e  add     r15w, 182h
0x180042374  mov     [rsp+0F8h+var_B6], r15w
0x18004237a  mov     [rsp+0F8h+var_A4], r13d
0x18004237f  test    bpl, bpl
0x180042382  jz      loc_180042A7C
0x180042388  cmp     rdi, r8
0x18004238b  jnb     loc_180042A7F
0x180042391  movzx   eax, [rsp+0F8h+arg_20]
0x180042399  cmp     r13d, eax
0x18004239c  jg      loc_180042A7C
0x1800423a2  test    r13d, r13d
0x1800423a5  jle     short loc_1800423B3
0x1800423a7  or      rcx, [r14+8]
0x1800423ab  mov     [rsp+0F8h+var_60], rcx
0x1800423b3  cmp     r13d, eax
0x1800423b6  jge     short loc_1800423D8
0x1800423b8  bt      r9w, 0Bh
0x1800423be  mov     rax, [rsi+18h]
0x1800423c2  movsxd  rcx, r13d
0x1800423c5  mov     r14, [rax+rcx*8]
0x1800423c9  mov     [rsp+0F8h+var_58], r14
0x1800423d1  jnb     short loc_1800423E8
0x1800423d3  jmp     loc_180042A55
0x1800423d8  mov     r14, [rsp+0F8h+arg_28]
0x1800423e0  mov     [rsp+0F8h+var_58], r14
0x1800423e8  test    dword ptr [r14+38h], 400h
0x1800423f0  jnz     loc_180042A65
0x1800423f6  movzx   eax, r9w
0x1800423fa  and     ax, r10w
0x1800423fe  mov     [rsp+0F8h+var_78], ax
0x180042406  jz      short loc_18004240D
0x180042408  mov     [r14+1Eh], r12w
0x18004240d  movzx   eax, byte ptr [r14+10h]
0x180042412  lea     rcx, [rax+rax*4]
0x180042416  mov     rax, [r11+8]
0x18004241a  add     rcx, rcx
0x18004241d  mov     r10d, [rax+rcx*8+28h]
0x180042422  mov     [rsp+0F8h+var_A8], r10d
0x180042427  cmp     [rsp+0F8h+var_A0], r12d
0x18004242c  jbe     loc_180042576
0x180042432  mov     r13d, [rsp+0F8h+var_A0]
0x180042437  mov     esi, r12d
0x18004243a  mov     eax, esi
0x18004243c  bt      rdi, rax
0x180042440  jb      loc_18004255A
0x180042446  mov     ebp, esi
0x180042448  shl     rbp, 5
0x18004244c  mov     r12d, esi
0x18004244f  mov     rcx, [rdx+rbp+8]
0x180042454  call    sqlite3ExprSkipCollateAndLikely
0x180042459  mov     rbx, rax
0x18004245c  test    rax, rax
0x18004245f  jz      loc_18004255A
0x180042465  mov     al, [rax]
0x180042467  add     al, 58h ; 'X'
0x180042469  test    al, 0FDh
0x18004246b  jnz     loc_18004255A
0x180042471  cmp     [rbx+2Ch], r10d
0x180042475  jnz     loc_18004255A
0x18004247b  mov     r9, [rsp+0F8h+var_60]
0x180042483  lea     rcx, [r11+70h]
0x180042487  movsx   r8d, word ptr [rbx+30h]
0x18004248c  not     r9
0x18004248f  movzx   eax, r15w
0x180042493  mov     edx, r10d
0x180042496  mov     [rsp+0F8h+var_D0], 0
0x18004249f  mov     dword ptr [rsp+0F8h+var_D8], eax
0x1800424a3  call    sqlite3WhereFindTerm
0x1800424a8  xor     r11d, r11d
0x1800424ab  mov     r15, rax
0x1800424ae  test    rax, rax
0x1800424b1  jz      loc_18004253F
0x1800424b7  lea     r9d, [r11+1]
0x1800424bb  cmp     [rax+14h], r9w
0x1800424c0  jnz     short loc_1800424E5
0x1800424c2  movzx   edx, word ptr [r14+3Ch]
0x1800424c7  mov     ecx, r11d
0x1800424ca  test    edx, edx
0x1800424cc  jz      short loc_1800424E1
0x1800424ce  mov     r8, [r14+48h]
0x1800424d2  mov     eax, ecx
0x1800424d4  cmp     r15, [r8+rax*8]
0x1800424d8  jz      short loc_180042536
0x1800424da  add     ecx, r9d
0x1800424dd  cmp     ecx, edx
0x1800424df  jl      short loc_1800424D2
0x1800424e1  cmp     ecx, edx
0x1800424e3  jge     short loc_18004253F
0x1800424e5  test    byte ptr [r15+14h], 82h
0x1800424ea  jz      short loc_180042536
0x1800424ec  cmp     [rbx+30h], r11w
0x1800424f1  jl      short loc_180042536
0x1800424f3  mov     rax, [rsp+0F8h+arg_8]
0x1800424fb  mov     rbx, [rsp+0F8h+arg_0]
0x180042503  mov     rdx, [rax+rbp+8]
0x180042508  mov     rbx, [rbx]
0x18004250b  mov     rcx, rbx
0x18004250e  call    sqlite3ExprNNCollSeq
0x180042513  mov     rdx, [r15]
0x180042516  mov     rcx, rbx
0x180042519  mov     rbp, rax
0x18004251c  call    sqlite3ExprCompareCollSeq
0x180042521  test    rax, rax
0x180042524  jz      short loc_18004253F
0x180042526  mov     rdx, [rax]
0x180042529  mov     rcx, [rbp+0]
0x18004252d  call    sqlite3StrICmp
0x180042532  test    eax, eax
0x180042534  jnz     short loc_18004253F
0x180042536  bts     rdi, r12
0x18004253a  mov     [rsp+0F8h+var_90], rdi
0x18004253f  mov     rdx, [rsp+0F8h+arg_8]
0x180042547  mov     r10d, [rsp+0F8h+var_A8]
0x18004254c  mov     r11, [rsp+0F8h+arg_0]
0x180042554  movzx   r15d, [rsp+0F8h+var_B6]
0x18004255a  inc     esi
0x18004255c  cmp     esi, r13d
0x18004255f  jl      loc_18004243A
0x180042565  mov     ebp, [rsp+0F8h+var_B0]
0x180042569  xor     r12d, r12d
0x18004256c  mov     r13d, [rsp+0F8h+var_A4]
0x180042571  mov     rbx, [rsp+0F8h+var_80]
0x180042576  test    dword ptr [r14+38h], 1000h
0x18004257e  jnz     loc_180042971
0x180042584  test    dword ptr [r14+38h], 100h
0x18004258c  jz      short loc_1800425EE
0x18004258e  cmp     [r14+28h], r12
0x180042592  jz      short loc_1800425DF
0x180042594  test    dword ptr [rbx+60h], 10000000h
0x18004259b  jnz     short loc_1800425DF
0x18004259d  lea     rax, [rsp+0F8h+var_90]
0x1800425a2  mov     r9d, r10d
0x1800425a5  mov     [rsp+0F8h+var_C8], rax
0x1800425aa  mov     r8d, r13d
0x1800425ad  mov     rax, [rsp+0F8h+arg_30]
0x1800425b5  mov     rcx, r11
0x1800425b8  mov     [rsp+0F8h+var_D0], rax
0x1800425bd  mov     [rsp+0F8h+var_D8], rdx
0x1800425c2  mov     rdx, r14
0x1800425c5  call    wherePathMatchSubqueryOB
0x1800425ca  mov     rdi, [rsp+0F8h+var_90]
0x1800425cf  test    eax, eax
0x1800425d1  jz      short loc_1800425DF
0x1800425d3  mov     bpl, r12b
0x1800425d6  mov     eax, r12d
0x1800425d9  mov     [rsp+0F8h+var_B0], ebp
0x1800425dd  jmp     short loc_1800425E4
0x1800425df  mov     eax, 1
0x1800425e4  mov     r13, r12
0x1800425e7  mov     [rsp+0F8h+var_88], r12d
0x1800425ec  jmp     short loc_180042639
0x1800425ee  mov     r13, [r14+20h]
0x1800425f2  test    r13, r13
0x1800425f5  jz      loc_180042AC8
0x1800425fb  test    byte ptr [r13+64h], 4
0x180042600  jnz     loc_180042AC8
0x180042606  movzx   eax, word ptr [r13+5Eh]
0x18004260b  mov     [rsp+0F8h+var_88], eax
0x18004260f  movzx   eax, word ptr [r13+60h]
0x180042614  cmp     [r13+62h], r12b
0x180042618  jz      short loc_180042632
0x18004261a  test    dword ptr [r14+38h], 8000h
0x180042622  jnz     short loc_180042632
0x180042624  mov     esi, 1
0x180042629  mov     bpl, sil
0x18004262c  mov     [rsp+0F8h+var_B0], ebp
0x180042630  jmp     short loc_18004263E
0x180042632  mov     bpl, r12b
0x180042635  mov     [rsp+0F8h+var_B0], ebp
0x180042639  mov     esi, 1
0x18004263e  mov     r11b, r12b
0x180042641  movzx   eax, ax
0x180042644  mov     [rsp+0F8h+var_9C], r11d
0x180042649  mov     ebx, r12d
0x18004264c  mov     [rsp+0F8h+var_74], eax
0x180042653  mov     [rsp+0F8h+var_AB], r12b
0x180042658  mov     [rsp+0F8h+var_AC], r12b
0x18004265d  cmp     ebx, eax
0x18004265f  jge     loc_180042940
0x180042665  movzx   r10d, word ptr [r14+18h]
0x18004266a  mov     r8b, sil
0x18004266d  cmp     ebx, r10d
0x180042670  jge     short loc_1800426D2
0x180042672  movzx   eax, word ptr [r14+3Eh]
0x180042677  cmp     ebx, eax
0x180042679  jl      short loc_1800426D2
0x18004267b  mov     r8, [r14+48h]
0x18004267f  movsxd  rax, ebx
0x180042682  mov     rcx, [r8+rax*8]
0x180042686  movzx   eax, word ptr [rcx+14h]
0x18004268a  test    ax, r15w
0x18004268e  jz      short loc_1800426AA
0x180042690  mov     ecx, 180h
0x180042695  test    cx, ax
0x180042698  jz      loc_180042932
0x18004269e  mov     bpl, r12b
0x1800426a1  mov     [rsp+0F8h+var_B0], ebp
0x1800426a5  jmp     loc_180042932
0x1800426aa  test    sil, al
0x1800426ad  jz      short loc_1800426CF
0x1800426af  mov     r9, [rcx]
0x1800426b2  lea     edx, [rbx+1]
0x1800426b5  cmp     edx, r10d
0x1800426b8  jge     short loc_1800426CF
0x1800426ba  movsxd  rax, edx
0x1800426bd  mov     rcx, [r8+rax*8]
0x1800426c1  cmp     [rcx], r9
0x1800426c4  jz      short loc_1800426CA
0x1800426c6  add     edx, esi
0x1800426c8  jmp     short loc_1800426B5
0x1800426ca  mov     r8b, r12b
0x1800426cd  jmp     short loc_1800426D2
0x1800426cf  mov     r8b, sil
0x1800426d2  test    r13, r13
0x1800426d5  jz      short loc_18004270A
0x1800426d7  mov     rax, [r13+8]
0x1800426db  movsxd  rcx, ebx
0x1800426de  movsx   r12d, word ptr [rax+rcx*2]
0x1800426e3  mov     rax, [r13+38h]
0x1800426e7  mov     dl, [rcx+rax]
0x1800426ea  mov     rax, [r13+18h]
0x1800426ee  and     dl, sil
0x1800426f1  mov     [rsp+0F8h+var_B4], dl
0x1800426f5  movsx   ecx, word ptr [rax+34h]
0x1800426f9  mov     eax, 0FFFFFFFFh
0x1800426fe  cmp     r12d, ecx
0x180042701  cmovz   r12d, eax
0x180042705  xor     r11d, r11d
0x180042708  jmp     short loc_180042716
0x18004270a  or      r12d, 0FFFFFFFFh
0x18004270e  xor     r11d, r11d
0x180042711  mov     [rsp+0F8h+var_B4], r11b
0x180042716  test    bpl, bpl
0x180042719  jz      short loc_180042752
0x18004271b  test    r12d, r12d
0x18004271e  js      short loc_180042742
0x180042720  cmp     ebx, r10d
0x180042723  jl      short loc_180042752
0x180042725  movsxd  rax, r12d
0x180042728  lea     rdx, [rax+rax*2]
0x18004272c  mov     rax, [r13+18h]
0x180042730  mov     rcx, [rax+8]
0x180042734  test    byte ptr [rcx+rdx*8+8], 0Fh
0x180042739  jnz     short loc_180042752
0x18004273b  mov     byte ptr [rsp+0F8h+var_B0], r11b
0x180042740  jmp     short loc_180042752
0x180042742  cmp     r12d, 0FFFFFFFEh
0x180042746  movzx   ebp, bpl
0x18004274a  cmovz   ebp, r11d
  ... truncated ...
```
