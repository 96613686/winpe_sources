# VerifyStackAvailable

- ea: `0x18000cae4`
- end: `0x18000cb07`
- name: `VerifyStackAvailable`
- size: `35`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x1800049a0`
- `0x18000b824`
- `0x18000bba0`
- `0x18000c1e0`
- `0x18000fb30`
- `0x1800101c0`
- `0x180010680`
- `0x180014990`

## callees

- `0x18000cae4`
- `0x18000cb10`
- `0x18001b220`

## pseudocode

```c
__int64 VerifyStackAvailable()
{
  InternalVerifyStackAvailable();
  return 1;
}

```

## disassembly

```asm
0x18000cae4  push    rbx
0x18000cae6  sub     rsp, 20h
0x18000caea  mov     ebx, 1
0x18000caef  call    InternalVerifyStackAvailable
0x18000caf4  jmp     short loc_18000CAFE
0x18000caf6  xor     ebx, ebx
0x18000caf8  call    _resetstkoflw_static
0x18000cafd  nop
0x18000cafe  mov     eax, ebx
0x18000cb00  add     rsp, 20h
0x18000cb04  pop     rbx
0x18000cb05  retn
0x18001b890  push    rbp
0x18001b892  sub     rsp, 20h
0x18001b896  mov     rbp, rdx
0x18001b899  mov     rax, [rcx]
0x18001b89c  xor     ecx, ecx
0x18001b89e  cmp     dword ptr [rax], 0C00000FDh
0x18001b8a4  setz    cl
0x18001b8a7  mov     eax, ecx
0x18001b8a9  add     rsp, 20h
0x18001b8ad  pop     rbp
0x18001b8ae  retn
```
