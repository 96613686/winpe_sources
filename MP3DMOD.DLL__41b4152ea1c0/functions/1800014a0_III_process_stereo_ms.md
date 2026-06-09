# III_process_stereo_ms

- ea: `0x1800014a0`
- end: `0x180001683`
- name: `III_process_stereo_ms`
- size: `483`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x1800012d0`

## callees

- `0x1800014a0`

## pseudocode

```c
void __fastcall III_process_stereo_ms(__int64 a1, __int64 a2, int a3, int a4, int a5)
{
  __int64 v6; // rdi
  int v7; // r11d
  double v8; // xmm4_8
  __int64 v9; // rax
  __int64 v10; // xmm2_8
  __int64 v11; // xmm3_8
  __int64 v12; // rax
  float v13; // xmm3_4
  float v14; // xmm2_4
  float v15; // xmm0_4
  double v16; // xmm3_8
  int v17; // ecx
  __int64 v18; // rax
  __int64 v19; // rax

  if ( a5 )
  {
    if ( a3 < a4 )
    {
      if ( (unsigned int)(a4 - a3) < 8 )
        goto LABEL_20;
      *(_QWORD *)&v16 = _mm_load_si128((const __m128i *)&_xmm).m128i_u64[0];
      v17 = a4 - (a4 - a3) % 8;
      do
      {
        v18 = a3;
        a3 += 8;
        *(double *)(a1 + 4 * v18) = COERCE_FLOAT(*(_QWORD *)(a1 + 4 * v18)) * v16;
        *(double *)(a1 + 4 * v18 + 8) = COERCE_FLOAT(*(_QWORD *)(a1 + 4 * v18 + 8)) * v16;
        *(double *)(a1 + 4 * v18 + 16) = COERCE_FLOAT(*(_QWORD *)(a1 + 4 * v18 + 16)) * v16;
        *(double *)(a1 + 4 * v18 + 24) = *(float *)(a1 + 4 * v18 + 24) * v16;
      }
      while ( a3 < v17 );
      if ( a3 < a4 )
      {
LABEL_20:
        do
        {
          v19 = a3++;
          *(float *)(a1 + 4 * v19) = *(float *)(a1 + 4 * v19) * 0.7071067811865476;
        }
        while ( a3 < a4 );
      }
    }
  }
  else if ( a3 < a4 )
  {
    if ( (unsigned int)(a4 - a3) < 2 )
      goto LABEL_21;
    v6 = a4 - 1;
    if ( a1 + 4LL * a3 <= (unsigned __int64)(a2 + 4 * v6) && a1 + 4 * v6 >= (unsigned __int64)(a2 + 4LL * a3) )
      goto LABEL_21;
    v7 = (a4 - a3) % 2;
    *(_QWORD *)&v8 = _mm_load_si128((const __m128i *)&_xmm).m128i_u64[0];
    do
    {
      v9 = a3;
      a3 += 2;
      v10 = *(_QWORD *)(a2 + 4 * v9);
      v11 = *(_QWORD *)(a1 + 4 * v9);
      *(double *)(a2 + 4 * v9) = (float)(*(float *)&v11 - *(float *)&v10) * v8;
      *(double *)(a1 + 4 * v9) = (float)(*(float *)&v10 + *(float *)&v11) * v8;
    }
    while ( a3 < a4 - v7 );
    if ( a3 < a4 )
    {
LABEL_21:
      do
      {
        v12 = a3++;
        v13 = *(float *)(a1 + 4 * v12);
        v14 = *(float *)(a2 + 4 * v12);
        v15 = (float)(v13 - v14) * 0.7071067811865476;
        *(float *)(a2 + 4 * v12) = v15;
        *(float *)(a1 + 4 * v12) = (float)(v13 + v14) * 0.7071067811865476;
      }
      while ( a3 < a4 );
    }
  }
}

