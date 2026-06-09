# VerifyStackAvailable

- ea: `0x180008078`
- end: `0x18000809b`
- name: `VerifyStackAvailable`
- size: `35`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180004f90`
- `0x180007730`
- `0x180014ce0`
- `0x180014e14`

## callees

- `0x180008078`
- `0x1800080b0`
- `0x1800183e4`

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
0x180008078  push    rbx
0x18000807a  sub     rsp, 20h
0x18000807e  mov     ebx, 1
0x180008083  call    InternalVerifyStackAvailable
0x180008088  jmp     short loc_180008092
0x18000808a  xor     ebx, ebx
0x18000808c  call    _resetstkoflw_static
0x180008091  nop
0x180008092  mov     eax, ebx
0x180008094  add     rsp, 20h
0x180008098  pop     rbx
0x180008099  retn
0x1800186ec  push    rbp
0x1800186ee  sub     rsp, 20h
0x1800186f2  mov     rbp, rdx
0x1800186f5  mov     rax, [rcx]
0x1800186f8  xor     ecx, ecx
0x1800186fa  cmp     dword ptr [rax], 0C00000FDh
0x180018700  setz    cl
0x180018703  mov     eax, ecx
0x180018705  add     rsp, 20h
0x180018709  pop     rbp
0x18001870a  retn
```
