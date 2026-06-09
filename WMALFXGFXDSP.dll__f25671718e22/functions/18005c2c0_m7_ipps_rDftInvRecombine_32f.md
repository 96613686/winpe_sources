# m7_ipps_rDftInvRecombine_32f

- ea: `0x18005c2c0`
- end: `0x18005c415`
- name: `m7_ipps_rDftInvRecombine_32f`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001dce0`

## callees

- `0x18005c2c0`

## pseudocode

```c
__int64 __fastcall m7_ipps_rDftInvRecombine_32f(float *a1, float *a2, __int64 a3, __m128 *a4)
{
  __int64 result; // rax
  float v6; // xmm0_4
  unsigned __int64 v7; // rbp
  float *v8; // r10
  double *v9; // rbp
  float *v10; // r13
  __int64 v11; // rbp
  unsigned __int64 *v12; // r12
  double *v13; // rbx
  __m128 v14; // xmm2
  __m128 v15; // xmm1
  __m128 v16; // xmm0
  __m128 v17; // xmm2
  __m128 v18; // xmm3
  __m128 v19; // xmm4
  __m128 v20; // xmm1
  __m128 v21; // xmm2

  result = a3;
  v6 = *a1 - a1[1];
  *a2 = a1[1] + *a1;
  a2[1] = v6;
  v7 = (a3 + 1) & 0xFFFFFFFFFFFFFFFEuLL;
  v8 = &a1[v7];
  v9 = (double *)&a2[v7];
  if ( (a3 & 1) == 0 )
    _mm_storel_ps(v9, _mm_mul_ps((__m128)*(unsigned __int64 *)v8, (__m128)xmmword_1801B7230));
  v10 = &a1[2 * a3 - 4];
  v11 = (__int64)&a2[2 * a3 - 4];
  v12 = (unsigned __int64 *)(a1 + 2);
  v13 = (double *)(a2 + 2);
  while ( 1 )
  {
    v14 = _mm_movelh_ps((__m128)*v12, (__m128)v12[1]);
    v15 = _mm_xor_ps(
            _mm_movelh_ps((__m128)*((unsigned __int64 *)v10 + 1), (__m128)*(unsigned __int64 *)v10),
            (__m128)xmmword_1801B7220);
    v16 = _mm_sub_ps(v14, v15);
    v17 = _mm_add_ps(v14, v15);
    v18 = _mm_mul_ps(_mm_moveldup_ps(*a4), v16);
    v19 = _mm_sub_ps(
            _mm_mul_ps(_mm_movehdup_ps(*a4), v16),
            _mm_xor_ps(_mm_shuffle_ps(v18, v18, 177), (__m128)xmmword_1801B7220));
    v20 = _mm_add_ps(v17, v19);
    v21 = _mm_sub_ps(_mm_xor_ps(v17, (__m128)xmmword_1801B7220), _mm_xor_ps(v19, (__m128)xmmword_1801B7220));
    _mm_storel_ps(v13, v20);
    _mm_storel_ps((double *)(v11 + 8), v21);
    ++a4;
    v12 += 2;
    v10 -= 4;
    v13 += 2;
    v11 -= 16;
    if ( (__int64)v12 >= (__int64)v8 )
      break;
    _mm_storeh_ps(v13 - 1, v20);
    _mm_storeh_ps((double *)(v11 + 16), v21);
  }
  if ( (__int64)v12 <= (__int64)v8 )
  {
    _mm_storeh_ps(v13 - 1, v20);
    _mm_storeh_ps((double *)(v11 + 16), v21);
  }
  return result;
}

