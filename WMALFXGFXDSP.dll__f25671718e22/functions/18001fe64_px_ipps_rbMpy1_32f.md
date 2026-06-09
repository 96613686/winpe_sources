# px_ipps_rbMpy1_32f

- ea: `0x18001fe64`
- end: `0x18001fee3`
- name: `px_ipps_rbMpy1_32f`
- size: `127`
- prototype: ``
- caller_count: `45`
- callee_count: `1`
- tags: ``

## callers

- `0x180018990`
- `0x180018af0`
- `0x180018ccc`
- `0x1800194e0`
- `0x1800196c0`
- `0x18001981c`
- `0x180019b10`
- `0x180019cb0`
- `0x180019eb0`
- `0x18001a6e0`
- `0x18001a900`
- `0x18001aa94`
- `0x18001adb0`
- `0x18001af50`
- `0x18001b150`
- `0x18001b980`
- `0x18001bba0`
- `0x18001bd34`
- `0x18001c560`
- `0x18001c700`
- `0x18001ce80`
- `0x18001d170`
- `0x18001d3d0`
- `0x18001d570`
- `0x18001dce0`
- `0x18001dfd0`
- `0x18001e160`
- `0x18001e300`
- `0x18001ea70`
- `0x18001ed60`
- `0x180022bc0`
- `0x180022fe0`
- `0x1800230fc`
- `0x18002351c`
- `0x180036808`
- `0x180036aec`
- `0x180036c24`
- `0x180036f08`
- `0x18004cf04`
- `0x18004d1e8`
- `0x18004d320`
- `0x18004d604`
- `0x180059558`
- `0x18005bc88`
- `0x18005e7ec`

## callees

- `0x18001fe64`

## pseudocode

```c
__int64 __fastcall px_ipps_rbMpy1_32f(float a1, __int64 a2, int a3)
{
  int v3; // r9d
  __int64 v4; // rax
  float *v5; // rcx
  unsigned __int64 v6; // rax
  float v7; // xmm1_4
  float v8; // xmm1_4
  __int64 result; // rax

  v3 = 0;
  v4 = a3 - 3;
  if ( v4 > 0 )
  {
    v5 = (float *)(a2 + 8);
    v6 = ((unsigned __int64)(v4 - 1) >> 2) + 1;
    v3 = 4 * v6;
    do
    {
      v7 = a1 * *(v5 - 1);
      *(v5 - 2) = a1 * *(v5 - 2);
      *(v5 - 1) = v7;
      v8 = a1 * v5[1];
      *v5 = a1 * *v5;
      v5[1] = v8;
      v5 += 4;
      --v6;
    }
    while ( v6 );
  }
  for ( result = v3; result < a3; ++result )
    *(float *)(a2 + 4 * result) = a1 * *(float *)(a2 + 4 * result);
  return result;
}

```

## disassembly

```asm
0x18001fe64  lea     eax, [r8-3]
0x18001fe68  xor     r9d, r9d
0x18001fe6b  movaps  xmm2, xmm0
0x18001fe6e  cdqe
0x18001fe70  test    rax, rax
0x18001fe73  jle     short loc_18001FEC5
0x18001fe75  dec     rax
0x18001fe78  lea     rcx, [rdx+8]
0x18001fe7c  shr     rax, 2
0x18001fe80  inc     rax
0x18001fe83  mov     r9d, eax
0x18001fe86  shl     r9d, 2
0x18001fe8a  movaps  xmm0, xmm2
0x18001fe8d  movaps  xmm1, xmm2
0x18001fe90  mulss   xmm0, dword ptr [rcx-8]
0x18001fe95  mulss   xmm1, dword ptr [rcx-4]
0x18001fe9a  movss   dword ptr [rcx-8], xmm0
0x18001fe9f  movss   dword ptr [rcx-4], xmm1
0x18001fea4  movaps  xmm0, xmm2
0x18001fea7  movaps  xmm1, xmm2
0x18001feaa  mulss   xmm0, dword ptr [rcx]
0x18001feae  mulss   xmm1, dword ptr [rcx+4]
0x18001feb3  movss   dword ptr [rcx], xmm0
0x18001feb7  movss   dword ptr [rcx+4], xmm1
0x18001febc  lea     rcx, [rcx+10h]
0x18001fec0  dec     rax
0x18001fec3  jnz     short loc_18001FE8A
0x18001fec5  movsxd  rax, r9d
0x18001fec8  movsxd  rcx, r8d
0x18001fecb  jmp     short loc_18001FEDD
0x18001fecd  movaps  xmm0, xmm2
0x18001fed0  mulss   xmm0, dword ptr [rdx+rax*4]
0x18001fed5  movss   dword ptr [rdx+rax*4], xmm0
0x18001feda  inc     rax
0x18001fedd  cmp     rax, rcx
0x18001fee0  jl      short loc_18001FECD
0x18001fee2  retn
```
