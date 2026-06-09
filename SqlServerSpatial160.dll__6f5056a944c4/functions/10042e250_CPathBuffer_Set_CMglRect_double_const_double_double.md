# CPathBuffer::Set(CMglRect<double> const &,double,double)

- ea: `0x10042e250`
- end: `0x10042e452`
- name: `?Set@CPathBuffer@@QEAAJAEBV?$CMglRect@N@@NN@Z`
- size: `514`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x10040f200`

## callees

- `0x10042e250`
- `0x100432b80`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!_finite` at `0x10042e30d`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x10042e386`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x10042e30d`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x10042e386`

## pseudocode

```c
__int64 __fastcall CPathBuffer::Set(__int64 a1, double *a2, double a3, double a4)
{
  __int128 v5; // xmm11
  __int128 v6; // xmm12
  __int64 result; // rax
  double v8; // xmm6_8
  double v9; // xmm1_8
  double v10; // xmm1_8
  double v11; // xmm6_8
  double v12; // xmm6_8
  __int64 v13; // rax
  double v14; // [rsp+20h] [rbp-88h] BYREF
  double v15; // [rsp+28h] [rbp-80h]
  double v16; // [rsp+30h] [rbp-78h]
  double v17; // [rsp+38h] [rbp-70h]
  int v18; // [rsp+B0h] [rbp+8h] BYREF

  v5 = *(_OWORD *)a2;
  v6 = *((_OWORD *)a2 + 1);
  *(double *)&v5 = *a2 - a3 * 1.000001;
  *(double *)&v6 = *(double *)&v6 - a3 * 1.000001;
  v14 = *(double *)&v5;
  v16 = *(double *)&v6;
  v15 = *((double *)&v5 + 1) + a3 * 1.000001;
  v17 = *((double *)&v6 + 1) + a3 * 1.000001;
  result = CWorkspaceTransform::SetWithScaleFactor(a1 + 392, &v14);
  if ( (int)result >= 0 )
  {
    v8 = fmax(
           *((double *)&v5 + 1) + a3 * 1.000001 - *(double *)&v5,
           *((double *)&v6 + 1) + a3 * 1.000001 - *(double *)&v6);
    if ( !_finite(v8) )
      v8 = DOUBLE_1_0;
    v9 = fmax(*(double *)(a1 + 424), *(double *)(a1 + 432));
    *(_QWORD *)(a1 + 400) = a1 + 1256;
    v10 = v9 * fmax(0.0, v8 * 3.0e-12);
    *(double *)(a1 + 1072) = v10;
    *(double *)(a1 + 1432) = v10;
    _mm_lfence();
    v11 = fmax(v15 - v14, v17 - v16);
    if ( !_finite(v11) )
      v11 = DOUBLE_1_0;
    v12 = v11 * 0.000001;
    if ( a4 > 0.0 )
      v12 = fmin(a4, v12);
    *(double *)(a1 + 1472) = v12;
    v13 = *(_QWORD *)(a1 + 384);
    v18 = 3;
    result = (*(__int64 (__fastcall **)(__int64, __int64, int *))(v13 + 8))(a1 + 384, 1, &v18);
    if ( (int)result >= 0 )
    {
      *(_QWORD *)(a1 + 24) = *(_QWORD *)&a3 & _xmm;
      *(double *)(a1 + 32) = a3 * a3;
      *(double *)(a1 + 40) = (COERCE_DOUBLE(*(_QWORD *)&a3 & _xmm) * 4.0 - (a3 * 0.000001 + a3 * 0.000001))
                           * (a3
                            * 0.000001);
    }
  }
  return result;
}

