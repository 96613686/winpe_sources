# MSCryptPqDsaCloseProvider

- ea: `0x18006a650`
- end: `0x18006a6cb`
- name: `MSCryptPqDsaCloseProvider`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180010270`
- `0x18006a650`
- `0x18006bcc4`
- `0x18007f7e0`

## string_xrefs

- `0x18006a672`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptPqDsaCloseProvider(unsigned __int64 a1, int a2)
{
  __int64 v2; // r9
  unsigned int v3; // ebx
  __int64 v4; // rcx
  unsigned int *v5; // rax
  unsigned int *v6; // rbx

  if ( !a1 )
  {
    v2 = 610;
LABEL_3:
    v3 = -1073741811;
    v4 = 3221225485LL;
    goto LABEL_4;
  }
  if ( a2 )
  {
    v2 = 617;
    goto LABEL_3;
  }
  v5 = (unsigned int *)validatePqDsaAlgorithm(a1);
  v6 = v5;
  if ( v5 )
  {
    RtlSetVolatileMemory(v5, 0, *v5);
    MSCryptFree(v6);
    return 0;
  }
  v3 = -1073741816;
  v2 = 625;
  v4 = 3221225480LL;
LABEL_4:
  DebugTraceError(v4, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", v2);
  return v3;
}

```

## disassembly

```asm
0x18006a650  push    rbx
0x18006a652  sub     rsp, 20h
0x18006a656  test    rcx, rcx
0x18006a659  jnz     short loc_18006A680
0x18006a65b  mov     r9d, 262h
0x18006a661  mov     ebx, 0C000000Dh
0x18006a666  mov     ecx, 0C000000Dh
0x18006a66b  lea     rdx, aStatus_0; "status"
0x18006a672  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006a679  call    DebugTraceError
0x18006a67e  jmp     short loc_18006A6C2
0x18006a680  test    edx, edx
0x18006a682  jz      short loc_18006A68C
0x18006a684  mov     r9d, 269h
0x18006a68a  jmp     short loc_18006A661
0x18006a68c  call    validatePqDsaAlgorithm
0x18006a691  mov     rbx, rax
0x18006a694  test    rax, rax
0x18006a697  jnz     short loc_18006A6AB
0x18006a699  mov     ebx, 0C0000008h
0x18006a69e  mov     r9d, 271h
0x18006a6a4  mov     ecx, 0C0000008h
0x18006a6a9  jmp     short loc_18006A66B
0x18006a6ab  mov     r8d, [rax]; Size
0x18006a6ae  xor     edx, edx; Val
0x18006a6b0  mov     rcx, rbx; void *
0x18006a6b3  call    RtlSetVolatileMemory
0x18006a6b8  mov     rcx, rbx
0x18006a6bb  call    MSCryptFree
0x18006a6c0  xor     ebx, ebx
0x18006a6c2  mov     eax, ebx
0x18006a6c4  add     rsp, 20h
0x18006a6c8  pop     rbx
0x18006a6c9  retn
```
