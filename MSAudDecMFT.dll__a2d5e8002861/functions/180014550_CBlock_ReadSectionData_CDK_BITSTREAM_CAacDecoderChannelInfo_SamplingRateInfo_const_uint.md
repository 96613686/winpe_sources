# CBlock_ReadSectionData(CDK_BITSTREAM *,CAacDecoderChannelInfo *,SamplingRateInfo const *,uint)

- ea: `0x180014550`
- end: `0x180014ada`
- name: `?CBlock_ReadSectionData@@YA?AW4AAC_DECODER_ERROR@@PEAUCDK_BITSTREAM@@PEAUCAacDecoderChannelInfo@@PEBUSamplingRateInfo@@I@Z`
- size: `1418`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014ae0`

## callees

- `0x1800140b0`
- `0x180014550`
- `0x18004dd14`

## pseudocode

```c
__int64 __fastcall CBlock_ReadSectionData(__int64 a1, __int64 a2, __int64 *a3, char a4)
{
  _BYTE *v5; // rax
  char v6; // si
  __int64 v7; // rbp
  __int64 *v8; // rcx
  unsigned int v9; // eax
  __int64 v10; // r13
  unsigned __int8 v11; // cl
  int v12; // r15d
  int v13; // r14d
  int v15; // eax
  int v16; // ebx
  int v17; // r9d
  int *v18; // rsi
  int v19; // r11d
  int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // edx
  __int64 v23; // rbp
  char v24; // r10
  __int64 v25; // r8
  __int64 v26; // r14
  __int64 v27; // r15
  __int64 v28; // r12
  unsigned int v29; // eax
  int v30; // r12d
  unsigned __int8 v31; // r12
  int v32; // ecx
  int v33; // eax
  int v34; // r9d
  unsigned int v35; // ecx
  unsigned int v36; // edx
  __int64 v37; // r11
  char v38; // r10
  __int64 v39; // r8
  __int64 v40; // rbp
  __int64 v41; // r14
  __int64 v42; // r15
  unsigned int v43; // eax
  int v44; // ecx
  int v45; // eax
  int v46; // eax
  int v47; // esi
  int v48; // r9d
  int v49; // r8d
  bool v50; // cc
  int v51; // ecx
  int v52; // r13d
  unsigned __int8 v53; // al
  unsigned __int8 v54; // [rsp+20h] [rbp-78h]
  int v55; // [rsp+28h] [rbp-70h]
  int v56; // [rsp+2Ch] [rbp-6Ch]
  int v57; // [rsp+30h] [rbp-68h]
  int v58; // [rsp+34h] [rbp-64h]
  __int64 v59; // [rsp+38h] [rbp-60h]
  unsigned __int8 *v60; // [rsp+40h] [rbp-58h]
  __int64 v61; // [rsp+48h] [rbp-50h]
  _BYTE *v62; // [rsp+50h] [rbp-48h]
  _BYTE *v63; // [rsp+58h] [rbp-40h]

  v5 = *(_BYTE **)(a2 + 1704);
  v6 = a4;
  v7 = a2;
  v57 = 0;
  v62 = v5 + 1394;
  v63 = v5 + 512;
  v60 = v5 + 1906;
  v8 = a3;
  if ( *(_DWORD *)(a2 + 1684) == 2 )
    v8 = a3 + 1;
  v61 = *v8;
  v5[2165] = 0;
  memset_0(v5 + 512, 0, 0x80u);
  v9 = 3;
  if ( *(_DWORD *)(v7 + 1684) != 2 )
    v9 = 5;
  v10 = v9;
  v11 = *(_BYTE *)(v7 + 1688);
  v12 = (1 << v9) - 1;
  v56 = v12;
  v13 = 0;
  v59 = v9;
  v54 = v11;
LABEL_6:
  v55 = v13;
  if ( v13 >= *(unsigned __int8 *)(v7 + 1680) )
    return 0;
  v15 = v11;
  v16 = 0;
  v58 = v11;
  while ( 1 )
  {
    if ( v16 >= v15 )
    {
      v11 = v54;
      ++v13;
      goto LABEL_6;
    }
    if ( (v6 & 1) != 0 )
    {
      v53 = CDKreadBits_0(a1);
      v18 = (int *)(a1 + 4);
      v31 = v53;
      if ( v53 >= 0xBu && (unsigned __int8)(v53 - 12) > 3u )
      {
        v46 = 1;
        goto LABEL_28;
      }
    }
    else
    {
      v17 = *(_DWORD *)(a1 + 4);
      v18 = (int *)(a1 + 4);
      LOBYTE(v19) = 0;
      v20 = 4 - v17;
      if ( 4 - v17 > 0 )
      {
        if ( v20 != 32 )
          v19 = *(_DWORD *)a1 << v20;
        v21 = *(_DWORD *)(a1 + 36);
        v22 = *(_DWORD *)(a1 + 20) + 32;
        *(_DWORD *)(a1 + 8) -= 32;
        v23 = *(_QWORD *)(a1 + 24);
        v24 = v22 & 7;
        v25 = (v22 - 1) >> 3;
        *(_DWORD *)(a1 + 20) = v22 & (v21 - 1);
        v26 = (unsigned int)(v25 - 3);
        v27 = (unsigned int)(v25 - 2);
        v28 = (unsigned int)(v25 - 1);
        if ( v22 > v21 )
        {
          if ( (v22 & 7) != 0 )
            v29 = ((unsigned int)(*(unsigned __int8 *)(((unsigned int)v25 & (*(_DWORD *)(a1 + 32) - 1)) + v23)
                                | ((*(unsigned __int8 *)(((unsigned int)v28 & (*(_DWORD *)(a1 + 32) - 1)) + v23)
                                  | ((*(unsigned __int8 *)(((unsigned int)v27 & (*(_DWORD *)(a1 + 32) - 1)) + v23)
                                    | (*(unsigned __int8 *)(((unsigned int)v26 & (*(_DWORD *)(a1 + 32) - 1)) + v23) << 8)) << 8)) << 8)) >> (8 - v24))
                | (*(unsigned __int8 *)(((*(_DWORD *)(a1 + 32) - 1) & (unsigned int)(v25 - 4)) + v23) << (v24 + 24));
          else
            v29 = *(unsigned __int8 *)(((unsigned int)v25 & (*(_DWORD *)(a1 + 32) - 1)) + v23)
                | ((*(unsigned __int8 *)(((unsigned int)v28 & (*(_DWORD *)(a1 + 32) - 1)) + v23)
                  | ((*(unsigned __int8 *)(((unsigned int)v27 & (*(_DWORD *)(a1 + 32) - 1)) + v23)
                    | (*(unsigned __int8 *)(((unsigned int)v26 & (*(_DWORD *)(a1 + 32) - 1)) + v23) << 8)) << 8)) << 8);
          v10 = v59;
        }
        else if ( (v22 & 7) != 0 )
        {
          v29 = ((unsigned int)(*(unsigned __int8 *)(v25 + v23)
                              | ((*(unsigned __int8 *)(v28 + v23)
                                | ((*(unsigned __int8 *)(v27 + v23) | (*(unsigned __int8 *)(v26 + v23) << 8)) << 8)) << 8)) >> (8 - v24))
              | (*(unsigned __int8 *)((unsigned int)(v25 - 4) + v23) << (v24 + 24));
        }
        else
        {
          v29 = *(unsigned __int8 *)(v25 + v23)
              | ((*(unsigned __int8 *)(v28 + v23)
                | ((*(unsigned __int8 *)(v27 + v23) | (*(unsigned __int8 *)(v26 + v23) << 8)) << 8)) << 8);
        }
        v12 = v56;
        v17 += 32;
        *(_DWORD *)a1 = v29;
      }
      v30 = *(_DWORD *)a1 >> (v17 - 4);
      *v18 = v17 - 4;
      v31 = (v19 | v30) & 0xF;
    }
    v32 = *v18;
    v33 = v10 - *v18;
    v34 = 0;
    if ( v33 > 0 )
    {
      if ( v33 != 32 )
        v34 = *(_DWORD *)a1 << v33;
      v35 = *(_DWORD *)(a1 + 36);
      v36 = *(_DWORD *)(a1 + 20) + 32;
      *(_DWORD *)(a1 + 8) -= 32;
      v37 = *(_QWORD *)(a1 + 24);
      v38 = v36 & 7;
      v39 = (v36 - 1) >> 3;
      *(_DWORD *)(a1 + 20) = v36 & (v35 - 1);
      v40 = (unsigned int)(v39 - 3);
      v41 = (unsigned int)(v39 - 2);
      v42 = (unsigned int)(v39 - 1);
      if ( v36 > v35 )
      {
        v52 = *(_DWORD *)(a1 + 32) - 1;
        if ( (v36 & 7) != 0 )
          v43 = ((unsigned int)(*(unsigned __int8 *)(((unsigned int)v39 & (*(_DWORD *)(a1 + 32) - 1)) + v37)
                              | ((*(unsigned __int8 *)(((*(_DWORD *)(a1 + 32) - 1) & (unsigned int)v42) + v37)
                                | ((*(unsigned __int8 *)(((*(_DWORD *)(a1 + 32) - 1) & (unsigned int)v41) + v37)
                                  | (*(unsigned __int8 *)((v52 & (unsigned int)v40) + v37) << 8)) << 8)) << 8)) >> (8 - v38))
              | (*(unsigned __int8 *)((v52 & (unsigned int)(v39 - 4)) + v37) << (v38 + 24));
        else
          v43 = *(unsigned __int8 *)(((unsigned int)v39 & (*(_DWORD *)(a1 + 32) - 1)) + v37)
              | ((*(unsigned __int8 *)(((*(_DWORD *)(a1 + 32) - 1) & (unsigned int)v42) + v37)
                | ((*(unsigned __int8 *)(((*(_DWORD *)(a1 + 32) - 1) & (unsigned int)v41) + v37)
                  | (*(unsigned __int8 *)((v52 & (unsigned int)v40) + v37) << 8)) << 8)) << 8);
        v10 = v59;
      }
      else if ( (v36 & 7) != 0 )
      {
        v43 = ((unsigned int)(*(unsigned __int8 *)(v39 + v37)
                            | ((*(unsigned __int8 *)(v42 + v37)
                              | ((*(unsigned __int8 *)(v41 + v37) | (*(unsigned __int8 *)(v40 + v37) << 8)) << 8)) << 8)) >> (8 - v38))
            | (*(unsigned __int8 *)((unsigned int)(v39 - 4) + v37) << (v38 + 24));
      }
      else
      {
        v43 = *(unsigned __int8 *)(v39 + v37)
            | ((*(unsigned __int8 *)(v42 + v37)
              | ((*(unsigned __int8 *)(v41 + v37) | (*(unsigned __int8 *)(v40 + v37) << 8)) << 8)) << 8);
      }
      v12 = v56;
      v32 = *v18 + 32;
      *(_DWORD *)a1 = v43;
    }
    v44 = v32 - v10;
    v45 = v34 | (*(_DWORD *)a1 >> v44);
    *v18 = v44;
    v46 = BitMask[v10] & v45;
    if ( v46 != v12 )
    {
      v7 = a2;
      v13 = v55;
LABEL_28:
      v47 = 0;
      goto LABEL_29;
    }
    v47 = 0;
    do
    {
      v47 += v12;
      v46 = CDKreadBits_0(a1);
    }
    while ( v46 == v12 );
    v7 = a2;
    v13 = v55;
LABEL_29:
    v48 = v46 + v47;
    v6 = a4;
    v49 = v48 + v16;
    if ( (a4 & 4) == 0 )
      goto LABEL_30;
    if ( v57 >= 256 || v49 > *((unsigned __int8 *)a3 + (*(_DWORD *)(v7 + 1684) == 2) + 16) )
      return 16386;
    *(_WORD *)&v62[2 * v57] = *(_WORD *)(v61 + 2LL * v49) - *(_WORD *)(v61 + 2LL * v16);
    if ( v31 == 12 )
      return 16390;
    ++v57;
    *v60++ = v31;
    ++*(_BYTE *)(*(_QWORD *)(v7 + 1704) + 2165LL);
LABEL_30:
    if ( *(_DWORD *)(v7 + 1684) == 2 )
      v50 = v49 + 16 * v13 <= 128;
    else
      v50 = v49 <= 64;
    if ( !v50 )
      return 16388;
    if ( v31 == 12 || (unsigned __int8)(v31 - 14) <= 1u && !*(_BYTE *)(*(_QWORD *)(v7 + 1704) + 1379LL) )
      return 16390;
    v15 = v58;
    if ( v16 < v49 )
    {
      v51 = v16;
      do
        ++v16;
      while ( v16 < v49 );
      memset_0(&v63[16 * v13 + v51], v31, v48);
      v15 = v58;
    }
  }
}

