# xcorr_kernel_sse

- ea: `0x180012eb0`
- end: `0x180012f90`
- name: `xcorr_kernel_sse`
- size: `224`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac10`
- `0x18000b570`
- `0x1800117c0`
- `0x180011a00`

## callees

- `0x180012eb0`

## pseudocode

```c
void __fastcall xcorr_kernel_sse(__int64 a1, __int64 a2, __m128 *a3, int a4)
{
  int v4; // r10d
  __m128 v5; // xmm6
  __m128 i; // xmm5
  __int64 v7; // rax
  __m128 v8; // xmm4
  __m128 v9; // xmm2
  __m128 v10; // xmm3
  __m128 v11; // xmm1
  __m128 v12; // xmm1
  __m128 v13; // xmm1

  v4 = 0;
  v5 = *a3;
  for ( i = 0;
        v4 < a4 - 3;
        i = _mm_add_ps(
              _mm_add_ps(i, _mm_mul_ps(_mm_shuffle_ps(v9, v10, 73), _mm_shuffle_ps(v8, v8, 85))),
              _mm_mul_ps(_mm_shuffle_ps(v8, v8, 255), v10)) )
  {
    v7 = v4;
    v4 += 4;
    v8 = *(__m128 *)(a1 + 4 * v7);
    v9 = *(__m128 *)(a2 + 4 * v7);
    v10 = *(__m128 *)(a2 + 4 * v7 + 12);
    v5 = _mm_add_ps(
           _mm_add_ps(v5, _mm_mul_ps(_mm_shuffle_ps(v8, v8, 0), v9)),
           _mm_mul_ps(_mm_shuffle_ps(v9, v10, 158), _mm_shuffle_ps(v8, v8, 170)));
  }
  if ( v4 < a4 )
  {
    v11 = (__m128)*(unsigned int *)(a1 + 4LL * v4);
    v5 = _mm_add_ps(v5, _mm_mul_ps(_mm_shuffle_ps(v11, v11, 0), *(__m128 *)(a2 + 4LL * v4)));
    if ( v4 + 1 < a4 )
    {
      v12 = (__m128)*(unsigned int *)(a1 + 4LL * v4 + 4);
      i = _mm_add_ps(i, _mm_mul_ps(_mm_shuffle_ps(v12, v12, 0), *(__m128 *)(a2 + 4LL * v4 + 4)));
      if ( v4 + 2 < a4 )
      {
        v13 = (__m128)*(unsigned int *)(a1 + 4LL * v4 + 8);
        v5 = _mm_add_ps(v5, _mm_mul_ps(_mm_shuffle_ps(v13, v13, 0), *(__m128 *)(a2 + 4LL * v4 + 8)));
      }
    }
  }
  *a3 = _mm_add_ps(i, v5);
}

```

## disassembly

```asm
0x180012eb0  push    rbx
0x180012eb2  sub     rsp, 10h
0x180012eb6  xor     r10d, r10d
0x180012eb9  movaps  [rsp+18h+var_18], xmm6
0x180012ebd  movups  xmm6, xmmword ptr [r8]
0x180012ec1  lea     r11d, [r9-3]
0x180012ec5  mov     rbx, r8
0x180012ec8  xorps   xmm5, xmm5
0x180012ecb  test    r11d, r11d
0x180012ece  jle     short loc_180012F25
0x180012ed0  movsxd  rax, r10d
0x180012ed3  add     r10d, 4
0x180012ed7  movups  xmm4, xmmword ptr [rcx+rax*4]
0x180012edb  movups  xmm2, xmmword ptr [rdx+rax*4]
0x180012edf  movaps  xmm0, xmm4
0x180012ee2  shufps  xmm0, xmm4, 0
0x180012ee6  movaps  xmm1, xmm2
0x180012ee9  mulps   xmm0, xmm2
0x180012eec  movups  xmm3, xmmword ptr [rdx+rax*4+0Ch]
0x180012ef1  shufps  xmm1, xmm3, 9Eh
0x180012ef5  addps   xmm6, xmm0
0x180012ef8  shufps  xmm2, xmm3, 49h ; 'I'
0x180012efc  movaps  xmm0, xmm4
0x180012eff  shufps  xmm0, xmm4, 0AAh
0x180012f03  mulps   xmm1, xmm0
0x180012f06  movaps  xmm0, xmm4
0x180012f09  shufps  xmm0, xmm4, 55h ; 'U'
0x180012f0d  mulps   xmm2, xmm0
0x180012f10  shufps  xmm4, xmm4, 0FFh
0x180012f14  addps   xmm6, xmm1
0x180012f17  mulps   xmm4, xmm3
0x180012f1a  addps   xmm5, xmm2
0x180012f1d  addps   xmm5, xmm4
0x180012f20  cmp     r10d, r11d
0x180012f23  jl      short loc_180012ED0
0x180012f25  cmp     r10d, r9d
0x180012f28  jge     short loc_180012F80
0x180012f2a  movsxd  r8, r10d
0x180012f2d  lea     eax, [r10+1]
0x180012f31  movss   xmm1, dword ptr [rcx+r8*4]
0x180012f37  shufps  xmm1, xmm1, 0
0x180012f3b  movups  xmm0, xmmword ptr [rdx+r8*4]
0x180012f40  mulps   xmm1, xmm0
0x180012f43  addps   xmm6, xmm1
0x180012f46  cmp     eax, r9d
0x180012f49  jge     short loc_180012F80
0x180012f4b  movss   xmm1, dword ptr [rcx+r8*4+4]
0x180012f52  inc     eax
0x180012f54  shufps  xmm1, xmm1, 0
0x180012f58  movups  xmm0, xmmword ptr [rdx+r8*4+4]
0x180012f5e  mulps   xmm1, xmm0
0x180012f61  addps   xmm5, xmm1
0x180012f64  cmp     eax, r9d
0x180012f67  jge     short loc_180012F80
0x180012f69  movss   xmm1, dword ptr [rcx+r8*4+8]
0x180012f70  movups  xmm0, xmmword ptr [rdx+r8*4+8]
0x180012f76  shufps  xmm1, xmm1, 0
0x180012f7a  mulps   xmm1, xmm0
0x180012f7d  addps   xmm6, xmm1
0x180012f80  addps   xmm5, xmm6
0x180012f83  movaps  xmm6, [rsp+18h+var_18]
0x180012f87  movups  xmmword ptr [rbx], xmm5
0x180012f8a  add     rsp, 10h
0x180012f8e  pop     rbx
0x180012f8f  retn
```
