# normalise_residual

- ea: `0x1800126a0`
- end: `0x18001271a`
- name: `normalise_residual`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180011e70`
- `0x180011fc0`

## callees

- `0x180002270`
- `0x1800126a0`

## pseudocode

```c
__int64 __fastcall normalise_residual(__int64 a1, __int64 a2, int a3, float a4, float a5)
{
  __m128d v5; // xmm1
  double v9; // xmm0_8
  int v10; // ecx
  float v11; // xmm0_4
  __int64 result; // rax

  v5 = 0;
  v5.m128d_f64[0] = a4;
  if ( a4 < 0.0 )
    v9 = sqrt(v5.m128d_f64[0]);
  else
    *(_QWORD *)&v9 = *(_OWORD *)&_mm_sqrt_pd(v5);
  v10 = 0;
  v11 = v9;
  do
  {
    result = v10++;
    *(float *)(a2 + 4 * result) = (float)*(int *)(a1 + 4 * result) * (float)((float)(1.0 / v11) * a5);
  }
  while ( v10 < a3 );
  return result;
}

```

## disassembly

```asm
0x1800126a0  mov     [rsp+arg_0], rbx
0x1800126a5  mov     [rsp+arg_8], rsi
0x1800126aa  push    rdi
0x1800126ab  sub     rsp, 20h
0x1800126af  xorps   xmm1, xmm1
0x1800126b2  xorps   xmm0, xmm0
0x1800126b5  cvtss2sd xmm1, xmm3
0x1800126b9  mov     ebx, r8d
0x1800126bc  mov     rdi, rdx
0x1800126bf  mov     rsi, rcx
0x1800126c2  ucomisd xmm0, xmm1
0x1800126c6  ja      short loc_1800126CE
0x1800126c8  sqrtpd  xmm0, xmm1
0x1800126cc  jmp     short loc_1800126D6
0x1800126ce  movaps  xmm0, xmm1; X
0x1800126d1  call    sqrt
0x1800126d6  movss   xmm1, cs:__real@3f800000
0x1800126de  xor     ecx, ecx
0x1800126e0  cvtsd2ss xmm0, xmm0
0x1800126e4  divss   xmm1, xmm0
0x1800126e8  mulss   xmm1, [rsp+28h+arg_20]
0x1800126ee  xchg    ax, ax
0x1800126f0  movsxd  rax, ecx
0x1800126f3  inc     ecx
0x1800126f5  movd    xmm0, dword ptr [rsi+rax*4]
0x1800126fa  cvtdq2ps xmm0, xmm0
0x1800126fd  mulss   xmm0, xmm1
0x180012701  movss   dword ptr [rdi+rax*4], xmm0
0x180012706  cmp     ecx, ebx
0x180012708  jl      short loc_1800126F0
0x18001270a  mov     rbx, [rsp+28h+arg_0]
0x18001270f  mov     rsi, [rsp+28h+arg_8]
0x180012714  add     rsp, 20h
0x180012718  pop     rdi
0x180012719  retn
```
