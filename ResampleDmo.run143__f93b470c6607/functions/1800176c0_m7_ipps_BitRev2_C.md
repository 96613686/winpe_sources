# m7_ipps_BitRev2_C

- ea: `0x1800176c0`
- end: `0x180017a38`
- name: `m7_ipps_BitRev2_C`
- size: `888`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e3c0`
- `0x18000e560`
- `0x18000e760`
- `0x18000f1d0`
- `0x180029f08`
- `0x180029ff4`

## callees

- `0x1800176c0`

## pseudocode

```c
void __fastcall m7_ipps_BitRev2_C(__m128 *a1, double *a2, __int64 a3, __int64 a4)
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
0x1800176c0  push    rbx
0x1800176c1  push    rsi
0x1800176c2  push    rdi
0x1800176c3  push    rbp
0x1800176c4  push    r12
0x1800176c6  push    r13
0x1800176c8  sub     rsp, 28h
0x1800176cc  movdqa  [rsp+58h+var_58], xmm7
0x1800176d1  movdqa  [rsp+58h+var_48], xmm6
0x1800176d7  mov     rdi, rcx
0x1800176da  mov     rsi, rdx
0x1800176dd  mov     rdx, r8
0x1800176e0  mov     rcx, r9
0x1800176e3  mov     r12, rdi
0x1800176e6  mov     r13, rsi
0x1800176e9  mov     r10, rdx
0x1800176ec  cmp     r10, 8
0x1800176f0  jz      loc_1800179E1
0x1800176f6  cmp     r10, 10000h
0x1800176fd  jle     loc_18001786F
0x180017703  mov     rbx, rcx
0x180017706  mov     r11, r12
0x180017709  shl     r10, 1
0x18001770c  lea     rax, [r10+r13]
0x180017710  mov     r8, rax
0x180017713  lea     rax, [r10+r10*2]
0x180017717  test    r12, 0Fh
0x18001771e  jnz     loc_1800177CB
0x180017724  test    r13, 0Fh
0x18001772b  jnz     loc_1800177CB
0x180017731  movaps  xmm0, xmmword ptr [r12]
0x180017736  movaps  xmm1, xmmword ptr [r12+10h]
0x18001773c  movaps  xmm2, xmmword ptr [r10+r12]
0x180017741  movaps  xmm3, xmmword ptr [r10+r12+10h]
0x180017747  movaps  xmm4, xmmword ptr [r12+r10*2]
0x18001774c  movaps  xmm5, xmmword ptr [r12+r10*2+10h]
0x180017752  movaps  xmm7, xmm0
0x180017755  movlhps xmm0, xmm4
0x180017758  movhlps xmm4, xmm7
0x18001775b  movaps  xmm7, xmm1
0x18001775e  movlhps xmm1, xmm5
0x180017761  movhlps xmm5, xmm7
0x180017764  movaps  xmm6, xmmword ptr [rax+r12]
0x180017769  movaps  xmm7, xmmword ptr [rax+r12+10h]
0x18001776f  movsxd  r12, dword ptr [rbx+4]
0x180017773  lea     r12, [r11+r12*4]
0x180017777  add     rbx, 4
0x18001777b  movaps  xmmword ptr [r13+0], xmm0
0x180017780  movaps  xmm0, xmm2
0x180017783  movlhps xmm2, xmm6
0x180017786  movhlps xmm6, xmm0
0x180017789  movaps  xmm0, xmm3
0x18001778c  movlhps xmm3, xmm7
0x18001778f  movhlps xmm7, xmm0
0x180017792  movaps  xmmword ptr [r13+10h], xmm2
0x180017797  movaps  xmmword ptr [r10+r13], xmm1
0x18001779c  movaps  xmmword ptr [r10+r13+10h], xmm3
0x1800177a2  movaps  xmmword ptr [r13+r10*2+0], xmm4
0x1800177a8  movaps  xmmword ptr [r13+r10*2+10h], xmm6
0x1800177ae  movaps  xmmword ptr [rax+r13], xmm5
0x1800177b3  movaps  xmmword ptr [rax+r13+10h], xmm7
0x1800177b9  add     r13, 20h ; ' '
0x1800177bd  cmp     r13, r8
0x1800177c0  jnz     loc_180017731
0x1800177c6  jmp     loc_180017A20
0x1800177cb  movups  xmm0, xmmword ptr [r12]
0x1800177d0  movups  xmm1, xmmword ptr [r12+10h]
0x1800177d6  movups  xmm2, xmmword ptr [r10+r12]
0x1800177db  movups  xmm3, xmmword ptr [r10+r12+10h]
0x1800177e1  movups  xmm4, xmmword ptr [r12+r10*2]
0x1800177e6  movups  xmm5, xmmword ptr [r12+r10*2+10h]
0x1800177ec  movups  xmm6, xmmword ptr [rax+r12]
0x1800177f1  movups  xmm7, xmmword ptr [rax+r12+10h]
0x1800177f7  movsxd  r12, dword ptr [rbx+4]
0x1800177fb  lea     r12, [r11+r12*4]
0x1800177ff  add     rbx, 4
0x180017803  movlps  qword ptr [r13+0], xmm0
0x180017808  movlps  qword ptr [r13+8], xmm4
0x18001780d  movlps  qword ptr [r13+10h], xmm2
0x180017812  movlps  qword ptr [r13+18h], xmm6
0x180017817  movlps  qword ptr [r10+r13], xmm1
0x18001781c  movlps  qword ptr [r10+r13+8], xmm5
0x180017822  movlps  qword ptr [r10+r13+10h], xmm3
0x180017828  movlps  qword ptr [r10+r13+18h], xmm7
0x18001782e  movhps  qword ptr [r13+r10*2+0], xmm0
0x180017834  movhps  qword ptr [r13+r10*2+8], xmm4
0x18001783a  movhps  qword ptr [r13+r10*2+10h], xmm2
0x180017840  movhps  qword ptr [r13+r10*2+18h], xmm6
0x180017846  movhps  qword ptr [rax+r13], xmm1
0x18001784b  movhps  qword ptr [rax+r13+8], xmm5
0x180017851  movhps  qword ptr [rax+r13+10h], xmm3
0x180017857  movhps  qword ptr [rax+r13+18h], xmm7
0x18001785d  add     r13, 20h ; ' '
0x180017861  cmp     r13, r8
0x180017864  jnz     loc_1800177CB
0x18001786a  jmp     loc_180017A20
0x18001786f  mov     rbx, rcx
0x180017872  mov     rax, r10
0x180017875  shr     rax, 4
0x180017879  lea     rbx, [rbx+rax*4]
0x18001787d  shl     r10, 1
0x180017880  lea     rax, [r10+r10*2]
0x180017884  mov     r11, r13
0x180017887  lea     r12, [r10+r12-20h]
0x18001788c  test    r12, 0Fh
0x180017893  jnz     loc_180017940
0x180017899  test    r13, 0Fh
0x1800178a0  jnz     loc_180017940
0x1800178a6  movsxd  r13, dword ptr [rbx-4]
0x1800178aa  lea     r13, [r11+r13*4]
0x1800178ae  sub     rbx, 4
0x1800178b2  movaps  xmm0, xmmword ptr [r12]
0x1800178b7  movaps  xmm1, xmmword ptr [r12+10h]
0x1800178bd  movaps  xmm2, xmmword ptr [r10+r12]
0x1800178c2  movaps  xmm3, xmmword ptr [r10+r12+10h]
0x1800178c8  movaps  xmm4, xmmword ptr [r12+r10*2]
0x1800178cd  movaps  xmm5, xmmword ptr [r12+r10*2+10h]
0x1800178d3  movaps  xmm7, xmm0
0x1800178d6  movlhps xmm0, xmm4
0x1800178d9  movhlps xmm4, xmm7
0x1800178dc  movaps  xmm7, xmm1
0x1800178df  movlhps xmm1, xmm5
0x1800178e2  movhlps xmm5, xmm7
0x1800178e5  movaps  xmm6, xmmword ptr [rax+r12]
0x1800178ea  movaps  xmm7, xmmword ptr [rax+r12+10h]
0x1800178f0  movaps  xmmword ptr [r13+0], xmm0
0x1800178f5  movaps  xmm0, xmm2
0x1800178f8  movlhps xmm2, xmm6
0x1800178fb  movhlps xmm6, xmm0
0x1800178fe  movaps  xmm0, xmm3
0x180017901  movlhps xmm3, xmm7
0x180017904  movhlps xmm7, xmm0
0x180017907  movaps  xmmword ptr [r13+10h], xmm2
0x18001790c  movaps  xmmword ptr [r10+r13], xmm1
0x180017911  movaps  xmmword ptr [r10+r13+10h], xmm3
0x180017917  movaps  xmmword ptr [r13+r10*2+0], xmm4
0x18001791d  movaps  xmmword ptr [r13+r10*2+10h], xmm6
0x180017923  movaps  xmmword ptr [rax+r13], xmm5
0x180017928  movaps  xmmword ptr [rax+r13+10h], xmm7
0x18001792e  sub     r12, 20h ; ' '
0x180017932  cmp     r12, rdi
0x180017935  jge     loc_1800178A6
0x18001793b  jmp     loc_180017A20
0x180017940  movsxd  r13, dword ptr [rbx-4]
0x180017944  lea     r13, [r11+r13*4]
0x180017948  sub     rbx, 4
0x18001794c  movups  xmm0, xmmword ptr [r12]
0x180017951  movups  xmm1, xmmword ptr [r12+10h]
0x180017957  movups  xmm2, xmmword ptr [r10+r12]
0x18001795c  movups  xmm3, xmmword ptr [r10+r12+10h]
0x180017962  movups  xmm4, xmmword ptr [r12+r10*2]
0x180017967  movups  xmm5, xmmword ptr [r12+r10*2+10h]
0x18001796d  movups  xmm6, xmmword ptr [rax+r12]
0x180017972  movups  xmm7, xmmword ptr [rax+r12+10h]
0x180017978  movlps  qword ptr [r13+0], xmm0
0x18001797d  movlps  qword ptr [r13+8], xmm4
0x180017982  movlps  qword ptr [r13+10h], xmm2
0x180017987  movlps  qword ptr [r13+18h], xmm6
0x18001798c  movlps  qword ptr [r10+r13], xmm1
0x180017991  movlps  qword ptr [r10+r13+8], xmm5
0x180017997  movlps  qword ptr [r10+r13+10h], xmm3
0x18001799d  movlps  qword ptr [r10+r13+18h], xmm7
0x1800179a3  movhps  qword ptr [r13+r10*2+0], xmm0
0x1800179a9  movhps  qword ptr [r13+r10*2+8], xmm4
0x1800179af  movhps  qword ptr [r13+r10*2+10h], xmm2
0x1800179b5  movhps  qword ptr [r13+r10*2+18h], xmm6
0x1800179bb  movhps  qword ptr [rax+r13], xmm1
0x1800179c0  movhps  qword ptr [rax+r13+8], xmm5
0x1800179c6  movhps  qword ptr [rax+r13+10h], xmm3
0x1800179cc  movhps  qword ptr [rax+r13+18h], xmm7
0x1800179d2  sub     r12, 20h ; ' '
0x1800179d6  cmp     r12, rdi
0x1800179d9  jge     loc_180017940
0x1800179df  jmp     short loc_180017A20
0x1800179e1  movups  xmm0, xmmword ptr [r12]
0x1800179e6  movups  xmm1, xmmword ptr [r12+10h]
0x1800179ec  movups  xmm2, xmmword ptr [r12+20h]
0x1800179f2  movups  xmm3, xmmword ptr [r12+30h]
0x1800179f8  movlps  qword ptr [r13+0], xmm0
0x1800179fd  movlps  qword ptr [r13+8], xmm2
0x180017a02  movlps  qword ptr [r13+10h], xmm1
0x180017a07  movlps  qword ptr [r13+18h], xmm3
0x180017a0c  movhps  qword ptr [r13+20h], xmm0
0x180017a11  movhps  qword ptr [r13+28h], xmm2
0x180017a16  movhps  qword ptr [r13+30h], xmm1
0x180017a1b  movhps  qword ptr [r13+38h], xmm3
0x180017a20  movdqa  xmm7, [rsp+58h+var_58]
0x180017a25  movdqa  xmm6, [rsp+58h+var_48]
0x180017a2b  add     rsp, 28h
0x180017a2f  pop     r13
0x180017a31  pop     r12
0x180017a33  pop     rbp
0x180017a34  pop     rdi
0x180017a35  pop     rsi
0x180017a36  pop     rbx
0x180017a37  retn
```
