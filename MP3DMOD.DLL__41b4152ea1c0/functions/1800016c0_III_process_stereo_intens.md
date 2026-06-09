# III_process_stereo_intens

- ea: `0x1800016c0`
- end: `0x18000186f`
- name: `III_process_stereo_intens`
- size: `431`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x1800012d0`
- `0x180001ac0`

## callees

- `0x1800016c0`

## pseudocode

```c
__int64 __fastcall III_process_stereo_intens(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        unsigned int a5,
        int a6,
        __int64 a7,
        int a8)
{
  __int64 result; // rax
  __int64 v11; // rcx
  float v12; // xmm0_4
  float v13; // xmm1_4
  int v14; // edx
  __int64 v15; // rdx
  float v16; // xmm0_4
  __int64 v17; // rcx
  __int64 v18; // rcx
  float v19; // xmm1_4

  result = a7;
  if ( *(_BYTE *)(a7 + 32) )
  {
    if ( a8 )
    {
      while ( a3 < a4 )
      {
        result = a3++;
        *(float *)(a1 + 4 * result) = *(float *)(a1 + 4 * result) * 0.5;
      }
    }
    else
    {
      result = 6;
      if ( a5 < 7 )
        result = a5;
      if ( a3 < a4 )
      {
        result = (int)result;
        do
        {
          v11 = a3++;
          v12 = *(float *)(a1 + 4 * v11);
          v13 = v12 * *(float *)&dword_180015D00[(int)result];
          *(float *)(a1 + 4 * v11) = v12 * *(float *)&dword_180015CE0[(int)result];
          *(float *)(a2 + 4 * v11) = v13;
        }
        while ( a3 < a4 );
      }
    }
  }
  else
  {
    v14 = 15;
    if ( a8 )
    {
      if ( a5 < 0x10 )
        v14 = a5;
      if ( a3 < a4 )
      {
        v19 = (float)(*(float *)&dword_180015C60[16 * a6 + v14] + 1.0) * 0.5;
        do
        {
          result = a3++;
          *(float *)(a1 + 4 * result) = v19 * *(float *)(a1 + 4 * result);
        }
        while ( a3 < a4 );
      }
    }
    else if ( (a5 & 1) != 0 )
    {
      result = (unsigned int)((int)(a5 + 1) >> 1);
      if ( (unsigned int)result >= 0x10 )
        result = 15;
      if ( a3 < a4 )
      {
        v15 = (int)result + 16LL * a6;
        do
        {
          v16 = *(float *)&dword_180015C60[v15];
          v17 = a3++;
          result = *(unsigned int *)(a1 + 4 * v17);
          *(_DWORD *)(a2 + 4 * v17) = result;
          *(float *)(a1 + 4 * v17) = v16 * *(float *)(a1 + 4 * v17);
        }
        while ( a3 < a4 );
      }
    }
    else
    {
      result = (unsigned int)((int)a5 >> 1);
      if ( (unsigned int)result >= 0x10 )
        result = 15;
      if ( a3 < a4 )
      {
        v18 = (int)result + 16LL * a6;
        do
        {
          result = a3++;
          *(float *)(a2 + 4 * result) = *(float *)&dword_180015C60[v18] * *(float *)(a1 + 4 * result);
        }
        while ( a3 < a4 );
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800016c0  mov     [rsp+arg_0], rbx
0x1800016c5  mov     rax, [rsp+arg_30]
0x1800016ca  mov     r10, rcx
0x1800016cd  xor     ecx, ecx
0x1800016cf  mov     rbx, rdx
0x1800016d2  cmp     [rax+20h], cl
0x1800016d5  jz      loc_18000175C
0x1800016db  cmp     [rsp+arg_38], ecx
0x1800016df  jnz     short loc_180001752
0x1800016e1  cmp     [rsp+arg_20], 7
0x1800016e6  lea     eax, [rcx+6]
0x1800016e9  cmovb   eax, [rsp+arg_20]
0x1800016ee  cmp     r8d, r9d
0x1800016f1  jge     loc_180001869
0x1800016f7  cdqe
0x1800016f9  lea     r11, cs:180000000h
0x180001700  movsxd  rcx, r8d
0x180001703  inc     r8d
0x180001706  movss   xmm1, dword ptr [r10+rcx*4]
0x18000170c  movaps  xmm0, xmm1
0x18000170f  mulss   xmm1, ds:rva dword_180015D00[r11+rax*4]
0x180001719  mulss   xmm0, ds:rva dword_180015CE0[r11+rax*4]
0x180001723  movss   dword ptr [r10+rcx*4], xmm0
0x180001729  movss   dword ptr [rdx+rcx*4], xmm1
0x18000172e  cmp     r8d, r9d
0x180001731  jl      short loc_180001700
0x180001733  jmp     loc_180001869
0x180001738  movsxd  rax, r8d
0x18000173b  inc     r8d
0x18000173e  movss   xmm0, dword ptr [r10+rax*4]
0x180001744  mulss   xmm0, cs:__real@3f000000
0x18000174c  movss   dword ptr [r10+rax*4], xmm0
0x180001752  cmp     r8d, r9d
0x180001755  jl      short loc_180001738
0x180001757  jmp     loc_180001869
0x18000175c  mov     edx, 0Fh
0x180001761  cmp     [rsp+arg_38], ecx
0x180001765  jnz     loc_180001810
0x18000176b  mov     eax, [rsp+arg_20]
0x18000176f  test    al, 1
0x180001771  jz      short loc_1800017C8
0x180001773  inc     eax
0x180001775  sar     eax, 1
0x180001777  cmp     eax, 10h
0x18000177a  cmovnb  eax, edx
0x18000177d  cmp     r8d, r9d
0x180001780  jge     loc_180001869
0x180001786  movsxd  rdx, [rsp+arg_28]
0x18000178b  lea     r11, cs:180000000h
0x180001792  shl     rdx, 4
0x180001796  cdqe
0x180001798  add     rdx, rax
0x18000179b  movss   xmm0, ds:rva dword_180015C60[r11+rdx*4]
0x1800017a5  movsxd  rcx, r8d
0x1800017a8  inc     r8d
0x1800017ab  mov     eax, [r10+rcx*4]
0x1800017af  mov     [rbx+rcx*4], eax
0x1800017b2  mulss   xmm0, dword ptr [r10+rcx*4]
0x1800017b8  movss   dword ptr [r10+rcx*4], xmm0
0x1800017be  cmp     r8d, r9d
0x1800017c1  jl      short loc_18000179B
0x1800017c3  jmp     loc_180001869
0x1800017c8  sar     eax, 1
0x1800017ca  cmp     eax, 10h
0x1800017cd  cmovnb  eax, edx
0x1800017d0  cmp     r8d, r9d
0x1800017d3  jge     loc_180001869
0x1800017d9  movsxd  rcx, [rsp+arg_28]
0x1800017de  lea     r11, cs:180000000h
0x1800017e5  shl     rcx, 4
0x1800017e9  cdqe
0x1800017eb  add     rcx, rax
0x1800017ee  movss   xmm0, ds:rva dword_180015C60[r11+rcx*4]
0x1800017f8  movsxd  rax, r8d
0x1800017fb  inc     r8d
0x1800017fe  mulss   xmm0, dword ptr [r10+rax*4]
0x180001804  movss   dword ptr [rbx+rax*4], xmm0
0x180001809  cmp     r8d, r9d
0x18000180c  jl      short loc_1800017EE
0x18000180e  jmp     short loc_180001869
0x180001810  cmp     [rsp+arg_20], 10h
0x180001815  cmovb   edx, [rsp+arg_20]
0x18000181a  cmp     r8d, r9d
0x18000181d  jge     short loc_180001869
0x18000181f  movsxd  rcx, [rsp+arg_28]
0x180001824  lea     r11, cs:180000000h
0x18000182b  shl     rcx, 4
0x18000182f  movsxd  rax, edx
0x180001832  add     rcx, rax
0x180001835  movss   xmm1, ds:rva dword_180015C60[r11+rcx*4]
0x18000183f  addss   xmm1, cs:__real@3f800000
0x180001847  mulss   xmm1, cs:__real@3f000000
0x18000184f  movsxd  rax, r8d
0x180001852  movaps  xmm0, xmm1
0x180001855  inc     r8d
0x180001858  mulss   xmm0, dword ptr [r10+rax*4]
0x18000185e  movss   dword ptr [r10+rax*4], xmm0
0x180001864  cmp     r8d, r9d
0x180001867  jl      short loc_18000184F
0x180001869  mov     rbx, [rsp+arg_0]
0x18000186e  retn
```
