# m7_ipps_cRealRecombine_32f

- ea: `0x18002b4c0`
- end: `0x18002b5fd`
- name: `m7_ipps_cRealRecombine_32f`
- size: `317`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e560`
- `0x18000e760`

## callees

- `0x18002b4c0`

## pseudocode

```c
void __fastcall m7_ipps_cRealRecombine_32f(__int64 a1, __int64 a2, __int64 a3, __m128 *a4)
{
  __int64 v4; // r12
  __int64 v6; // r10
  double *i; // r13
  __m128 v8; // xmm1
  __m128 v9; // xmm2
  __m128 v10; // xmm0
  __m128 v11; // xmm1
  __m128 v12; // xmm4
  __m128 v13; // xmm5
  __m128 v14; // xmm3
  __m128 v15; // xmm2
  __m128 v16; // xmm0
  __m128 v17; // xmm5
  __m128 v18; // xmm4
  __m128 v19; // xmm6
  __m128 v20; // xmm7
  __m128 v21; // xmm0
  __m128 v22; // xmm7
  __m128 v23; // xmm4
  __m128 v24; // xmm6
  __m128 v25; // xmm7
  __m128 v26; // xmm0
  __m128 v27; // xmm3
  __m128 v28; // xmm6
  __m128 v29; // xmm0
  __m128 v30; // xmm5
  __m128 v31; // xmm2
  __m128 v32; // xmm5

  v4 = a1;
  v6 = a1 + 4 * a2;
  for ( i = (double *)(a1 + 8 * a2); ; _mm_storeh_ps(i, v32) )
  {
    v8 = _mm_movelh_ps((__m128)*(unsigned __int64 *)(v4 + 8), (__m128)*(unsigned __int64 *)(v4 + 16));
    v9 = _mm_movelh_ps((__m128)*(unsigned __int64 *)(v4 + 24), (__m128)*(unsigned __int64 *)(v4 + 32));
    v10 = _mm_shuffle_ps(v8, v9, 136);
    v11 = _mm_shuffle_ps(v8, v9, 221);
    v12 = _mm_movelh_ps((__m128)*((unsigned __int64 *)i - 1), (__m128)*((unsigned __int64 *)i - 2));
    v13 = _mm_movelh_ps((__m128)*((unsigned __int64 *)i - 3), (__m128)*((unsigned __int64 *)i - 4));
    v14 = _mm_shuffle_ps(v12, v13, 136);
    v15 = v10;
    v16 = _mm_sub_ps(v10, v14);
    v17 = _mm_shuffle_ps(v12, v13, 221);
    v18 = _mm_add_ps(v17, v11);
    v19 = _mm_mul_ps(*a4, v16);
    v20 = a4[1];
    v21 = _mm_mul_ps(v16, v20);
    v22 = _mm_mul_ps(v20, v18);
    v23 = _mm_add_ps(_mm_mul_ps(v18, *a4), v21);
    v24 = _mm_sub_ps(v22, v19);
    v25 = _mm_sub_ps(v24, v17);
    v26 = _mm_add_ps(v14, v23);
    a4 += 2;
    v27 = _mm_unpacklo_ps(v26, v25);
    v28 = _mm_sub_ps(v24, v11);
    _mm_storel_ps((double *)(v4 + 8), v27);
    _mm_storeh_ps((double *)(v4 + 16), v27);
    v29 = _mm_unpackhi_ps(v26, v25);
    _mm_storel_ps((double *)(v4 + 24), v29);
    v4 += 32;
    v30 = _mm_sub_ps(v15, v23);
    v31 = _mm_unpacklo_ps(v30, v28);
    _mm_storel_ps(i - 1, v31);
    _mm_storeh_ps(i - 2, v31);
    v32 = _mm_unpackhi_ps(v30, v28);
    _mm_storel_ps(i - 3, v32);
    i -= 4;
    if ( v4 == v6 )
      break;
    _mm_storeh_ps((double *)v4, v29);
  }
  *(_DWORD *)(v6 + 4) ^= 0x80000000;
}

