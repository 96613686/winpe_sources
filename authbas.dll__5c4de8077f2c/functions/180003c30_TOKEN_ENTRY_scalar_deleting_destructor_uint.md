# TOKEN_ENTRY::`scalar deleting destructor'(uint)

- ea: `0x180003c30`
- end: `0x180003c5f`
- name: `??_GTOKEN_ENTRY@@EEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(TOKEN_ENTRY *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180003ba4`
- `0x180003c30`

## pseudocode

```c
TOKEN_ENTRY *__fastcall TOKEN_ENTRY::`scalar deleting destructor'(TOKEN_ENTRY *this, char a2)
{
  TOKEN_ENTRY::~TOKEN_ENTRY(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003c30  mov     [rsp+arg_0], rbx
0x180003c35  push    rdi
0x180003c36  sub     rsp, 20h
0x180003c3a  mov     ebx, edx
0x180003c3c  mov     rdi, rcx
0x180003c3f  call    ??1TOKEN_ENTRY@@EEAA@XZ; TOKEN_ENTRY::~TOKEN_ENTRY(void)
0x180003c44  test    bl, 1
0x180003c47  jz      short loc_180003C51
0x180003c49  mov     rcx, rdi; Block
0x180003c4c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003c51  mov     rbx, [rsp+28h+arg_0]
0x180003c56  mov     rax, rdi
0x180003c59  add     rsp, 20h
0x180003c5d  pop     rdi
0x180003c5e  retn
```
