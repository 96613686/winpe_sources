# u8_ipps_rDftFwdRecombine_32f

- ea: `0x180058ee0`
- end: `0x18005900e`
- name: `u8_ipps_rDftFwdRecombine_32f`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180049840`

## callees

- `0x180058ee0`

## pseudocode

```c
__int64 __fastcall u8_ipps_rDftFwdRecombine_32f(float *a1, __int64 a2, __m128 *a3)
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
            (__m128)xmmword_1800B4540);
    v11 = _mm_sub_ps(v9, v10);
    v12 = _mm_mul_ps(_mm_moveldup_ps(*a3), v11);
    v13 = _mm_add_ps(
            _mm_xor_ps(_mm_shuffle_ps(v12, v12, 177), (__m128)xmmword_1800B4540),
            _mm_mul_ps(_mm_movehdup_ps(*a3), v11));
    v14 = _mm_add_ps(v10, v13);
    v15 = _mm_sub_ps(_mm_xor_ps(v9, (__m128)xmmword_1800B4540), _mm_xor_ps(v13, (__m128)xmmword_1800B4540));
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
0x180058ee0  push    rsi
0x180058ee1  push    rdi
0x180058ee2  push    r12
0x180058ee4  push    r13
0x180058ee6  sub     rsp, 28h
0x180058eea  movdqa  [rsp+48h+var_48], xmm7
0x180058eef  movdqa  [rsp+48h+var_38], xmm6
0x180058ef5  mov     rdi, rcx
0x180058ef8  mov     rsi, rdx
0x180058efb  mov     rdx, r8
0x180058efe  mov     r12, rdi
0x180058f01  mov     rax, rsi
0x180058f04  mov     r11, rdx
0x180058f07  movss   xmm0, dword ptr [r12]
0x180058f0d  movss   xmm1, dword ptr [r12+4]
0x180058f14  addss   xmm1, xmm0
0x180058f18  subss   xmm0, dword ptr [r12+4]
0x180058f1f  movss   dword ptr [r12], xmm1
0x180058f25  movss   dword ptr [r12+4], xmm0
0x180058f2c  lea     r10, [rax+1]
0x180058f30  and     r10, 0FFFFFFFFFFFFFFFEh
0x180058f34  lea     r10, [r12+r10*4]
0x180058f38  lea     r13, ds:0[rax*2]
0x180058f40  lea     r13, [r12+r13*4-10h]
0x180058f45  add     r12, 8
0x180058f49  jmp     short loc_180058F5B
0x180058f50  movhps  qword ptr [r12-8], xmm1
0x180058f56  movhps  qword ptr [r13+10h], xmm2
0x180058f5b  movsd   xmm0, qword ptr [r12]
0x180058f61  movsd   xmm7, qword ptr [r12+8]
0x180058f68  movlhps xmm0, xmm7
0x180058f6b  movsd   xmm1, qword ptr [r13+8]
0x180058f71  movsd   xmm7, qword ptr [r13+0]
0x180058f77  movlhps xmm1, xmm7
0x180058f7a  movaps  xmm2, xmm0
0x180058f7d  xorps   xmm1, cs:xmmword_1800B4540
0x180058f84  subps   xmm0, xmm1
0x180058f87  movsldup xmm3, xmmword ptr [r11]
0x180058f8c  movshdup xmm4, xmmword ptr [r11]
0x180058f91  mulps   xmm3, xmm0
0x180058f94  mulps   xmm4, xmm0
0x180058f97  shufps  xmm3, xmm3, 0B1h
0x180058f9b  xorps   xmm3, cs:xmmword_1800B4540
0x180058fa2  addps   xmm3, xmm4
0x180058fa5  addps   xmm1, xmm3
0x180058fa8  xorps   xmm2, cs:xmmword_1800B4540
0x180058faf  xorps   xmm3, cs:xmmword_1800B4540
0x180058fb6  subps   xmm2, xmm3
0x180058fb9  movlps  qword ptr [r12], xmm1
0x180058fbe  movlps  qword ptr [r13+8], xmm2
0x180058fc3  add     r11, 10h
0x180058fc7  add     r12, 10h
0x180058fcb  sub     r13, 10h
0x180058fcf  cmp     r12, r10
0x180058fd2  jl      loc_180058F50
0x180058fd8  cmp     r12, r10
0x180058fdb  jg      short loc_180058FE8
0x180058fdd  movhps  qword ptr [r12-8], xmm1
0x180058fe3  movhps  qword ptr [r13+10h], xmm2
0x180058fe8  test    rax, 1
0x180058fee  jnz     short loc_180058FF8
0x180058ff0  xor     dword ptr [r10+4], 80000000h
0x180058ff8  movdqa  xmm7, [rsp+48h+var_48]
0x180058ffd  movdqa  xmm6, [rsp+48h+var_38]
0x180059003  add     rsp, 28h
0x180059007  pop     r13
0x180059009  pop     r12
0x18005900b  pop     rdi
0x18005900c  pop     rsi
0x18005900d  retn
```