```

## disassembly

```asm
0x1800014a0  sub     rsp, 8
0x1800014a4  cmp     [rsp+8+arg_20], 0
0x1800014a9  mov     r10, rcx
0x1800014ac  jnz     loc_1800015BE
0x1800014b2  cmp     r8d, r9d
0x1800014b5  jge     loc_1800015B9
0x1800014bb  mov     r11d, r9d
0x1800014be  mov     [rsp+8+arg_0], rbx
0x1800014c3  sub     r11d, r8d
0x1800014c6  mov     [rsp+8+var_8], rdi
0x1800014ca  cmp     r11d, 2
0x1800014ce  jb      loc_180001566
0x1800014d4  lea     eax, [r9-1]
0x1800014d8  movsxd  rbx, r8d
0x1800014db  movsxd  rdi, eax
0x1800014de  lea     rcx, [rcx+rbx*4]
0x1800014e2  lea     rax, [rdx+rdi*4]
0x1800014e6  cmp     rcx, rax
0x1800014e9  ja      short loc_1800014F8
0x1800014eb  lea     rcx, [rdx+rbx*4]
0x1800014ef  lea     rax, [r10+rdi*4]
0x1800014f3  cmp     rax, rcx
0x1800014f6  jnb     short loc_180001566
0x1800014f8  and     r11d, 80000001h
0x1800014ff  jge     short loc_18000150B
0x180001501  dec     r11d
0x180001504  or      r11d, 0FFFFFFFEh
0x180001508  inc     r11d
0x18000150b  mov     ecx, r9d
0x18000150e  sub     ecx, r11d
0x180001511  movdqa  xmm4, cs:__xmm@3fe6a09e667f3bcd3fe6a09e667f3bcd
0x180001519  nop     dword ptr [rax+00000000h]
0x180001520  movsxd  rax, r8d
0x180001523  add     r8d, 2
0x180001527  movsd   xmm0, qword ptr [r10+rax*4]
0x18000152d  movsd   xmm2, qword ptr [rdx+rax*4]
0x180001532  movaps  xmm3, xmm0
0x180001535  subps   xmm0, xmm2
0x180001538  addps   xmm2, xmm3
0x18000153b  cvtps2pd xmm1, xmm0
0x18000153e  mulpd   xmm1, xmm4
0x180001542  cvtpd2ps xmm0, xmm1
0x180001546  movsd   qword ptr [rdx+rax*4], xmm0
0x18000154b  cvtps2pd xmm0, xmm2
0x18000154e  mulpd   xmm0, xmm4
0x180001552  cvtpd2ps xmm0, xmm0
0x180001556  movsd   qword ptr [r10+rax*4], xmm0
0x18000155c  cmp     r8d, ecx
0x18000155f  jl      short loc_180001520
0x180001561  cmp     r8d, r9d
0x180001564  jge     short loc_1800015B0
0x180001566  movsd   xmm4, cs:__real@3fe6a09e667f3bcd
0x18000156e  movsxd  rax, r8d
0x180001571  inc     r8d
0x180001574  movss   xmm3, dword ptr [r10+rax*4]
0x18000157a  movss   xmm2, dword ptr [rdx+rax*4]
0x18000157f  movaps  xmm0, xmm3
0x180001582  subss   xmm0, xmm2
0x180001586  addss   xmm3, xmm2
0x18000158a  cvtps2pd xmm1, xmm0
0x18000158d  mulsd   xmm1, xmm4
0x180001591  cvtpd2ps xmm0, xmm1
0x180001595  movss   dword ptr [rdx+rax*4], xmm0
0x18000159a  cvtps2pd xmm0, xmm3
0x18000159d  mulsd   xmm0, xmm4
0x1800015a1  cvtpd2ps xmm0, xmm0
0x1800015a5  movss   dword ptr [r10+rax*4], xmm0
0x1800015ab  cmp     r8d, r9d
0x1800015ae  jl      short loc_18000156E
0x1800015b0  mov     rbx, [rsp+8+arg_0]
0x1800015b5  mov     rdi, [rsp+8+var_8]
0x1800015b9  add     rsp, 8
0x1800015bd  retn
0x1800015be  cmp     r8d, r9d
0x1800015c1  jge     short loc_1800015B9
0x1800015c3  mov     eax, r9d
0x1800015c6  sub     eax, r8d
0x1800015c9  cmp     eax, 8
0x1800015cc  jb      loc_180001657
0x1800015d2  and     eax, 80000007h
0x1800015d7  jge     short loc_1800015E0
0x1800015d9  dec     eax
0x1800015db  or      eax, 0FFFFFFF8h
0x1800015de  inc     eax
0x1800015e0  movdqa  xmm3, cs:__xmm@3fe6a09e667f3bcd3fe6a09e667f3bcd
0x1800015e8  mov     ecx, r9d
0x1800015eb  sub     ecx, eax
0x1800015ed  nop     dword ptr [rax]
0x1800015f0  movsxd  rax, r8d
0x1800015f3  add     r8d, 8
0x1800015f7  cvtps2pd xmm2, qword ptr [r10+rax*4]
0x1800015fc  mulpd   xmm2, xmm3
0x180001600  cvtpd2ps xmm0, xmm2
0x180001604  movsd   qword ptr [r10+rax*4], xmm0
0x18000160a  cvtps2pd xmm2, qword ptr [r10+rax*4+8]
0x180001610  mulpd   xmm2, xmm3
0x180001614  cvtpd2ps xmm0, xmm2
0x180001618  movsd   qword ptr [r10+rax*4+8], xmm0
0x18000161f  cvtps2pd xmm2, qword ptr [r10+rax*4+10h]
0x180001625  mulpd   xmm2, xmm3
0x180001629  cvtpd2ps xmm0, xmm2
0x18000162d  movsd   qword ptr [r10+rax*4+10h], xmm0
0x180001634  cvtps2pd xmm2, qword ptr [r10+rax*4+18h]
0x18000163a  mulpd   xmm2, xmm3
0x18000163e  cvtpd2ps xmm0, xmm2
0x180001642  movsd   qword ptr [r10+rax*4+18h], xmm0
0x180001649  cmp     r8d, ecx
0x18000164c  jl      short loc_1800015F0
0x18000164e  cmp     r8d, r9d
0x180001651  jge     loc_1800015B9
0x180001657  movsxd  rax, r8d
0x18000165a  inc     r8d
0x18000165d  movss   xmm0, dword ptr [r10+rax*4]
0x180001663  cvtps2pd xmm0, xmm0
0x180001666  mulsd   xmm0, cs:__real@3fe6a09e667f3bcd
0x18000166e  cvtpd2ps xmm0, xmm0
0x180001672  movss   dword ptr [r10+rax*4], xmm0
0x180001678  cmp     r8d, r9d
0x18000167b  jge     loc_1800015B9
0x180001681  jmp     short loc_180001657
```
