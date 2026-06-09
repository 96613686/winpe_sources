# u8_ipps_BitRev2_C

- ea: `0x18003b1a0`
- end: `0x18003b518`
- name: `u8_ipps_BitRev2_C`
- size: `888`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18001adb0`
- `0x18001af50`
- `0x18001b150`
- `0x18001bba0`
- `0x18004ef90`
- `0x18004f090`

## callees

- `0x18003b1a0`

## pseudocode

```c
void __fastcall u8_ipps_BitRev2_C(__m128 *a1, double *a2, __int64 a3, __int64 a4)
{
  __m128 *v4; // r12
  double *v5; // r13
  __int64 v6; // rbx
  __int64 v7; // r10
  double *v8; // r8
  __int64 v9; // rax
  __m128 v10; // xmm2
  __m128 v11; // xmm3
  __m128 v12; // xmm4
  __m128 v13; // xmm5
  __m128 v14; // xmm0
  __m128 v15; // xmm4
  __m128 v16; // xmm7
  __m128 v17; // xmm1
  __m128 v18; // xmm5
  __m128 v19; // xmm6
  __m128 v20; // xmm7
  __m128 v21; // xmm0
  __m128 v22; // xmm1
  __m128 v23; // xmm2
  __m128 v24; // xmm3
  __m128 v25; // xmm4
  __m128 v26; // xmm5
  __m128 v27; // xmm6
  __m128 v28; // xmm7
  __int64 v29; // rbx
  __int64 v30; // r10
  __int64 v31; // rax
  __int64 v32; // r12
  __m128 *v33; // r13
  __m128 v34; // xmm2
  __m128 v35; // xmm3
  __m128 v36; // xmm4
  __m128 v37; // xmm5
  __m128 v38; // xmm0
  __m128 v39; // xmm4
  __m128 v40; // xmm7
  __m128 v41; // xmm1
  __m128 v42; // xmm5
  __m128 v43; // xmm6
  __m128 v44; // xmm7
  double *v45; // r13
  __m128 v46; // xmm0
  __m128 v47; // xmm1
  __m128 v48; // xmm2
  __m128 v49; // xmm3
  __m128 v50; // xmm4
  __m128 v51; // xmm5
  __m128 v52; // xmm6
  __m128 v53; // xmm7
  __m128 v54; // xmm0
  __m128 v55; // xmm1
  __m128 v56; // xmm2
  __m128 v57; // xmm3

  v4 = a1;
  v5 = a2;
  if ( a3 == 8 )
  {
    v54 = *a1;
    v55 = a1[1];
    v56 = a1[2];
    v57 = a1[3];
    _mm_storel_ps(a2, *a1);
    _mm_storel_ps(a2 + 1, v56);
    _mm_storel_ps(a2 + 2, v55);
    _mm_storel_ps(a2 + 3, v57);
    _mm_storeh_ps(a2 + 4, v54);
    _mm_storeh_ps(a2 + 5, v56);
    _mm_storeh_ps(a2 + 6, v55);
    _mm_storeh_ps(a2 + 7, v57);
  }
  else if ( a3 <= 0x10000 )
  {
    v29 = a4 + 4 * ((unsigned __int64)a3 >> 4);
    v30 = 2 * a3;
    v31 = 6 * a3;
    v32 = (__int64)&a1[-2] + 2 * a3;
    if ( (v32 & 0xF) != 0 || ((unsigned __int8)a2 & 0xF) != 0 )
    {
      do
      {
        v45 = (double *)((char *)a2 + 4 * *(int *)(v29 - 4));
        v29 -= 4;
        v46 = *(__m128 *)v32;
        v47 = *(__m128 *)(v32 + 16);
        v48 = *(__m128 *)(v30 + v32);
        v49 = *(__m128 *)(v30 + v32 + 16);
        v50 = *(__m128 *)(v32 + 4 * a3);
        v51 = *(__m128 *)(v32 + 4 * a3 + 16);
        v52 = *(__m128 *)(v31 + v32);
        v53 = *(__m128 *)(v31 + v32 + 16);
        _mm_storel_ps(v45, *(__m128 *)v32);
        _mm_storel_ps(v45 + 1, v50);
        _mm_storel_ps(v45 + 2, v48);
        _mm_storel_ps(v45 + 3, v52);
        _mm_storel_ps((double *)((char *)v45 + v30), v47);
        _mm_storel_ps((double *)((char *)v45 + v30 + 8), v51);
        _mm_storel_ps((double *)((char *)v45 + v30 + 16), v49);
        _mm_storel_ps((double *)((char *)v45 + v30 + 24), v53);
        _mm_storeh_ps((double *)((char *)v45 + 4 * a3), v46);
        _mm_storeh_ps((double *)((char *)v45 + 4 * a3 + 8), v50);
        _mm_storeh_ps((double *)((char *)v45 + 4 * a3 + 16), v48);
        _mm_storeh_ps((double *)((char *)v45 + 4 * a3 + 24), v52);
        _mm_storeh_ps((double *)((char *)v45 + v31), v47);
        _mm_storeh_ps((double *)((char *)v45 + v31 + 8), v51);
        _mm_storeh_ps((double *)((char *)v45 + v31 + 16), v49);
        _mm_storeh_ps((double *)((char *)v45 + v31 + 24), v53);
        v32 -= 32;
      }
      while ( v32 >= (__int64)a1 );
    }
    else
    {
      do
      {
        v33 = (__m128 *)((char *)a2 + 4 * *(int *)(v29 - 4));
        v29 -= 4;
        v34 = *(__m128 *)(v30 + v32);
        v35 = *(__m128 *)(v30 + v32 + 16);
        v36 = *(__m128 *)(v32 + 4 * a3);
        v37 = *(__m128 *)(v32 + 4 * a3 + 16);
        v38 = _mm_movelh_ps(*(__m128 *)v32, v36);
        v39 = _mm_movehl_ps(v36, *(__m128 *)v32);
        v40 = *(__m128 *)(v32 + 16);
        v41 = _mm_movelh_ps(v40, v37);
        v42 = _mm_movehl_ps(v37, v40);
        v43 = *(__m128 *)(v31 + v32);
        v44 = *(__m128 *)(v31 + v32 + 16);
        *v33 = v38;
        v33[1] = _mm_movelh_ps(v34, v43);
        *(__m128 *)((char *)v33 + v30) = v41;
        *(__m128 *)((char *)v33 + v30 + 16) = _mm_movelh_ps(v35, v44);
        *(__m128 *)((char *)v33 + 4 * a3) = v39;
        *(__m128 *)((char *)v33 + 4 * a3 + 16) = _mm_movehl_ps(v43, v34);
        *(__m128 *)((char *)v33 + v31) = v42;
        *(__m128 *)((char *)v33 + v31 + 16) = _mm_movehl_ps(v44, v35);
        v32 -= 32;
      }
      while ( v32 >= (__int64)a1 );
    }
  }
  else
  {
    v6 = a4;
    v7 = 2 * a3;
    v8 = (double *)((char *)a2 + 2 * a3);
    v9 = 3 * v7;
    if ( ((unsigned __int8)a1 & 0xF) != 0 || ((unsigned __int8)a2 & 0xF) != 0 )
    {
      do
      {
        v21 = *v4;
        v22 = v4[1];
        v23 = *(__m128 *)((char *)v4 + v7);
        v24 = *(__m128 *)((char *)v4 + v7 + 16);
        v25 = *(__m128 *)((char *)v4 + 2 * v7);
        v26 = *(__m128 *)((char *)v4 + 2 * v7 + 16);
        v27 = *(__m128 *)((char *)v4 + v9);
        v28 = *(__m128 *)((char *)v4 + v9 + 16);
        v4 = (__m128 *)((char *)a1 + 4 * *(int *)(v6 + 4));
        v6 += 4;
        _mm_storel_ps(v5, v21);
        _mm_storel_ps(v5 + 1, v25);
        _mm_storel_ps(v5 + 2, v23);
        _mm_storel_ps(v5 + 3, v27);
        _mm_storel_ps((double *)((char *)v5 + v7), v22);
        _mm_storel_ps((double *)((char *)v5 + v7 + 8), v26);
        _mm_storel_ps((double *)((char *)v5 + v7 + 16), v24);
        _mm_storel_ps((double *)((char *)v5 + v7 + 24), v28);
        _mm_storeh_ps((double *)((char *)v5 + 2 * v7), v21);
        _mm_storeh_ps((double *)((char *)v5 + 2 * v7 + 8), v25);
        _mm_storeh_ps((double *)((char *)v5 + 2 * v7 + 16), v23);
        _mm_storeh_ps((double *)((char *)v5 + 2 * v7 + 24), v27);
        _mm_storeh_ps((double *)((char *)v5 + v9), v22);
        _mm_storeh_ps((double *)((char *)v5 + v9 + 8), v26);
        _mm_storeh_ps((double *)((char *)v5 + v9 + 16), v24);
        _mm_storeh_ps((double *)((char *)v5 + v9 + 24), v28);
        v5 += 4;
      }
      while ( v5 != v8 );
    }
    else
    {
      do
      {
        v10 = *(__m128 *)((char *)v4 + v7);
        v11 = *(__m128 *)((char *)v4 + v7 + 16);
        v12 = *(__m128 *)((char *)v4 + 2 * v7);
        v13 = *(__m128 *)((char *)v4 + 2 * v7 + 16);
        v14 = _mm_movelh_ps(*v4, v12);
        v15 = _mm_movehl_ps(v12, *v4);
        v16 = v4[1];
        v17 = _mm_movelh_ps(v16, v13);
        v18 = _mm_movehl_ps(v13, v16);
        v19 = *(__m128 *)((char *)v4 + v9);
        v20 = *(__m128 *)((char *)v4 + v9 + 16);
        v4 = (__m128 *)((char *)a1 + 4 * *(int *)(v6 + 4));
        v6 += 4;
        *(__m128 *)v5 = v14;
        *((__m128 *)v5 + 1) = _mm_movelh_ps(v10, v19);
        *(__m128 *)((char *)v5 + v7) = v17;
        *(__m128 *)((char *)v5 + v7 + 16) = _mm_movelh_ps(v11, v20);
        *(__m128 *)((char *)v5 + 2 * v7) = v15;
        *(__m128 *)((char *)v5 + 2 * v7 + 16) = _mm_movehl_ps(v19, v10);
        *(__m128 *)((char *)v5 + v9) = v18;
        *(__m128 *)((char *)v5 + v9 + 16) = _mm_movehl_ps(v20, v11);
        v5 += 4;
      }
      while ( v5 != v8 );
    }
  }
}

