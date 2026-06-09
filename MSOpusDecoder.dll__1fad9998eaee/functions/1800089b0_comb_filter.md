# comb_filter

- ea: `0x1800089b0`
- end: `0x180008d30`
- name: `comb_filter`
- size: `896`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005aa0`
- `0x180008400`

## callees

- `0x1800089b0`
- `0x180012c50`
- `0x18001b030`

## pseudocode

```c
__int64 __fastcall comb_filter(
        char *a1,
        char *a2,
        int a3,
        unsigned int a4,
        int a5,
        float a6,
        float a7,
        int a8,
        int a9,
        __int64 a10,
        int a11)
{
  float v12; // xmm6_4
  __int64 result; // rax
  int v14; // r11d
  int v15; // r9d
  float v16; // xmm12_4
  float v17; // xmm13_4
  float v18; // xmm14_4
  float v19; // xmm8_4
  float v20; // xmm9_4
  float v21; // xmm10_4
  int v22; // r8d
  int v23; // ebx
  float v24; // xmm15_4
  float v25; // xmm7_4
  int v26; // r9d
  float v27; // xmm6_4
  __int64 v28; // rcx
  __int64 v29; // rax
  float v30; // xmm4_4
  float v31; // xmm5_4
  float v32; // xmm3_4
  float v33; // xmm1_4
  float v34; // xmm0_4
  float v35; // [rsp+128h] [rbp+30h]

  v12 = a7;
  result = a4;
  if ( a6 == 0.0 && a7 == 0.0 )
  {
    if ( a2 != a1 )
      return (__int64)memmove_0(a1, a2, 4LL * a5);
  }
  else
  {
    v14 = 15;
    v15 = 15;
    if ( a3 > 15 )
      v15 = a3;
    if ( (int)result > 15 )
      v14 = result;
    v16 = a6 * *((float *)qword_180025048 + 3 * a8);
    v17 = a6 * *((float *)qword_180025048 + 3 * a8 + 1);
    v18 = a6 * *((float *)&qword_180025048[1] + 3 * a8);
    v19 = a7 * *((float *)qword_180025048 + 3 * a9);
    v20 = a7 * *((float *)qword_180025048 + 3 * a9 + 1);
    v21 = a7 * *((float *)&qword_180025048[1] + 3 * a9);
    if ( a6 == a7 && v15 == v14 && a8 == a9 )
    {
      v22 = 0;
      v23 = 0;
    }
    else
    {
      v23 = 0;
      v22 = a11;
      v24 = *(float *)&a2[4 * (1 - v14)];
      result = -2 - v14;
      v35 = *(float *)&a2[4 * result];
      if ( a11 > 0 )
      {
        v25 = *(float *)&a2[-4 * v14];
        v26 = -v15;
        v27 = *(float *)&a2[4 * ~v14];
        do
        {
          v28 = v23;
          v29 = v23 - v14;
          ++v23;
          v30 = *(float *)(a10 + 4 * v28) * *(float *)(a10 + 4 * v28);
          v31 = *(float *)&a2[4 * v29 + 8];
          result = v26++;
          v32 = (float)((float)((float)((float)(*(float *)&a2[4 * result - 4] + *(float *)&a2[4 * result + 4])
                                      * (float)((float)(1.0 - v30) * v17))
                              + (float)((float)((float)((float)(1.0 - v30) * v16) * *(float *)&a2[4 * result])
                                      + *(float *)&a2[4 * v28]))
                      + (float)((float)(*(float *)&a2[4 * result - 8] + *(float *)&a2[4 * result + 8])
                              * (float)((float)(1.0 - v30) * v18)))
              + (float)((float)(v30 * v19) * v25);
          v33 = (float)(v30 * v20) * (float)(v27 + v24);
          v34 = v31 + v35;
          v35 = v27;
          v27 = v25;
          v25 = v24;
          v24 = v31;
          *(float *)&a1[4 * v28] = (float)(v32 + v33) + (float)((float)(v30 * v21) * v34);
        }
        while ( v23 < a11 );
        v12 = a7;
      }
    }
    if ( v12 == 0.0 )
    {
      if ( a2 != a1 )
        return (__int64)memmove_0(&a1[4 * v22], &a2[4 * v22], 4LL * (a5 - v22));
    }
    else
    {
      return comb_filter_const_sse(
               (int)a1 + 4 * v23,
               (int)a2 + 4 * v23,
               v14,
               a5 - v23,
               LODWORD(v19),
               LODWORD(v20),
               LODWORD(v21));
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800089b0  mov     rax, rsp
0x1800089b3  sub     rsp, 0F8h
0x1800089ba  movss   xmm0, [rsp+0F8h+arg_28]
0x1800089c3  mov     r10, rcx
0x1800089c6  movaps  xmmword ptr [rax-18h], xmm6
0x1800089ca  movss   xmm6, [rsp+0F8h+arg_30]
0x1800089d3  movaps  xmmword ptr [rax-28h], xmm7
0x1800089d7  xorps   xmm7, xmm7
0x1800089da  ucomiss xmm0, xmm7
0x1800089dd  mov     eax, r9d
0x1800089e0  jp      short loc_180008A0A
0x1800089e2  jnz     short loc_180008A0A
0x1800089e4  ucomiss xmm6, xmm7
0x1800089e7  jp      short loc_180008A0A
0x1800089e9  jnz     short loc_180008A0A
0x1800089eb  cmp     rdx, rcx
0x1800089ee  jz      loc_180008D18
0x1800089f4  movsxd  r8, [rsp+0F8h+arg_20]
0x1800089fc  shl     r8, 2; Size
0x180008a00  call    memmove_0
0x180008a05  jmp     loc_180008D18
0x180008a0a  mov     [rsp+0F8h+arg_0], rbx
0x180008a12  mov     r11d, 0Fh
0x180008a18  movsxd  rbx, [rsp+0F8h+arg_40]
0x180008a20  cmp     r8d, r11d
0x180008a23  mov     [rsp+0F8h+var_8], rdi
0x180008a2b  mov     r9d, r11d
0x180008a2e  movaps  [rsp+0F8h+var_38], xmm8
0x180008a37  lea     rdi, qword_180025048
0x180008a3e  movaps  [rsp+0F8h+var_48], xmm9
0x180008a47  cmovg   r9d, r8d
0x180008a4b  movsxd  r8, [rsp+0F8h+arg_38]
0x180008a53  cmp     eax, r11d
0x180008a56  movaps  [rsp+0F8h+var_58], xmm10
0x180008a5f  movaps  xmm8, xmm6
0x180008a63  movaps  [rsp+0F8h+var_78], xmm12
0x180008a6c  cmovg   r11d, eax
0x180008a70  ucomiss xmm0, xmm6
0x180008a73  lea     rcx, [r8+r8*2]
0x180008a77  movaps  [rsp+0F8h+var_88], xmm13
0x180008a7d  movaps  xmm12, xmm0
0x180008a81  mulss   xmm12, dword ptr [rdi+rcx*4]
0x180008a87  movaps  xmm13, xmm0
0x180008a8b  mulss   xmm13, dword ptr [rdi+rcx*4+4]
0x180008a92  movaps  xmm9, xmm6
0x180008a96  movaps  [rsp+0F8h+var_98], xmm14
0x180008a9c  movaps  xmm10, xmm6
0x180008aa0  movaps  xmm14, xmm0
0x180008aa4  mulss   xmm14, dword ptr [rdi+rcx*4+8]
0x180008aab  lea     rcx, [rbx+rbx*2]
0x180008aaf  mulss   xmm8, dword ptr [rdi+rcx*4]
0x180008ab5  mulss   xmm9, dword ptr [rdi+rcx*4+4]
0x180008abc  mulss   xmm10, dword ptr [rdi+rcx*4+8]
0x180008ac3  jp      short loc_180008ADC
0x180008ac5  jnz     short loc_180008ADC
0x180008ac7  cmp     r9d, r11d
0x180008aca  jnz     short loc_180008ADC
0x180008acc  cmp     r8d, ebx
0x180008acf  jnz     short loc_180008ADC
0x180008ad1  xor     r8d, r8d
0x180008ad4  mov     ebx, r8d
0x180008ad7  jmp     loc_180008C76
0x180008adc  mov     edi, [rsp+0F8h+arg_50]
0x180008ae3  mov     eax, 1
0x180008ae8  sub     eax, r11d
0x180008aeb  mov     [rsp+0F8h+arg_8], rsi
0x180008af3  mov     rsi, [rsp+0F8h+arg_48]
0x180008afb  xor     r8d, r8d
0x180008afe  cdqe
0x180008b00  mov     ebx, r8d
0x180008b03  movaps  [rsp+0F8h+var_A8], xmm15
0x180008b09  mov     r8d, edi
0x180008b0c  movsxd  rcx, r11d
0x180008b0f  shl     rcx, 2
0x180008b13  movss   xmm15, dword ptr [rdx+rax*4]
0x180008b19  mov     rax, rdx
0x180008b1c  sub     rax, rcx
0x180008b1f  movss   xmm0, dword ptr [rax]
0x180008b23  mov     eax, r11d
0x180008b26  not     eax
0x180008b28  movss   [rsp+0F8h+var_B8], xmm0
0x180008b2e  cdqe
0x180008b30  movss   xmm0, dword ptr [rdx+rax*4]
0x180008b35  mov     eax, 0FFFFFFFEh
0x180008b3a  sub     eax, r11d
0x180008b3d  movss   [rsp+0F8h+var_B4], xmm0
0x180008b43  cdqe
0x180008b45  movss   xmm0, dword ptr [rdx+rax*4]
0x180008b4a  movss   [rsp+0F8h+arg_28], xmm0
0x180008b53  test    edi, edi
0x180008b55  jle     loc_180008C68
0x180008b5b  movss   xmm7, [rsp+0F8h+var_B8]
0x180008b61  neg     r9d
0x180008b64  movss   xmm6, [rsp+0F8h+var_B4]
0x180008b6a  movaps  [rsp+0F8h+var_68], xmm11
0x180008b73  movss   xmm11, cs:__real@3f800000
0x180008b7c  nop     dword ptr [rax+00h]
0x180008b80  movsxd  rcx, ebx
0x180008b83  mov     eax, ebx
0x180008b85  sub     eax, r11d
0x180008b88  movaps  xmm2, xmm11
0x180008b8c  cdqe
0x180008b8e  inc     ebx
0x180008b90  movss   xmm4, dword ptr [rsi+rcx*4]
0x180008b95  mulss   xmm4, xmm4
0x180008b99  movss   xmm5, dword ptr [rdx+rax*4+8]
0x180008b9f  movsxd  rax, r9d
0x180008ba2  inc     r9d
0x180008ba5  subss   xmm2, xmm4
0x180008ba9  movss   xmm3, dword ptr [rdx+rax*4-4]
0x180008baf  addss   xmm3, dword ptr [rdx+rax*4+4]
0x180008bb5  movaps  xmm1, xmm2
0x180008bb8  movaps  xmm0, xmm2
0x180008bbb  mulss   xmm0, xmm13
0x180008bc0  mulss   xmm1, xmm12
0x180008bc5  mulss   xmm2, xmm14
0x180008bca  mulss   xmm3, xmm0
0x180008bce  mulss   xmm1, dword ptr [rdx+rax*4]
0x180008bd3  movss   xmm0, dword ptr [rdx+rax*4-8]
0x180008bd9  addss   xmm0, dword ptr [rdx+rax*4+8]
0x180008bdf  addss   xmm1, dword ptr [rdx+rcx*4]
0x180008be4  mulss   xmm0, xmm2
0x180008be8  addss   xmm3, xmm1
0x180008bec  movaps  xmm1, xmm4
0x180008bef  mulss   xmm1, xmm9
0x180008bf4  addss   xmm3, xmm0
0x180008bf8  movaps  xmm0, xmm4
0x180008bfb  mulss   xmm0, xmm8
0x180008c00  mulss   xmm4, xmm10
0x180008c05  mulss   xmm0, xmm7
0x180008c09  addss   xmm3, xmm0
0x180008c0d  movaps  xmm0, xmm6
0x180008c10  addss   xmm0, xmm15
0x180008c15  mulss   xmm1, xmm0
0x180008c19  movaps  xmm0, xmm5
0x180008c1c  addss   xmm0, [rsp+0F8h+arg_28]
0x180008c25  movss   [rsp+0F8h+arg_28], xmm6
0x180008c2e  movaps  xmm6, xmm7
0x180008c31  addss   xmm3, xmm1
0x180008c35  movaps  xmm7, xmm15
0x180008c39  movaps  xmm15, xmm5
0x180008c3d  mulss   xmm4, xmm0
0x180008c41  addss   xmm3, xmm4
0x180008c45  movss   dword ptr [r10+rcx*4], xmm3
0x180008c4b  cmp     ebx, edi
0x180008c4d  jl      loc_180008B80
0x180008c53  movaps  xmm11, [rsp+0F8h+var_68]
0x180008c5c  xorps   xmm7, xmm7
0x180008c5f  movss   xmm6, [rsp+0F8h+arg_30]
0x180008c68  mov     rsi, [rsp+0F8h+arg_8]
0x180008c70  movaps  xmm15, [rsp+0F8h+var_A8]
0x180008c76  ucomiss xmm6, xmm7
0x180008c79  mov     rdi, [rsp+0F8h+var_8]
0x180008c81  movaps  xmm14, [rsp+0F8h+var_98]
0x180008c87  movaps  xmm13, [rsp+0F8h+var_88]
0x180008c8d  movaps  xmm12, [rsp+0F8h+var_78]
0x180008c96  jp      short loc_180008CC2
0x180008c98  jnz     short loc_180008CC2
0x180008c9a  cmp     rdx, r10
0x180008c9d  jz      short loc_180008CF5
0x180008c9f  mov     eax, [rsp+0F8h+arg_20]
0x180008ca6  movsxd  rcx, r8d
0x180008ca9  sub     eax, r8d
0x180008cac  movsxd  r8, eax
0x180008caf  shl     r8, 2; Size
0x180008cb3  lea     rdx, [rdx+rcx*4]; Src
0x180008cb7  lea     rcx, [r10+rcx*4]; void *
0x180008cbb  call    memmove_0
0x180008cc0  jmp     short loc_180008CF5
0x180008cc2  mov     r9d, [rsp+0F8h+arg_20]
0x180008cca  mov     r8d, r11d
0x180008ccd  movsxd  rax, ebx
0x180008cd0  sub     r9d, ebx
0x180008cd3  movss   [rsp+0F8h+var_C8], xmm10
0x180008cda  movss   [rsp+0F8h+var_D0], xmm9
0x180008ce1  movss   [rsp+0F8h+var_D8], xmm8
0x180008ce8  lea     rdx, [rdx+rax*4]
0x180008cec  lea     rcx, [r10+rax*4]
0x180008cf0  call    comb_filter_const_sse
0x180008cf5  movaps  xmm8, [rsp+0F8h+var_38]
0x180008cfe  movaps  xmm9, [rsp+0F8h+var_48]
0x180008d07  mov     rbx, [rsp+0F8h+arg_0]
0x180008d0f  movaps  xmm10, [rsp+0F8h+var_58]
0x180008d18  movaps  xmm6, [rsp+0F8h+var_18]
0x180008d20  movaps  xmm7, [rsp+0F8h+var_28]
0x180008d28  add     rsp, 0F8h
0x180008d2f  retn
```
