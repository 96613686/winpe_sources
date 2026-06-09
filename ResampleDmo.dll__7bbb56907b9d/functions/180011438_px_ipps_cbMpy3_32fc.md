# px_ipps_cbMpy3_32fc

- ea: `0x180011438`
- end: `0x180011546`
- name: `px_ipps_cbMpy3_32fc`
- size: `270`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18005363c`
- `0x1800538f4`
- `0x180053a6c`
- `0x180055d6c`
- `0x180056024`
- `0x18005619c`
- `0x1800588dc`
- `0x180058b94`
- `0x180058d0c`

## callees

- `0x180011438`

## pseudocode

```c
__int64 __fastcall px_ipps_cbMpy3_32fc(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 result; // rax
  __int64 v5; // r11
  __int64 v6; // rbx
  float *v7; // rdi
  __int64 v8; // r10
  float v9; // xmm6_4
  float v10; // xmm2_4
  float v11; // xmm3_4
  float v12; // xmm1_4
  float v13; // xmm2_4
  float v14; // xmm4_4
  float v15; // xmm0_4
  float v16; // xmm1_4
  float v17; // xmm2_4
  float v18; // xmm3_4

  result = 0;
  if ( a4 - 1 > 0 )
  {
    v5 = a2 - a1;
    v6 = a3 - a1;
    v7 = (float *)(a1 + 12);
    v8 = ((unsigned int)(a4 - 2) >> 1) + 1;
    result = (unsigned int)(2 * v8);
    do
    {
      v9 = *(float *)((char *)v7 + v5 - 8);
      v10 = *(v7 - 1);
      v11 = v10 * *(float *)((char *)v7 + v5);
      v12 = *(float *)((char *)v7 + v5 - 4);
      v13 = v10 * v12;
      v14 = (float)(*(v7 - 3) * v9) + (float)(*(float *)((char *)v7 + v5 - 12) * *(v7 - 2));
      v15 = *(float *)((char *)v7 + v5) * *v7;
      v16 = v12 * *v7;
      *(float *)((char *)v7 + v6 - 12) = (float)(*(float *)((char *)v7 + v5 - 12) * *(v7 - 3)) - (float)(v9 * *(v7 - 2));
      *(float *)((char *)v7 + v6 - 8) = v14;
      *(float *)((char *)v7 + v6 - 4) = v13 - v15;
      *(float *)((char *)v7 + v6) = v11 + v16;
      v7 += 4;
      --v8;
    }
    while ( v8 );
  }
  if ( (a4 & 1) != 0 )
  {
    result = (int)result;
    v17 = *(float *)(a1 + 8LL * (int)result + 4);
    v18 = (float)(*(float *)(a2 + 8LL * (int)result) * *(float *)(a1 + 8LL * (int)result))
        - (float)(v17 * *(float *)(a2 + 8LL * (int)result + 4));
    *(float *)(a3 + 8LL * (int)result + 4) = (float)(*(float *)(a2 + 8LL * (int)result) * v17)
                                           + (float)(*(float *)(a2 + 8LL * (int)result + 4)
                                                   * *(float *)(a1 + 8LL * (int)result));
    *(float *)(a3 + 8LL * (int)result) = v18;
  }
  return result;
}

```

## disassembly

```asm
0x180011438  mov     [rsp+arg_0], rbx
0x18001143d  push    rdi
0x18001143e  sub     rsp, 10h
0x180011442  lea     r10d, [r9-1]
0x180011446  xor     eax, eax
0x180011448  movaps  [rsp+18h+var_18], xmm6
0x18001144c  test    r10d, r10d
0x18001144f  jle     loc_1800114F2
0x180011455  lea     eax, [r10-1]
0x180011459  mov     r11, rdx
0x18001145c  mov     rbx, r8
0x18001145f  shr     eax, 1
0x180011461  sub     r11, rcx
0x180011464  sub     rbx, rcx
0x180011467  inc     eax
0x180011469  lea     rdi, [rcx+0Ch]
0x18001146d  mov     r10d, eax
0x180011470  add     eax, eax
0x180011472  movss   xmm5, dword ptr [r11+rdi-0Ch]
0x180011479  movss   xmm6, dword ptr [r11+rdi-8]
0x180011480  movss   xmm3, dword ptr [rdi-4]
0x180011485  movaps  xmm0, xmm5
0x180011488  mulss   xmm5, dword ptr [rdi-0Ch]
0x18001148d  movaps  xmm2, xmm3
0x180011490  mulss   xmm0, dword ptr [rdi-8]
0x180011495  mulss   xmm3, dword ptr [r11+rdi]
0x18001149b  movss   xmm1, dword ptr [r11+rdi-4]
0x1800114a2  movss   xmm4, dword ptr [rdi-0Ch]
0x1800114a7  mulss   xmm4, xmm6
0x1800114ab  mulss   xmm6, dword ptr [rdi-8]
0x1800114b0  mulss   xmm2, xmm1
0x1800114b4  addss   xmm4, xmm0
0x1800114b8  movss   xmm0, dword ptr [r11+rdi]
0x1800114be  subss   xmm5, xmm6
0x1800114c2  mulss   xmm0, dword ptr [rdi]
0x1800114c6  mulss   xmm1, dword ptr [rdi]
0x1800114ca  movss   dword ptr [rbx+rdi-0Ch], xmm5
0x1800114d0  movss   dword ptr [rbx+rdi-8], xmm4
0x1800114d6  subss   xmm2, xmm0
0x1800114da  addss   xmm3, xmm1
0x1800114de  movss   dword ptr [rbx+rdi-4], xmm2
0x1800114e4  movss   dword ptr [rbx+rdi], xmm3
0x1800114e9  add     rdi, 10h
0x1800114ed  dec     r10
0x1800114f0  jnz     short loc_180011472
0x1800114f2  test    r9b, 1
0x1800114f6  jz      short loc_180011537
0x1800114f8  cdqe
0x1800114fa  movss   xmm3, dword ptr [rdx+rax*8]
0x1800114ff  movss   xmm2, dword ptr [rcx+rax*8+4]
0x180011505  movss   xmm0, dword ptr [rdx+rax*8+4]
0x18001150b  mulss   xmm0, dword ptr [rcx+rax*8]
0x180011510  movaps  xmm1, xmm3
0x180011513  mulss   xmm3, dword ptr [rcx+rax*8]
0x180011518  mulss   xmm1, xmm2
0x18001151c  mulss   xmm2, dword ptr [rdx+rax*8+4]
0x180011522  addss   xmm1, xmm0
0x180011526  subss   xmm3, xmm2
0x18001152a  movss   dword ptr [r8+rax*8+4], xmm1
0x180011531  movss   dword ptr [r8+rax*8], xmm3
0x180011537  mov     rbx, [rsp+18h+arg_0]
0x18001153c  movaps  xmm6, [rsp+18h+var_18]
0x180011540  add     rsp, 10h
0x180011544  pop     rdi
0x180011545  retn
```
