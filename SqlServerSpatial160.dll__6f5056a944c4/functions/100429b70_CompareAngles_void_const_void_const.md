# CompareAngles(void const *,void const *)

- ea: `0x100429b70`
- end: `0x100429c4b`
- name: `?CompareAngles@@YAHPEBX0@Z`
- size: `219`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100429e10`

## callees

- `0x100429a30`
- `0x100429b70`

## pseudocode

```c
__int64 __fastcall CompareAngles(__m128d *a1, __m128d *a2)
{
  __m128d v2; // xmm6
  __m128d v3; // xmm8
  double v4; // xmm7_8
  double v5; // xmm9_8
  double v6; // xmm1_8
  double v7; // xmm0_8
  int v8; // eax
  int v9; // ecx
  int v10; // eax

  v2 = *a1;
  v3 = *a2;
  v4 = _mm_unpackhi_pd(v2, v2).m128d_f64[0];
  v5 = _mm_unpackhi_pd(v3, v3).m128d_f64[0];
  v6 = a2->m128d_f64[0] * v4;
  v7 = v5 * a1->m128d_f64[0];
  if ( v7 != v6 )
  {
    if ( v6 <= v7 )
      return 0xFFFFFFFFLL;
    return 1;
  }
  if ( COERCE_DOUBLE(*(_QWORD *)&v7 & _xmm) < 9.007199254740992e15 )
    goto LABEL_5;
  v8 = CompareUsingExactArithmetic();
  if ( v8 == -1 )
    return 1;
  if ( v8 == 1 )
    return 0xFFFFFFFFLL;
LABEL_5:
  v9 = 0;
  if ( v2.m128d_f64[0] != 0.0 || (v10 = 0, v4 != 0.0) )
    v10 = 1;
  if ( v3.m128d_f64[0] != 0.0 || v5 != 0.0 )
    v9 = 1;
  return (unsigned int)(v10 - v9);
}

```

## disassembly

```asm
0x100429b70  sub     rsp, 68h
0x100429b74  movaps  [rsp+68h+var_18], xmm6
0x100429b79  movups  xmm6, xmmword ptr [rcx]
0x100429b7c  movaps  [rsp+68h+var_28], xmm7
0x100429b81  movaps  [rsp+68h+var_38], xmm8
0x100429b87  movaps  xmm7, xmm6
0x100429b8a  movups  xmm8, xmmword ptr [rdx]
0x100429b8e  movaps  [rsp+68h+var_48], xmm9
0x100429b94  movaps  xmm9, xmm8
0x100429b98  unpckhpd xmm7, xmm6
0x100429b9c  unpckhpd xmm9, xmm8
0x100429ba1  movaps  xmm1, xmm8
0x100429ba5  movaps  xmm0, xmm9
0x100429ba9  mulsd   xmm1, xmm7
0x100429bad  mulsd   xmm0, xmm6
0x100429bb1  ucomisd xmm0, xmm1
0x100429bb5  jp      short loc_100429C1E
0x100429bb7  jnz     short loc_100429C1E
0x100429bb9  andps   xmm0, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x100429bc0  comisd  xmm0, cs:__real@4340000000000000
0x100429bc8  jb      short loc_100429BE7
0x100429bca  movaps  xmm3, xmm9
0x100429bce  movaps  xmm2, xmm8
0x100429bd2  movaps  xmm1, xmm7
0x100429bd5  movaps  xmm0, xmm6
0x100429bd8  call    ?CompareUsingExactArithmetic@@YA?AW4COMPARISON@RobustIntersections@@NNNN@Z; CompareUsingExactArithmetic(double,double,double,double)
0x100429bdd  cmp     eax, 0FFFFFFFFh
0x100429be0  jz      short loc_100429C24
0x100429be2  cmp     eax, 1
0x100429be5  jz      short loc_100429C2B
0x100429be7  xorps   xmm0, xmm0
0x100429bea  xor     ecx, ecx
0x100429bec  ucomisd xmm6, xmm0
0x100429bf0  jp      short loc_100429BFE
0x100429bf2  jnz     short loc_100429BFE
0x100429bf4  ucomisd xmm7, xmm0
0x100429bf8  jp      short loc_100429BFE
0x100429bfa  mov     eax, ecx
0x100429bfc  jz      short loc_100429C03
0x100429bfe  mov     eax, 1
0x100429c03  ucomisd xmm8, xmm0
0x100429c08  jp      short loc_100429C15
0x100429c0a  jnz     short loc_100429C15
0x100429c0c  ucomisd xmm9, xmm0
0x100429c11  jp      short loc_100429C15
0x100429c13  jz      short loc_100429C1A
0x100429c15  mov     ecx, 1
0x100429c1a  sub     eax, ecx
0x100429c1c  jmp     short loc_100429C30
0x100429c1e  comisd  xmm1, xmm0
0x100429c22  jbe     short loc_100429C2B
0x100429c24  mov     eax, 1
0x100429c29  jmp     short loc_100429C30
0x100429c2b  mov     eax, 0FFFFFFFFh
0x100429c30  movaps  xmm6, [rsp+68h+var_18]
0x100429c35  movaps  xmm7, [rsp+68h+var_28]
0x100429c3a  movaps  xmm8, [rsp+68h+var_38]
0x100429c40  movaps  xmm9, [rsp+68h+var_48]
0x100429c46  add     rsp, 68h
0x100429c4a  retn
```
