# CPoint3D::GetOrthonormalComplement(CPoint3D &,CPoint3D &)

- ea: `0x100426ce0`
- end: `0x100426e84`
- name: `?GetOrthonormalComplement@CPoint3D@@QEBAXAEAV1@0@Z`
- size: `420`
- prototype: `void __fastcall(CPoint3D *__hidden this, struct CPoint3D *, struct CPoint3D *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10041c700`
- `0x1004275b0`

## callees

- `0x100426ce0`
- `0x100469af8`

## pseudocode

```c
void __fastcall CPoint3D::GetOrthonormalComplement(CPoint3D *this, struct CPoint3D *a2, struct CPoint3D *a3)
{
  __m128 v4; // xmm2
  __m128 v6; // xmm3
  double v7; // xmm4_8
  double v8; // xmm6_8
  double v9; // xmm5_8
  double v11; // xmm1_8
  double v12; // xmm1_8
  __m128d v13; // xmm8
  __m128d v14; // xmm7
  double v15; // xmm6_8
  double v16; // xmm1_8
  double v17; // xmm1_8
  double v18; // xmm0_8
  __m128d v19; // xmm7
  __m128d v20; // xmm6
  double v21; // xmm3_8
  double v22; // xmm4_8
  double v23; // xmm2_8
  double v24; // xmm0_8

  v4 = (__m128)*((unsigned __int64 *)this + 1);
  v6 = (__m128)*((unsigned __int64 *)this + 2);
  *(_QWORD *)&v7 = *((_QWORD *)this + 1) & _xmm;
  v8 = *(double *)this;
  *(_QWORD *)&v9 = *((_QWORD *)this + 2) & _xmm;
  v11 = COERCE_DOUBLE(*(_QWORD *)this & _xmm) - 1.0e-12;
  if ( v11 <= v7 )
  {
    if ( v11 <= v9 )
    {
      v13 = (__m128d)_mm_xor_ps(v6, (__m128)_xmm);
      v14 = 0;
      v17 = *(double *)v6.m128_u64 * *(double *)v6.m128_u64;
      v15 = *((double *)this + 1);
    }
    else
    {
      v14 = (__m128d)_mm_xor_ps(v4, (__m128)_xmm);
      v13 = (__m128d)*(unsigned __int64 *)this;
      v17 = v8 * v8;
      v15 = 0.0;
    }
    v16 = v17 + *(double *)v4.m128_u64 * *(double *)v4.m128_u64;
  }
  else
  {
    v12 = v8 * v8;
    if ( v7 - 1.0e-12 <= v9 )
    {
      *(_QWORD *)&v15 = *(_QWORD *)&v8 ^ _xmm;
      v14 = (__m128d)*((unsigned __int64 *)this + 2);
      v13 = 0;
      v16 = v12 + *(double *)v6.m128_u64 * *(double *)v6.m128_u64;
    }
    else
    {
      v13 = (__m128d)*(unsigned __int64 *)this;
      v14 = (__m128d)_mm_xor_ps(v4, (__m128)_xmm);
      v15 = 0.0;
      v16 = v12 + *(double *)v4.m128_u64 * *(double *)v4.m128_u64;
    }
  }
  if ( v16 < 0.0 )
    v18 = sqrt_0(v16);
  else
    *(_QWORD *)&v18 = *(_OWORD *)&_mm_sqrt_pd((__m128d)*(unsigned __int64 *)&v16);
  v14.m128d_f64[0] = v14.m128d_f64[0] * (1.0 / v18);
  v13.m128d_f64[0] = v13.m128d_f64[0] * (1.0 / v18);
  *((double *)a2 + 2) = v15 * (1.0 / v18);
  v19 = _mm_unpacklo_pd(v14, v13);
  *(__m128d *)a2 = v19;
  v20 = *(__m128d *)this;
  v21 = *((double *)this + 2);
  v22 = _mm_unpackhi_pd(v20, v20).m128d_f64[0];
  v23 = _mm_unpackhi_pd(v19, v19).m128d_f64[0];
  v24 = *(double *)this * *((double *)a2 + 2);
  *(double *)a3 = *((double *)a2 + 2) * v22 - v23 * v21;
  *((double *)a3 + 2) = v20.m128d_f64[0] * v23 - v19.m128d_f64[0] * v22;
  *((double *)a3 + 1) = v19.m128d_f64[0] * v21 - v24;
}

```

## disassembly