```

## disassembly

```asm
0x18003b1a0  push    rbx
0x18003b1a1  push    rsi
0x18003b1a2  push    rdi
0x18003b1a3  push    rbp
0x18003b1a4  push    r12
0x18003b1a6  push    r13
0x18003b1a8  sub     rsp, 28h
0x18003b1ac  movdqa  [rsp+58h+var_58], xmm7
0x18003b1b1  movdqa  [rsp+58h+var_48], xmm6
0x18003b1b7  mov     rdi, rcx
0x18003b1ba  mov     rsi, rdx
0x18003b1bd  mov     rdx, r8
0x18003b1c0  mov     rcx, r9
0x18003b1c3  mov     r12, rdi
0x18003b1c6  mov     r13, rsi
0x18003b1c9  mov     r10, rdx
0x18003b1cc  cmp     r10, 8
0x18003b1d0  jz      loc_18003B4C1
0x18003b1d6  cmp     r10, 10000h
0x18003b1dd  jle     loc_18003B34F
0x18003b1e3  mov     rbx, rcx
0x18003b1e6  mov     r11, r12
0x18003b1e9  shl     r10, 1
0x18003b1ec  lea     rax, [r10+r13]
0x18003b1f0  mov     r8, rax
0x18003b1f3  lea     rax, [r10+r10*2]
0x18003b1f7  test    r12, 0Fh
0x18003b1fe  jnz     loc_18003B2AB
0x18003b204  test    r13, 0Fh
0x18003b20b  jnz     loc_18003B2AB
0x18003b211  movaps  xmm0, xmmword ptr [r12]
0x18003b216  movaps  xmm1, xmmword ptr [r12+10h]
0x18003b21c  movaps  xmm2, xmmword ptr [r10+r12]
0x18003b221  movaps  xmm3, xmmword ptr [r10+r12+10h]
0x18003b227  movaps  xmm4, xmmword ptr [r12+r10*2]
0x18003b22c  movaps  xmm5, xmmword ptr [r12+r10*2+10h]
0x18003b232  movaps  xmm7, xmm0
0x18003b235  movlhps xmm0, xmm4
0x18003b238  movhlps xmm4, xmm7
0x18003b23b  movaps  xmm7, xmm1
0x18003b23e  movlhps xmm1, xmm5
0x18003b241  movhlps xmm5, xmm7
0x18003b244  movaps  xmm6, xmmword ptr [rax+r12]
0x18003b249  movaps  xmm7, xmmword ptr [rax+r12+10h]
0x18003b24f  movsxd  r12, dword ptr [rbx+4]
0x18003b253  lea     r12, [r11+r12*4]
0x18003b257  add     rbx, 4
0x18003b25b  movaps  xmmword ptr [r13+0], xmm0
0x18003b260  movaps  xmm0, xmm2
0x18003b263  movlhps xmm2, xmm6
0x18003b266  movhlps xmm6, xmm0
0x18003b269  movaps  xmm0, xmm3
0x18003b26c  movlhps xmm3, xmm7
0x18003b26f  movhlps xmm7, xmm0
0x18003b272  movaps  xmmword ptr [r13+10h], xmm2
0x18003b277  movaps  xmmword ptr [r10+r13], xmm1
0x18003b27c  movaps  xmmword ptr [r10+r13+10h], xmm3
0x18003b282  movaps  xmmword ptr [r13+r10*2+0], xmm4
0x18003b288  movaps  xmmword ptr [r13+r10*2+10h], xmm6
0x18003b28e  movaps  xmmword ptr [rax+r13], xmm5
0x18003b293  movaps  xmmword ptr [rax+r13+10h], xmm7
0x18003b299  add     r13, 20h ; ' '
0x18003b29d  cmp     r13, r8
0x18003b2a0  jnz     loc_18003B211
0x18003b2a6  jmp     loc_18003B500
0x18003b2ab  movups  xmm0, xmmword ptr [r12]
0x18003b2b0  movups  xmm1, xmmword ptr [r12+10h]
0x18003b2b6  movups  xmm2, xmmword ptr [r10+r12]
0x18003b2bb  movups  xmm3, xmmword ptr [r10+r12+10h]
0x18003b2c1  movups  xmm4, xmmword ptr [r12+r10*2]
0x18003b2c6  movups  xmm5, xmmword ptr [r12+r10*2+10h]
0x18003b2cc  movups  xmm6, xmmword ptr [rax+r12]
0x18003b2d1  movups  xmm7, xmmword ptr [rax+r12+10h]
0x18003b2d7  movsxd  r12, dword ptr [rbx+4]
0x18003b2db  lea     r12, [r11+r12*4]
0x18003b2df  add     rbx, 4
0x18003b2e3  movlps  qword ptr [r13+0], xmm0
0x18003b2e8  movlps  qword ptr [r13+8], xmm4
0x18003b2ed  movlps  qword ptr [r13+10h], xmm2
0x18003b2f2  movlps  qword ptr [r13+18h], xmm6
0x18003b2f7  movlps  qword ptr [r10+r13], xmm1
0x18003b2fc  movlps  qword ptr [r10+r13+8], xmm5
0x18003b302  movlps  qword ptr [r10+r13+10h], xmm3
0x18003b308  movlps  qword ptr [r10+r13+18h], xmm7
0x18003b30e  movhps  qword ptr [r13+r10*2+0], xmm0
0x18003b314  movhps  qword ptr [r13+r10*2+8], xmm4
0x18003b31a  movhps  qword ptr [r13+r10*2+10h], xmm2
0x18003b320  movhps  qword ptr [r13+r10*2+18h], xmm6
0x18003b326  movhps  qword ptr [rax+r13], xmm1
0x18003b32b  movhps  qword ptr [rax+r13+8], xmm5
0x18003b331  movhps  qword ptr [rax+r13+10h], xmm3
0x18003b337  movhps  qword ptr [rax+r13+18h], xmm7
0x18003b33d  add     r13, 20h ; ' '
0x18003b341  cmp     r13, r8
0x18003b344  jnz     loc_18003B2AB
0x18003b34a  jmp     loc_18003B500
0x18003b34f  mov     rbx, rcx
0x18003b352  mov     rax, r10
0x18003b355  shr     rax, 4
0x18003b359  lea     rbx, [rbx+rax*4]
0x18003b35d  shl     r10, 1
0x18003b360  lea     rax, [r10+r10*2]
0x18003b364  mov     r11, r13
0x18003b367  lea     r12, [r10+r12-20h]
0x18003b36c  test    r12, 0Fh
0x18003b373  jnz     loc_18003B420
0x18003b379  test    r13, 0Fh
0x18003b380  jnz     loc_18003B420
0x18003b386  movsxd  r13, dword ptr [rbx-4]
0x18003b38a  lea     r13, [r11+r13*4]
0x18003b38e  sub     rbx, 4
0x18003b392  movaps  xmm0, xmmword ptr [r12]
0x18003b397  movaps  xmm1, xmmword ptr [r12+10h]
0x18003b39d  movaps  xmm2, xmmword ptr [r10+r12]
0x18003b3a2  movaps  xmm3, xmmword ptr [r10+r12+10h]
0x18003b3a8  movaps  xmm4, xmmword ptr [r12+r10*2]
0x18003b3ad  movaps  xmm5, xmmword ptr [r12+r10*2+10h]
0x18003b3b3  movaps  xmm7, xmm0
0x18003b3b6  movlhps xmm0, xmm4
0x18003b3b9  movhlps xmm4, xmm7
0x18003b3bc  movaps  xmm7, xmm1
0x18003b3bf  movlhps xmm1, xmm5
0x18003b3c2  movhlps xmm5, xmm7
0x18003b3c5  movaps  xmm6, xmmword ptr [rax+r12]
0x18003b3ca  movaps  xmm7, xmmword ptr [rax+r12+10h]
0x18003b3d0  movaps  xmmword ptr [r13+0], xmm0
0x18003b3d5  movaps  xmm0, xmm2
0x18003b3d8  movlhps xmm2, xmm6
0x18003b3db  movhlps xmm6, xmm0
0x18003b3de  movaps  xmm0, xmm3
0x18003b3e1  movlhps xmm3, xmm7
0x18003b3e4  movhlps xmm7, xmm0
0x18003b3e7  movaps  xmmword ptr [r13+10h], xmm2
0x18003b3ec  movaps  xmmword ptr [r10+r13], xmm1
0x18003b3f1  movaps  xmmword ptr [r10+r13+10h], xmm3
0x18003b3f7  movaps  xmmword ptr [r13+r10*2+0], xmm4
0x18003b3fd  movaps  xmmword ptr [r13+r10*2+10h], xmm6
0x18003b403  movaps  xmmword ptr [rax+r13], xmm5
0x18003b408  movaps  xmmword ptr [rax+r13+10h], xmm7
0x18003b40e  sub     r12, 20h ; ' '
0x18003b412  cmp     r12, rdi
0x18003b415  jge     loc_18003B386
0x18003b41b  jmp     loc_18003B500
0x18003b420  movsxd  r13, dword ptr [rbx-4]
0x18003b424  lea     r13, [r11+r13*4]
0x18003b428  sub     rbx, 4
0x18003b42c  movups  xmm0, xmmword ptr [r12]
0x18003b431  movups  xmm1, xmmword ptr [r12+10h]
0x18003b437  movups  xmm2, xmmword ptr [r10+r12]
0x18003b43c  movups  xmm3, xmmword ptr [r10+r12+10h]
0x18003b442  movups  xmm4, xmmword ptr [r12+r10*2]
0x18003b447  movups  xmm5, xmmword ptr [r12+r10*2+10h]
0x18003b44d  movups  xmm6, xmmword ptr [rax+r12]
0x18003b452  movups  xmm7, xmmword ptr [rax+r12+10h]
0x18003b458  movlps  qword ptr [r13+0], xmm0
0x18003b45d  movlps  qword ptr [r13+8], xmm4
0x18003b462  movlps  qword ptr [r13+10h], xmm2
0x18003b467  movlps  qword ptr [r13+18h], xmm6
0x18003b46c  movlps  qword ptr [r10+r13], xmm1
0x18003b471  movlps  qword ptr [r10+r13+8], xmm5
0x18003b477  movlps  qword ptr [r10+r13+10h], xmm3
0x18003b47d  movlps  qword ptr [r10+r13+18h], xmm7
0x18003b483  movhps  qword ptr [r13+r10*2+0], xmm0
0x18003b489  movhps  qword ptr [r13+r10*2+8], xmm4
0x18003b48f  movhps  qword ptr [r13+r10*2+10h], xmm2
0x18003b495  movhps  qword ptr [r13+r10*2+18h], xmm6
0x18003b49b  movhps  qword ptr [rax+r13], xmm1
0x18003b4a0  movhps  qword ptr [rax+r13+8], xmm5
0x18003b4a6  movhps  qword ptr [rax+r13+10h], xmm3
0x18003b4ac  movhps  qword ptr [rax+r13+18h], xmm7
0x18003b4b2  sub     r12, 20h ; ' '
0x18003b4b6  cmp     r12, rdi
0x18003b4b9  jge     loc_18003B420
0x18003b4bf  jmp     short loc_18003B500
0x18003b4c1  movups  xmm0, xmmword ptr [r12]
0x18003b4c6  movups  xmm1, xmmword ptr [r12+10h]
0x18003b4cc  movups  xmm2, xmmword ptr [r12+20h]
0x18003b4d2  movups  xmm3, xmmword ptr [r12+30h]
0x18003b4d8  movlps  qword ptr [r13+0], xmm0
0x18003b4dd  movlps  qword ptr [r13+8], xmm2
0x18003b4e2  movlps  qword ptr [r13+10h], xmm1
0x18003b4e7  movlps  qword ptr [r13+18h], xmm3
0x18003b4ec  movhps  qword ptr [r13+20h], xmm0
0x18003b4f1  movhps  qword ptr [r13+28h], xmm2
0x18003b4f6  movhps  qword ptr [r13+30h], xmm1
0x18003b4fb  movhps  qword ptr [r13+38h], xmm3
0x18003b500  movdqa  xmm7, [rsp+58h+var_58]
0x18003b505  movdqa  xmm6, [rsp+58h+var_48]
0x18003b50b  add     rsp, 28h
0x18003b50f  pop     r13
0x18003b511  pop     r12
0x18003b513  pop     rbp
0x18003b514  pop     rdi
0x18003b515  pop     rsi
0x18003b516  pop     rbx
0x18003b517  retn
```
