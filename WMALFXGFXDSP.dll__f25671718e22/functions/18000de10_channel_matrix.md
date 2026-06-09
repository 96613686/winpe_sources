# channel_matrix

- ea: `0x18000de10`
- end: `0x18000df79`
- name: `channel_matrix`
- size: `361`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ddb0`
- `0x18007b1e0`
- `0x18007b260`
- `0x18007b2b0`
- `0x18007b310`
- `0x18007b370`
- `0x18007b3d0`
- `0x18007b430`

## callees

- `0x18000de10`

## pseudocode

```c
void __fastcall channel_matrix(int a1, int a2, int a3, __m128 *a4, __int64 a5, float *a6, __int64 a7, int a8, int a9)
{
  __m128 *v9; // rax
  int v13; // r9d
  int i; // r14d
  __int64 v15; // r8
  __m128 *v16; // rsi
  int v17; // edx
  float v18; // xmm1_4
  signed int v19; // r9d
  int v20; // edx
  __m128 v21; // xmm3
  __m128 v22; // xmm2
  int v23; // eax
  __m128 v24; // xmm1
  __m128 v25; // xmm0
  __m128 v26; // xmm2
  __m128 v27; // xmm1
  int v28; // eax
  float v29; // xmm0_4

  if ( a1 > 0 )
  {
    v9 = a4;
    v13 = a1;
    for ( i = 0; i < v13; ++i )
    {
      v15 = 0;
      v16 = v9;
      if ( a3 > 0 )
      {
        do
        {
          v17 = i;
          if ( a7 )
            v17 = i - *(_DWORD *)(a7 + 4 * v15);
          if ( a9 )
            v17 = (a9 + v17 + a8) % a9;
          v18 = 0.0;
          if ( a2 > 0 )
          {
            v19 = 0;
            v20 = a2 * v17;
            if ( (unsigned int)a2 >= 8 )
            {
              v21 = 0;
              v22 = 0;
              do
              {
                v23 = v20 + v19;
                v19 += 8;
                v24 = _mm_mul_ps(*(__m128 *)(a5 + 4LL * v23), *v16);
                v25 = v16[1];
                v16 += 2;
                v21 = _mm_add_ps(v21, v24);
                v22 = _mm_add_ps(v22, _mm_mul_ps(*(__m128 *)(a5 + 4LL * v23 + 16), v25));
              }
              while ( v19 < (int)(a2 & 0xFFFFFFF8) );
              v26 = _mm_add_ps(v22, v21);
              v27 = _mm_add_ps(_mm_movehl_ps(v26, v26), v26);
              v18 = v27.m128_f32[0] + _mm_shuffle_ps(v27, v27, 245).m128_f32[0];
            }
            for ( ; v19 < a2; v18 = v18 + v29 )
            {
              v28 = v20 + v19++;
              v29 = *(float *)(a5 + 4LL * v28) * v16->m128_f32[0];
              v16 = (__m128 *)((char *)v16 + 4);
            }
          }
          *a6 = v18;
          v15 = (unsigned int)(v15 + 1);
          ++a6;
        }
        while ( (int)v15 < a3 );
        v13 = a1;
        v9 = a4;
      }
    }
  }
}