```asm
0x100426ce0  mov     [rsp+arg_0], rbx
0x100426ce5  mov     [rsp+arg_8], rsi
0x100426cea  push    rdi
0x100426ceb  sub     rsp, 70h
0x100426cef  movsd   xmm0, qword ptr cs:__xmm@7fffffffffffffff7fffffffffffffff
0x100426cf7  mov     rsi, r8
0x100426cfa  movsd   xmm2, qword ptr [rcx+8]
0x100426cff  mov     rdi, rdx
0x100426d02  movsd   xmm3, qword ptr [rcx+10h]
0x100426d07  movaps  xmm4, xmm2
0x100426d0a  movaps  [rsp+78h+var_18], xmm6
0x100426d0f  andps   xmm4, xmm0
0x100426d12  movsd   xmm6, qword ptr [rcx]
0x100426d16  movaps  xmm5, xmm3
0x100426d19  movaps  xmm1, xmm6
0x100426d1c  movaps  [rsp+78h+var_28], xmm7
0x100426d21  andps   xmm1, xmm0
0x100426d24  movaps  [rsp+78h+var_38], xmm8
0x100426d2a  andps   xmm5, xmm0
0x100426d2d  mov     rbx, rcx
0x100426d30  movsd   xmm0, cs:__real@3d719799812dea11
0x100426d38  subsd   xmm1, xmm0
0x100426d3c  comisd  xmm1, xmm4
0x100426d40  jbe     short loc_100426D89
0x100426d42  subsd   xmm4, xmm0
0x100426d46  movaps  xmm1, xmm6
0x100426d49  mulsd   xmm1, xmm6
0x100426d4d  comisd  xmm4, xmm5
0x100426d51  jbe     short loc_100426D6E
0x100426d53  movaps  xmm7, xmm2
0x100426d56  movaps  xmm8, xmm6
0x100426d5a  xorps   xmm7, cs:__xmm@80000000000000008000000000000000
0x100426d61  xorps   xmm6, xmm6
0x100426d64  mulsd   xmm2, xmm2
0x100426d68  addsd   xmm1, xmm2
0x100426d6c  jmp     short loc_100426DCD
0x100426d6e  xorps   xmm6, cs:__xmm@80000000000000008000000000000000
0x100426d75  movaps  xmm2, xmm3
0x100426d78  mulsd   xmm2, xmm3
0x100426d7c  movaps  xmm7, xmm3
0x100426d7f  xorps   xmm8, xmm8
0x100426d83  addsd   xmm1, xmm2
0x100426d87  jmp     short loc_100426DCD
0x100426d89  comisd  xmm1, xmm5
0x100426d8d  movaps  xmm0, xmm2
0x100426d90  mulsd   xmm0, xmm2
0x100426d94  jbe     short loc_100426DB0
0x100426d96  movaps  xmm1, xmm6
0x100426d99  movaps  xmm7, xmm2
0x100426d9c  xorps   xmm7, cs:__xmm@80000000000000008000000000000000
0x100426da3  movaps  xmm8, xmm6
0x100426da7  mulsd   xmm1, xmm6
0x100426dab  xorps   xmm6, xmm6
0x100426dae  jmp     short loc_100426DC9
0x100426db0  movaps  xmm1, xmm3
0x100426db3  movaps  xmm8, xmm3
0x100426db7  xorps   xmm8, cs:__xmm@80000000000000008000000000000000
0x100426dbf  xorps   xmm7, xmm7
0x100426dc2  mulsd   xmm1, xmm3
0x100426dc6  movaps  xmm6, xmm2
0x100426dc9  addsd   xmm1, xmm0
0x100426dcd  xorps   xmm0, xmm0
0x100426dd0  ucomisd xmm0, xmm1
0x100426dd4  ja      short loc_100426DDC
0x100426dd6  sqrtpd  xmm0, xmm1
0x100426dda  jmp     short loc_100426DE4
0x100426ddc  movaps  xmm0, xmm1; X
0x100426ddf  call    sqrt_0
0x100426de4  movsd   xmm1, cs:__real@3ff0000000000000
0x100426dec  lea     r11, [rsp+78h+var_8]
0x100426df1  divsd   xmm1, xmm0
0x100426df5  mulsd   xmm6, xmm1
0x100426df9  mulsd   xmm7, xmm1
0x100426dfd  mulsd   xmm8, xmm1
0x100426e02  movsd   qword ptr [rdi+10h], xmm6
0x100426e07  unpcklpd xmm7, xmm8
0x100426e0c  movaps  xmm8, xmmword ptr [r11-30h]
0x100426e11  movaps  xmm2, xmm7
0x100426e14  movups  xmmword ptr [rdi], xmm7
0x100426e17  movups  xmm6, xmmword ptr [rbx]
0x100426e1a  movsd   xmm3, qword ptr [rbx+10h]
0x100426e1f  movsd   xmm5, qword ptr [rdi+10h]
0x100426e24  movaps  xmm4, xmm6
0x100426e27  mov     rbx, [r11+10h]
0x100426e2b  movaps  xmm1, xmm5
0x100426e2e  unpckhpd xmm4, xmm6
0x100426e32  unpckhpd xmm2, xmm7
0x100426e36  mulsd   xmm1, xmm4
0x100426e3a  movaps  xmm0, xmm2
0x100426e3d  mulsd   xmm0, xmm3
0x100426e41  subsd   xmm1, xmm0
0x100426e45  movaps  xmm0, xmm6
0x100426e48  mulsd   xmm6, xmm2
0x100426e4c  mulsd   xmm0, xmm5
0x100426e50  movsd   qword ptr [rsi], xmm1
0x100426e54  movaps  xmm1, xmm7
0x100426e57  mulsd   xmm7, xmm4
0x100426e5b  mulsd   xmm1, xmm3
0x100426e5f  subsd   xmm6, xmm7
0x100426e63  movaps  xmm7, [rsp+78h+var_28]
0x100426e68  subsd   xmm1, xmm0
0x100426e6c  movsd   qword ptr [rsi+10h], xmm6
0x100426e71  movaps  xmm6, [rsp+78h+var_18]
0x100426e76  movsd   qword ptr [rsi+8], xmm1
0x100426e7b  mov     rsi, [r11+18h]
0x100426e7f  mov     rsp, r11
0x100426e82  pop     rdi
0x100426e83  retn
```
