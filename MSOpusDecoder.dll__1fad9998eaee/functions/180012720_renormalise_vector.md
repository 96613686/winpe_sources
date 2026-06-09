# renormalise_vector

- ea: `0x180012720`
- end: `0x180012857`
- name: `renormalise_vector`
- size: `311`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180004890`
- `0x18000cc20`
- `0x180010060`

## callees

- `0x180002270`
- `0x180012720`
- `0x180012b80`

## pseudocode

```c
void __fastcall renormalise_vector(__m128 *a1, int a2, float a3)
{
  __m128 *v5; // rbx
  __m128d v6; // xmm1
  double v7; // xmm0_8
  float v8; // xmm0_4
  __m128 v9; // xmm2
  __m128 v10; // xmm3
  signed int v11; // ecx
  float v12; // xmm1_4
  float v13; // xmm0_4
  float v14; // xmm1_4
  float v15; // xmm0_4

  v5 = a1;
  v6 = 0;
  v6.m128d_f64[0] = (float)(celt_inner_prod_sse(a1, a1, (unsigned int)a2) + 1.0e-15);
  if ( v6.m128d_f64[0] < 0.0 )
    v7 = sqrt(v6.m128d_f64[0]);
  else
    *(_QWORD *)&v7 = *(_OWORD *)&_mm_sqrt_pd(v6);
  v9 = (__m128)LODWORD(FLOAT_1_0);
  v8 = v7;
  v9.m128_f32[0] = (float)(1.0 / v8) * a3;
  v10 = _mm_shuffle_ps(v9, v9, 0);
  if ( a2 > 0 )
  {
    v11 = 0;
    if ( (unsigned int)a2 < 0x10 )
      goto LABEL_10;
    do
    {
      v11 += 16;
      *v5 = _mm_mul_ps(v10, *v5);
      v5[1] = _mm_mul_ps(v5[1], v10);
      v5[2] = _mm_mul_ps(v5[2], v10);
      v5[3] = _mm_mul_ps(v5[3], v10);
      v5 += 4;
    }
    while ( v11 < (int)(a2 & 0xFFFFFFF0) );
    if ( v11 < a2 )
    {
LABEL_10:
      if ( a2 - v11 < 4 )
        goto LABEL_14;
      do
      {
        v11 += 4;
        v12 = v9.m128_f32[0] * v5->m128_f32[1];
        v5->m128_f32[0] = v9.m128_f32[0] * v5->m128_f32[0];
        v13 = v9.m128_f32[0] * v5->m128_f32[2];
        v5->m128_f32[1] = v12;
        v14 = v9.m128_f32[0] * v5->m128_f32[3];
        v5->m128_f32[2] = v13;
        v5->m128_f32[3] = v14;
        ++v5;
      }
      while ( v11 < a2 - 3 );
      if ( v11 < a2 )
      {
LABEL_14:
        do
        {
          ++v11;
          v15 = v9.m128_f32[0] * v5->m128_f32[0];
          v5 = (__m128 *)((char *)v5 + 4);
          v5[-1].m128_f32[3] = v15;
        }
        while ( v11 < a2 );
      }
    }
  }
}

