# CHuffmanDecoder::ReadBigValues(CBitStream &,int *,int const *,int const *)

- ea: `0x1800042f0`
- end: `0x180004aad`
- name: `?ReadBigValues@CHuffmanDecoder@@AEAAHAEAVCBitStream@@PEAHPEBH2@Z`
- size: `1981`
- prototype: `__int64 __fastcall(CHuffmanDecoder *__hidden this, struct CBitStream *, int *, const int *, const int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003e80`

## callees

- `0x1800042f0`
- `0x18000efc8`

## pseudocode

```c
__int64 __fastcall CHuffmanDecoder::ReadBigValues(
        CHuffmanDecoder *this,
        struct CBitStream *a2,
        int *a3,
        const int *a4,
        const int *a5)
{
  int v5; // r13d
  __int64 v6; // rdi
  const int *v7; // rax
  int *v8; // r11
  __int64 v11; // rax
  __int64 v12; // rax
  int v13; // eax
  int v14; // ecx
  __int64 v15; // rbp
  int v16; // r15d
  int v17; // r11d
  __int64 v18; // rdi
  int v19; // esi
  __int64 v20; // rax
  unsigned __int16 v21; // r9
  unsigned int v22; // ecx
  int v23; // edx
  int v24; // r10d
  int v25; // edx
  unsigned __int64 v26; // r9
  unsigned int v27; // ecx
  unsigned int v28; // eax
  int v29; // ecx
  unsigned int v30; // r9d
  int v31; // r10d
  int v32; // r9d
  int v33; // edi
  __int64 v34; // rsi
  unsigned int v35; // r11d
  unsigned __int16 v36; // r10
  unsigned int v37; // ecx
  int v38; // eax
  int v39; // eax
  int v40; // esi
  __int64 v41; // rbp
  unsigned int v42; // edi
  unsigned __int16 v43; // r11
  unsigned int v44; // ecx
  int v45; // eax
  int v46; // eax
  int v47; // edi
  __int64 v48; // rsi
  unsigned int v49; // r11d
  unsigned __int16 v50; // r9
  unsigned int v51; // ecx
  int v52; // eax
  int v53; // eax
  int v54; // esi
  __int64 v55; // rbp
  unsigned int v56; // edi
  unsigned __int16 v57; // r11
  unsigned int v58; // ecx
  int v59; // eax
  int v60; // eax
  const int *v61; // rcx
  const int *v63; // rax
  int v64; // ecx
  __int64 v65; // rdx
  __int64 v66; // rbp
  int v67; // r15d
  int v68; // edi
  __int64 v69; // rsi
  int v70; // r11d
  __int64 v71; // rax
  unsigned __int16 v72; // r9
  unsigned int v73; // ecx
  int v74; // edx
  int v75; // r10d
  int v76; // edx
  unsigned __int64 v77; // r8
  unsigned int v78; // ecx
  unsigned int v79; // eax
  int v80; // ecx
  unsigned int v81; // r10d
  int v82; // esi
  int v83; // r10d
  int v84; // edi
  __int64 v85; // rbp
  unsigned int v86; // r9d
  unsigned __int16 v87; // r11
  unsigned int v88; // ecx
  int v89; // eax
  int v90; // eax
  int v91; // edi
  __int64 v92; // rbp
  unsigned int v93; // r9d
  unsigned __int16 v94; // r11
  unsigned int v95; // ecx
  int v96; // eax
  int v97; // eax
  __int64 v98; // [rsp+20h] [rbp-48h]
  __int64 v99; // [rsp+28h] [rbp-40h]
  __int64 v100; // [rsp+28h] [rbp-40h]

  v5 = 0;
  v6 = 0;
  v7 = a4;
  v98 = 0;
  v8 = a3;
  do
  {
    v11 = (unsigned int)v7[v6];
    *((_DWORD *)this + 4) = v11;
    v12 = 2 * v11;
    if ( !*((_QWORD *)&CHuffmanTable::ht + v12 + 1) )
    {
      v63 = a5;
      v64 = a5[v6];
      if ( v5 < v64 )
      {
        v65 = v5;
        do
          ++v5;
        while ( v5 < v64 );
        memset_0(&v8[v65], 0, 4LL * (v64 - (int)v65));
        v8 = a3;
LABEL_35:
        v61 = a5;
        goto LABEL_29;
      }
      goto LABEL_53;
    }
    v13 = *((_DWORD *)&CHuffmanTable::ht + 2 * v12);
    *((_DWORD *)this + 18) = v13;
    v14 = a5[v6];
    if ( !v13 )
    {
      if ( v5 >= v14 )
        goto LABEL_35;
      do
      {
        v66 = 0;
        v67 = *((_DWORD *)a2 + 8);
        v68 = v67;
        v69 = *((_QWORD *)a2 + 6);
        v100 = v5;
        v70 = *((_DWORD *)a2 + 5) - 1;
        while ( 1 )
        {
          v71 = (*((int *)a2 + 9) >> 3) & 0xFFFFFFFE;
          v72 = (*(unsigned __int8 *)((unsigned int)(v71 + 1) + v69)
               | (unsigned __int16)(*(unsigned __int8 *)(v71 + v69) << 8)) << (*((_BYTE *)a2 + 36) & 0xF);
          v73 = 16 - (*((_DWORD *)a2 + 9) & 0xF);
          if ( v73 < 2 )
            v72 |= (unsigned __int16)(*(unsigned __int8 *)(((*((_DWORD *)a2 + 4) - 1)
                                                          & (((*((int *)a2 + 9) >> 3) & 0xFFFFFFFE) + 2))
                                                         + 1
                                                         + v69)
                                    | (*(unsigned __int8 *)(((*((_DWORD *)a2 + 4) - 1)
                                                           & (((*((int *)a2 + 9) >> 3) & 0xFFFFFFFE) + 2))
                                                          + v69) << 8)) >> v73;
          v74 = *((_DWORD *)a2 + 6);
          v75 = v70 & (*((_DWORD *)a2 + 9) + 2);
          *((_DWORD *)a2 + 9) = v75;
          v76 = v74 - 2;
          *((_DWORD *)a2 + 6) = v76;
          v68 += 2;
          *((_DWORD *)a2 + 8) = v68;
          v77 = 4 * (((unsigned __int64)v72 >> 14) + 4 * v66);
          v78 = *(_DWORD *)(v77
                          + *((_QWORD *)&CHuffmanTable::ht + 2 * *(unsigned int *)(*((_QWORD *)this + 5) + 8LL) + 1));
          v79 = v78 >> 8;
          if ( (v78 & 0xFF00) != 0 )
            break;
          v66 = (unsigned __int8)v78;
        }
        v80 = v67 + BYTE1(v78) - v68;
        *((_DWORD *)a2 + 6) = v76 - v80;
        *((_DWORD *)a2 + 8) = v67 + (unsigned __int8)v79;
        *((_DWORD *)a2 + 9) = v70 & (v80 + v75);
        v81 = (unsigned __int8)*(_DWORD *)(*((_QWORD *)&CHuffmanTable::ht
                                           + 2 * *(unsigned int *)(*((_QWORD *)this + 5) + 8LL)
                                           + 1)
                                         + v77);
        *((_DWORD *)this + 8) = v81;
        v82 = v81 >> 4;
        v83 = v81 & 0xF;
        if ( v82 )
        {
          v84 = *((_DWORD *)a2 + 9);
          v85 = *((_QWORD *)a2 + 6);
          v86 = *((_DWORD *)this + 14);
          v87 = (*(unsigned __int8 *)(((v84 >> 3) & 0xFFFFFFFE) + 1 + v85)
               | (unsigned __int16)(*(unsigned __int8 *)(((v84 >> 3) & 0xFFFFFFFE) + v85) << 8)) << (*((_BYTE *)a2 + 36) & 0xF);
          v88 = 16 - (v84 & 0xF);
          if ( v86 > v88 )
            v87 |= (unsigned __int16)(*(unsigned __int8 *)(((*((_DWORD *)a2 + 4) - 1) & (((v84 >> 3) & 0xFFFFFFFE) + 2))
                                                         + 1
                                                         + v85)
                                    | (*(unsigned __int8 *)(((*((_DWORD *)a2 + 4) - 1) & (((v84 >> 3) & 0xFFFFFFFE) + 2))
                                                          + v85) << 8)) >> v88;
          v89 = *((_DWORD *)a2 + 5);
          *((_DWORD *)a2 + 8) += v86;
          *((_DWORD *)a2 + 6) -= v86;
          *((_DWORD *)a2 + 9) = (v89 - 1) & (v84 + v86);
          v90 = v87 >> (16 - v86);
          *((_DWORD *)this + 15) = v90;
          if ( v90 == 1 )
            v82 = -v82;
        }
        if ( v83 )
        {
          v91 = *((_DWORD *)a2 + 9);
          v92 = *((_QWORD *)a2 + 6);
          v93 = *((_DWORD *)this + 14);
          v94 = (*(unsigned __int8 *)(((v91 >> 3) & 0xFFFFFFFE) + 1 + v92)
               | (unsigned __int16)(*(unsigned __int8 *)(((v91 >> 3) & 0xFFFFFFFE) + v92) << 8)) << (*((_BYTE *)a2 + 36) & 0xF);
          v95 = 16 - (v91 & 0xF);
          if ( v93 > v95 )
            v94 |= (unsigned __int16)(*(unsigned __int8 *)(((*((_DWORD *)a2 + 4) - 1) & (((v91 >> 3) & 0xFFFFFFFE) + 2))
                                                         + 1
                                                         + v92)
                                    | (*(unsigned __int8 *)(((*((_DWORD *)a2 + 4) - 1) & (((v91 >> 3) & 0xFFFFFFFE) + 2))
                                                          + v92) << 8)) >> v95;
          v96 = *((_DWORD *)a2 + 5);
          *((_DWORD *)a2 + 8) += v93;
          *((_DWORD *)a2 + 6) -= v93;
          *((_DWORD *)a2 + 9) = (v96 - 1) & (v91 + v93);
          v97 = v94 >> (16 - v93);
          *((_DWORD *)this + 15) = v97;
          if ( v97 == 1 )
            v83 = -v83;
        }
        v8 = a3;
        v5 += 2;
        v6 = v98;
        v63 = a5;
        a3[v100] = v82;
        a3[v100 + 1] = v83;
      }
      while ( v5 < a5[v98] );
LABEL_53:
      v61 = v63;
      goto LABEL_29;
    }
    if ( v5 >= v14 )
      goto LABEL_35;
    do
    {
      v15 = 0;
      v16 = *((_DWORD *)a2 + 8);
      v17 = v16;
      v18 = *((_QWORD *)a2 + 6);
      v99 = v5;
      v19 = *((_DWORD *)a2 + 5) - 1;
      while ( 1 )
      {
        v20 = (*((int *)a2 + 9) >> 3) & 0xFFFFFFFE;
        v21 = (*(unsigned __int8 *)((unsigned int)(v20 + 1) + v18)
             | (unsigned __int16)(*(unsigned __int8 *)(v20 + v18) << 8)) << (*((_BYTE *)a2 + 36) & 0xF);
        v22 = 16 - (*((_DWORD *)a2 + 9) & 0xF);
        if ( v22 < 2 )
          v21 |= (unsigned __int16)(*(unsigned __int8 *)(((*((_DWORD *)a2 + 4) - 1)
                                                        & (((*((int *)a2 + 9) >> 3) & 0xFFFFFFFE) + 2))
                                                       + 1
                                                       + v18)
                                  | (*(unsigned __int8 *)(((*((_DWORD *)a2 + 4) - 1)
                                                         & (((*((int *)a2 + 9) >> 3) & 0xFFFFFFFE) + 2))
                                                        + v18) << 8)) >> v22;
        v23 = *((_DWORD *)a2 + 6);
        v24 = v19 & (*((_DWORD *)a2 + 9) + 2);
        *((_DWORD *)a2 + 9) = v24;
        v25 = v23 - 2;
        *((_DWORD *)a2 + 6) = v25;
        v17 += 2;
        *((_DWORD *)a2 + 8) = v17;
        v26 = 4 * (((unsigned __int64)v21 >> 14) + 4 * v15);
        v27 = *(_DWORD *)(v26 + *((_QWORD *)&CHuffmanTable::ht + 2 * *(unsigned int *)(*((_QWORD *)this + 5) + 8LL) + 1));
        v28 = v27 >> 8;
        if ( (v27 & 0xFF00) != 0 )
          break;
        v15 = (unsigned __int8)v27;
      }
      v29 = v16 + BYTE1(v27) - v17;
      *((_DWORD *)a2 + 6) = v25 - v29;
      *((_DWORD *)a2 + 8) = v16 + (unsigned __int8)v28;
      *((_DWORD *)a2 + 9) = v19 & (v29 + v24);
      v30 = (unsigned __int8)*(_DWORD *)(*((_QWORD *)&CHuffmanTable::ht
                                         + 2 * *(unsigned int *)(*((_QWORD *)this + 5) + 8LL)
                                         + 1)
                                       + v26);
      *((_DWORD *)this + 8) = v30;
      v31 = v30 >> 4;
      v32 = v30 & 0xF;
      if ( v31 == 15 )
      {
        v33 = *((_DWORD *)a2 + 9);
        v34 = *((_QWORD *)a2 + 6);
        v35 = *((_DWORD *)this + 18);
        v36 = (*(unsigned __int8 *)(((v33 >> 3) & 0xFFFFFFFE) + 1 + v34)
             | (unsigned __int16)(*(unsigned __int8 *)(((v33 >> 3) & 0xFFFFFFFE) + v34) << 8)) << (*((_BYTE *)a2 + 36)
                                                                                                 & 0xF);
        v37 = 16 - (v33 & 0xF);
        if ( v35 > v37 )
          v36 |= (unsigned __int16)(*(unsigned __int8 *)(((((v33 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)a2 + 4) - 1))
                                                       + 1
                                                       + v34)
                                  | (*(unsigned __int8 *)(((((v33 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)a2 + 4) - 1))
                                                        + v34) << 8)) >> v37;
        v38 = *((_DWORD *)a2 + 5);
        *((_DWORD *)a2 + 8) += v35;
        *((_DWORD *)a2 + 6) -= v35;
        *((_DWORD *)a2 + 9) = (v38 - 1) & (v33 + v35);
        v39 = v36 >> (16 - v35);
        *((_DWORD *)this + 19) = v39;
        v31 = v39 + 15;
      }
      if ( v31 )
      {
        v40 = *((_DWORD *)a2 + 9);
        v41 = *((_QWORD *)a2 + 6);
        v42 = *((_DWORD *)this + 14);
        v43 = (*(unsigned __int8 *)(((v40 >> 3) & 0xFFFFFFFE) + 1 + v41)
             | (unsigned __int16)(*(unsigned __int8 *)(((v40 >> 3) & 0xFFFFFFFE) + v41) << 8)) << (*((_BYTE *)a2 + 36)
                                                                                                 & 0xF);
        v44 = 16 - (v40 & 0xF);
        if ( v42 > v44 )
          v43 |= (unsigned __int16)(*(unsigned __int8 *)(((((v40 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)a2 + 4) - 1))
                                                       + 1
                                                       + v41)
                                  | (*(unsigned __int8 *)(((((v40 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)a2 + 4) - 1))
                                                        + v41) << 8)) >> v44;
        v45 = *((_DWORD *)a2 + 5);
        *((_DWORD *)a2 + 8) += v42;
        *((_DWORD *)a2 + 6) -= v42;
        *((_DWORD *)a2 + 9) = (v45 - 1) & (v40 + v42);
        v46 = v43 >> (16 - v42);
        *((_DWORD *)this + 15) = v46;
        if ( v46 == 1 )
          v31 = -v31;
      }
      if ( v32 == 15 )
      {
        v47 = *((_DWORD *)a2 + 9);
        v48 = *((_QWORD *)a2 + 6);
        v49 = *((_DWORD *)this + 18);
        v50 = (*(unsigned __int8 *)(((v47 >> 3) & 0xFFFFFFFE) + 1 + v48)
             | (unsigned __int16)(*(unsigned __int8 *)(((v47 >> 3) & 0xFFFFFFFE) + v48) << 8)) << (*((_BYTE *)a2 + 36)
                                                                                                 & 0xF);
        v51 = 16 - (v47 & 0xF);
        if ( v49 > v51 )
          v50 |= (unsigned __int16)(*(unsigned __int8 *)(((((v47 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)a2 + 4) - 1))
                                                       + 1
                                                       + v48)
                                  | (*(unsigned __int8 *)(((((v47 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)a2 + 4) - 1))
                                                        + v48) << 8)) >> v51;
        v52 = *((_DWORD *)a2 + 5);
        *((_DWORD *)a2 + 8) += v49;
        *((_DWORD *)a2 + 6) -= v49;
        *((_DWORD *)a2 + 9) = (v52 - 1) & (v47 + v49);
        v53 = v50 >> (16 - v49);
        *((_DWORD *)this + 19) = v53;
        v32 = v53 + 15;
      }
      if ( v32 )
      {
        v54 = *((_DWORD *)a2 + 9);
        v55 = *((_QWORD *)a2 + 6);
        v56 = *((_DWORD *)this + 14);
        v57 = (*(unsigned __int8 *)(((v54 >> 3) & 0xFFFFFFFE) + 1 + v55)
             | (unsigned __int16)(*(unsigned __int8 *)(((v54 >> 3) & 0xFFFFFFFE) + v55) << 8)) << (*((_BYTE *)a2 + 36)
                                                                                                 & 0xF);
        v58 = 16 - (v54 & 0xF);
        if ( v56 > v58 )
          v57 |= (unsigned __int16)(*(unsigned __int8 *)(((((v54 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)a2 + 4) - 1))
                                                       + 1
                                                       + v55)
                                  | (*(unsigned __int8 *)(((((v54 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)a2 + 4) - 1))
                                                        + v55) << 8)) >> v58;
        v59 = *((_DWORD *)a2 + 5);
        *((_DWORD *)a2 + 8) += v56;
        *((_DWORD *)a2 + 6) -= v56;
        *((_DWORD *)a2 + 9) = (v59 - 1) & (v56 + v54);
        v60 = v57 >> (16 - v56);
        *((_DWORD *)this + 15) = v60;
        if ( v60 == 1 )
          v32 = -v32;
      }
      v8 = a3;
      v5 += 2;
      v6 = v98;
      v61 = a5;
      a3[v99] = v31;
      a3[v99 + 1] = v32;
    }
    while ( v5 < a5[v98] );
LABEL_29:
    v7 = a4;
    v98 = ++v6;
  }
  while ( v6 != 3 );
  return *((unsigned int *)v61 + 2);
}

```

