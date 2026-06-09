# celt_inner_prod_sse

- ea: `0x180012b80`
- end: `0x180012c49`
- name: `celt_inner_prod_sse`
- size: `201`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac10`
- `0x18000b570`
- `0x18000e400`
- `0x180012720`
- `0x180012860`

## callees

- `0x180012b80`

## pseudocode

```c
__m128 __fastcall celt_inner_prod_sse(__int64 a1, __int64 a2, int a3)
{
  int v3; // r9d
  int v4; // r10d
  __m128 i; // xmm2
  __int64 v6; // rax
  __m128 v7; // xmm1
  __int64 v8; // rax
  __int128 v9; // xmm2
  __m128 result; // xmm0
  __int64 v11; // rax

  v3 = 0;
  v4 = a3 - 3;
  for ( i = 0; v3 < v4; i = _mm_add_ps(i, _mm_mul_ps(*(__m128 *)(a1 + 4 * v6), *(__m128 *)(a2 + 4 * v6))) )
  {
    v6 = v3;
    v3 += 4;
  }
  v7 = _mm_add_ps(_mm_movehl_ps(i, i), i);
  v7.m128_f32[0] = v7.m128_f32[0] + _mm_shuffle_ps(v7, v7, 85).m128_f32[0];
  if ( v3 >= a3 )
  {
    return v7;
  }
  else
  {
    if ( a3 - v3 < 4 )
      goto LABEL_13;
    do
    {
      v8 = v3;
      v3 += 4;
      v9 = *(unsigned int *)(a1 + 4 * v8);
      *(float *)&v9 = (float)((float)((float)((float)(*(float *)&v9 * *(float *)(a2 + 4 * v8)) + v7.m128_f32[0])
                                    + (float)(*(float *)(a1 + 4 * v8 + 4) * *(float *)(a2 + 4 * v8 + 4)))
                            + (float)(*(float *)(a1 + 4 * v8 + 8) * *(float *)(a2 + 4 * v8 + 8)))
                    + (float)(*(float *)(a1 + 4 * v8 + 12) * *(float *)(a2 + 4 * v8 + 12));
      v7.m128_i32[0] = v9;
    }
    while ( v3 < v4 );
    if ( v3 < a3 )
    {
LABEL_13:
      do
      {
        v11 = v3++;
        result = (__m128)*(unsigned int *)(a1 + 4 * v11);
        result.m128_f32[0] = (float)(result.m128_f32[0] * *(float *)(a2 + 4 * v11)) + v7.m128_f32[0];
        v7.m128_i32[0] = result.m128_i32[0];
      }
      while ( v3 < a3 );
    }
    else
    {
      return (__m128)v9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180012b80  xor     r9d, r9d
0x180012b83  lea     r10d, [r8-3]
0x180012b87  xorps   xmm2, xmm2
0x180012b8a  test    r10d, r10d
0x180012b8d  jle     short loc_180012BAA
0x180012b8f  nop
0x180012b90  movsxd  rax, r9d
0x180012b93  add     r9d, 4
0x180012b97  movups  xmm1, xmmword ptr [rcx+rax*4]
0x180012b9b  movups  xmm0, xmmword ptr [rdx+rax*4]
0x180012b9f  mulps   xmm1, xmm0
0x180012ba2  addps   xmm2, xmm1
0x180012ba5  cmp     r9d, r10d
0x180012ba8  jl      short loc_180012B90
0x180012baa  movaps  xmm1, xmm2
0x180012bad  movhlps xmm1, xmm2
0x180012bb0  addps   xmm1, xmm2
0x180012bb3  movaps  xmm0, xmm1
0x180012bb6  shufps  xmm0, xmm1, 55h ; 'U'
0x180012bba  addss   xmm1, xmm0
0x180012bbe  cmp     r9d, r8d
0x180012bc1  jge     loc_180012C45
0x180012bc7  mov     eax, r8d
0x180012bca  sub     eax, r9d
0x180012bcd  cmp     eax, 4
0x180012bd0  jl      short loc_180012C28
0x180012bd2  movsxd  rax, r9d
0x180012bd5  add     r9d, 4
0x180012bd9  movss   xmm2, dword ptr [rcx+rax*4]
0x180012bde  mulss   xmm2, dword ptr [rdx+rax*4]
0x180012be3  movss   xmm0, dword ptr [rcx+rax*4+4]
0x180012be9  mulss   xmm0, dword ptr [rdx+rax*4+4]
0x180012bef  addss   xmm2, xmm1
0x180012bf3  movss   xmm1, dword ptr [rcx+rax*4+8]
0x180012bf9  mulss   xmm1, dword ptr [rdx+rax*4+8]
0x180012bff  addss   xmm2, xmm0
0x180012c03  movss   xmm0, dword ptr [rcx+rax*4+0Ch]
0x180012c09  mulss   xmm0, dword ptr [rdx+rax*4+0Ch]
0x180012c0f  addss   xmm2, xmm1
0x180012c13  addss   xmm2, xmm0
0x180012c17  movaps  xmm1, xmm2
0x180012c1a  cmp     r9d, r10d
0x180012c1d  jl      short loc_180012BD2
0x180012c1f  cmp     r9d, r8d
0x180012c22  jl      short loc_180012C28
0x180012c24  movaps  xmm0, xmm2
0x180012c27  retn
0x180012c28  movsxd  rax, r9d
0x180012c2b  inc     r9d
0x180012c2e  movss   xmm0, dword ptr [rcx+rax*4]
0x180012c33  mulss   xmm0, dword ptr [rdx+rax*4]
0x180012c38  addss   xmm0, xmm1
0x180012c3c  movaps  xmm1, xmm0
0x180012c3f  cmp     r9d, r8d
0x180012c42  jl      short loc_180012C28
0x180012c44  retn
0x180012c45  movaps  xmm0, xmm1
0x180012c48  retn
```