```

## disassembly

```asm
0x18000de10  test    ecx, ecx
0x18000de12  jle     locret_18000DF78
0x18000de18  mov     [rsp+arg_18], r9
0x18000de1d  mov     [rsp+arg_0], ecx
0x18000de21  push    rdi
0x18000de22  push    r13
0x18000de24  push    r14
0x18000de26  push    r15
0x18000de28  sub     rsp, 18h
0x18000de2c  mov     rdi, [rsp+38h+arg_30]
0x18000de31  mov     rax, r9
0x18000de34  mov     r13, [rsp+38h+arg_20]
0x18000de39  mov     r15d, r8d
0x18000de3c  mov     r11, [rsp+38h+arg_28]
0x18000de41  mov     r10d, edx
0x18000de44  mov     [rsp+38h+arg_8], rbx
0x18000de49  mov     r9d, ecx
0x18000de4c  mov     ebx, [rsp+38h+arg_40]
0x18000de53  xor     r14d, r14d
0x18000de56  mov     [rsp+38h+var_28], rbp
0x18000de5b  mov     [rsp+38h+var_30], rsi
0x18000de60  mov     [rsp+38h+var_38], r12
0x18000de64  mov     r12d, [rsp+38h+arg_38]
0x18000de69  nop     dword ptr [rax+00000000h]
0x18000de70  xor     r8d, r8d
0x18000de73  mov     rsi, rax
0x18000de76  test    r15d, r15d
0x18000de79  jle     loc_18000DF4E
0x18000de7f  nop
0x18000de80  mov     edx, r14d
0x18000de83  test    rdi, rdi
0x18000de86  jz      short loc_18000DE8C
0x18000de88  sub     edx, [rdi+r8*4]
0x18000de8c  test    ebx, ebx
0x18000de8e  jz      short loc_18000DE99
0x18000de90  lea     eax, [rdx+r12]
0x18000de94  add     eax, ebx
0x18000de96  cdq
0x18000de97  idiv    ebx
0x18000de99  xorps   xmm1, xmm1
0x18000de9c  test    r10d, r10d
0x18000de9f  jle     loc_18000DF2F
0x18000dea5  xor     r9d, r9d
0x18000dea8  imul    edx, r10d
0x18000deac  cmp     r10d, 8
0x18000deb0  jb      short loc_18000DF08
0x18000deb2  mov     ebp, r10d
0x18000deb5  xorps   xmm3, xmm3
0x18000deb8  and     ebp, 0FFFFFFF8h
0x18000debb  xorps   xmm2, xmm2
0x18000debe  movups  xmm0, xmmword ptr [rsi]
0x18000dec1  lea     eax, [rdx+r9]
0x18000dec5  add     r9d, 8
0x18000dec9  movsxd  rcx, eax
0x18000decc  movups  xmm1, xmmword ptr [r13+rcx*4+0]
0x18000ded2  mulps   xmm1, xmm0
0x18000ded5  movups  xmm0, xmmword ptr [rsi+10h]
0x18000ded9  add     rsi, 20h ; ' '
0x18000dedd  addps   xmm3, xmm1
0x18000dee0  movups  xmm1, xmmword ptr [r13+rcx*4+10h]
0x18000dee6  mulps   xmm1, xmm0
0x18000dee9  addps   xmm2, xmm1
0x18000deec  cmp     r9d, ebp
0x18000deef  jl      short loc_18000DEBE
0x18000def1  addps   xmm2, xmm3
0x18000def4  movaps  xmm1, xmm2
0x18000def7  movhlps xmm1, xmm2
0x18000defa  addps   xmm1, xmm2
0x18000defd  movaps  xmm0, xmm1
0x18000df00  shufps  xmm0, xmm1, 0F5h
0x18000df04  addss   xmm1, xmm0
0x18000df08  cmp     r9d, r10d
0x18000df0b  jge     short loc_18000DF2F
0x18000df0d  lea     eax, [rdx+r9]
0x18000df11  inc     r9d
0x18000df14  movsxd  rcx, eax
0x18000df17  movss   xmm0, dword ptr [r13+rcx*4+0]
0x18000df1e  mulss   xmm0, dword ptr [rsi]
0x18000df22  add     rsi, 4
0x18000df26  addss   xmm1, xmm0
0x18000df2a  cmp     r9d, r10d
0x18000df2d  jl      short loc_18000DF0D
0x18000df2f  movss   dword ptr [r11], xmm1
0x18000df34  inc     r8d
0x18000df37  add     r11, 4
0x18000df3b  cmp     r8d, r15d
0x18000df3e  jl      loc_18000DE80
0x18000df44  mov     r9d, [rsp+38h+arg_0]
0x18000df49  mov     rax, [rsp+38h+arg_18]
0x18000df4e  inc     r14d
0x18000df51  cmp     r14d, r9d
0x18000df54  jl      loc_18000DE70
0x18000df5a  mov     r12, [rsp+38h+var_38]
0x18000df5e  mov     rsi, [rsp+38h+var_30]
0x18000df63  mov     rbp, [rsp+38h+var_28]
0x18000df68  mov     rbx, [rsp+38h+arg_8]
0x18000df6d  add     rsp, 18h
0x18000df71  pop     r15
0x18000df73  pop     r14
0x18000df75  pop     r13
0x18000df77  pop     rdi
0x18000df78  retn
```
