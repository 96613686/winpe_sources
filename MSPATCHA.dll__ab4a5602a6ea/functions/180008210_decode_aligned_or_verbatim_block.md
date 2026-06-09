# decode_aligned_or_verbatim_block

- ea: `0x180008210`
- end: `0x1800087a9`
- name: `decode_aligned_or_verbatim_block`
- size: `1433`
- prototype: `__int64 __fastcall(__int64, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007c94`

## callees

- `0x180008210`

## pseudocode

```c
__int64 __fastcall decode_aligned_or_verbatim_block(__int64 a1, int a2, int a3, int a4)
{
  unsigned __int64 v4; // rbp
  int v5; // r12d
  int v6; // r14d
  char v7; // r11
  unsigned int v9; // r10d
  unsigned __int8 *v10; // rdi
  __int64 v11; // r13
  int v12; // r15d
  __int64 v13; // r8
  unsigned int v14; // r9d
  __int64 v15; // rdx
  char v16; // cl
  unsigned int v17; // edx
  int v18; // r10d
  int v19; // eax
  int v20; // r8d
  __int64 v21; // rax
  int v22; // r9d
  __int64 v23; // r9
  unsigned int v24; // esi
  __int64 v25; // rdx
  char v26; // cl
  unsigned int v27; // edx
  int v28; // r10d
  int v29; // eax
  __int64 v30; // r8
  __int64 v31; // rsi
  unsigned __int8 v32; // al
  int v33; // eax
  unsigned int v34; // r8d
  unsigned int v35; // edx
  int v36; // r10d
  int v37; // eax
  int v38; // ebp
  __int64 v39; // r8
  char v40; // cl
  unsigned int v41; // edx
  int v42; // r10d
  int v43; // eax
  int v44; // esi
  int v45; // esi
  char v46; // al
  unsigned int v47; // r8d
  int v48; // edx
  char v49; // al
  unsigned int v50; // edx
  int v51; // r10d
  int v52; // eax
  int v53; // ecx
  int v54; // r8d
  unsigned int v55; // edx
  int v56; // edx
  unsigned int v57; // r8d
  int v58; // r10d
  int v59; // eax
  int v60; // r8d
  unsigned int v61; // r8d
  int v62; // edx
  unsigned int v63; // r8d
  unsigned int v64; // r9d
  int v65; // r10d
  int v66; // eax
  unsigned int v67; // edx
  int v68; // r8d
  unsigned int v69; // edx
  unsigned int v70; // r9d
  int v71; // r10d
  int v72; // eax
  int v73; // r8d
  int v74; // r9d
  unsigned int v75; // edx
  int v76; // r10d
  int v77; // eax
  __int64 v78; // rdx
  int v79; // r9d
  char v80; // al
  __int64 v81; // rcx
  char v82; // al
  __int64 v83; // rcx
  __int64 result; // rax
  unsigned __int64 v85; // [rsp+40h] [rbp+8h]
  unsigned int v86; // [rsp+48h] [rbp+10h]

  v4 = *(_QWORD *)(a1 + 16);
  v5 = a2 + a3;
  v6 = a2;
  v7 = *(_BYTE *)(a1 + 4);
  v9 = *(_DWORD *)a1;
  v10 = *(unsigned __int8 **)(a1 + 8);
  v11 = *(_QWORD *)(a1 + 24);
  v12 = *(_DWORD *)(a1 + 36);
  v85 = v4;
  v86 = *(_DWORD *)(a1 + 32);
  if ( a2 >= a2 + a3 )
  {
LABEL_68:
    *(_BYTE *)(a1 + 4) = v7;
    *(_DWORD *)a1 = v9;
    result = (unsigned int)(v6 - v5);
    *(_QWORD *)(a1 + 8) = v10;
    *(_DWORD *)(a1 + 64) = v6 & v12;
    return result;
  }
  while ( 1 )
  {
    v13 = (unsigned int)*(__int16 *)(a1 + 2 * ((unsigned __int64)v9 >> 22) + 124);
    if ( (int)v13 < 0 )
    {
      v14 = 0x200000;
      do
      {
        v15 = -(__int64)((v9 & v14) != 0);
        v14 >>= 1;
        v13 = (unsigned int)*(__int16 *)((v15 & 2) + a1 + 5656 + -4LL * (_DWORD)v13);
      }
      while ( (int)v13 < 0 );
    }
    if ( (unsigned __int64)v10 >= v4 )
      return 0xFFFFFFFFLL;
    v16 = *(_BYTE *)(v13 + a1 + 2684);
    v9 <<= v16;
    v7 -= v16;
    v17 = v9;
    if ( v7 <= 0 )
    {
      v18 = v10[1];
      v19 = *v10;
      v10 += 2;
      v9 = v17 | ((v19 | (v18 << 8)) << -v7);
      v7 += 16;
    }
    v20 = v13 - 256;
    if ( v20 < 0 )
    {
      v21 = v6++;
      *(_BYTE *)(v21 + v11) = v20;
      goto LABEL_67;
    }
    v22 = v20 & 7;
    if ( v22 == 7 )
    {
      v23 = (unsigned int)*(__int16 *)(a1 + 2 * ((unsigned __int64)v9 >> 24) + 2172);
      if ( (int)v23 < 0 )
      {
        v24 = 0x800000;
        do
        {
          v25 = -(__int64)((v9 & v24) != 0);
          v24 >>= 1;
          v23 = (unsigned int)*(__int16 *)((v25 & 2) + a1 + 26328 + -4LL * (_DWORD)v23);
        }
        while ( (int)v23 < 0 );
      }
      v26 = *(_BYTE *)(v23 + a1 + 5268);
      v9 <<= v26;
      v7 -= v26;
      v27 = v9;
      if ( v7 <= 0 )
      {
        v28 = v10[1];
        v29 = *v10;
        v10 += 2;
        v9 = v27 | ((v29 | (v28 << 8)) << -v7);
        v7 += 16;
      }
      v22 = v23 + 7;
    }
    v30 = (unsigned int)(v20 >> 3);
    if ( (unsigned int)v30 > 2 )
    {
      if ( (unsigned int)v30 >= 0x123 )
        return 0xFFFFFFFFLL;
      if ( a4 )
      {
        v31 = (unsigned int)v30;
        v32 = *((_BYTE *)dec_extra_bits + v30);
        _mm_lfence();
        if ( v32 >= 3u )
        {
          v33 = *((unsigned __int8 *)dec_extra_bits + v30);
          if ( v33 == 3 )
          {
            v34 = 0;
          }
          else
          {
            _mm_lfence();
            v34 = v9 >> (35 - v33);
            v7 = v7 - *((_BYTE *)dec_extra_bits + v31) + 3;
            v9 <<= v33 - 3;
            v35 = v9;
            if ( v7 <= 0 )
            {
              v36 = v10[1];
              v37 = *v10;
              v10 += 2;
              v9 = v35 | ((v37 | (v36 << 8)) << -v7);
              v7 += 16;
            }
          }
          if ( (unsigned __int64)v10 >= v4 )
            return 0xFFFFFFFFLL;
          v38 = 8 * v34;
          v39 = (unsigned int)*(char *)(((unsigned __int64)v9 >> 25) + a1 + 5520);
          v40 = *(_BYTE *)(v39 + a1 + 5648);
          v9 <<= v40;
          v7 -= v40;
          v41 = v9;
          if ( v7 <= 0 )
          {
            v42 = v10[1];
            v43 = *v10;
            v10 += 2;
            v9 = v41 | ((v43 | (v42 << 8)) << -v7);
            v7 += 16;
          }
          v44 = v38 + MP_POS_minus2[v31];
          v4 = v85;
          v45 = v39 + v44;
LABEL_40:
          *(_DWORD *)(a1 + 120) = *(_DWORD *)(a1 + 116);
          *(_DWORD *)(a1 + 116) = *(_DWORD *)(a1 + 112);
LABEL_43:
          *(_DWORD *)(a1 + 112) = v45;
          goto LABEL_44;
        }
        if ( !v32 )
        {
          v45 = MP_POS_minus2[v30];
          goto LABEL_40;
        }
        v46 = *((_BYTE *)dec_extra_bits + v30);
        v7 -= v46;
        v47 = v9 >> (32 - v46);
        v9 <<= v46;
        v48 = v9;
        if ( v7 <= 0 )
        {
          v9 = *(unsigned __int16 *)v10 << -v7;
          goto LABEL_37;
        }
      }
      else
      {
        if ( (unsigned int)v30 <= 3 )
        {
          v45 = 1;
          goto LABEL_40;
        }
        _mm_lfence();
        v31 = (unsigned int)v30;
        v49 = *((_BYTE *)dec_extra_bits + v30);
        v47 = v9 >> (32 - v49);
        v7 -= v49;
        v9 <<= v49;
        v50 = v9;
        if ( v7 <= 0 )
        {
          v51 = v10[1];
          v52 = *v10;
          v10 += 2;
          v53 = -v7;
          v7 += 16;
          v9 = v50 | ((v52 | (v51 << 8)) << v53);
          if ( v7 <= 0 )
          {
            v48 = *(unsigned __int16 *)v10 << -v7;
LABEL_37:
            v9 |= v48;
            v10 += 2;
            v7 += 16;
          }
        }
      }
      v45 = v47 + MP_POS_minus2[v31];
      goto LABEL_40;
    }
    _mm_lfence();
    v45 = *(_DWORD *)(a1 + 4 * v30 + 112);
    if ( (_DWORD)v30 )
    {
      *(_DWORD *)(a1 + 4 * v30 + 112) = *(_DWORD *)(a1 + 112);
      goto LABEL_43;
    }
LABEL_44:
    v54 = v22 + 2;
    if ( v22 == 255 )
    {
      v55 = v9;
      v7 -= 9;
      v9 <<= 9;
      v56 = v55 >> 23;
      v57 = v9;
      if ( v7 <= 0 )
      {
        v58 = v10[1];
        v59 = *v10;
        v10 += 2;
        v9 = v57 | ((v59 | (v58 << 8)) << -v7);
        v7 += 16;
      }
      if ( (v56 & 0x100) != 0 )
      {
        if ( (v56 & 0x80u) == 0 )
        {
          v73 = 8 * v9;
          v7 -= 3;
          v74 = 8 * (v56 & 0x7F);
          v75 = v9 >> 29;
          if ( v7 > 0 )
          {
            v9 *= 8;
          }
          else
          {
            v76 = v10[1];
            v77 = *v10;
            v10 += 2;
            v9 = v73 | ((v77 | (v76 << 8)) << -v7);
            v7 += 16;
          }
          v56 = (v74 | v75) + 256;
        }
        else
        {
          v60 = v56 & 0x3F;
          if ( (v56 & 0x40) != 0 )
          {
            v7 -= 9;
            v61 = v9;
            v62 = (v56 & 0x3F) << 9;
            v9 <<= 9;
            v63 = v61 >> 23;
            v64 = v9;
            if ( v7 <= 0 )
            {
              v65 = v10[1];
              v66 = *v10;
              v10 += 2;
              v9 = v64 | ((v66 | (v65 << 8)) << -v7);
              v7 += 16;
            }
            v56 = v63 | v62;
          }
          else
          {
            v67 = v9;
            v68 = v60 << 6;
            v9 <<= 6;
            v7 -= 6;
            v69 = v67 >> 26;
            v70 = v9;
            if ( v7 <= 0 )
            {
              v71 = v10[1];
              v72 = *v10;
              v10 += 2;
              v9 = v70 | ((v72 | (v71 << 8)) << -v7);
              v7 += 16;
            }
            v56 = (v68 | v69) + 1280;
          }
        }
      }
      v54 = v56 + 257;
    }
    if ( v54 + v6 > v5 )
      goto LABEL_68;
    v78 = v12 & (unsigned int)(v6 - v45);
    if ( (int)v78 + v54 > v86 )
    {
      v79 = v86 - v78;
      v54 -= v86 - v78;
      do
      {
        v80 = *(_BYTE *)(v78 + v11);
        v78 = (unsigned int)(v78 + 1);
        v81 = v6++;
        *(_BYTE *)(v81 + v11) = v80;
        --v79;
      }
      while ( v79 );
      v78 = v12 & (unsigned int)v78;
    }
    do
    {
      v82 = *(_BYTE *)(v78 + v11);
      v78 = (unsigned int)(v78 + 1);
      v83 = v6++;
      *(_BYTE *)(v83 + v11) = v82;
      --v54;
    }
    while ( v54 );
LABEL_67:
    if ( v6 >= v5 )
      goto LABEL_68;
  }
}

```