```

## disassembly

```asm
0x180014550  mov     [rsp+arg_0], rbx
0x180014555  mov     [rsp+arg_18], r9d
0x18001455a  mov     [rsp+arg_10], r8
0x18001455f  mov     [rsp+arg_8], rdx
0x180014564  push    rbp
0x180014565  push    rsi
0x180014566  push    rdi
0x180014567  push    r12
0x180014569  push    r13
0x18001456b  push    r14
0x18001456d  push    r15
0x18001456f  sub     rsp, 60h
0x180014573  cmp     dword ptr [rdx+694h], 2
0x18001457a  mov     rdi, rcx
0x18001457d  mov     rax, [rdx+6A8h]
0x180014584  mov     esi, r9d
0x180014587  mov     rbp, rdx
0x18001458a  mov     [rsp+98h+var_68], 0
0x180014592  lea     rcx, [rax+572h]
0x180014599  mov     [rsp+98h+var_48], rcx
0x18001459e  lea     r9, [rax+200h]
0x1800145a5  lea     rcx, [rax+772h]
0x1800145ac  mov     [rsp+98h+var_40], r9
0x1800145b1  mov     [rsp+98h+var_58], rcx
0x1800145b6  mov     rcx, r8
0x1800145b9  jnz     short loc_1800145BF
0x1800145bb  lea     rcx, [r8+8]
0x1800145bf  mov     rcx, [rcx]
0x1800145c2  xor     edx, edx; Val
0x1800145c4  mov     [rsp+98h+var_50], rcx
0x1800145c9  mov     r8d, 80h; Size
0x1800145cf  mov     rcx, r9; void *
0x1800145d2  mov     byte ptr [rax+875h], 0
0x1800145d9  call    memset_0
0x1800145de  cmp     dword ptr [rbp+694h], 2
0x1800145e5  mov     eax, 3
0x1800145ea  mov     edx, 5
0x1800145ef  mov     r15d, 1
0x1800145f5  cmovnz  eax, edx
0x1800145f8  mov     ecx, eax
0x1800145fa  mov     r13d, eax
0x1800145fd  shl     r15d, cl
0x180014600  movzx   ecx, byte ptr [rbp+698h]
0x180014607  dec     r15d
0x18001460a  mov     [rsp+98h+var_6C], r15d
0x18001460f  xor     r14d, r14d
0x180014612  mov     [rsp+98h+var_60], r13
0x180014617  mov     [rsp+98h+var_78], cl
0x18001461b  movzx   eax, byte ptr [rbp+690h]
0x180014622  mov     [rsp+98h+var_70], r14d
0x180014627  cmp     r14d, eax
0x18001462a  jl      short loc_180014647
0x18001462c  xor     eax, eax
0x18001462e  mov     rbx, [rsp+98h+arg_0]
0x180014636  add     rsp, 60h
0x18001463a  pop     r15
0x18001463c  pop     r14
0x18001463e  pop     r13
0x180014640  pop     r12
0x180014642  pop     rdi
0x180014643  pop     rsi
0x180014644  pop     rbp
0x180014645  retn
0x180014647  movzx   eax, cl
0x18001464a  xor     ebx, ebx
0x18001464c  mov     [rsp+98h+var_64], eax
0x180014650  cmp     ebx, eax
0x180014652  jge     loc_1800148A8
0x180014658  mov     [rsp+98h+var_74], 0
0x180014660  test    sil, 1
0x180014664  jnz     loc_1800149FA
0x18001466a  mov     r9d, [rdi+4]
0x18001466e  lea     rsi, [rdi+4]
0x180014672  mov     ecx, 4
0x180014677  xor     r11d, r11d
0x18001467a  sub     ecx, r9d
0x18001467d  test    ecx, ecx
0x18001467f  jle     loc_18001471D
0x180014685  cmp     ecx, 20h ; ' '
0x180014688  jz      short loc_180014690
0x18001468a  mov     r11d, [rdi]
0x18001468d  shl     r11d, cl
0x180014690  mov     edx, [rdi+14h]
0x180014693  mov     ecx, [rdi+24h]
0x180014696  add     edx, 20h ; ' '
0x180014699  add     dword ptr [rdi+8], 0FFFFFFE0h
0x18001469d  mov     r10d, edx
0x1800146a0  mov     rbp, [rdi+18h]
0x1800146a4  and     r10d, 7
0x1800146a8  lea     r8d, [rdx-1]
0x1800146ac  shr     r8d, 3
0x1800146b0  lea     eax, [rcx-1]
0x1800146b3  and     eax, edx
0x1800146b5  mov     [rdi+14h], eax
0x1800146b8  lea     r14d, [r8-3]
0x1800146bc  lea     r15d, [r8-2]
0x1800146c0  lea     r12d, [r8-1]
0x1800146c4  cmp     edx, ecx
0x1800146c6  ja      loc_18001497D
0x1800146cc  movzx   ecx, byte ptr [r15+rbp]
0x1800146d1  movzx   edx, byte ptr [r14+rbp]
0x1800146d6  shl     edx, 8
0x1800146d9  or      edx, ecx
0x1800146db  movzx   ecx, byte ptr [r12+rbp]
0x1800146e0  shl     edx, 8
0x1800146e3  or      edx, ecx
0x1800146e5  movzx   ecx, byte ptr [r8+rbp]
0x1800146ea  shl     edx, 8
0x1800146ed  or      edx, ecx
0x1800146ef  test    r10d, r10d
0x1800146f2  jz      loc_180014AB1
0x1800146f8  lea     ecx, [r10+18h]
0x1800146fc  lea     eax, [r8-4]
0x180014700  movzx   eax, byte ptr [rax+rbp]
0x180014704  shl     eax, cl
0x180014706  mov     ecx, 8
0x18001470b  sub     ecx, r10d
0x18001470e  shr     edx, cl
0x180014710  or      eax, edx
0x180014712  mov     r15d, [rsp+98h+var_6C]
0x180014717  add     r9d, 20h ; ' '
0x18001471b  mov     [rdi], eax
0x18001471d  mov     r12d, [rdi]
0x180014720  lea     ecx, [r9-4]
0x180014724  shr     r12d, cl
0x180014727  or      r12b, r11b
0x18001472a  mov     [rsi], ecx
0x18001472c  and     r12b, 0Fh
0x180014730  mov     ecx, [rsi]
0x180014732  mov     eax, r13d
0x180014735  sub     eax, ecx
0x180014737  xor     r9d, r9d
0x18001473a  test    eax, eax
0x18001473c  jle     loc_1800147DF
0x180014742  cmp     eax, 20h ; ' '
0x180014745  jz      short loc_18001474F
0x180014747  mov     r9d, [rdi]
0x18001474a  mov     ecx, eax
0x18001474c  shl     r9d, cl
0x18001474f  mov     edx, [rdi+14h]
0x180014752  mov     ecx, [rdi+24h]
0x180014755  add     edx, 20h ; ' '
0x180014758  add     dword ptr [rdi+8], 0FFFFFFE0h
0x18001475c  mov     r10d, edx
0x18001475f  mov     r11, [rdi+18h]
0x180014763  and     r10d, 7
0x180014767  lea     r8d, [rdx-1]
0x18001476b  shr     r8d, 3
0x18001476f  lea     eax, [rcx-1]
0x180014772  and     eax, edx
0x180014774  mov     [rdi+14h], eax
0x180014777  lea     ebp, [r8-3]
0x18001477b  lea     r14d, [r8-2]
0x18001477f  lea     r15d, [r8-1]
0x180014783  cmp     edx, ecx
0x180014785  ja      loc_1800148FC
0x18001478b  movzx   ecx, byte ptr [r14+r11]
0x180014790  movzx   edx, byte ptr [rbp+r11+0]
0x180014796  shl     edx, 8
0x180014799  or      edx, ecx
0x18001479b  movzx   ecx, byte ptr [r15+r11]
0x1800147a0  shl     edx, 8
0x1800147a3  or      edx, ecx
0x1800147a5  movzx   ecx, byte ptr [r8+r11]
0x1800147aa  shl     edx, 8
0x1800147ad  or      edx, ecx
0x1800147af  test    r10d, r10d
0x1800147b2  jz      loc_180014AAA
0x1800147b8  lea     ecx, [r10+18h]
0x1800147bc  lea     eax, [r8-4]
0x1800147c0  movzx   eax, byte ptr [rax+r11]
0x1800147c5  shl     eax, cl
0x1800147c7  mov     ecx, 8
0x1800147cc  sub     ecx, r10d
0x1800147cf  shr     edx, cl
0x1800147d1  or      eax, edx
0x1800147d3  mov     ecx, [rsi]
0x1800147d5  mov     r15d, [rsp+98h+var_6C]
0x1800147da  add     ecx, 20h ; ' '
0x1800147dd  mov     [rdi], eax
0x1800147df  mov     eax, [rdi]
0x1800147e1  sub     ecx, r13d
0x1800147e4  shr     eax, cl
0x1800147e6  or      eax, r9d
0x1800147e9  mov     [rsi], ecx
0x1800147eb  lea     rcx, BitMask
0x1800147f2  and     eax, [rcx+r13*4]
0x1800147f6  cmp     eax, r15d
0x1800147f9  jz      loc_1800148B5
0x1800147ff  mov     rbp, [rsp+98h+arg_8]
0x180014807  mov     r14d, [rsp+98h+var_70]
0x18001480c  mov     esi, [rsp+98h+var_74]
0x180014810  lea     r9d, [rax+rsi]
0x180014814  mov     esi, [rsp+98h+arg_18]
0x18001481b  lea     r8d, [r9+rbx]
0x18001481f  test    sil, 4
0x180014823  jnz     loc_180014A27
0x180014829  cmp     dword ptr [rbp+694h], 2
0x180014830  jz      short loc_180014898
0x180014832  cmp     r8d, 40h ; '@'
0x180014836  jg      loc_180014AB8
0x18001483c  cmp     r12b, 0Ch
0x180014840  jz      loc_1800148F2
0x180014846  lea     eax, [r12-0Eh]
0x18001484b  cmp     al, 1
0x18001484d  jbe     loc_1800148DE
0x180014853  mov     eax, [rsp+98h+var_64]
0x180014857  mov     edx, 5
0x18001485c  cmp     ebx, r8d
0x18001485f  jge     loc_180014650
0x180014865  mov     ecx, ebx
0x180014867  inc     ebx
0x180014869  cmp     ebx, r8d
0x18001486c  jl      short loc_180014867
0x18001486e  mov     eax, r14d
0x180014871  movsxd  r8, r9d; Size
0x180014874  shl     eax, 4
0x180014877  movzx   edx, r12b; Val
0x18001487b  add     eax, ecx
0x18001487d  movsxd  rcx, eax
0x180014880  add     rcx, [rsp+98h+var_40]; void *
0x180014885  call    memset_0
0x18001488a  mov     eax, [rsp+98h+var_64]
0x18001488e  mov     edx, 5
0x180014893  jmp     loc_180014650
0x180014898  mov     eax, r14d
0x18001489b  shl     eax, 4
0x18001489e  add     eax, r8d
0x1800148a1  cmp     eax, 80h
0x1800148a6  jmp     short loc_180014836
0x1800148a8  movzx   ecx, [rsp+98h+var_78]
0x1800148ad  inc     r14d
0x1800148b0  jmp     loc_18001461B
0x1800148b5  mov     esi, [rsp+98h+var_74]
0x1800148b9  mov     edx, r13d
0x1800148bc  mov     rcx, rdi
0x1800148bf  add     esi, r15d
0x1800148c2  call    CDKreadBits_0
0x1800148c7  cmp     eax, r15d
0x1800148ca  jz      short loc_1800148B9
0x1800148cc  mov     rbp, [rsp+98h+arg_8]
0x1800148d4  mov     r14d, [rsp+98h+var_70]
0x1800148d9  jmp     loc_180014810
0x1800148de  mov     rax, [rbp+6A8h]
0x1800148e5  cmp     byte ptr [rax+563h], 0
0x1800148ec  jnz     loc_180014853
0x1800148f2  mov     eax, 4006h
0x1800148f7  jmp     loc_18001462E
0x1800148fc  mov     r13d, [rdi+20h]
0x180014900  dec     r13d
0x180014903  mov     ecx, ebp
0x180014905  mov     eax, r13d
0x180014908  and     rcx, rax
0x18001490b  mov     eax, r13d
0x18001490e  movzx   edx, byte ptr [rcx+r11]
0x180014913  shl     edx, 8
0x180014916  mov     ecx, r14d
0x180014919  and     rcx, rax
0x18001491c  movzx   eax, byte ptr [rcx+r11]
0x180014921  or      edx, eax
0x180014923  mov     ecx, r15d
0x180014926  shl     edx, 8
0x180014929  mov     eax, r13d
0x18001492c  and     rcx, rax
0x18001492f  movzx   eax, byte ptr [rcx+r11]
0x180014934  or      edx, eax
0x180014936  mov     ecx, r13d
0x180014939  mov     eax, r8d
0x18001493c  and     rcx, rax
0x18001493f  shl     edx, 8
0x180014942  movzx   eax, byte ptr [rcx+r11]
0x180014947  or      edx, eax
0x180014949  test    r10d, r10d
0x18001494c  jz      loc_180014AC9
0x180014952  mov     eax, r13d
0x180014955  lea     ecx, [r8-4]
0x180014959  and     rcx, rax
0x18001495c  movzx   eax, byte ptr [rcx+r11]
0x180014961  lea     ecx, [r10+18h]
0x180014965  shl     eax, cl
0x180014967  mov     ecx, 8
0x18001496c  sub     ecx, r10d
0x18001496f  shr     edx, cl
0x180014971  or      eax, edx
0x180014973  mov     r13, [rsp+98h+var_60]
0x180014978  jmp     loc_1800147D3
0x18001497d  mov     r13d, [rdi+20h]
0x180014981  dec     r13d
0x180014984  mov     eax, r14d
0x180014987  mov     ecx, r13d
0x18001498a  and     rcx, rax
0x18001498d  mov     eax, r15d
0x180014990  movzx   edx, byte ptr [rcx+rbp]
0x180014994  shl     edx, 8
0x180014997  mov     ecx, r13d
0x18001499a  and     rcx, rax
0x18001499d  movzx   eax, byte ptr [rcx+rbp]
0x1800149a1  or      edx, eax
0x1800149a3  mov     ecx, r13d
0x1800149a6  shl     edx, 8
  ... truncated ...
```
