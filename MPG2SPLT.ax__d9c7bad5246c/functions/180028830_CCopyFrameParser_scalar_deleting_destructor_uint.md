# CCopyFrameParser::`scalar deleting destructor'(uint)

- ea: `0x180028830`
- end: `0x180028864`
- name: `??_GCCopyFrameParser@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CCopyFrameParser *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800287a0`

## callees

- `0x180001048`
- `0x18002858c`
- `0x180028830`

## pseudocode

```c
CCopyFrameParser *__fastcall CCopyFrameParser::`scalar deleting destructor'(CCopyFrameParser *this, char a2)
{
  CCopyFrameParser::~CCopyFrameParser(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180028830  mov     [rsp+arg_0], rbx
0x180028835  push    rdi
0x180028836  sub     rsp, 20h
0x18002883a  mov     ebx, edx
0x18002883c  mov     rdi, rcx
0x18002883f  call    ??1CCopyFrameParser@@UEAA@XZ; CCopyFrameParser::~CCopyFrameParser(void)
0x180028844  test    bl, 1
0x180028847  jz      short loc_180028856
0x180028849  mov     edx, 188h; unsigned __int64
0x18002884e  mov     rcx, rdi; void *
0x180028851  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028856  mov     rbx, [rsp+28h+arg_0]
0x18002885b  mov     rax, rdi
0x18002885e  add     rsp, 20h
0x180028862  pop     rdi
0x180028863  retn
```