## disassembly

```asm
0x180008210  mov     [rsp+arg_10], rbx
0x180008215  mov     [rsp+arg_18], r9d
0x18000821a  push    rbp
0x18000821b  push    rsi
0x18000821c  push    rdi
0x18000821d  push    r12
0x18000821f  push    r13
0x180008221  push    r14
0x180008223  push    r15
0x180008225  mov     rbp, [rcx+10h]
0x180008229  lea     r12d, [rdx+r8]
0x18000822d  mov     esi, [rcx+20h]
0x180008230  mov     r14d, edx
0x180008233  mov     r11b, [rcx+4]
0x180008237  mov     rbx, rcx
0x18000823a  mov     r10d, [rcx]
0x18000823d  mov     rdi, [rcx+8]
0x180008241  mov     r13, [rcx+18h]
0x180008245  mov     r15d, [rcx+24h]
0x180008249  mov     [rsp+38h+arg_0], rbp
0x18000824e  mov     [rsp+38h+arg_8], esi
0x180008252  cmp     edx, r12d
0x180008255  jge     loc_18000877B
0x18000825b  mov     eax, r10d
0x18000825e  shr     rax, 16h
0x180008262  movsx   r8d, word ptr [rbx+rax*2+7Ch]
0x180008268  test    r8d, r8d
0x18000826b  jns     short loc_1800082A1
0x18000826d  mov     r9d, 200000h
0x180008273  mov     eax, r9d
0x180008276  and     eax, r10d
0x180008279  neg     eax
0x18000827b  lea     rax, [rbx+1618h]
0x180008282  sbb     rdx, rdx
0x180008285  neg     r8d
0x180008288  add     r8d, r8d
0x18000828b  shr     r9d, 1
0x18000828e  and     edx, 2
0x180008291  movsxd  rcx, r8d
0x180008294  add     rax, rdx
0x180008297  movsx   r8d, word ptr [rax+rcx*2]
0x18000829c  test    r8d, r8d
0x18000829f  js      short loc_180008273
0x1800082a1  cmp     rdi, rbp
0x1800082a4  jnb     loc_1800087A4
0x1800082aa  mov     cl, [r8+rbx+0A7Ch]
0x1800082b2  shl     r10d, cl
0x1800082b5  sub     r11b, cl
0x1800082b8  mov     edx, r10d
0x1800082bb  test    r11b, r11b
0x1800082be  jg      short loc_1800082E3
0x1800082c0  movzx   r10d, byte ptr [rdi+1]
0x1800082c5  movzx   eax, byte ptr [rdi]
0x1800082c8  add     rdi, 2
0x1800082cc  shl     r10d, 8
0x1800082d0  or      r10d, eax
0x1800082d3  movsx   ecx, r11b
0x1800082d7  neg     ecx
0x1800082d9  shl     r10d, cl
0x1800082dc  or      r10d, edx
0x1800082df  add     r11b, 10h
0x1800082e3  add     r8d, 0FFFFFF00h
0x1800082ea  jns     short loc_1800082FB
0x1800082ec  movsxd  rax, r14d
0x1800082ef  inc     r14d
0x1800082f2  mov     [rax+r13], r8b
0x1800082f6  jmp     loc_180008772
0x1800082fb  mov     r9d, r8d
0x1800082fe  and     r9d, 7
0x180008302  cmp     r9d, 7
0x180008306  jnz     loc_18000838F
0x18000830c  mov     eax, r10d
0x18000830f  shr     rax, 18h
0x180008313  movsx   r9d, word ptr [rbx+rax*2+87Ch]
0x18000831c  test    r9d, r9d
0x18000831f  jns     short loc_180008352
0x180008321  mov     esi, 800000h
0x180008326  mov     eax, esi
0x180008328  and     eax, r10d
0x18000832b  neg     eax
0x18000832d  lea     rax, [rbx+66D8h]
0x180008334  sbb     rdx, rdx
0x180008337  neg     r9d
0x18000833a  add     r9d, r9d
0x18000833d  shr     esi, 1
0x18000833f  and     edx, 2
0x180008342  movsxd  rcx, r9d
0x180008345  add     rax, rdx
0x180008348  movsx   r9d, word ptr [rax+rcx*2]
0x18000834d  test    r9d, r9d
0x180008350  js      short loc_180008326
0x180008352  mov     cl, [r9+rbx+1494h]
0x18000835a  shl     r10d, cl
0x18000835d  sub     r11b, cl
0x180008360  mov     edx, r10d
0x180008363  test    r11b, r11b
0x180008366  jg      short loc_18000838B
0x180008368  movzx   r10d, byte ptr [rdi+1]
0x18000836d  movzx   eax, byte ptr [rdi]
0x180008370  add     rdi, 2
0x180008374  shl     r10d, 8
0x180008378  or      r10d, eax
0x18000837b  movsx   ecx, r11b
0x18000837f  neg     ecx
0x180008381  shl     r10d, cl
0x180008384  or      r10d, edx
0x180008387  add     r11b, 10h
0x18000838b  add     r9d, 7
0x18000838f  sar     r8d, 3
0x180008393  cmp     r8d, 2
0x180008397  jbe     loc_1800085B3
0x18000839d  cmp     r8d, 123h
0x1800083a4  jnb     loc_1800087A4
0x1800083aa  cmp     [rsp+38h+arg_18], 0
0x1800083af  jz      loc_180008509
0x1800083b5  lea     rcx, cs:180000000h
0x1800083bc  mov     esi, r8d
0x1800083bf  mov     al, [r8+rcx+0BD00h]
0x1800083c7  lfence
0x1800083ca  cmp     al, 3
0x1800083cc  jb      loc_1800084B1
0x1800083d2  movzx   eax, byte ptr [r8+rcx+0BD00h]
0x1800083db  lea     edx, [rax-3]
0x1800083de  test    edx, edx
0x1800083e0  jz      short loc_180008437
0x1800083e2  lfence
0x1800083e5  mov     r8d, r10d
0x1800083e8  mov     ecx, 23h ; '#'
0x1800083ed  sub     ecx, eax
0x1800083ef  lea     rax, cs:180000000h
0x1800083f6  sub     r11b, [rsi+rax+0BD00h]
0x1800083fe  shr     r8d, cl
0x180008401  add     r11b, 3
0x180008405  mov     ecx, edx
0x180008407  shl     r10d, cl
0x18000840a  mov     edx, r10d
0x18000840d  test    r11b, r11b
0x180008410  jg      short loc_18000843A
0x180008412  movzx   r10d, byte ptr [rdi+1]
0x180008417  movzx   eax, byte ptr [rdi]
0x18000841a  add     rdi, 2
0x18000841e  shl     r10d, 8
0x180008422  or      r10d, eax
0x180008425  movsx   ecx, r11b
0x180008429  neg     ecx
0x18000842b  shl     r10d, cl
0x18000842e  or      r10d, edx
0x180008431  add     r11b, 10h
0x180008435  jmp     short loc_18000843A
0x180008437  xor     r8d, r8d
0x18000843a  cmp     rdi, rbp
0x18000843d  jnb     loc_1800087A4
0x180008443  mov     eax, r10d
0x180008446  lea     ebp, ds:0[r8*8]
0x18000844e  shr     rax, 19h
0x180008452  movsx   r8d, byte ptr [rax+rbx+1590h]
0x18000845b  mov     cl, [r8+rbx+1610h]
0x180008463  shl     r10d, cl
0x180008466  sub     r11b, cl
0x180008469  mov     edx, r10d
0x18000846c  test    r11b, r11b
0x18000846f  jg      short loc_180008494
0x180008471  movzx   r10d, byte ptr [rdi+1]
0x180008476  movzx   eax, byte ptr [rdi]
0x180008479  add     rdi, 2
0x18000847d  shl     r10d, 8
0x180008481  or      r10d, eax
0x180008484  movsx   ecx, r11b
0x180008488  neg     ecx
0x18000848a  shl     r10d, cl
0x18000848d  or      r10d, edx
0x180008490  add     r11b, 10h
0x180008494  lea     rax, cs:180000000h
0x18000849b  mov     esi, ds:rva MP_POS_minus2[rax+rsi*4]
0x1800084a2  add     esi, ebp
0x1800084a4  mov     rbp, [rsp+38h+arg_0]
0x1800084a9  add     esi, r8d
0x1800084ac  jmp     loc_1800085A5
0x1800084b1  test    al, al
0x1800084b3  jz      short loc_1800084FC
0x1800084b5  movzx   eax, byte ptr [r8+rcx+0BD00h]
0x1800084be  mov     r8d, r10d
0x1800084c1  mov     ecx, 20h ; ' '
0x1800084c6  sub     r11b, al
0x1800084c9  sub     ecx, eax
0x1800084cb  shr     r8d, cl
0x1800084ce  mov     ecx, eax
0x1800084d0  shl     r10d, cl
0x1800084d3  mov     edx, r10d
0x1800084d6  test    r11b, r11b
0x1800084d9  jg      loc_18000858D
0x1800084df  movzx   r10d, byte ptr [rdi+1]
0x1800084e4  movzx   eax, byte ptr [rdi]
0x1800084e7  shl     r10d, 8
0x1800084eb  movsx   ecx, r11b
0x1800084ef  or      r10d, eax
0x1800084f2  neg     ecx
0x1800084f4  shl     r10d, cl
0x1800084f7  jmp     loc_180008582
0x1800084fc  mov     esi, ds:rva MP_POS_minus2[rcx+r8*4]
0x180008504  jmp     loc_1800085A5
0x180008509  cmp     r8d, 3
0x18000850d  jbe     loc_1800085A0
0x180008513  lfence
0x180008516  mov     esi, r8d
0x180008519  lea     rax, cs:180000000h
0x180008520  movzx   eax, byte ptr [r8+rax+0BD00h]
0x180008529  mov     ecx, 20h ; ' '
0x18000852e  sub     ecx, eax
0x180008530  mov     r8d, r10d
0x180008533  shr     r8d, cl
0x180008536  sub     r11b, al
0x180008539  mov     ecx, eax
0x18000853b  shl     r10d, cl
0x18000853e  mov     edx, r10d
0x180008541  test    r11b, r11b
0x180008544  jg      short loc_18000858D
0x180008546  movzx   r10d, byte ptr [rdi+1]
0x18000854b  movzx   eax, byte ptr [rdi]
0x18000854e  add     rdi, 2
0x180008552  shl     r10d, 8
0x180008556  or      r10d, eax
0x180008559  movsx   ecx, r11b
0x18000855d  neg     ecx
0x18000855f  add     r11b, 10h
0x180008563  shl     r10d, cl
0x180008566  or      r10d, edx
0x180008569  test    r11b, r11b
0x18000856c  jg      short loc_18000858D
0x18000856e  movzx   edx, byte ptr [rdi+1]
0x180008572  movzx   eax, byte ptr [rdi]
0x180008575  shl     edx, 8
0x180008578  movsx   ecx, r11b
0x18000857c  or      edx, eax
0x18000857e  neg     ecx
0x180008580  shl     edx, cl
0x180008582  or      r10d, edx
0x180008585  add     rdi, 2
0x180008589  add     r11b, 10h
0x18000858d  lea     rax, cs:180000000h
0x180008594  mov     esi, ds:rva MP_POS_minus2[rax+rsi*4]
0x18000859b  add     esi, r8d
0x18000859e  jmp     short loc_1800085A5
0x1800085a0  mov     esi, 1
0x1800085a5  mov     eax, [rbx+74h]
0x1800085a8  mov     [rbx+78h], eax
0x1800085ab  mov     eax, [rbx+70h]
0x1800085ae  mov     [rbx+74h], eax
0x1800085b1  jmp     short loc_1800085C8
0x1800085b3  lfence
0x1800085b6  mov     esi, [rbx+r8*4+70h]
0x1800085bb  test    r8d, r8d
0x1800085be  jz      short loc_1800085CB
0x1800085c0  mov     eax, [rbx+70h]
0x1800085c3  mov     [rbx+r8*4+70h], eax
0x1800085c8  mov     [rbx+70h], esi
0x1800085cb  lea     r8d, [r9+2]
0x1800085cf  cmp     r8d, 101h
0x1800085d6  jnz     loc_18000871D
0x1800085dc  mov     edx, r10d
0x1800085df  sub     r11b, 9
0x1800085e3  shl     r10d, 9
0x1800085e7  shr     edx, 17h
0x1800085ea  mov     r8d, r10d
0x1800085ed  test    r11b, r11b
0x1800085f0  jg      short loc_180008615
0x1800085f2  movzx   r10d, byte ptr [rdi+1]
0x1800085f7  movzx   eax, byte ptr [rdi]
0x1800085fa  add     rdi, 2
0x1800085fe  shl     r10d, 8
0x180008602  or      r10d, eax
0x180008605  movsx   ecx, r11b
0x180008609  neg     ecx
0x18000860b  shl     r10d, cl
0x18000860e  or      r10d, r8d
0x180008611  add     r11b, 10h
0x180008615  bt      edx, 8
0x180008619  jnb     loc_180008716
0x18000861f  test    dl, dl
0x180008621  jns     loc_1800086C3
0x180008627  mov     r8d, edx
0x18000862a  and     r8d, 3Fh
0x18000862e  test    dl, 40h
0x180008631  jz      short loc_18000867B
0x180008633  mov     edx, r8d
0x180008636  sub     r11b, 9
0x18000863a  mov     r8d, r10d
0x18000863d  shl     edx, 9
0x180008640  shl     r10d, 9
0x180008644  shr     r8d, 17h
0x180008648  mov     r9d, r10d
0x18000864b  test    r11b, r11b
0x18000864e  jg      short loc_180008673
0x180008650  movzx   r10d, byte ptr [rdi+1]
0x180008655  movzx   eax, byte ptr [rdi]
0x180008658  add     rdi, 2
0x18000865c  shl     r10d, 8
0x180008660  or      r10d, eax
0x180008663  movsx   ecx, r11b
0x180008667  neg     ecx
  ... truncated ...
```