```

## disassembly

```asm
0x18005c2c0  push    rbx
0x18005c2c1  push    rsi
0x18005c2c2  push    rdi
0x18005c2c3  push    rbp
0x18005c2c4  push    r12
0x18005c2c6  push    r13
0x18005c2c8  sub     rsp, 28h
0x18005c2cc  movdqa  [rsp+58h+var_58], xmm7
0x18005c2d1  movdqa  [rsp+58h+var_48], xmm6
0x18005c2d7  mov     rdi, rcx
0x18005c2da  mov     rsi, rdx
0x18005c2dd  mov     rdx, r8
0x18005c2e0  mov     rcx, r9
0x18005c2e3  mov     r12, rdi
0x18005c2e6  mov     rbx, rsi
0x18005c2e9  mov     rax, rdx
0x18005c2ec  mov     r11, rcx
0x18005c2ef  movss   xmm0, dword ptr [r12]
0x18005c2f5  movss   xmm1, dword ptr [r12+4]
0x18005c2fc  addss   xmm1, xmm0
0x18005c300  subss   xmm0, dword ptr [r12+4]
0x18005c307  movss   dword ptr [rbx], xmm1
0x18005c30b  movss   dword ptr [rbx+4], xmm0
0x18005c310  lea     rbp, [rax+1]
0x18005c314  and     rbp, 0FFFFFFFFFFFFFFFEh
0x18005c318  lea     r10, [r12+rbp*4]
0x18005c31c  lea     rbp, [rbx+rbp*4]
0x18005c320  test    rax, 1
0x18005c326  jnz     short loc_18005C338
0x18005c328  movsd   xmm0, qword ptr [r10]
0x18005c32d  mulps   xmm0, cs:xmmword_1801B7230
0x18005c334  movlps  qword ptr [rbp+0], xmm0
0x18005c338  lea     rbp, ds:0[rax*2]
0x18005c340  lea     r13, [r12+rbp*4-10h]
0x18005c345  lea     rbp, [rbx+rbp*4-10h]
0x18005c34a  add     r12, 8
0x18005c34e  add     rbx, 8
0x18005c352  jmp     short loc_18005C368
0x18005c360  movhps  qword ptr [rbx-8], xmm1
0x18005c364  movhps  qword ptr [rbp+10h], xmm2
0x18005c368  movsd   xmm0, qword ptr [r12]
0x18005c36e  movsd   xmm7, qword ptr [r12+8]
0x18005c375  movlhps xmm0, xmm7
0x18005c378  movsd   xmm1, qword ptr [r13+8]
0x18005c37e  movsd   xmm7, qword ptr [r13+0]
0x18005c384  movlhps xmm1, xmm7
0x18005c387  movaps  xmm2, xmm0
0x18005c38a  xorps   xmm1, cs:xmmword_1801B7220
0x18005c391  subps   xmm0, xmm1
0x18005c394  addps   xmm2, xmm1
0x18005c397  movsldup xmm3, xmmword ptr [r11]
0x18005c39c  movshdup xmm4, xmmword ptr [r11]
0x18005c3a1  mulps   xmm3, xmm0
0x18005c3a4  mulps   xmm4, xmm0
0x18005c3a7  shufps  xmm3, xmm3, 0B1h
0x18005c3ab  xorps   xmm3, cs:xmmword_1801B7220
0x18005c3b2  subps   xmm4, xmm3
0x18005c3b5  movaps  xmm1, xmm2
0x18005c3b8  addps   xmm1, xmm4
0x18005c3bb  xorps   xmm2, cs:xmmword_1801B7220
0x18005c3c2  xorps   xmm4, cs:xmmword_1801B7220
0x18005c3c9  subps   xmm2, xmm4
0x18005c3cc  movlps  qword ptr [rbx], xmm1
0x18005c3cf  movlps  qword ptr [rbp+8], xmm2
0x18005c3d3  add     r11, 10h
0x18005c3d7  add     r12, 10h
0x18005c3db  sub     r13, 10h
0x18005c3df  add     rbx, 10h
0x18005c3e3  sub     rbp, 10h
0x18005c3e7  cmp     r12, r10
0x18005c3ea  jl      loc_18005C360
0x18005c3f0  cmp     r12, r10
0x18005c3f3  jg      short loc_18005C3FD
0x18005c3f5  movhps  qword ptr [rbx-8], xmm1
0x18005c3f9  movhps  qword ptr [rbp+10h], xmm2
0x18005c3fd  movdqa  xmm7, [rsp+58h+var_58]
0x18005c402  movdqa  xmm6, [rsp+58h+var_48]
0x18005c408  add     rsp, 28h
0x18005c40c  pop     r13
0x18005c40e  pop     r12
0x18005c410  pop     rbp
0x18005c411  pop     rdi
0x18005c412  pop     rsi
0x18005c413  pop     rbx
0x18005c414  retn
```
