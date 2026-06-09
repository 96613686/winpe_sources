# comb_filter_const_sse

- ea: `0x180012c50`
- end: `0x180012d01`
- name: `comb_filter_const_sse`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800089b0`

## callees

- `0x180012c50`

## pseudocode

```c
__int64 __fastcall comb_filter_const_sse(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7)
{
  int v8; // r9d
  __int64 result; // rax
  int v10; // ecx
  __m128 v11; // xmm4
  __m128 v12; // xmm5
  __m128 v13; // xmm6
  __m128 i; // xmm7
  __m128 v15; // xmm1
  __m128 v16; // xmm3
  __m128 v17; // xmm2
  __m128 v18; // xmm0

  v8 = a4 - 3;
  result = -2 - a3;
  v10 = 0;
  v11 = _mm_shuffle_ps((__m128)a5, (__m128)a5, 0);
  v12 = _mm_shuffle_ps((__m128)a6, (__m128)a6, 0);
  v13 = _mm_shuffle_ps((__m128)a7, (__m128)a7, 0);
  for ( i = *(__m128 *)(a2 + 4 * result);
        v10 < v8;
        *(__m128 *)(a1 + 4 * result) = _mm_add_ps(
                                         _mm_add_ps(_mm_mul_ps(v16, v11), *(__m128 *)(a2 + 4 * result)),
                                         _mm_add_ps(_mm_mul_ps(v17, v12), _mm_mul_ps(v18, v13))) )
  {
    v15 = *(__m128 *)(a2 + 4LL * (v10 - a3) + 8);
    result = v10;
    v10 += 4;
    v16 = _mm_shuffle_ps(i, v15, 78);
    v17 = _mm_add_ps(_mm_shuffle_ps(v16, v15, 153), _mm_shuffle_ps(i, v16, 153));
    v18 = _mm_add_ps(v15, i);
    i = v15;
  }
  return result;
}

```

## disassembly

```asm
0x180012c50  sub     rsp, 28h
0x180012c54  movss   xmm4, [rsp+28h+arg_20]
0x180012c5a  mov     eax, 0FFFFFFFEh
0x180012c5f  movss   xmm5, [rsp+28h+arg_28]
0x180012c65  sub     eax, r8d
0x180012c68  movaps  [rsp+28h+var_18], xmm6
0x180012c6d  mov     r10, rcx
0x180012c70  movss   xmm6, [rsp+28h+arg_30]
0x180012c76  add     r9d, 0FFFFFFFDh
0x180012c7a  cdqe
0x180012c7c  xor     ecx, ecx
0x180012c7e  movaps  [rsp+28h+var_28], xmm7
0x180012c82  shufps  xmm4, xmm4, 0
0x180012c86  shufps  xmm5, xmm5, 0
0x180012c8a  shufps  xmm6, xmm6, 0
0x180012c8e  movups  xmm7, xmmword ptr [rdx+rax*4]
0x180012c92  test    r9d, r9d
0x180012c95  jle     short loc_180012CF3
0x180012c97  nop     word ptr [rax+rax+00000000h]
0x180012ca0  mov     eax, ecx
0x180012ca2  movaps  xmm3, xmm7
0x180012ca5  sub     eax, r8d
0x180012ca8  movaps  xmm0, xmm7
0x180012cab  cdqe
0x180012cad  movups  xmm1, xmmword ptr [rdx+rax*4+8]
0x180012cb2  movsxd  rax, ecx
0x180012cb5  add     ecx, 4
0x180012cb8  shufps  xmm3, xmm1, 4Eh ; 'N'
0x180012cbc  shufps  xmm0, xmm3, 99h
0x180012cc0  movaps  xmm2, xmm3
0x180012cc3  shufps  xmm2, xmm1, 99h
0x180012cc7  mulps   xmm3, xmm4
0x180012cca  addps   xmm2, xmm0
0x180012ccd  movaps  xmm0, xmm1
0x180012cd0  addps   xmm0, xmm7
0x180012cd3  movaps  xmm7, xmm1
0x180012cd6  mulps   xmm2, xmm5
0x180012cd9  mulps   xmm0, xmm6
0x180012cdc  addps   xmm2, xmm0
0x180012cdf  movups  xmm0, xmmword ptr [rdx+rax*4]
0x180012ce3  addps   xmm3, xmm0
0x180012ce6  addps   xmm3, xmm2
0x180012ce9  movups  xmmword ptr [r10+rax*4], xmm3
0x180012cee  cmp     ecx, r9d
0x180012cf1  jl      short loc_180012CA0
0x180012cf3  movaps  xmm6, [rsp+28h+var_18]
0x180012cf8  movaps  xmm7, [rsp+28h+var_28]
0x180012cfc  add     rsp, 28h
0x180012d00  retn
```
