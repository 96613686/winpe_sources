# CPathSimpleBuffer::Set(CMglRect<double> const &,double,double)

- ea: `0x10042e690`
- end: `0x10042e828`
- name: `?Set@CPathSimpleBuffer@@QEAAJAEBV?$CMglRect@N@@NN@Z`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10040fad0`

## callees

- `0x10042e690`
- `0x100432b80`
- `0x100469aec`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!_finite` at `0x10042e768`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x10042e768`

## pseudocode

```c
__int64 __fastcall CPathSimpleBuffer::Set(__int64 a1, __int128 *a2, double a3, double a4)
{
  double v5; // xmm1_8
  double v6; // xmm9_8
  __int128 v7; // xmm10
  double v8; // xmm6_8
  __int64 result; // rax
  double v10; // xmm6_8
  double v11; // xmm1_8
  double v12; // xmm1_8
  __int128 v13; // [rsp+20h] [rbp-88h] BYREF
  __int64 v14; // [rsp+30h] [rbp-78h]
  double v15; // [rsp+38h] [rbp-70h]
  int v16; // [rsp+B0h] [rbp+8h] BYREF

  v7 = a2[1];
  v13 = *a2;
  v5 = (a3 / sin_0(0.5235987750000001) + a4) * 1.000001;
  v6 = *(double *)&v13 - v5;
  *(double *)&v7 = *(double *)&v7 - v5;
  v8 = *((double *)&v13 + 1) + v5;
  *(double *)&v13 = *(double *)&v13 - v5;
  v14 = v7;
  *((double *)&v13 + 1) = *((double *)&v13 + 1) + v5;
  v15 = *((double *)&v7 + 1) + v5;
  result = CWorkspaceTransform::SetWithScaleFactor(a1 + 424, &v13);
  if ( (int)result >= 0 )
  {
    v10 = fmax(v8 - v6, *((double *)&v7 + 1) + v5 - *(double *)&v7);
    if ( !_finite(v10) )
      v10 = DOUBLE_1_0;
    v11 = fmax(*(double *)(a1 + 456), *(double *)(a1 + 464));
    *(_QWORD *)(a1 + 432) = a1 + 1288;
    v12 = v11 * fmax(0.0, v10 * 3.0e-12);
    *(double *)(a1 + 1104) = v12;
    *(double *)(a1 + 1464) = v12;
    _mm_lfence();
    v16 = 4;
    result = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)(a1 + 416) + 8LL))(a1 + 416, 1, &v16);
    if ( (int)result >= 0 )
    {
      *(_QWORD *)(a1 + 24) = *(_QWORD *)&a3 & _xmm;
      *(double *)(a1 + 32) = a4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10042e690  mov     rax, rsp
0x10042e693  mov     [rax+10h], rbx
0x10042e697  push    rdi
0x10042e698  sub     rsp, 0A0h
0x10042e69f  movsd   xmm0, cs:__real@3fe0c15237db38a1; X
0x10042e6a7  mov     rbx, rcx
0x10042e6aa  movaps  xmmword ptr [rax-18h], xmm6
0x10042e6ae  movaps  xmmword ptr [rax-28h], xmm7
0x10042e6b2  movaps  xmm7, xmm2
0x10042e6b5  movaps  xmmword ptr [rax-38h], xmm8
0x10042e6ba  movaps  xmmword ptr [rax-48h], xmm9
0x10042e6bf  movups  xmm9, xmmword ptr [rdx]
0x10042e6c3  movaps  xmmword ptr [rax-58h], xmm10
0x10042e6c8  movups  xmm10, xmmword ptr [rdx+10h]
0x10042e6cd  movaps  xmmword ptr [rax-68h], xmm12
0x10042e6d2  movaps  xmm12, xmm3
0x10042e6d6  movups  [rsp+0A8h+var_88], xmm9
0x10042e6dc  movups  xmmword ptr [rax-78h], xmm10
0x10042e6e1  call    sin_0
0x10042e6e6  movsd   xmm6, qword ptr [rsp+0A8h+var_88+8]
0x10042e6ec  lea     rdx, [rsp+0A8h+var_88]
0x10042e6f1  movsd   xmm8, [rsp+0A8h+var_70]
0x10042e6f8  lea     rcx, [rbx+1A8h]
0x10042e6ff  movsd   xmm2, cs:__real@3ff0000000000000
0x10042e707  movaps  xmm1, xmm7
0x10042e70a  divsd   xmm1, xmm0
0x10042e70e  addsd   xmm1, xmm12
0x10042e713  mulsd   xmm1, cs:__real@3ff000010c6f7a0b
0x10042e71b  subsd   xmm9, xmm1
0x10042e720  subsd   xmm10, xmm1
0x10042e725  addsd   xmm6, xmm1
0x10042e729  addsd   xmm8, xmm1
0x10042e72e  movsd   qword ptr [rsp+0A8h+var_88], xmm9
0x10042e735  movsd   [rsp+0A8h+var_78], xmm10
0x10042e73c  movsd   qword ptr [rsp+0A8h+var_88+8], xmm6
0x10042e742  movsd   [rsp+0A8h+var_70], xmm8
0x10042e749  call    ?SetWithScaleFactor@CWorkspaceTransform@@QEAAJAEBV?$CMglRect@N@@N@Z; CWorkspaceTransform::SetWithScaleFactor(CMglRect<double> const &,double)
0x10042e74e  test    eax, eax
0x10042e750  js      loc_10042E7F9
0x10042e756  subsd   xmm6, xmm9
0x10042e75b  subsd   xmm8, xmm10
0x10042e760  maxsd   xmm6, xmm8
0x10042e765  movaps  xmm0, xmm6; X
0x10042e768  call    cs:__imp__finite
0x10042e76e  test    eax, eax
0x10042e770  jnz     short loc_10042E77A
0x10042e772  movsd   xmm6, cs:__real@3ff0000000000000
0x10042e77a  movsd   xmm1, qword ptr [rbx+1C8h]
0x10042e782  lea     rax, [rbx+508h]
0x10042e789  maxsd   xmm1, qword ptr [rbx+1D0h]
0x10042e791  mulsd   xmm6, cs:__real@3d8a636641c4df1a
0x10042e799  xorps   xmm0, xmm0
0x10042e79c  mov     [rbx+1B0h], rax
0x10042e7a3  maxsd   xmm0, xmm6
0x10042e7a7  mulsd   xmm1, xmm0
0x10042e7ab  movsd   qword ptr [rbx+450h], xmm1
0x10042e7b3  movsd   qword ptr [rbx+5B8h], xmm1
0x10042e7bb  lfence
0x10042e7be  lea     rcx, [rbx+1A0h]
0x10042e7c5  mov     [rsp+0A8h+arg_0], 4
0x10042e7d0  mov     rax, [rcx]
0x10042e7d3  lea     r8, [rsp+0A8h+arg_0]
0x10042e7db  mov     edx, 1
0x10042e7e0  call    qword ptr [rax+8]
0x10042e7e3  test    eax, eax
0x10042e7e5  js      short loc_10042E7F9
0x10042e7e7  andps   xmm7, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x10042e7ee  movsd   qword ptr [rbx+18h], xmm7
0x10042e7f3  movsd   qword ptr [rbx+20h], xmm12
0x10042e7f9  lea     r11, [rsp+0A8h+var_8]
0x10042e801  mov     rbx, [r11+18h]
0x10042e805  movaps  xmm6, xmmword ptr [r11-10h]
0x10042e80a  movaps  xmm7, xmmword ptr [r11-20h]
0x10042e80f  movaps  xmm8, xmmword ptr [r11-30h]
0x10042e814  movaps  xmm9, xmmword ptr [r11-40h]
0x10042e819  movaps  xmm10, xmmword ptr [r11-50h]
0x10042e81e  movaps  xmm12, xmmword ptr [r11-60h]
0x10042e823  mov     rsp, r11
0x10042e826  pop     rdi
0x10042e827  retn
```