```

## disassembly

```asm
0x180012720  mov     [rsp+arg_0], rbx
0x180012725  push    rdi
0x180012726  sub     rsp, 30h
0x18001272a  mov     edi, edx
0x18001272c  movaps  [rsp+38h+var_18], xmm6
0x180012731  mov     r8d, edx
0x180012734  movaps  xmm6, xmm2
0x180012737  mov     rdx, rcx
0x18001273a  mov     rbx, rcx
0x18001273d  call    celt_inner_prod_sse
0x180012742  addss   xmm0, cs:__real@26901d7d
0x18001274a  xorps   xmm1, xmm1
0x18001274d  cvtss2sd xmm1, xmm0
0x180012751  xorps   xmm0, xmm0
0x180012754  ucomisd xmm0, xmm1
0x180012758  ja      short loc_180012760
0x18001275a  sqrtpd  xmm0, xmm1
0x18001275e  jmp     short loc_180012768
0x180012760  movaps  xmm0, xmm1; X
0x180012763  call    sqrt
0x180012768  movss   xmm2, cs:__real@3f800000
0x180012770  cvtsd2ss xmm0, xmm0
0x180012774  divss   xmm2, xmm0
0x180012778  mulss   xmm2, xmm6
0x18001277c  movaps  xmm3, xmm2
0x18001277f  shufps  xmm3, xmm3, 0
0x180012783  test    edi, edi
0x180012785  jle     loc_180012847
0x18001278b  xor     ecx, ecx
0x18001278d  cmp     edi, 10h
0x180012790  jb      short loc_1800127DC
0x180012792  mov     eax, edi
0x180012794  and     eax, 0FFFFFFF0h
0x180012797  nop     word ptr [rax+rax+00000000h]
0x1800127a0  movups  xmm0, xmmword ptr [rbx]
0x1800127a3  add     ecx, 10h
0x1800127a6  movaps  xmm1, xmm3
0x1800127a9  mulps   xmm1, xmm0
0x1800127ac  movups  xmmword ptr [rbx], xmm1
0x1800127af  movups  xmm0, xmmword ptr [rbx+10h]
0x1800127b3  mulps   xmm0, xmm3
0x1800127b6  movups  xmmword ptr [rbx+10h], xmm0
0x1800127ba  movups  xmm0, xmmword ptr [rbx+20h]
0x1800127be  mulps   xmm0, xmm3
0x1800127c1  movups  xmmword ptr [rbx+20h], xmm0
0x1800127c5  movups  xmm0, xmmword ptr [rbx+30h]
0x1800127c9  mulps   xmm0, xmm3
0x1800127cc  movups  xmmword ptr [rbx+30h], xmm0
0x1800127d0  add     rbx, 40h ; '@'
0x1800127d4  cmp     ecx, eax
0x1800127d6  jl      short loc_1800127A0
0x1800127d8  cmp     ecx, edi
0x1800127da  jge     short loc_180012847
0x1800127dc  mov     eax, edi
0x1800127de  sub     eax, ecx
0x1800127e0  cmp     eax, 4
0x1800127e3  jl      short loc_180012831
0x1800127e5  lea     edx, [rdi-3]
0x1800127e8  nop     dword ptr [rax+rax+00000000h]
0x1800127f0  movaps  xmm0, xmm2
0x1800127f3  movaps  xmm1, xmm2
0x1800127f6  mulss   xmm0, dword ptr [rbx]
0x1800127fa  add     ecx, 4
0x1800127fd  mulss   xmm1, dword ptr [rbx+4]
0x180012802  movss   dword ptr [rbx], xmm0
0x180012806  movaps  xmm0, xmm2
0x180012809  mulss   xmm0, dword ptr [rbx+8]
0x18001280e  movss   dword ptr [rbx+4], xmm1
0x180012813  movaps  xmm1, xmm2
0x180012816  mulss   xmm1, dword ptr [rbx+0Ch]
0x18001281b  movss   dword ptr [rbx+8], xmm0
0x180012820  movss   dword ptr [rbx+0Ch], xmm1
0x180012825  add     rbx, 10h
0x180012829  cmp     ecx, edx
0x18001282b  jl      short loc_1800127F0
0x18001282d  cmp     ecx, edi
0x18001282f  jge     short loc_180012847
0x180012831  movaps  xmm0, xmm2
0x180012834  inc     ecx
0x180012836  mulss   xmm0, dword ptr [rbx]
0x18001283a  lea     rbx, [rbx+4]
0x18001283e  movss   dword ptr [rbx-4], xmm0
0x180012843  cmp     ecx, edi
0x180012845  jl      short loc_180012831
0x180012847  mov     rbx, [rsp+38h+arg_0]
0x18001284c  movaps  xmm6, [rsp+38h+var_18]
0x180012851  add     rsp, 30h
0x180012855  pop     rdi
0x180012856  retn
```
