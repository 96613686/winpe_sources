# LEQ_UpdateWeight

- ea: `0x18000f4e0`
- end: `0x18000f55a`
- name: `LEQ_UpdateWeight`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180008df0`
- `0x18000f280`

## callees

- `0x18000f4e0`

## pseudocode

```c
__int64 __fastcall LEQ_UpdateWeight(__int64 a1, int a2)
{
  float v2; // xmm3_4
  unsigned int v3; // r8d
  unsigned int v4; // r9d
  unsigned int v5; // eax
  unsigned int v6; // eax
  __int64 result; // rax

  v2 = FLOAT_1_0;
  v3 = 0;
  v4 = *(_DWORD *)(a1 + 56);
  while ( 1 )
  {
    v5 = 3;
    if ( v4 < 3 )
      v5 = *(_DWORD *)(a1 + 56);
    if ( v3 >= v5 )
      break;
    v2 = v2 * 0.1;
    ++v3;
  }
  while ( 1 )
  {
    v6 = 7;
    if ( v4 < 7 )
      v6 = *(_DWORD *)(a1 + 56);
    if ( v3 >= v6 )
      break;
    v2 = v2 * 0.31600001;
    ++v3;
  }
  result = (unsigned int)a2;
  *(float *)(a1 + 44) = (float)((float)*(int *)(a1 + 60) * (float)(86.132812 / (float)a2)) * v2;
  return result;
}

```

## disassembly

```asm
0x18000f4e0  movss   xmm3, cs:__real@3f800000
0x18000f4e8  xor     r8d, r8d
0x18000f4eb  mov     r9d, [rcx+38h]
0x18000f4ef  mov     eax, 3
0x18000f4f4  cmp     r9d, eax
0x18000f4f7  cmovb   eax, r9d
0x18000f4fb  cmp     r8d, eax
0x18000f4fe  jnb     short loc_18000F50D
0x18000f500  mulss   xmm3, cs:__real@3dcccccd
0x18000f508  inc     r8d
0x18000f50b  jmp     short loc_18000F4EF
0x18000f50d  mov     eax, 7
0x18000f512  cmp     r9d, eax
0x18000f515  cmovb   eax, r9d
0x18000f519  cmp     r8d, eax
0x18000f51c  jb      short loc_18000F54D
0x18000f51e  mov     eax, [rcx+3Ch]
0x18000f521  xorps   xmm2, xmm2
0x18000f524  movss   xmm1, cs:__real@42ac4400
0x18000f52c  xorps   xmm0, xmm0
0x18000f52f  cvtsi2ss xmm2, rax
0x18000f534  mov     eax, edx
0x18000f536  cvtsi2ss xmm0, rax
0x18000f53b  divss   xmm1, xmm0
0x18000f53f  mulss   xmm2, xmm1
0x18000f543  mulss   xmm2, xmm3
0x18000f547  movss   dword ptr [rcx+2Ch], xmm2
0x18000f54c  retn
0x18000f54d  mulss   xmm3, cs:__real@3ea1cac1
0x18000f555  inc     r8d
0x18000f558  jmp     short loc_18000F50D
```
