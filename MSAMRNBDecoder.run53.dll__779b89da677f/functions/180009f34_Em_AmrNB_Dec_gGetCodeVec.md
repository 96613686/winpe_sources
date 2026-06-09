# Em_AmrNB_Dec_gGetCodeVec

- ea: `0x180009f34`
- end: `0x18000a419`
- name: `Em_AmrNB_Dec_gGetCodeVec`
- size: `1253`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003800`

## callees

- `0x180009f34`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_gGetCodeVec(__int64 a1)
{
  int i; // ecx
  __int64 v3; // rdx
  __int16 v4; // dx
  unsigned __int16 *v5; // rcx
  int v6; // r9d
  __int16 v7; // bx
  int v8; // edx
  int k; // r8d
  __int64 v10; // rax
  __int16 v11; // cx
  int v12; // edx
  __int16 v13; // ax
  bool v14; // cf
  int v15; // ecx
  int v16; // eax
  unsigned int v17; // r9d
  unsigned int v18; // eax
  int v19; // r9d
  int v20; // edx
  int v21; // edx
  int v22; // r8d
  int v23; // ecx
  int v24; // r15d
  int j; // r8d
  __int16 v26; // dx
  int v27; // ecx
  int v28; // eax
  int v29; // ecx
  int v30; // eax
  unsigned __int16 *v31; // rbx
  __int64 v32; // rbx
  __int16 v33; // ax
  __int16 v34; // r8
  int v35; // r9d
  int v36; // edx
  __int64 v37; // rcx
  __int16 v38; // ax
  unsigned int v39; // r8d
  int v40; // r9d
  int v41; // r8d
  unsigned int v42; // eax
  unsigned int v43; // r9d
  int v44; // r8d
  int v45; // eax
  unsigned int v46; // r9d
  unsigned int v47; // r8d
  int v48; // r9d
  int v49; // r8d
  unsigned int v50; // ecx
  unsigned int v51; // r9d
  int v52; // r8d
  unsigned int v53; // r11d
  unsigned int v54; // eax
  unsigned int v55; // r11d
  unsigned int v56; // r9d
  int v57; // r8d
  unsigned int v58; // edx
  unsigned int v59; // r9d
  int v60; // eax
  int v61; // r11d
  __int64 v62; // r9
  __int16 v63; // r8
  __int64 v64; // rdx
  __int16 v65; // cx
  _DWORD v67[4]; // [rsp+0h] [rbp-68h]
  _DWORD v68[22]; // [rsp+10h] [rbp-58h]

  for ( i = 0; i < 40; ++i )
  {
    v3 = i;
    *(_WORD *)(a1 + 2 * v3 + 88) = 0;
  }
  v4 = *(_WORD *)(a1 + 1306);
  if ( (unsigned __int16)(v4 - 6) <= 1u )
  {
    v31 = *(unsigned __int16 **)(a1 + 1320);
    if ( v4 == 7 )
    {
      *(_QWORD *)(a1 + 1320) = v31 + 1;
      v32 = 0;
      do
      {
        v33 = *(_WORD *)(*(_QWORD *)(a1 + 1320) + 2 * v32);
        v34 = (v33 & 8) != 0 ? -4096 : 4096;
        v35 = 5 * Em_AmrNB_Dec_dgray[v33 & 7];
        *(_WORD *)(a1 + 2LL * ((int)v32 + v35) + 88) = v34;
        v36 = 5 * Em_AmrNB_Dec_dgray[*(_WORD *)(*(_QWORD *)(a1 + 1320) + 2 * v32 + 10) & 7LL];
        v37 = v36 + (int)v32;
        v38 = -v34;
        if ( v36 >= v35 )
          v38 = v34;
        v32 = (unsigned int)(v32 + 1);
        *(_WORD *)(a1 + 2 * v37 + 88) += v38;
      }
      while ( (int)v32 < 5 );
      *(_QWORD *)(a1 + 1320) += 20LL;
    }
    else
    {
      v39 = v31[4];
      v40 = v39 & 7;
      v41 = v39 >> 3;
      v42 = v40;
      if ( v41 > 124 )
        v41 = 124;
      v43 = v40 & 3;
      v67[1] = (v42 >> 2) + (((1311 * v41) >> 14) & 0xFFFFFFFE);
      v44 = v41 - (__int16)(25 * ((1311 * v41) >> 15));
      v68[0] = (v43 >> 1) + (((6554 * v44) >> 14) & 0xFFFFFFFE);
      v45 = (v43 & 1) + 2 * (v44 - (__int16)(5 * ((6554 * v44) >> 15)));
      v46 = v31[5];
      v67[0] = v45;
      v47 = v46;
      v48 = v46 & 7;
      v49 = v47 >> 3;
      v50 = v48;
      if ( v49 > 124 )
        v49 = 124;
      v51 = v48 & 3;
      v68[1] = (((1311 * v49) >> 14) & 0xFFFFFFFE) + (v50 >> 2);
      v52 = v49 - (__int16)(25 * ((1311 * v49) >> 15));
      v68[2] = (((6554 * v52) >> 14) & 0xFFFFFFFE) + (v51 >> 1);
      v67[2] = (v51 & 1) + 2 * (v52 - (__int16)(5 * ((6554 * v52) >> 15)));
      v53 = v31[6];
      v54 = v53 >> 2;
      v55 = v53 & 3;
      v56 = (25 * v54 + 12) >> 5;
      v57 = (int)(6554 * v56) >> 15;
      v58 = ((int)(6554 * v56) >> 14) & 0xFFFFFFFE;
      v59 = v56 - (__int16)(5 * v57);
      v68[3] = v58 + (v55 >> 1);
      if ( (v57 & 1) != 0 )
        v59 = 4 - v59;
      v60 = (v55 & 1) + 2 * v59;
      v61 = 0;
      v62 = 0;
      v67[3] = v60;
      do
      {
        v63 = *(_WORD *)(*(_QWORD *)(a1 + 1320) + 2 * v62) != 0 ? -8191 : 0x1FFF;
        *(_WORD *)(a1 + 2LL * (v61 + (__int16)(4 * LOWORD(v67[v62]))) + 88) = v63;
        v64 = v61 + (__int16)(4 * LOWORD(v68[v62]));
        v65 = -v63;
        if ( v68[v62] >= v67[v62] )
          v65 = v63;
        ++v61;
        *(_WORD *)(a1 + 2 * v64 + 88) += v65;
        ++v62;
      }
      while ( v61 < 4 );
      *(_QWORD *)(a1 + 1320) += 14LL;
    }
  }
  else
  {
    v5 = *(unsigned __int16 **)(a1 + 1320);
    v6 = *v5;
    *(_QWORD *)(a1 + 1320) = v5 + 1;
    v7 = v5[1];
    *(_QWORD *)(a1 + 1320) = v5 + 2;
    if ( (unsigned __int16)(v4 - 4) <= 1u )
    {
      v24 = 0;
      for ( j = 0; j < 4; ++j )
      {
        v26 = (v7 & 1) != 0 ? 0x3FFF : 0;
        v7 >>= 1;
        v27 = Em_AmrNB_Dec_dgray[v6 & 7];
        v28 = v27 + j + 4 * v27;
        v29 = v6 >> 3;
        *(_WORD *)(a1 + 2LL * (v24 + v28) + 88) = v26 - 0x2000;
        v30 = (v6 >> 3) & 1;
        if ( j != 2 )
          v30 = v24;
        v6 >>= 4;
        v24 = v30;
        if ( j != 2 )
          v6 = v29;
      }
    }
    else if ( v4 == 3 )
    {
      v8 = 0;
      for ( k = 0; k < 3; ++k )
      {
        v10 = k + (v6 & 7) + 4 * (v6 & 7) + 2 * v8;
        v11 = -((v7 & 1) != 0);
        v12 = v6 >> 3;
        v7 >>= 1;
        v6 >>= 4;
        v8 = v12 & 1;
        *(_WORD *)(a1 + 2 * v10 + 88) = (v11 & 0x3FFF) - 0x2000;
      }
    }
    else
    {
      v13 = v7 & 1;
      if ( v4 == 2 )
      {
        v14 = v13 != 0;
        v15 = 5 * (((unsigned int)v6 >> 1) & 7);
        v16 = v6 & 1;
        v17 = (unsigned int)v6 >> 4;
        *(_WORD *)(a1 + 2LL * (unsigned int)(v15 + 2 * v16) + 90) = v14 ? 0x1FFF : -8192;
        v18 = v17 >> 2;
        v19 = v17 & 3;
        v20 = 5 * (v18 & 7);
        if ( v19 == 3 )
          v21 = v20 + 4;
        else
          v21 = v19 + v20;
        *(_WORD *)(a1 + 2LL * v21 + 88) = (v7 & 2) != 0 ? 0x1FFF : -8192;
      }
      else
      {
        v22 = ((unsigned int)v6 >> 5) & 2;
        *(_WORD *)(a1
                 + 2LL
                 * (5 * (v6 & 7) + (unsigned int)Em_AmrNB_Dec_StrtPosMR475andMR515[4 * *(__int16 *)(a1 + 1308) + v22])
                 + 88) = v13 != 0 ? 0x1FFF : -8192;
        v23 = 5 * (((unsigned int)v6 >> 3) & 7)
            + Em_AmrNB_Dec_StrtPosMR475andMR515[4 * *(__int16 *)(a1 + 1308) + 1 + v22];
        if ( (v7 & 2) != 0 )
          *(_WORD *)(a1 + 2LL * v23 + 88) = 0x1FFF;
        else
          *(_WORD *)(a1 + 2LL * v23 + 88) = -8192;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180009f34  push    rbx
0x180009f36  push    rbp
0x180009f37  push    rsi
0x180009f38  push    rdi
0x180009f39  push    r12
0x180009f3b  push    r14
0x180009f3d  push    r15
0x180009f3f  sub     rsp, 30h
0x180009f43  mov     r10, rcx
0x180009f46  xor     ecx, ecx
0x180009f48  lea     r12d, [rcx+1]
0x180009f4c  movsxd  rdx, ecx
0x180009f4f  xor     eax, eax
0x180009f51  add     ecx, r12d
0x180009f54  mov     [r10+rdx*2+58h], ax
0x180009f5a  cmp     ecx, 28h ; '('
0x180009f5d  jl      short loc_180009F4C
0x180009f5f  movzx   edx, word ptr [r10+51Ah]
0x180009f67  mov     r11d, 7
0x180009f6d  lea     eax, [rdx-6]
0x180009f70  cmp     ax, r12w
0x180009f74  jbe     loc_18000A180
0x180009f7a  mov     rcx, [r10+528h]
0x180009f81  lea     r14d, [r11-3]
0x180009f85  mov     edi, 0FFFFE000h
0x180009f8a  movzx   r9d, word ptr [rcx]
0x180009f8e  lea     rax, [rcx+2]
0x180009f92  mov     [r10+528h], rax
0x180009f99  movzx   ebx, word ptr [rax]
0x180009f9c  lea     rax, [rcx+4]
0x180009fa0  mov     [r10+528h], rax
0x180009fa7  movzx   eax, dx
0x180009faa  sub     ax, r14w
0x180009fae  cmp     ax, r12w
0x180009fb2  jbe     loc_18000A10E
0x180009fb8  lea     ebp, [r11-4]
0x180009fbc  cmp     dx, bp
0x180009fbf  jnz     short loc_18000A00E
0x180009fc1  xor     edx, edx
0x180009fc3  xor     r8d, r8d
0x180009fc6  mov     ecx, r9d
0x180009fc9  and     ecx, r11d
0x180009fcc  lea     eax, [r8+rcx]
0x180009fd0  lea     eax, [rax+rcx*4]
0x180009fd3  lea     edx, [rax+rdx*2]
0x180009fd6  mov     al, bl
0x180009fd8  and     al, r12b
0x180009fdb  neg     al
0x180009fdd  movsxd  rax, edx
0x180009fe0  sbb     cx, cx
0x180009fe3  sar     r9d, 3
0x180009fe7  mov     edx, r9d
0x180009fea  sar     bx, 1
0x180009fed  and     cx, 3FFFh
0x180009ff2  sar     r9d, 1
0x180009ff5  add     cx, di
0x180009ff8  and     edx, r12d
0x180009ffb  add     r8d, r12d
0x180009ffe  mov     [r10+rax*2+58h], cx
0x18000a004  cmp     r8d, ebp
0x18000a007  jl      short loc_180009FC6
0x18000a009  jmp     loc_18000A408
0x18000a00e  movzx   eax, bx
0x18000a011  mov     esi, 2
0x18000a016  and     ax, r12w
0x18000a01a  cmp     dx, si
0x18000a01d  jnz     short loc_18000A085
0x18000a01f  neg     ax
0x18000a022  mov     eax, r9d
0x18000a025  sbb     dx, dx
0x18000a028  shr     eax, 1
0x18000a02a  and     eax, r11d
0x18000a02d  and     dx, 3FFFh
0x18000a032  add     dx, di
0x18000a035  lea     ecx, [rax+rax*4]
0x18000a038  mov     eax, r9d
0x18000a03b  and     eax, r12d
0x18000a03e  shr     r9d, 4
0x18000a042  lea     eax, [rcx+rax*2]
0x18000a045  mov     [r10+rax*2+5Ah], dx
0x18000a04b  mov     eax, r9d
0x18000a04e  shr     eax, 2
0x18000a051  and     r9d, ebp
0x18000a054  and     eax, r11d
0x18000a057  lea     edx, [rax+rax*4]
0x18000a05a  cmp     r9d, ebp
0x18000a05d  jnz     short loc_18000A064
0x18000a05f  add     edx, r14d
0x18000a062  jmp     short loc_18000A067
0x18000a064  add     edx, r9d
0x18000a067  and     bl, sil
0x18000a06a  movsxd  rax, edx
0x18000a06d  neg     bl
0x18000a06f  sbb     cx, cx
0x18000a072  and     cx, 3FFFh
0x18000a077  add     cx, di
0x18000a07a  mov     [r10+rax*2+58h], cx
0x18000a080  jmp     loc_18000A408
0x18000a085  mov     r8d, r9d
0x18000a088  lea     rbp, cs:180000000h
0x18000a08f  shr     r8d, 5
0x18000a093  and     r8d, esi
0x18000a096  neg     ax
0x18000a099  movsx   eax, word ptr [r10+51Ch]
0x18000a0a1  sbb     dx, dx
0x18000a0a4  and     dx, 3FFFh
0x18000a0a9  add     dx, di
0x18000a0ac  lea     eax, [r8+rax*4]
0x18000a0b0  cdqe
0x18000a0b2  movzx   ecx, byte ptr [rax+rbp+184C0h]
0x18000a0ba  mov     eax, r9d
0x18000a0bd  and     eax, r11d
0x18000a0c0  shr     r9d, 3
0x18000a0c4  and     r9d, r11d
0x18000a0c7  lea     eax, [rax+rax*4]
0x18000a0ca  add     ecx, eax
0x18000a0cc  mov     [r10+rcx*2+58h], dx
0x18000a0d2  movsx   eax, word ptr [r10+51Ch]
0x18000a0da  lea     eax, [r8+rax*4]
0x18000a0de  cdqe
0x18000a0e0  movzx   ecx, byte ptr [rax+rbp+184C1h]
0x18000a0e8  lea     eax, [r9+r9*4]
0x18000a0ec  add     ecx, eax
0x18000a0ee  movsxd  rax, ecx
0x18000a0f1  test    sil, bl
0x18000a0f4  jz      short loc_18000A103
0x18000a0f6  mov     word ptr [r10+rax*2+58h], 1FFFh
0x18000a0fe  jmp     loc_18000A408
0x18000a103  mov     [r10+rax*2+58h], di
0x18000a109  jmp     loc_18000A408
0x18000a10e  xor     r15d, r15d
0x18000a111  lea     rbp, cs:180000000h
0x18000a118  xor     r8d, r8d
0x18000a11b  lea     esi, [r15+2]
0x18000a11f  mov     al, bl
0x18000a121  and     al, r12b
0x18000a124  neg     al
0x18000a126  mov     eax, r9d
0x18000a129  sbb     dx, dx
0x18000a12c  and     rax, r11
0x18000a12f  and     dx, 3FFFh
0x18000a134  sar     bx, 1
0x18000a137  add     dx, di
0x18000a13a  movsx   ecx, ss:rva Em_AmrNB_Dec_dgray[rbp+rax*2]
0x18000a142  lea     eax, [r8+rcx*4]
0x18000a146  add     eax, ecx
0x18000a148  mov     ecx, r9d
0x18000a14b  add     eax, r15d
0x18000a14e  sar     ecx, 3
0x18000a151  cdqe
0x18000a153  mov     [r10+rax*2+58h], dx
0x18000a159  mov     eax, ecx
0x18000a15b  and     eax, r12d
0x18000a15e  cmp     r8d, esi
0x18000a161  cmovnz  eax, r15d
0x18000a165  sar     r9d, 4
0x18000a169  cmp     r8d, esi
0x18000a16c  mov     r15d, eax
0x18000a16f  cmovnz  r9d, ecx
0x18000a173  add     r8d, r12d
0x18000a176  cmp     r8d, r14d
0x18000a179  jl      short loc_18000A11F
0x18000a17b  jmp     loc_18000A408
0x18000a180  mov     rbx, [r10+528h]
0x18000a187  cmp     dx, r11w
0x18000a18b  jnz     loc_18000A230
0x18000a191  lea     rax, [rbx+2]
0x18000a195  mov     edi, 0FFFFE000h
0x18000a19a  mov     [r10+528h], rax
0x18000a1a1  lea     rbp, cs:180000000h
0x18000a1a8  xor     ebx, ebx
0x18000a1aa  mov     rax, [r10+528h]
0x18000a1b1  movzx   ecx, word ptr [rax+rbx*2]
0x18000a1b5  mov     eax, ecx
0x18000a1b7  and     cl, 8
0x18000a1ba  and     rax, r11
0x18000a1bd  neg     cl
0x18000a1bf  sbb     r8w, r8w
0x18000a1c3  movsx   eax, ss:rva Em_AmrNB_Dec_dgray[rbp+rax*2]
0x18000a1cb  and     r8w, di
0x18000a1cf  add     r8w, 1000h
0x18000a1d5  lea     r9d, [rax+rax*4]
0x18000a1d9  lea     eax, [rbx+r9]
0x18000a1dd  movsxd  rcx, eax
0x18000a1e0  mov     [r10+rcx*2+58h], r8w
0x18000a1e6  mov     rax, [r10+528h]
0x18000a1ed  movzx   ecx, word ptr [rax+rbx*2+0Ah]
0x18000a1f2  and     rcx, r11
0x18000a1f5  movsx   eax, ss:rva Em_AmrNB_Dec_dgray[rbp+rcx*2]
0x18000a1fd  lea     edx, [rax+rax*4]
0x18000a200  lea     eax, [rdx+rbx]
0x18000a203  movsxd  rcx, eax
0x18000a206  movzx   eax, r8w
0x18000a20a  neg     ax
0x18000a20d  cmp     edx, r9d
0x18000a210  cmovge  ax, r8w
0x18000a215  add     ebx, r12d
0x18000a218  add     [r10+rcx*2+58h], ax
0x18000a21e  cmp     ebx, 5
0x18000a221  jl      short loc_18000A1AA
0x18000a223  add     qword ptr [r10+528h], 14h
0x18000a22b  jmp     loc_18000A408
0x18000a230  movzx   r9d, word ptr [rbx+8]
0x18000a235  mov     edi, 7Ch ; '|'
0x18000a23a  mov     r8d, r9d
0x18000a23d  and     r9d, r11d
0x18000a240  shr     r8d, 3
0x18000a244  mov     eax, r9d
0x18000a247  cmp     r8d, edi
0x18000a24a  lea     ebp, [rdi-79h]
0x18000a24d  cmovg   r8d, edi
0x18000a251  shr     eax, 2
0x18000a254  imul    edx, r8d, 51Fh
0x18000a25b  and     r9d, ebp
0x18000a25e  mov     ecx, edx
0x18000a260  sar     edx, 0Fh
0x18000a263  sar     ecx, 0Eh
0x18000a266  and     ecx, 0FFFFFFFEh
0x18000a269  add     ecx, eax
0x18000a26b  movsx   eax, dx
0x18000a26e  imul    eax, 19h
0x18000a271  mov     [rsp+68h+var_64], ecx
0x18000a275  cwde
0x18000a276  sub     r8d, eax
0x18000a279  mov     eax, r9d
0x18000a27c  shr     eax, 1
0x18000a27e  and     r9d, r12d
0x18000a281  imul    edx, r8d, 199Ah
0x18000a288  mov     ecx, edx
0x18000a28a  sar     edx, 0Fh
0x18000a28d  sar     ecx, 0Eh
0x18000a290  and     ecx, 0FFFFFFFEh
0x18000a293  add     ecx, eax
0x18000a295  movzx   eax, dx
0x18000a298  shl     ax, 2
0x18000a29c  add     ax, dx
0x18000a29f  mov     [rsp+68h+var_58], ecx
0x18000a2a3  cwde
0x18000a2a4  sub     r8d, eax
0x18000a2a7  lea     eax, [r9+r8*2]
0x18000a2ab  movzx   r9d, word ptr [rbx+0Ah]
0x18000a2b0  mov     [rsp+68h+var_68], eax
0x18000a2b3  mov     r8d, r9d
0x18000a2b6  and     r9d, r11d
0x18000a2b9  shr     r8d, 3
0x18000a2bd  cmp     r8d, edi
0x18000a2c0  mov     ecx, r9d
0x18000a2c3  cmovg   r8d, edi
0x18000a2c7  shr     ecx, 2
0x18000a2ca  imul    edx, r8d, 51Fh
0x18000a2d1  and     r9d, ebp
0x18000a2d4  mov     eax, edx
0x18000a2d6  sar     edx, 0Fh
0x18000a2d9  sar     eax, 0Eh
0x18000a2dc  and     eax, 0FFFFFFFEh
0x18000a2df  add     ecx, eax
0x18000a2e1  movsx   eax, dx
0x18000a2e4  imul    eax, 19h
0x18000a2e7  mov     [rsp+68h+var_54], ecx
0x18000a2eb  mov     ecx, r9d
0x18000a2ee  shr     ecx, 1
0x18000a2f0  and     r9d, r12d
0x18000a2f3  cwde
0x18000a2f4  sub     r8d, eax
0x18000a2f7  imul    edx, r8d, 199Ah
0x18000a2fe  mov     eax, edx
0x18000a300  sar     edx, 0Fh
0x18000a303  sar     eax, 0Eh
0x18000a306  and     eax, 0FFFFFFFEh
0x18000a309  add     ecx, eax
0x18000a30b  movzx   eax, dx
0x18000a30e  shl     ax, 2
0x18000a312  add     ax, dx
0x18000a315  mov     [rsp+68h+var_50], ecx
0x18000a319  cwde
0x18000a31a  sub     r8d, eax
0x18000a31d  lea     eax, [r9+r8*2]
0x18000a321  mov     [rsp+68h+var_60], eax
0x18000a325  movzx   eax, word ptr [rbx+0Ch]
0x18000a329  mov     r11d, eax
0x18000a32c  shr     eax, 2
0x18000a32f  and     r11d, ebp
0x18000a332  imul    r9d, eax, 19h
0x18000a336  add     r9d, 0Ch
0x18000a33a  lea     r14d, [rdi-78h]
0x18000a33e  shr     r9d, 5
0x18000a342  imul    edx, r9d, 199Ah
0x18000a349  mov     r8d, edx
0x18000a34c  sar     edx, 0Eh
0x18000a34f  sar     r8d, 0Fh
0x18000a353  and     edx, 0FFFFFFFEh
0x18000a356  movzx   eax, r8w
0x18000a35a  shl     ax, 2
0x18000a35e  add     ax, r8w
0x18000a362  cwde
0x18000a363  sub     r9d, eax
0x18000a366  mov     eax, r11d
0x18000a369  shr     eax, 1
0x18000a36b  add     eax, edx
0x18000a36d  mov     [rsp+68h+var_4C], eax
  ... truncated ...
```