```

## disassembly

```asm
0x10042e250  mov     rax, rsp
0x10042e253  mov     [rax+10h], rbx
0x10042e257  push    rdi
0x10042e258  sub     rsp, 0A0h
0x10042e25f  movaps  xmmword ptr [rax-18h], xmm6
0x10042e263  movaps  xmm0, xmm2
0x10042e266  mulsd   xmm0, cs:__real@3ff000010c6f7a0b
0x10042e26e  mov     rbx, rcx
0x10042e271  add     rcx, 188h
0x10042e278  movaps  xmmword ptr [rax-28h], xmm7
0x10042e27c  movaps  xmm7, xmm2
0x10042e27f  movsd   xmm2, cs:__real@3ff0000000000000
0x10042e287  movaps  xmmword ptr [rax-38h], xmm8
0x10042e28c  movaps  xmm8, xmm3
0x10042e290  movaps  xmmword ptr [rax-48h], xmm9
0x10042e295  movaps  xmmword ptr [rax-58h], xmm11
0x10042e29a  movups  xmm11, xmmword ptr [rdx]
0x10042e29e  movaps  xmmword ptr [rax-68h], xmm12
0x10042e2a3  movups  xmm12, xmmword ptr [rdx+10h]
0x10042e2a8  lea     rdx, [rsp+0A8h+var_88]
0x10042e2ad  movups  [rsp+0A8h+var_88], xmm11
0x10042e2b3  movups  xmmword ptr [rax-78h], xmm12
0x10042e2b8  subsd   xmm11, xmm0
0x10042e2bd  subsd   xmm12, xmm0
0x10042e2c2  movsd   qword ptr [rsp+0A8h+var_88], xmm11
0x10042e2c9  movsd   xmm6, qword ptr [rax-80h]
0x10042e2ce  movsd   xmm9, qword ptr [rax-70h]
0x10042e2d4  addsd   xmm6, xmm0
0x10042e2d8  addsd   xmm9, xmm0
0x10042e2dd  movsd   qword ptr [rax-78h], xmm12
0x10042e2e3  movsd   qword ptr [rax-80h], xmm6
0x10042e2e8  movsd   qword ptr [rax-70h], xmm9
0x10042e2ee  call    ?SetWithScaleFactor@CWorkspaceTransform@@QEAAJAEBV?$CMglRect@N@@N@Z; CWorkspaceTransform::SetWithScaleFactor(CMglRect<double> const &,double)
0x10042e2f3  test    eax, eax
0x10042e2f5  js      loc_10042E423
0x10042e2fb  subsd   xmm6, xmm11
0x10042e300  subsd   xmm9, xmm12
0x10042e305  maxsd   xmm6, xmm9
0x10042e30a  movaps  xmm0, xmm6; X
0x10042e30d  call    cs:__imp__finite
0x10042e313  test    eax, eax
0x10042e315  jnz     short loc_10042E31F
0x10042e317  movsd   xmm6, cs:__real@3ff0000000000000
0x10042e31f  movsd   xmm1, qword ptr [rbx+1A8h]
0x10042e327  lea     rax, [rbx+4E8h]
0x10042e32e  maxsd   xmm1, qword ptr [rbx+1B0h]
0x10042e336  mulsd   xmm6, cs:__real@3d8a636641c4df1a
0x10042e33e  xorps   xmm0, xmm0
0x10042e341  mov     [rbx+190h], rax
0x10042e348  xorps   xmm11, xmm11
0x10042e34c  maxsd   xmm0, xmm6
0x10042e350  mulsd   xmm1, xmm0
0x10042e354  movsd   qword ptr [rbx+430h], xmm1
0x10042e35c  movsd   qword ptr [rbx+598h], xmm1
0x10042e364  lfence
0x10042e367  movsd   xmm0, [rsp+0A8h+var_70]
0x10042e36d  subsd   xmm0, [rsp+0A8h+var_78]
0x10042e373  movsd   xmm6, qword ptr [rsp+0A8h+var_88+8]
0x10042e379  subsd   xmm6, qword ptr [rsp+0A8h+var_88]
0x10042e37f  maxsd   xmm6, xmm0
0x10042e383  movaps  xmm0, xmm6; X
0x10042e386  call    cs:__imp__finite
0x10042e38c  test    eax, eax
0x10042e38e  jnz     short loc_10042E398
0x10042e390  movsd   xmm6, cs:__real@3ff0000000000000
0x10042e398  comisd  xmm8, xmm11
0x10042e39d  movsd   xmm9, cs:__real@3eb0c6f7a0b5ed8d
0x10042e3a6  mulsd   xmm6, xmm9
0x10042e3ab  jbe     short loc_10042E3B6
0x10042e3ad  minsd   xmm8, xmm6
0x10042e3b2  movaps  xmm6, xmm8
0x10042e3b6  lea     rcx, [rbx+180h]
0x10042e3bd  movsd   qword ptr [rbx+5C0h], xmm6
0x10042e3c5  mov     rax, [rcx]
0x10042e3c8  lea     r8, [rsp+0A8h+arg_0]
0x10042e3d0  mov     edx, 1
0x10042e3d5  mov     [rsp+0A8h+arg_0], 3
0x10042e3e0  call    qword ptr [rax+8]
0x10042e3e3  test    eax, eax
0x10042e3e5  js      short loc_10042E423
0x10042e3e7  movaps  xmm1, xmm7
0x10042e3ea  movaps  xmm2, xmm7
0x10042e3ed  andps   xmm2, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x10042e3f4  mulsd   xmm1, xmm9
0x10042e3f9  movsd   qword ptr [rbx+18h], xmm2
0x10042e3fe  mulsd   xmm2, cs:__real@4010000000000000
0x10042e406  movaps  xmm0, xmm1
0x10042e409  mulsd   xmm7, xmm7
0x10042e40d  addsd   xmm0, xmm1
0x10042e411  movsd   qword ptr [rbx+20h], xmm7
0x10042e416  subsd   xmm2, xmm0
0x10042e41a  mulsd   xmm2, xmm1
0x10042e41e  movsd   qword ptr [rbx+28h], xmm2
0x10042e423  lea     r11, [rsp+0A8h+var_8]
0x10042e42b  mov     rbx, [r11+18h]
0x10042e42f  movaps  xmm6, xmmword ptr [r11-10h]
0x10042e434  movaps  xmm7, xmmword ptr [r11-20h]
0x10042e439  movaps  xmm8, xmmword ptr [r11-30h]
0x10042e43e  movaps  xmm9, xmmword ptr [r11-40h]
0x10042e443  movaps  xmm11, xmmword ptr [r11-50h]
0x10042e448  movaps  xmm12, xmmword ptr [r11-60h]
0x10042e44d  mov     rsp, r11
0x10042e450  pop     rdi
0x10042e451  retn
```