## disassembly

```asm
0x1800042f0  mov     [rsp+arg_0], rbx
0x1800042f5  mov     [rsp+arg_18], r9
0x1800042fa  mov     [rsp+arg_10], r8
0x1800042ff  push    rbp
0x180004300  push    rsi
0x180004301  push    rdi
0x180004302  push    r12
0x180004304  push    r13
0x180004306  push    r14
0x180004308  push    r15
0x18000430a  sub     rsp, 30h
0x18000430e  xor     r13d, r13d
0x180004311  lea     rsi, ?ht@CHuffmanTable@@0QBUhuffmantab@1@B; CHuffmanTable::huffmantab const near * const CHuffmanTable::ht
0x180004318  xor     edi, edi
0x18000431a  mov     rax, r9
0x18000431d  mov     [rsp+68h+var_48], rdi
0x180004322  mov     r11, r8
0x180004325  mov     rbx, rdx
0x180004328  mov     r14, rcx
0x18000432b  mov     eax, [rax+rdi*4]
0x18000432e  mov     [r14+10h], eax
0x180004332  add     rax, rax
0x180004335  cmp     qword ptr [rsi+rax*8+8], 0
0x18000433b  jz      loc_1800047A2
0x180004341  mov     eax, [rsi+rax*8]
0x180004344  mov     rcx, [rsp+68h+arg_20]
0x18000434c  mov     [r14+48h], eax
0x180004350  mov     ecx, [rcx+rdi*4]
0x180004353  test    eax, eax
0x180004355  jz      loc_1800047EA
0x18000435b  cmp     r13d, ecx
0x18000435e  jge     loc_1800047DD
0x180004364  nop     dword ptr [rax+00h]
0x180004368  nop     dword ptr [rax+rax+00000000h]
0x180004370  mov     esi, [rbx+14h]
0x180004373  xor     ebp, ebp
0x180004375  mov     r15d, [rbx+20h]
0x180004379  mov     r11d, r15d
0x18000437c  mov     rdi, [rbx+30h]
0x180004380  movsxd  r12, r13d
0x180004383  shl     r12, 2
0x180004387  mov     [rsp+68h+var_40], r12
0x18000438c  dec     esi
0x18000438e  lea     r12, ?ht@CHuffmanTable@@0QBUhuffmantab@1@B; CHuffmanTable::huffmantab const near * const CHuffmanTable::ht
0x180004395  mov     r10d, [rbx+24h]
0x180004399  mov     eax, r10d
0x18000439c  sar     eax, 3
0x18000439f  mov     edx, r10d
0x1800043a2  and     eax, 0FFFFFFFEh
0x1800043a5  and     edx, 0Fh
0x1800043a8  mov     r8d, eax
0x1800043ab  mov     ecx, edx
0x1800043ad  movzx   r9d, byte ptr [rax+rdi]
0x1800043b2  inc     eax
0x1800043b4  shl     r9w, 8
0x1800043b9  movzx   eax, byte ptr [rax+rdi]
0x1800043bd  or      r9w, ax
0x1800043c1  shl     r9w, cl
0x1800043c5  mov     ecx, 10h
0x1800043ca  sub     ecx, edx
0x1800043cc  cmp     ecx, 2
0x1800043cf  jb      loc_1800046B4
0x1800043d5  mov     edx, [rbx+18h]
0x1800043d8  add     r10d, 2
0x1800043dc  and     r10d, esi
0x1800043df  movzx   ecx, r9w
0x1800043e3  mov     [rbx+24h], r10d
0x1800043e7  add     edx, 0FFFFFFFEh
0x1800043ea  mov     [rbx+18h], edx
0x1800043ed  add     r11d, 2
0x1800043f1  mov     [rbx+20h], r11d
0x1800043f5  mov     rax, [r14+28h]
0x1800043f9  shr     rcx, 0Eh
0x1800043fd  mov     eax, [rax+8]
0x180004400  add     rax, rax
0x180004403  lea     rcx, [rcx+rbp*4]
0x180004407  lea     r9, ds:0[rcx*4]
0x18000440f  mov     rax, [r12+rax*8+8]
0x180004414  mov     ecx, [r9+rax]
0x180004418  mov     eax, ecx
0x18000441a  shr     eax, 8
0x18000441d  test    ecx, 0FF00h
0x180004423  jnz     short loc_18000442D
0x180004425  movzx   ebp, cl
0x180004428  jmp     loc_180004395
0x18000442d  movzx   ecx, al
0x180004430  sub     ecx, r11d
0x180004433  add     ecx, r15d
0x180004436  sub     edx, ecx
0x180004438  mov     [rbx+18h], edx
0x18000443b  lea     eax, [rcx+r11]
0x18000443f  mov     [rbx+20h], eax
0x180004442  lea     eax, [rcx+r10]
0x180004446  and     eax, esi
0x180004448  mov     [rbx+24h], eax
0x18000444b  mov     rax, [r14+28h]
0x18000444f  mov     eax, [rax+8]
0x180004452  add     rax, rax
0x180004455  mov     rax, [r12+rax*8+8]
0x18000445a  mov     r9d, [rax+r9]
0x18000445e  movzx   r9d, r9b
0x180004462  mov     r10d, r9d
0x180004465  mov     [r14+20h], r9d
0x180004469  shr     r10d, 4
0x18000446d  and     r9d, 0Fh
0x180004471  cmp     r10d, 0Fh
0x180004475  jnz     short loc_1800044E8
0x180004477  mov     edi, [rbx+24h]
0x18000447a  mov     eax, edi
0x18000447c  mov     rsi, [rbx+30h]
0x180004480  mov     edx, edi
0x180004482  mov     r11d, [r14+48h]
0x180004486  and     edx, r10d
0x180004489  sar     eax, 3
0x18000448c  mov     ecx, edx
0x18000448e  and     eax, 0FFFFFFFEh
0x180004491  mov     r8d, eax
0x180004494  movzx   r10d, byte ptr [rax+rsi]
0x180004499  inc     eax
0x18000449b  shl     r10w, 8
0x1800044a0  movzx   eax, byte ptr [rax+rsi]
0x1800044a4  or      r10w, ax
0x1800044a8  shl     r10w, cl
0x1800044ac  mov     ecx, 10h
0x1800044b1  sub     ecx, edx
0x1800044b3  cmp     r11d, ecx
0x1800044b6  ja      loc_180004746
0x1800044bc  mov     eax, [rbx+14h]
0x1800044bf  lea     ecx, [rdi+r11]
0x1800044c3  add     [rbx+20h], r11d
0x1800044c7  dec     eax
0x1800044c9  sub     [rbx+18h], r11d
0x1800044cd  and     ecx, eax
0x1800044cf  mov     [rbx+24h], ecx
0x1800044d2  mov     ecx, 10h
0x1800044d7  movzx   eax, r10w
0x1800044db  sub     ecx, r11d
0x1800044de  shr     eax, cl
0x1800044e0  mov     [r14+4Ch], eax
0x1800044e4  lea     r10d, [rax+0Fh]
0x1800044e8  mov     r12, [rsp+68h+var_40]
0x1800044ed  test    r10d, r10d
0x1800044f0  jz      short loc_180004562
0x1800044f2  mov     esi, [rbx+24h]
0x1800044f5  mov     eax, esi
0x1800044f7  mov     rbp, [rbx+30h]
0x1800044fb  mov     edx, esi
0x1800044fd  mov     edi, [r14+38h]
0x180004501  and     edx, 0Fh
0x180004504  sar     eax, 3
0x180004507  mov     ecx, edx
0x180004509  and     eax, 0FFFFFFFEh
0x18000450c  mov     r8d, eax
0x18000450f  movzx   r11d, byte ptr [rax+rbp]
0x180004514  inc     eax
0x180004516  shl     r11w, 8
0x18000451b  movzx   eax, byte ptr [rax+rbp]
0x18000451f  or      r11w, ax
0x180004523  shl     r11w, cl
0x180004527  mov     ecx, 10h
0x18000452c  sub     ecx, edx
0x18000452e  cmp     edi, ecx
0x180004530  ja      loc_1800046EA
0x180004536  mov     eax, [rbx+14h]
0x180004539  lea     ecx, [rsi+rdi]
0x18000453c  add     [rbx+20h], edi
0x18000453f  dec     eax
0x180004541  sub     [rbx+18h], edi
0x180004544  and     ecx, eax
0x180004546  mov     [rbx+24h], ecx
0x180004549  mov     ecx, 10h
0x18000454e  sub     ecx, edi
0x180004550  movzx   eax, r11w
0x180004554  shr     eax, cl
0x180004556  mov     [r14+3Ch], eax
0x18000455a  cmp     eax, 1
0x18000455d  jnz     short loc_180004562
0x18000455f  neg     r10d
0x180004562  cmp     r9d, 0Fh
0x180004566  jnz     short loc_1800045D9
0x180004568  mov     edi, [rbx+24h]
0x18000456b  mov     eax, edi
0x18000456d  mov     rsi, [rbx+30h]
0x180004571  mov     edx, edi
0x180004573  mov     r11d, [r14+48h]
0x180004577  and     edx, r9d
0x18000457a  sar     eax, 3
0x18000457d  mov     ecx, edx
0x18000457f  and     eax, 0FFFFFFFEh
0x180004582  mov     r8d, eax
0x180004585  movzx   r9d, byte ptr [rax+rsi]
0x18000458a  inc     eax
0x18000458c  shl     r9w, 8
0x180004591  movzx   eax, byte ptr [rax+rsi]
0x180004595  or      r9w, ax
0x180004599  shl     r9w, cl
0x18000459d  mov     ecx, 10h
0x1800045a2  sub     ecx, edx
0x1800045a4  cmp     r11d, ecx
0x1800045a7  ja      loc_180004774
0x1800045ad  mov     eax, [rbx+14h]
0x1800045b0  lea     ecx, [rdi+r11]
0x1800045b4  add     [rbx+20h], r11d
0x1800045b8  dec     eax
0x1800045ba  sub     [rbx+18h], r11d
0x1800045be  and     ecx, eax
0x1800045c0  mov     [rbx+24h], ecx
0x1800045c3  mov     ecx, 10h
0x1800045c8  movzx   eax, r9w
0x1800045cc  sub     ecx, r11d
0x1800045cf  shr     eax, cl
0x1800045d1  mov     [r14+4Ch], eax
0x1800045d5  lea     r9d, [rax+0Fh]
0x1800045d9  test    r9d, r9d
0x1800045dc  jz      short loc_18000464F
0x1800045de  mov     esi, [rbx+24h]
0x1800045e1  mov     eax, esi
0x1800045e3  mov     rbp, [rbx+30h]
0x1800045e7  mov     edx, esi
0x1800045e9  mov     edi, [r14+38h]
0x1800045ed  and     edx, 0Fh
0x1800045f0  sar     eax, 3
0x1800045f3  mov     ecx, edx
0x1800045f5  and     eax, 0FFFFFFFEh
0x1800045f8  mov     r8d, eax
0x1800045fb  movzx   r11d, byte ptr [rax+rbp]
0x180004600  inc     eax
0x180004602  shl     r11w, 8
0x180004607  movzx   eax, byte ptr [rax+rbp]
0x18000460b  or      r11w, ax
0x18000460f  shl     r11w, cl
0x180004613  mov     ecx, 10h
0x180004618  sub     ecx, edx
0x18000461a  cmp     edi, ecx
0x18000461c  ja      loc_180004718
0x180004622  mov     eax, [rbx+14h]
0x180004625  lea     ecx, [rdi+rsi]
0x180004628  add     [rbx+20h], edi
0x18000462b  dec     eax
0x18000462d  sub     [rbx+18h], edi
0x180004630  and     ecx, eax
0x180004632  mov     [rbx+24h], ecx
0x180004635  mov     ecx, 10h
0x18000463a  sub     ecx, edi
0x18000463c  movzx   eax, r11w
0x180004640  shr     eax, cl
0x180004642  mov     [r14+3Ch], eax
0x180004646  cmp     eax, 1
0x180004649  jz      loc_1800046E2
0x18000464f  mov     r11, [rsp+68h+arg_10]
0x180004657  add     r13d, 2
0x18000465b  mov     rdi, [rsp+68h+var_48]
0x180004660  mov     rcx, [rsp+68h+arg_20]
0x180004668  mov     [r12+r11], r10d
0x18000466c  mov     [r12+r11+4], r9d
0x180004671  cmp     r13d, [rcx+rdi*4]
0x180004675  jl      loc_180004370
0x18000467b  lea     rsi, ?ht@CHuffmanTable@@0QBUhuffmantab@1@B; CHuffmanTable::huffmantab const near * const CHuffmanTable::ht
0x180004682  mov     rax, [rsp+68h+arg_18]
0x18000468a  inc     rdi
0x18000468d  mov     [rsp+68h+var_48], rdi
0x180004692  cmp     rdi, 3
0x180004696  jnz     loc_18000432B
0x18000469c  mov     eax, [rcx+8]
0x18000469f  mov     rbx, [rsp+68h+arg_0]
0x1800046a4  add     rsp, 30h
0x1800046a8  pop     r15
0x1800046aa  pop     r14
0x1800046ac  pop     r13
0x1800046ae  pop     r12
0x1800046b0  pop     rdi
0x1800046b1  pop     rsi
0x1800046b2  pop     rbp
0x1800046b3  retn
0x1800046b4  mov     eax, [rbx+10h]
0x1800046b7  lea     edx, [r8+2]
0x1800046bb  dec     eax
0x1800046bd  and     edx, eax
0x1800046bf  mov     eax, edx
0x1800046c1  movzx   r8d, byte ptr [rdx+rdi]
0x1800046c6  shl     r8w, 8
0x1800046cb  inc     eax
0x1800046cd  movzx   eax, byte ptr [rax+rdi]
0x1800046d1  or      r8w, ax
0x1800046d5  shr     r8w, cl
0x1800046d9  or      r9w, r8w
0x1800046dd  jmp     loc_1800043D5
0x1800046e2  neg     r9d
0x1800046e5  jmp     loc_18000464F
0x1800046ea  mov     edx, [rbx+10h]
0x1800046ed  lea     eax, [r8+2]
0x1800046f1  dec     edx
0x1800046f3  and     edx, eax
0x1800046f5  mov     eax, edx
0x1800046f7  movzx   r8d, byte ptr [rdx+rbp]
0x1800046fc  shl     r8w, 8
0x180004701  inc     eax
0x180004703  movzx   eax, byte ptr [rax+rbp]
0x180004707  or      r8w, ax
0x18000470b  shr     r8w, cl
  ... truncated ...
```
