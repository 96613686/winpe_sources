# u8_ipps_rDftInvRecombine_32f

- ea: `0x180059010`
- end: `0x180059165`
- name: `u8_ipps_rDftInvRecombine_32f`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180049fb0`

## callees

- `0x180059010`

## pseudocode

```c
__int64 __fastcall u8_ipps_rDftInvRecombine_32f(float *a1, float *a2, __int64 a3, __m128 *a4)
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
    _mm_storel_ps(v9, _mm_mul_ps((__m128)*(unsigned __int64 *)v8, (__m128)xmmword_1800B4550));
  v10 = &a1[2 * a3 - 4];
  v11 = (__int64)&a2[2 * a3 - 4];
  v12 = (unsigned __int64 *)(a1 + 2);
  v13 = (double *)(a2 + 2);
  while ( 1 )
  {
    v14 = _mm_movelh_ps((__m128)*v12, (__m128)v12[1]);
    v15 = _mm_xor_ps(
            _mm_movelh_ps((__m128)*((unsigned __int64 *)v10 + 1), (__m128)*(unsigned __int64 *)v10),
            (__m128)xmmword_1800B4540);
    v16 = _mm_sub_ps(v14, v15);
    v17 = _mm_add_ps(v14, v15);
    v18 = _mm_mul_ps(_mm_moveldup_ps(*a4), v16);
    v19 = _mm_sub_ps(
            _mm_mul_ps(_mm_movehdup_ps(*a4), v16),
            _mm_xor_ps(_mm_shuffle_ps(v18, v18, 177), (__m128)xmmword_1800B4540));
    v20 = _mm_add_ps(v17, v19);
    v21 = _mm_sub_ps(_mm_xor_ps(v17, (__m128)xmmword_1800B4540), _mm_xor_ps(v19, (__m128)xmmword_1800B4540));
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
0x180059010  push    rbx
0x180059011  push    rsi
0x180059012  push    rdi
0x180059013  push    rbp
0x180059014  push    r12
0x180059016  push    r13
0x180059018  sub     rsp, 28h
0x18005901c  movdqa  [rsp+58h+var_58], xmm7
0x180059021  movdqa  [rsp+58h+var_48], xmm6
0x180059027  mov     rdi, rcx
0x18005902a  mov     rsi, rdx
0x18005902d  mov     rdx, r8
0x180059030  mov     rcx, r9
0x180059033  mov     r12, rdi
0x180059036  mov     rbx, rsi
0x180059039  mov     rax, rdx
0x18005903c  mov     r11, rcx
0x18005903f  movss   xmm0, dword ptr [r12]
0x180059045  movss   xmm1, dword ptr [r12+4]
0x18005904c  addss   xmm1, xmm0
0x180059050  subss   xmm0, dword ptr [r12+4]
0x180059057  movss   dword ptr [rbx], xmm1
0x18005905b  movss   dword ptr [rbx+4], xmm0
0x180059060  lea     rbp, [rax+1]
0x180059064  and     rbp, 0FFFFFFFFFFFFFFFEh
0x180059068  lea     r10, [r12+rbp*4]
0x18005906c  lea     rbp, [rbx+rbp*4]
0x180059070  test    rax, 1
0x180059076  jnz     short loc_180059088
0x180059078  movsd   xmm0, qword ptr [r10]
0x18005907d  mulps   xmm0, cs:xmmword_1800B4550
0x180059084  movlps  qword ptr [rbp+0], xmm0
0x180059088  lea     rbp, ds:0[rax*2]
0x180059090  lea     r13, [r12+rbp*4-10h]
0x180059095  lea     rbp, [rbx+rbp*4-10h]
0x18005909a  add     r12, 8
0x18005909e  add     rbx, 8
0x1800590a2  jmp     short loc_1800590B8
0x1800590b0  movhps  qword ptr [rbx-8], xmm1
0x1800590b4  movhps  qword ptr [rbp+10h], xmm2
0x1800590b8  movsd   xmm0, qword ptr [r12]
0x1800590be  movsd   xmm7, qword ptr [r12+8]
0x1800590c5  movlhps xmm0, xmm7
0x1800590c8  movsd   xmm1, qword ptr [r13+8]
0x1800590ce  movsd   xmm7, qword ptr [r13+0]
0x1800590d4  movlhps xmm1, xmm7
0x1800590d7  movaps  xmm2, xmm0
0x1800590da  xorps   xmm1, cs:xmmword_1800B4540
0x1800590e1  subps   xmm0, xmm1
0x1800590e4  addps   xmm2, xmm1
0x1800590e7  movsldup xmm3, xmmword ptr [r11]
0x1800590ec  movshdup xmm4, xmmword ptr [r11]
0x1800590f1  mulps   xmm3, xmm0
0x1800590f4  mulps   xmm4, xmm0
0x1800590f7  shufps  xmm3, xmm3, 0B1h
0x1800590fb  xorps   xmm3, cs:xmmword_1800B4540
0x180059102  subps   xmm4, xmm3
0x180059105  movaps  xmm1, xmm2
0x180059108  addps   xmm1, xmm4
0x18005910b  xorps   xmm2, cs:xmmword_1800B4540
0x180059112  xorps   xmm4, cs:xmmword_1800B4540
0x180059119  subps   xmm2, xmm4
0x18005911c  movlps  qword ptr [rbx], xmm1
0x18005911f  movlps  qword ptr [rbp+8], xmm2
0x180059123  add     r11, 10h
0x180059127  add     r12, 10h
0x18005912b  sub     r13, 10h
0x18005912f  add     rbx, 10h
0x180059133  sub     rbp, 10h
0x180059137  cmp     r12, r10
0x18005913a  jl      loc_1800590B0
0x180059140  cmp     r12, r10
0x180059143  jg      short loc_18005914D
0x180059145  movhps  qword ptr [rbx-8], xmm1
0x180059149  movhps  qword ptr [rbp+10h], xmm2
0x18005914d  movdqa  xmm7, [rsp+58h+var_58]
0x180059152  movdqa  xmm6, [rsp+58h+var_48]
0x180059158  add     rsp, 28h
0x18005915c  pop     r13
0x18005915e  pop     r12
0x180059160  pop     rbp
0x180059161  pop     rdi
0x180059162  pop     rsi
0x180059163  pop     rbx
0x180059164  retn
```
