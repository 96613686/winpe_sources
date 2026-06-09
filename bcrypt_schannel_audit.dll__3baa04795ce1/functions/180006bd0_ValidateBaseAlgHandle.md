# ValidateBaseAlgHandle

- ea: `0x180006bd0`
- end: `0x180006d9a`
- name: `ValidateBaseAlgHandle`
- size: `458`
- prototype: ``
- caller_count: `10`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180005280`
- `0x180005b00`
- `0x180005bc0`
- `0x180006020`
- `0x1800066f0`
- `0x180007b50`
- `0x180008890`
- `0x18000a230`
- `0x18000b1d0`
- `0x180014320`

## callees

- `0x180004200`
- `0x180005b00`
- `0x180006bd0`
- `0x1800070d0`
- `0x180007b50`
- `0x180009430`
- `0x18001b7a9`

## pseudocode

```c
signed __int64 __fastcall ValidateBaseAlgHandle(unsigned __int64 a1)
{
  volatile signed __int64 result; // rax
  unsigned __int64 v2; // rcx
  __int64 v3; // rdi
  __int64 v4; // r14
  __int64 v5; // rbp
  char *v6; // rsi
  volatile signed __int64 *v7; // rbx
  __int64 v8; // r9
  __int64 v9; // rdx
  BCRYPT_ALG_HANDLE v10; // rcx
  SIZE_T v11; // r15
  char *v12; // rax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp+8h] BYREF

  if ( !a1 )
    return 0;
  if ( (a1 & 0xF) != 1 )
  {
    if ( *(_DWORD *)a1 >= 0x3C8u && *(_DWORD *)(a1 + 4) == 1431655761 )
      return a1;
    else
      return 0;
  }
  v2 = a1 >> 4;
  if ( v2 >= 0x4B )
    return 0;
  _mm_lfence();
  v3 = 5 * v2;
  v4 = *((unsigned __int8 *)PseudoHandlePropertyTable + 5 * v2 + 3);
  v5 = *((unsigned __int8 *)PseudoHandlePropertyTable + 5 * v2 + 4);
  v6 = (char *)PseudoHandleTableTable[v4];
  if ( !v6 )
  {
    v11 = 8LL * *((unsigned __int8 *)&PseudoHandleTableSize + v4);
    v12 = (char *)SafeAllocaAllocateFromHeap(v11);
    v6 = v12;
    if ( !v12 )
      return 0;
    memset_0(v12, 0, v11);
    if ( _InterlockedCompareExchange64(&PseudoHandleTableTable[v4], (signed __int64)v6, 0) )
    {
      MSCryptFree(v6);
      v6 = (char *)PseudoHandleTableTable[v4];
    }
  }
  result = *(_QWORD *)&v6[8 * v5];
  v7 = (volatile signed __int64 *)&v6[8 * v5];
  if ( !result )
  {
    v8 = *((unsigned __int8 *)PseudoHandlePropertyTable + v3 + 1);
    v9 = *((unsigned __int8 *)PseudoHandlePropertyTable + v3);
    phAlgorithm = 0;
    if ( BCryptOpenAlgorithmProvider(&phAlgorithm, PseudoHandleAlgName[v9], 0, PseudoHandleFlags[v8]) < 0
      || *((_BYTE *)PseudoHandlePropertyTable + v3 + 2)
      && BCryptSetProperty(
           phAlgorithm,
           L"ChainingMode",
           (PUCHAR)PseudohandleChainingMode[2 * *((unsigned __int8 *)PseudoHandlePropertyTable + v3 + 2)],
           dword_18001D858[4 * *((unsigned __int8 *)PseudoHandlePropertyTable + v3 + 2)],
           0) < 0
      || (v10 = phAlgorithm,
          *((_DWORD *)phAlgorithm + 2) |= 0x80000000,
          _InterlockedCompareExchange64(v7, (signed __int64)v10, 0)) )
    {
      if ( phAlgorithm )
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    }
    return *v7;
  }
  return result;
}

