# m7_ipps_initTabTwdBase_32f

- ea: `0x180015cb4`
- end: `0x180015df8`
- name: `m7_ipps_initTabTwdBase_32f`
- size: `324`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000daa8`
- `0x18000dc00`
- `0x18000ecc8`
- `0x18000ee20`
- `0x18000ff88`
- `0x1800100e0`

## callees

- `0x18000b6f4`
- `0x18000b748`
- `0x180015cb4`

## pseudocode

```c
char *__fastcall m7_ipps_initTabTwdBase_32f(int a1, float *a2)
{
  char v2; // r9
  __int64 v4; // rbx
  int v5; // r8d
  __int64 v6; // rdi
  char *v7; // r15
  __int64 *v8; // rcx
  float v9; // eax
  int v10; // r14d
  double v11; // xmm6_8
  float *v12; // rbp
  double v13; // xmm0_8
  float v14; // xmm1_4
  int v15; // r14d
  __int64 v16; // rbp
  __int64 v17; // rbx
  int v18; // edi
  double v19; // xmm0_8
  float v20; // xmm1_4

  v2 = a1;
  v4 = 0;
  v5 = 1 << a1;
  v6 = (1 << a1) / 4;
  v7 = (char *)&a2[(int)v6 + 1] + (-(4 * ((_DWORD)v6 + 1) + (_DWORD)a2) & 0x1F);
  if ( a1 > 10 )
  {
    v10 = v5 / 8;
    v11 = 6.283185307179586 / (double)v5;
    if ( v5 / 8 >= 0 )
    {
      v12 = a2;
      do
      {
        v13 = o_sin_0((double)(int)v4 * v11);
        LODWORD(v4) = v4 + 1;
        v14 = v13;
        *v12++ = v14;
      }
      while ( (int)v4 <= v10 );
    }
    v15 = v10 + 1;
    v16 = v6;
    v17 = v15;
    if ( v15 <= v6 )
    {
      v18 = v6 - v15;
      do
      {
        v19 = cos((double)v18-- * v11);
        v20 = v19;
        a2[v17++] = v20;
      }
      while ( v17 <= v16 );
    }
  }
  else
  {
    if ( (int)v6 > 0 )
    {
      v8 = fft_fix_twiddle_table_32f;
      do
      {
        v9 = *(float *)v8;
        v8 = (__int64 *)((char *)v8 + 4 * (1 << (10 - v2)));
        a2[v4++] = v9;
      }
      while ( v4 < v6 );
    }
    a2[v6] = 1.0;
  }
  return v7;
}

```

## disassembly

```asm
0x180015cb4  mov     rax, rsp
0x180015cb7  mov     [rax+8], rbx
0x180015cbb  mov     [rax+10h], rbp
0x180015cbf  mov     [rax+18h], rsi
0x180015cc3  push    rdi
0x180015cc4  push    r14
0x180015cc6  push    r15
0x180015cc8  sub     rsp, 30h
0x180015ccc  movaps  xmmword ptr [rax-28h], xmm6
0x180015cd0  mov     r9d, ecx
0x180015cd3  mov     r15, rdx
0x180015cd6  mov     r8d, 1
0x180015cdc  mov     rsi, r15
0x180015cdf  xor     ebx, ebx
0x180015ce1  shl     r8d, cl
0x180015ce4  mov     eax, r8d
0x180015ce7  cdq
0x180015ce8  and     edx, 3
0x180015ceb  add     eax, edx
0x180015ced  sar     eax, 2
0x180015cf0  movsxd  rdi, eax
0x180015cf3  lea     eax, [rdi+1]
0x180015cf6  cdqe
0x180015cf8  shl     rax, 2
0x180015cfc  lea     rcx, [rax+r15]
0x180015d00  neg     rcx
0x180015d03  and     ecx, 1Fh
0x180015d06  add     rcx, rax
0x180015d09  add     r15, rcx
0x180015d0c  mov     ecx, 0Ah
0x180015d11  cmp     r9d, ecx
0x180015d14  jg      short loc_180015D4C
0x180015d16  test    edi, edi
0x180015d18  jle     short loc_180015D40
0x180015d1a  sub     ecx, r9d
0x180015d1d  lea     eax, [rbx+1]
0x180015d20  shl     eax, cl
0x180015d22  lea     rcx, fft_fix_twiddle_table_32f
0x180015d29  movsxd  r8, eax
0x180015d2c  shl     r8, 2
0x180015d30  mov     eax, [rcx]
0x180015d32  add     rcx, r8
0x180015d35  mov     [rsi+rbx*4], eax
0x180015d38  inc     rbx
0x180015d3b  cmp     rbx, rdi
0x180015d3e  jl      short loc_180015D30
0x180015d40  mov     dword ptr [rsi+rdi*4], 3F800000h
0x180015d47  jmp     loc_180015DD7
0x180015d4c  movsd   xmm6, cs:__real@401921fb54442d18
0x180015d54  movd    xmm0, r8d
0x180015d59  mov     eax, r8d
0x180015d5c  cdq
0x180015d5d  and     edx, 7
0x180015d60  add     eax, edx
0x180015d62  sar     eax, 3
0x180015d65  mov     r14d, eax
0x180015d68  cvtdq2pd xmm0, xmm0
0x180015d6c  divsd   xmm6, xmm0
0x180015d70  test    eax, eax
0x180015d72  js      short loc_180015D9F
0x180015d74  mov     rbp, rsi
0x180015d77  movd    xmm0, ebx
0x180015d7b  cvtdq2pd xmm0, xmm0
0x180015d7f  mulsd   xmm0, xmm6; X
0x180015d83  call    _o_sin_0
0x180015d88  xorps   xmm1, xmm1
0x180015d8b  inc     ebx
0x180015d8d  cvtsd2ss xmm1, xmm0
0x180015d91  movss   dword ptr [rbp+0], xmm1
0x180015d96  lea     rbp, [rbp+4]
0x180015d9a  cmp     ebx, r14d
0x180015d9d  jle     short loc_180015D77
0x180015d9f  inc     r14d
0x180015da2  mov     rbp, rdi
0x180015da5  movsxd  rbx, r14d
0x180015da8  cmp     rbx, rdi
0x180015dab  jg      short loc_180015DD7
0x180015dad  sub     edi, r14d
0x180015db0  movd    xmm0, edi
0x180015db4  cvtdq2pd xmm0, xmm0
0x180015db8  mulsd   xmm0, xmm6; X
0x180015dbc  call    cos
0x180015dc1  xorps   xmm1, xmm1
0x180015dc4  dec     edi
0x180015dc6  cvtsd2ss xmm1, xmm0
0x180015dca  movss   dword ptr [rsi+rbx*4], xmm1
0x180015dcf  inc     rbx
0x180015dd2  cmp     rbx, rbp
0x180015dd5  jle     short loc_180015DB0
0x180015dd7  mov     rbx, [rsp+48h+arg_0]
0x180015ddc  mov     rbp, [rsp+48h+arg_8]
0x180015de1  mov     rsi, [rsp+48h+arg_10]
0x180015de6  movaps  xmm6, [rsp+48h+var_28]
0x180015deb  mov     rax, r15
0x180015dee  add     rsp, 30h
0x180015df2  pop     r15
0x180015df4  pop     r14
0x180015df6  pop     rdi
0x180015df7  retn
```