```

## disassembly

```asm
0x18002b4c0  push    rsi
0x18002b4c1  push    rdi
0x18002b4c2  push    r12
0x18002b4c4  push    r13
0x18002b4c6  sub     rsp, 28h
0x18002b4ca  movdqa  [rsp+48h+var_48], xmm7
0x18002b4cf  movdqa  [rsp+48h+var_38], xmm6
0x18002b4d5  mov     rdi, rcx
0x18002b4d8  mov     rsi, rdx
0x18002b4db  mov     rdx, r8
0x18002b4de  mov     rcx, r9
0x18002b4e1  mov     r12, rdi
0x18002b4e4  mov     r11, rcx
0x18002b4e7  lea     r10, [r12+rsi*4]
0x18002b4eb  lea     r13, [r12+rsi*8]
0x18002b4ef  jmp     short loc_18002B50A
0x18002b500  movhps  qword ptr [r12], xmm0
0x18002b505  movhps  qword ptr [r13+0], xmm5
0x18002b50a  movsd   xmm0, qword ptr [r12+8]
0x18002b511  movsd   xmm7, qword ptr [r12+10h]
0x18002b518  movlhps xmm0, xmm7
0x18002b51b  movaps  xmm1, xmm0
0x18002b51e  movsd   xmm2, qword ptr [r12+18h]
0x18002b525  movsd   xmm7, qword ptr [r12+20h]
0x18002b52c  movlhps xmm2, xmm7
0x18002b52f  shufps  xmm0, xmm2, 88h
0x18002b533  shufps  xmm1, xmm2, 0DDh
0x18002b537  movsd   xmm3, qword ptr [r13-8]
0x18002b53d  movsd   xmm7, qword ptr [r13-10h]
0x18002b543  movlhps xmm3, xmm7
0x18002b546  movaps  xmm4, xmm3
0x18002b549  movsd   xmm5, qword ptr [r13-18h]
0x18002b54f  movsd   xmm7, qword ptr [r13-20h]
0x18002b555  movlhps xmm5, xmm7
0x18002b558  shufps  xmm3, xmm5, 88h
0x18002b55c  shufps  xmm4, xmm5, 0DDh
0x18002b560  movaps  xmm2, xmm0
0x18002b563  subps   xmm0, xmm3
0x18002b566  movaps  xmm6, xmmword ptr [r11]
0x18002b56a  movaps  xmm5, xmm4
0x18002b56d  addps   xmm4, xmm1
0x18002b570  mulps   xmm6, xmm0
0x18002b573  movaps  xmm7, xmmword ptr [r11+10h]
0x18002b578  mulps   xmm0, xmm7
0x18002b57b  mulps   xmm7, xmm4
0x18002b57e  mulps   xmm4, xmmword ptr [r11]
0x18002b582  subps   xmm7, xmm6
0x18002b585  addps   xmm4, xmm0
0x18002b588  movaps  xmm6, xmm7
0x18002b58b  subps   xmm7, xmm5
0x18002b58e  addps   xmm3, xmm4
0x18002b591  subps   xmm2, xmm4
0x18002b594  movaps  xmm0, xmm3
0x18002b597  add     r11, 20h ; ' '
0x18002b59b  unpcklps xmm3, xmm7
0x18002b59e  subps   xmm6, xmm1
0x18002b5a1  movlps  qword ptr [r12+8], xmm3
0x18002b5a7  movhps  qword ptr [r12+10h], xmm3
0x18002b5ad  unpckhps xmm0, xmm7
0x18002b5b0  movlps  qword ptr [r12+18h], xmm0
0x18002b5b6  add     r12, 20h ; ' '
0x18002b5ba  movaps  xmm5, xmm2
0x18002b5bd  unpcklps xmm2, xmm6
0x18002b5c0  movlps  qword ptr [r13-8], xmm2
0x18002b5c5  movhps  qword ptr [r13-10h], xmm2
0x18002b5ca  unpckhps xmm5, xmm6
0x18002b5cd  movlps  qword ptr [r13-18h], xmm5
0x18002b5d2  sub     r13, 20h ; ' '
0x18002b5d6  cmp     r12, r10
0x18002b5d9  jnz     loc_18002B500
0x18002b5df  xor     dword ptr [r10+4], 80000000h
0x18002b5e7  movdqa  xmm7, [rsp+48h+var_48]
0x18002b5ec  movdqa  xmm6, [rsp+48h+var_38]
0x18002b5f2  add     rsp, 28h
0x18002b5f6  pop     r13
0x18002b5f8  pop     r12
0x18002b5fa  pop     rdi
0x18002b5fb  pop     rsi
0x18002b5fc  retn
```