```

## disassembly

```asm
0x180006bd0  push    rbx
0x180006bd2  sub     rsp, 50h
0x180006bd6  xor     ebx, ebx
0x180006bd8  test    rcx, rcx
0x180006bdb  jz      short loc_180006C04
0x180006bdd  movzx   eax, cl
0x180006be0  and     al, 0Fh
0x180006be2  cmp     al, 1
0x180006be4  jz      short loc_180006C0E
0x180006be6  cmp     dword ptr [rcx], 3C8h
0x180006bec  jb      short loc_180006BFB
0x180006bee  cmp     dword ptr [rcx+4], 55555551h
0x180006bf5  jz      loc_180006D92
0x180006bfb  xor     eax, eax
0x180006bfd  add     rsp, 50h
0x180006c01  pop     rbx
0x180006c02  retn
0x180006c04  mov     rax, rbx
0x180006c07  add     rsp, 50h
0x180006c0b  pop     rbx
0x180006c0c  retn
0x180006c0e  shr     rcx, 4
0x180006c12  cmp     rcx, 4Bh ; 'K'
0x180006c16  jnb     short loc_180006C04
0x180006c18  mov     [rsp+58h+arg_10], rbp
0x180006c1d  mov     [rsp+58h+arg_18], rsi
0x180006c22  mov     [rsp+58h+var_10], rdi
0x180006c27  mov     [rsp+58h+var_18], r12
0x180006c2c  mov     [rsp+58h+var_20], r14
0x180006c31  mov     [rsp+58h+var_28], r15
0x180006c36  lfence
0x180006c39  lea     r12, __ImageBase
0x180006c40  lea     rdi, [rcx+rcx*4]
0x180006c44  movzx   r14d, byte ptr [rdi+r12+1E8C3h]
0x180006c4d  movzx   ebp, byte ptr [rdi+r12+1E8C4h]
0x180006c56  mov     rsi, rva PseudoHandleTableTable[r12+r14*8]
0x180006c5e  test    rsi, rsi
0x180006c61  jz      loc_180006D3C
0x180006c67  mov     rax, [rsi+rbp*8]
0x180006c6b  lea     rbx, [rsi+rbp*8]
0x180006c6f  test    rax, rax
0x180006c72  jnz     loc_180006D19
0x180006c78  movzx   r9d, byte ptr [rdi+r12+1E8C1h]
0x180006c81  lea     rcx, [rsp+58h+phAlgorithm]; phAlgorithm
0x180006c86  movzx   edx, byte ptr [rdi+r12+1E8C0h]
0x180006c8f  xor     r8d, r8d; pszImplementation
0x180006c92  mov     [rsp+58h+phAlgorithm], rax
0x180006c97  mov     r9d, ds:rva PseudoHandleFlags[r12+r9*4]; dwFlags
0x180006c9f  mov     rdx, ds:rva PseudoHandleAlgName[r12+rdx*8]; pszAlgId
0x180006ca7  call    BCryptOpenAlgorithmProvider
0x180006cac  test    eax, eax
0x180006cae  js      short loc_180006D05
0x180006cb0  movzx   eax, byte ptr [rdi+r12+1E8C2h]
0x180006cb9  test    al, al
0x180006cbb  jz      short loc_180006CF0
0x180006cbd  mov     rcx, [rsp+58h+phAlgorithm]; hObject
0x180006cc2  lea     rdx, aChainingmode; "ChainingMode"
0x180006cc9  mov     r8d, eax
0x180006ccc  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180006cd4  add     r8, r8
0x180006cd7  mov     r9d, ds:rva dword_18001D858[r12+r8*8]; cbInput
0x180006cdf  mov     r8, ds:rva PseudohandleChainingMode[r12+r8*8]; pbInput
0x180006ce7  call    BCryptSetProperty
0x180006cec  test    eax, eax
0x180006cee  js      short loc_180006D05
0x180006cf0  mov     rcx, [rsp+58h+phAlgorithm]
0x180006cf5  or      dword ptr [rcx+8], 80000000h
0x180006cfc  xor     eax, eax
0x180006cfe  lock cmpxchg [rbx], rcx
0x180006d03  jz      short loc_180006D16
0x180006d05  mov     rcx, [rsp+58h+phAlgorithm]; hAlgorithm
0x180006d0a  test    rcx, rcx
0x180006d0d  jz      short loc_180006D16
0x180006d0f  xor     edx, edx; dwFlags
0x180006d11  call    BCryptCloseAlgorithmProvider
0x180006d16  mov     rax, [rbx]
0x180006d19  mov     r15, [rsp+58h+var_28]
0x180006d1e  mov     r12, [rsp+58h+var_18]
0x180006d23  mov     rdi, [rsp+58h+var_10]
0x180006d28  mov     rsi, [rsp+58h+arg_18]
0x180006d2d  mov     rbp, [rsp+58h+arg_10]
0x180006d32  mov     r14, [rsp+58h+var_20]
0x180006d37  jmp     loc_180006BFD
0x180006d3c  movzx   r15d, byte ptr [r14+r12+1E898h]
0x180006d45  shl     r15, 3
0x180006d49  mov     rcx, r15
0x180006d4c  call    SafeAllocaAllocateFromHeap
0x180006d51  mov     rsi, rax
0x180006d54  test    rax, rax
0x180006d57  jz      short loc_180006D8D
0x180006d59  mov     r8, r15; Size
0x180006d5c  xor     edx, edx; Val
0x180006d5e  mov     rcx, rax; void *
0x180006d61  call    memset_0
0x180006d66  xor     eax, eax
0x180006d68  lock cmpxchg rva PseudoHandleTableTable[r12+r14*8], rsi
0x180006d72  jz      loc_180006C67
0x180006d78  mov     rcx, rsi
0x180006d7b  call    MSCryptFree
0x180006d80  mov     rsi, rva PseudoHandleTableTable[r12+r14*8]
0x180006d88  jmp     loc_180006C67
0x180006d8d  mov     rax, rbx
0x180006d90  jmp     short loc_180006D19
0x180006d92  mov     rax, rcx
0x180006d95  jmp     loc_180006BFD
```
