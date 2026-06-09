# m7_ipps_rDftFwdRecombine_32f

- ea: `0x18005c190`
- end: `0x18005c2be`
- name: `m7_ipps_rDftFwdRecombine_32f`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001d570`

## callees

- `0x18005c190`

## pseudocode

```c
__int64 __fastcall m7_ipps_rDftFwdRecombine_32f(float *a1, __int64 a2, __m128 *a3)
{
  __int64 result; // rax
  float v5; // xmm0_4
  float *v6; // r10
  double *v7; // r13
  double *v8; // r12
  __m128 v9; // xmm2
  __m128 v10; // xmm1
  __m128 v11; // xmm0
  __m128 v12; // xmm3
  __m128 v13; // xmm3
  __m128 v14; // xmm1
  __m128 v15; // xmm2

  result = a2;
  v5 = *a1 - a1[1];
  *a1 = a1[1] + *a1;
  a1[1] = v5;
  v6 = &a1[(a2 + 1) & 0xFFFFFFFFFFFFFFFEuLL];
  v7 = (double *)&a1[2 * a2 - 4];
  v8 = (double *)(a1 + 2);
  while ( 1 )
  {
    v9 = _mm_movelh_ps((__m128)*(unsigned __int64 *)v8, (__m128)*((unsigned __int64 *)v8 + 1));
    v10 = _mm_xor_ps(
            _mm_movelh_ps((__m128)*((unsigned __int64 *)v7 + 1), (__m128)*(unsigned __int64 *)v7),
            (__m128)xmmword_1801B7220);
    v11 = _mm_sub_ps(v9, v10);
    v12 = _mm_mul_ps(_mm_moveldup_ps(*a3), v11);
    v13 = _mm_add_ps(
            _mm_xor_ps(_mm_shuffle_ps(v12, v12, 177), (__m128)xmmword_1801B7220),
            _mm_mul_ps(_mm_movehdup_ps(*a3), v11));
    v14 = _mm_add_ps(v10, v13);
    v15 = _mm_sub_ps(_mm_xor_ps(v9, (__m128)xmmword_1801B7220), _mm_xor_ps(v13, (__m128)xmmword_1801B7220));
    _mm_storel_ps(v8, v14);
    _mm_storel_ps(v7 + 1, v15);
    ++a3;
    v8 += 2;
    v7 -= 2;
    if ( (__int64)v8 >= (__int64)v6 )
      break;
    _mm_storeh_ps(v8 - 1, v14);
    _mm_storeh_ps(v7 + 2, v15);
  }
  if ( (__int64)v8 <= (__int64)v6 )
  {
    _mm_storeh_ps(v8 - 1, v14);
    _mm_storeh_ps(v7 + 2, v15);
  }
  if ( (a2 & 1) == 0 )
    *((_DWORD *)v6 + 1) ^= 0x80000000;
  return result;
}

```

## disassembly

```asm
0x18005c190  push    rsi
0x18005c191  push    rdi
0x18005c192  push    r12
0x18005c194  push    r13
0x18005c196  sub     rsp, 28h
0x18005c19a  movdqa  [rsp+48h+var_48], xmm7
0x18005c19f  movdqa  [rsp+48h+var_38], xmm6
0x18005c1a5  mov     rdi, rcx
0x18005c1a8  mov     rsi, rdx
0x18005c1ab  mov     rdx, r8
0x18005c1ae  mov     r12, rdi
0x18005c1b1  mov     rax, rsi
0x18005c1b4  mov     r11, rdx
0x18005c1b7  movss   xmm0, dword ptr [r12]
0x18005c1bd  movss   xmm1, dword ptr [r12+4]
0x18005c1c4  addss   xmm1, xmm0
0x18005c1c8  subss   xmm0, dword ptr [r12+4]
0x18005c1cf  movss   dword ptr [r12], xmm1
0x18005c1d5  movss   dword ptr [r12+4], xmm0
0x18005c1dc  lea     r10, [rax+1]
0x18005c1e0  and     r10, 0FFFFFFFFFFFFFFFEh
0x18005c1e4  lea     r10, [r12+r10*4]
0x18005c1e8  lea     r13, ds:0[rax*2]
0x18005c1f0  lea     r13, [r12+r13*4-10h]
0x18005c1f5  add     r12, 8
0x18005c1f9  jmp     short loc_18005C20B
0x18005c200  movhps  qword ptr [r12-8], xmm1
0x18005c206  movhps  qword ptr [r13+10h], xmm2
0x18005c20b  movsd   xmm0, qword ptr [r12]
0x18005c211  movsd   xmm7, qword ptr [r12+8]
0x18005c218  movlhps xmm0, xmm7
0x18005c21b  movsd   xmm1, qword ptr [r13+8]
0x18005c221  movsd   xmm7, qword ptr [r13+0]
0x18005c227  movlhps xmm1, xmm7
0x18005c22a  movaps  xmm2, xmm0
0x18005c22d  xorps   xmm1, cs:xmmword_1801B7220
0x18005c234  subps   xmm0, xmm1
0x18005c237  movsldup xmm3, xmmword ptr [r11]
0x18005c23c  movshdup xmm4, xmmword ptr [r11]
0x18005c241  mulps   xmm3, xmm0
0x18005c244  mulps   xmm4, xmm0
0x18005c247  shufps  xmm3, xmm3, 0B1h
0x18005c24b  xorps   xmm3, cs:xmmword_1801B7220
0x18005c252  addps   xmm3, xmm4
0x18005c255  addps   xmm1, xmm3
0x18005c258  xorps   xmm2, cs:xmmword_1801B7220
0x18005c25f  xorps   xmm3, cs:xmmword_1801B7220
0x18005c266  subps   xmm2, xmm3
0x18005c269  movlps  qword ptr [r12], xmm1
0x18005c26e  movlps  qword ptr [r13+8], xmm2
0x18005c273  add     r11, 10h
0x18005c277  add     r12, 10h
0x18005c27b  sub     r13, 10h
0x18005c27f  cmp     r12, r10
0x18005c282  jl      loc_18005C200
0x18005c288  cmp     r12, r10
0x18005c28b  jg      short loc_18005C298
0x18005c28d  movhps  qword ptr [r12-8], xmm1
0x18005c293  movhps  qword ptr [r13+10h], xmm2
0x18005c298  test    rax, 1
0x18005c29e  jnz     short loc_18005C2A8
0x18005c2a0  xor     dword ptr [r10+4], 80000000h
0x18005c2a8  movdqa  xmm7, [rsp+48h+var_48]
0x18005c2ad  movdqa  xmm6, [rsp+48h+var_38]
0x18005c2b3  add     rsp, 28h
0x18005c2b7  pop     r13
0x18005c2b9  pop     r12
0x18005c2bb  pop     rdi
0x18005c2bc  pop     rsi
0x18005c2bd  retn
```
