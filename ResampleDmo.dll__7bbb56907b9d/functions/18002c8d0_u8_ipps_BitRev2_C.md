# u8_ipps_BitRev2_C

- ea: `0x18002c8d0`
- end: `0x18002cc48`
- name: `u8_ipps_BitRev2_C`
- size: `888`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f680`
- `0x18000f820`
- `0x18000fa20`
- `0x180010490`
- `0x1800406c0`
- `0x1800407c0`

## callees

- `0x18002c8d0`

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
0x18002c8d0  push    rbx
0x18002c8d1  push    rsi
0x18002c8d2  push    rdi
0x18002c8d3  push    rbp
0x18002c8d4  push    r12
0x18002c8d6  push    r13
0x18002c8d8  sub     rsp, 28h
0x18002c8dc  movdqa  [rsp+58h+var_58], xmm7
0x18002c8e1  movdqa  [rsp+58h+var_48], xmm6
0x18002c8e7  mov     rdi, rcx
0x18002c8ea  mov     rsi, rdx
0x18002c8ed  mov     rdx, r8
0x18002c8f0  mov     rcx, r9
0x18002c8f3  mov     r12, rdi
0x18002c8f6  mov     r13, rsi
0x18002c8f9  mov     r10, rdx
0x18002c8fc  cmp     r10, 8
0x18002c900  jz      loc_18002CBF1
0x18002c906  cmp     r10, 10000h
0x18002c90d  jle     loc_18002CA7F
0x18002c913  mov     rbx, rcx
0x18002c916  mov     r11, r12
0x18002c919  shl     r10, 1
0x18002c91c  lea     rax, [r10+r13]
0x18002c920  mov     r8, rax
0x18002c923  lea     rax, [r10+r10*2]
0x18002c927  test    r12, 0Fh
0x18002c92e  jnz     loc_18002C9DB
0x18002c934  test    r13, 0Fh
0x18002c93b  jnz     loc_18002C9DB
0x18002c941  movaps  xmm0, xmmword ptr [r12]
0x18002c946  movaps  xmm1, xmmword ptr [r12+10h]
0x18002c94c  movaps  xmm2, xmmword ptr [r10+r12]
0x18002c951  movaps  xmm3, xmmword ptr [r10+r12+10h]
0x18002c957  movaps  xmm4, xmmword ptr [r12+r10*2]
0x18002c95c  movaps  xmm5, xmmword ptr [r12+r10*2+10h]
0x18002c962  movaps  xmm7, xmm0
0x18002c965  movlhps xmm0, xmm4
0x18002c968  movhlps xmm4, xmm7
0x18002c96b  movaps  xmm7, xmm1
0x18002c96e  movlhps xmm1, xmm5
0x18002c971  movhlps xmm5, xmm7
0x18002c974  movaps  xmm6, xmmword ptr [rax+r12]
0x18002c979  movaps  xmm7, xmmword ptr [rax+r12+10h]
0x18002c97f  movsxd  r12, dword ptr [rbx+4]
0x18002c983  lea     r12, [r11+r12*4]
0x18002c987  add     rbx, 4
0x18002c98b  movaps  xmmword ptr [r13+0], xmm0
0x18002c990  movaps  xmm0, xmm2
0x18002c993  movlhps xmm2, xmm6
0x18002c996  movhlps xmm6, xmm0
0x18002c999  movaps  xmm0, xmm3
0x18002c99c  movlhps xmm3, xmm7
0x18002c99f  movhlps xmm7, xmm0
0x18002c9a2  movaps  xmmword ptr [r13+10h], xmm2
0x18002c9a7  movaps  xmmword ptr [r10+r13], xmm1
0x18002c9ac  movaps  xmmword ptr [r10+r13+10h], xmm3
0x18002c9b2  movaps  xmmword ptr [r13+r10*2+0], xmm4
0x18002c9b8  movaps  xmmword ptr [r13+r10*2+10h], xmm6
0x18002c9be  movaps  xmmword ptr [rax+r13], xmm5
0x18002c9c3  movaps  xmmword ptr [rax+r13+10h], xmm7
0x18002c9c9  add     r13, 20h ; ' '
0x18002c9cd  cmp     r13, r8
0x18002c9d0  jnz     loc_18002C941
0x18002c9d6  jmp     loc_18002CC30
0x18002c9db  movups  xmm0, xmmword ptr [r12]
0x18002c9e0  movups  xmm1, xmmword ptr [r12+10h]
0x18002c9e6  movups  xmm2, xmmword ptr [r10+r12]
0x18002c9eb  movups  xmm3, xmmword ptr [r10+r12+10h]
0x18002c9f1  movups  xmm4, xmmword ptr [r12+r10*2]
0x18002c9f6  movups  xmm5, xmmword ptr [r12+r10*2+10h]
0x18002c9fc  movups  xmm6, xmmword ptr [rax+r12]
0x18002ca01  movups  xmm7, xmmword ptr [rax+r12+10h]
0x18002ca07  movsxd  r12, dword ptr [rbx+4]
0x18002ca0b  lea     r12, [r11+r12*4]
0x18002ca0f  add     rbx, 4
0x18002ca13  movlps  qword ptr [r13+0], xmm0
0x18002ca18  movlps  qword ptr [r13+8], xmm4
0x18002ca1d  movlps  qword ptr [r13+10h], xmm2
0x18002ca22  movlps  qword ptr [r13+18h], xmm6
0x18002ca27  movlps  qword ptr [r10+r13], xmm1
0x18002ca2c  movlps  qword ptr [r10+r13+8], xmm5
0x18002ca32  movlps  qword ptr [r10+r13+10h], xmm3
0x18002ca38  movlps  qword ptr [r10+r13+18h], xmm7
0x18002ca3e  movhps  qword ptr [r13+r10*2+0], xmm0
0x18002ca44  movhps  qword ptr [r13+r10*2+8], xmm4
0x18002ca4a  movhps  qword ptr [r13+r10*2+10h], xmm2
0x18002ca50  movhps  qword ptr [r13+r10*2+18h], xmm6
0x18002ca56  movhps  qword ptr [rax+r13], xmm1
0x18002ca5b  movhps  qword ptr [rax+r13+8], xmm5
0x18002ca61  movhps  qword ptr [rax+r13+10h], xmm3
0x18002ca67  movhps  qword ptr [rax+r13+18h], xmm7
0x18002ca6d  add     r13, 20h ; ' '
0x18002ca71  cmp     r13, r8
0x18002ca74  jnz     loc_18002C9DB
0x18002ca7a  jmp     loc_18002CC30
0x18002ca7f  mov     rbx, rcx
0x18002ca82  mov     rax, r10
0x18002ca85  shr     rax, 4
0x18002ca89  lea     rbx, [rbx+rax*4]
0x18002ca8d  shl     r10, 1
0x18002ca90  lea     rax, [r10+r10*2]
0x18002ca94  mov     r11, r13
0x18002ca97  lea     r12, [r10+r12-20h]
0x18002ca9c  test    r12, 0Fh
0x18002caa3  jnz     loc_18002CB50
0x18002caa9  test    r13, 0Fh
0x18002cab0  jnz     loc_18002CB50
0x18002cab6  movsxd  r13, dword ptr [rbx-4]
0x18002caba  lea     r13, [r11+r13*4]
0x18002cabe  sub     rbx, 4
0x18002cac2  movaps  xmm0, xmmword ptr [r12]
0x18002cac7  movaps  xmm1, xmmword ptr [r12+10h]
0x18002cacd  movaps  xmm2, xmmword ptr [r10+r12]
0x18002cad2  movaps  xmm3, xmmword ptr [r10+r12+10h]
0x18002cad8  movaps  xmm4, xmmword ptr [r12+r10*2]
0x18002cadd  movaps  xmm5, xmmword ptr [r12+r10*2+10h]
0x18002cae3  movaps  xmm7, xmm0
0x18002cae6  movlhps xmm0, xmm4
0x18002cae9  movhlps xmm4, xmm7
0x18002caec  movaps  xmm7, xmm1
0x18002caef  movlhps xmm1, xmm5
0x18002caf2  movhlps xmm5, xmm7
0x18002caf5  movaps  xmm6, xmmword ptr [rax+r12]
0x18002cafa  movaps  xmm7, xmmword ptr [rax+r12+10h]
0x18002cb00  movaps  xmmword ptr [r13+0], xmm0
0x18002cb05  movaps  xmm0, xmm2
0x18002cb08  movlhps xmm2, xmm6
0x18002cb0b  movhlps xmm6, xmm0
0x18002cb0e  movaps  xmm0, xmm3
0x18002cb11  movlhps xmm3, xmm7
0x18002cb14  movhlps xmm7, xmm0
0x18002cb17  movaps  xmmword ptr [r13+10h], xmm2
0x18002cb1c  movaps  xmmword ptr [r10+r13], xmm1
0x18002cb21  movaps  xmmword ptr [r10+r13+10h], xmm3
0x18002cb27  movaps  xmmword ptr [r13+r10*2+0], xmm4
0x18002cb2d  movaps  xmmword ptr [r13+r10*2+10h], xmm6
0x18002cb33  movaps  xmmword ptr [rax+r13], xmm5
0x18002cb38  movaps  xmmword ptr [rax+r13+10h], xmm7
0x18002cb3e  sub     r12, 20h ; ' '
0x18002cb42  cmp     r12, rdi
0x18002cb45  jge     loc_18002CAB6
0x18002cb4b  jmp     loc_18002CC30
0x18002cb50  movsxd  r13, dword ptr [rbx-4]
0x18002cb54  lea     r13, [r11+r13*4]
0x18002cb58  sub     rbx, 4
0x18002cb5c  movups  xmm0, xmmword ptr [r12]
0x18002cb61  movups  xmm1, xmmword ptr [r12+10h]
0x18002cb67  movups  xmm2, xmmword ptr [r10+r12]
0x18002cb6c  movups  xmm3, xmmword ptr [r10+r12+10h]
0x18002cb72  movups  xmm4, xmmword ptr [r12+r10*2]
0x18002cb77  movups  xmm5, xmmword ptr [r12+r10*2+10h]
0x18002cb7d  movups  xmm6, xmmword ptr [rax+r12]
0x18002cb82  movups  xmm7, xmmword ptr [rax+r12+10h]
0x18002cb88  movlps  qword ptr [r13+0], xmm0
0x18002cb8d  movlps  qword ptr [r13+8], xmm4
0x18002cb92  movlps  qword ptr [r13+10h], xmm2
0x18002cb97  movlps  qword ptr [r13+18h], xmm6
0x18002cb9c  movlps  qword ptr [r10+r13], xmm1
0x18002cba1  movlps  qword ptr [r10+r13+8], xmm5
0x18002cba7  movlps  qword ptr [r10+r13+10h], xmm3
0x18002cbad  movlps  qword ptr [r10+r13+18h], xmm7
0x18002cbb3  movhps  qword ptr [r13+r10*2+0], xmm0
0x18002cbb9  movhps  qword ptr [r13+r10*2+8], xmm4
0x18002cbbf  movhps  qword ptr [r13+r10*2+10h], xmm2
0x18002cbc5  movhps  qword ptr [r13+r10*2+18h], xmm6
0x18002cbcb  movhps  qword ptr [rax+r13], xmm1
0x18002cbd0  movhps  qword ptr [rax+r13+8], xmm5
0x18002cbd6  movhps  qword ptr [rax+r13+10h], xmm3
0x18002cbdc  movhps  qword ptr [rax+r13+18h], xmm7
0x18002cbe2  sub     r12, 20h ; ' '
0x18002cbe6  cmp     r12, rdi
0x18002cbe9  jge     loc_18002CB50
0x18002cbef  jmp     short loc_18002CC30
0x18002cbf1  movups  xmm0, xmmword ptr [r12]
0x18002cbf6  movups  xmm1, xmmword ptr [r12+10h]
0x18002cbfc  movups  xmm2, xmmword ptr [r12+20h]
0x18002cc02  movups  xmm3, xmmword ptr [r12+30h]
0x18002cc08  movlps  qword ptr [r13+0], xmm0
0x18002cc0d  movlps  qword ptr [r13+8], xmm2
0x18002cc12  movlps  qword ptr [r13+10h], xmm1
0x18002cc17  movlps  qword ptr [r13+18h], xmm3
0x18002cc1c  movhps  qword ptr [r13+20h], xmm0
0x18002cc21  movhps  qword ptr [r13+28h], xmm2
0x18002cc26  movhps  qword ptr [r13+30h], xmm1
0x18002cc2b  movhps  qword ptr [r13+38h], xmm3
0x18002cc30  movdqa  xmm7, [rsp+58h+var_58]
0x18002cc35  movdqa  xmm6, [rsp+58h+var_48]
0x18002cc3b  add     rsp, 28h
0x18002cc3f  pop     r13
0x18002cc41  pop     r12
0x18002cc43  pop     rbp
0x18002cc44  pop     rdi
0x18002cc45  pop     rsi
0x18002cc46  pop     rbx
0x18002cc47  retn
```
