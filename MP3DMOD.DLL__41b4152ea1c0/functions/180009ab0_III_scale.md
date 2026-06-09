# III_scale

- ea: `0x180009ab0`
- end: `0x180009bff`
- name: `III_scale`
- size: `335`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180009968`
- `0x18000d974`

## callees

- `0x180009ab0`
- `0x18000efb0`
- `0x18000efc8`

## pseudocode

```c
void *__fastcall III_scale(__int64 a1, char *a2, int a3, int a4, unsigned int a5)
{
  void *result; // rax
  int v7; // ebx
  double v10; // xmm6_8
  __int64 v11; // rdi
  int v12; // esi
  int v13; // eax
  double v14; // xmm0_8
  float v15; // xmm0_4

  result = (void *)(int)a5;
  v7 = a3;
  if ( a5 > 0x7F )
  {
    if ( a3 < a4 )
      return memset_0(&a2[4 * a3], 0, 4LL * (a4 - a3));
  }
  else
  {
    v10 = *(float *)&dword_180015F20[a5];
    if ( a3 < a4 )
    {
      do
      {
        v11 = 4LL * v7;
        v12 = *(_DWORD *)(v11 + a1);
        v13 = -v12;
        if ( v12 > 0 )
          v13 = *(_DWORD *)(v11 + a1);
        if ( v13 )
        {
          if ( v13 >= 128 )
            v14 = pow((double)v13, 1.333333333333333);
          else
            v14 = *(float *)&dword_180015D20[v13];
          if ( v12 <= 0 )
            *(_QWORD *)&v14 ^= _xmm;
          v15 = v14 * v10;
        }
        else
        {
          v15 = 0.0;
        }
        result = a2;
        ++v7;
        *(float *)&a2[v11] = v15;
      }
      while ( v7 < a4 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009ab0  mov     r11, rsp
0x180009ab3  mov     [r11+20h], rbx
0x180009ab7  push    rbp
0x180009ab8  push    r14
0x180009aba  push    r15
0x180009abc  sub     rsp, 60h
0x180009ac0  movsxd  rax, [rsp+78h+arg_20]
0x180009ac8  mov     ebp, r9d
0x180009acb  movsxd  rbx, r8d
0x180009ace  mov     r15, rdx
0x180009ad1  mov     r14, rcx
0x180009ad4  cmp     eax, 7Fh
0x180009ad7  ja      loc_180009BD6
0x180009add  mov     [r11+18h], r12
0x180009ae1  lea     r12, cs:180000000h
0x180009ae8  movaps  [rsp+78h+var_28], xmm6
0x180009aed  movss   xmm6, ds:rva dword_180015F20[r12+rax*4]
0x180009af7  cvtps2pd xmm6, xmm6
0x180009afa  cmp     ebx, r9d
0x180009afd  jge     loc_180009B9F
0x180009b03  mov     [r11+8], rsi
0x180009b07  mov     [r11+10h], rdi
0x180009b0b  movaps  [rsp+78h+var_38], xmm7
0x180009b10  xorps   xmm7, xmm7
0x180009b13  movaps  xmmword ptr [r11-48h], xmm8
0x180009b18  movsd   xmm8, cs:__xmm@80000000000000008000000000000000
0x180009b21  movaps  xmmword ptr [r11-58h], xmm9
0x180009b26  movsd   xmm9, cs:__real@3ff5555555555555
0x180009b2f  nop
0x180009b30  movsxd  rax, ebx
0x180009b33  lea     rdi, ds:0[rax*4]
0x180009b3b  mov     esi, [rdi+r14]
0x180009b3f  mov     eax, esi
0x180009b41  neg     eax
0x180009b43  cmovs   eax, esi
0x180009b46  test    eax, eax
0x180009b48  jz      short loc_180009BBE
0x180009b4a  cmp     eax, 80h
0x180009b4f  jge     short loc_180009BC3
0x180009b51  cdqe
0x180009b53  movss   xmm0, ds:rva dword_180015D20[r12+rax*4]
0x180009b5d  cvtps2pd xmm0, xmm0
0x180009b60  test    esi, esi
0x180009b62  jg      short loc_180009B68
0x180009b64  xorps   xmm0, xmm8
0x180009b68  mulsd   xmm0, xmm6
0x180009b6c  cvtsd2ss xmm0, xmm0
0x180009b70  mov     rax, r15
0x180009b73  inc     ebx
0x180009b75  movss   dword ptr [rax+rdi], xmm0
0x180009b7a  cmp     ebx, ebp
0x180009b7c  jl      short loc_180009B30
0x180009b7e  movaps  xmm9, [rsp+78h+var_58]
0x180009b84  movaps  xmm8, [rsp+78h+var_48]
0x180009b8a  movaps  xmm7, [rsp+78h+var_38]
0x180009b8f  mov     rdi, [rsp+78h+arg_8]
0x180009b97  mov     rsi, [rsp+78h+arg_0]
0x180009b9f  mov     r12, [rsp+78h+arg_10]
0x180009ba7  movaps  xmm6, [rsp+78h+var_28]
0x180009bac  mov     rbx, [rsp+78h+arg_18]
0x180009bb4  add     rsp, 60h
0x180009bb8  pop     r15
0x180009bba  pop     r14
0x180009bbc  pop     rbp
0x180009bbd  retn
0x180009bbe  movaps  xmm0, xmm7
0x180009bc1  jmp     short loc_180009B70
0x180009bc3  movd    xmm0, eax
0x180009bc7  movaps  xmm1, xmm9; Y
0x180009bcb  cvtdq2pd xmm0, xmm0; X
0x180009bcf  call    pow
0x180009bd4  jmp     short loc_180009B60
0x180009bd6  cmp     ebx, ebp
0x180009bd8  jge     short loc_180009BAC
0x180009bda  sub     ebp, ebx
0x180009bdc  lea     rcx, [rdx+rbx*4]; void *
0x180009be0  movsxd  r8, ebp
0x180009be3  xor     edx, edx; Val
0x180009be5  shl     r8, 2; Size
0x180009be9  mov     rbx, [rsp+78h+arg_18]
0x180009bf1  add     rsp, 60h
0x180009bf5  pop     r15
0x180009bf7  pop     r14
0x180009bf9  pop     rbp
0x180009bfa  jmp     memset_0
```
