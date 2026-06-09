# VerifyStackAvailable

- ea: `0x140036f94`
- end: `0x140036fb6`
- name: `VerifyStackAvailable`
- size: `34`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140004810`
- `0x1400145ac`
- `0x140018880`
- `0x14001c194`
- `0x14001c4a8`
- `0x14001c788`
- `0x14001ca30`

## callees

- `0x140036e5c`
- `0x140036f94`
- `0x140036fbc`

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
0x140036f94  push    rbx
0x140036f96  sub     rsp, 20h
0x140036f9a  mov     ebx, 1
0x140036f9f  call    InternalVerifyStackAvailable
0x140036fa4  jmp     short loc_140036FAE
0x140036fa6  xor     ebx, ebx
0x140036fa8  call    _resetstkoflw_static
0x140036fad  nop
0x140036fae  mov     eax, ebx
0x140036fb0  add     rsp, 20h
0x140036fb4  pop     rbx
0x140036fb5  retn
0x140038f9f  push    rbp
0x140038fa1  sub     rsp, 20h
0x140038fa5  mov     rbp, rdx
0x140038fa8  mov     rax, [rcx]
0x140038fab  xor     ecx, ecx
0x140038fad  cmp     dword ptr [rax], 0C00000FDh
0x140038fb3  setz    cl
0x140038fb6  mov     eax, ecx
0x140038fb8  add     rsp, 20h
0x140038fbc  pop     rbp
0x140038fbd  retn
```
