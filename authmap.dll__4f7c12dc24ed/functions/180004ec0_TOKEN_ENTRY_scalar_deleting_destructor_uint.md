# TOKEN_ENTRY::`scalar deleting destructor'(uint)

- ea: `0x180004ec0`
- end: `0x180004eef`
- name: `??_GTOKEN_ENTRY@@EEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(TOKEN_ENTRY *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180004e30`
- `0x180004ec0`

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
0x180004ec0  mov     [rsp+arg_0], rbx
0x180004ec5  push    rdi
0x180004ec6  sub     rsp, 20h
0x180004eca  mov     ebx, edx
0x180004ecc  mov     rdi, rcx
0x180004ecf  call    ??1TOKEN_ENTRY@@EEAA@XZ; TOKEN_ENTRY::~TOKEN_ENTRY(void)
0x180004ed4  test    bl, 1
0x180004ed7  jz      short loc_180004EE1
0x180004ed9  mov     rcx, rdi; Block
0x180004edc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004ee1  mov     rbx, [rsp+28h+arg_0]
0x180004ee6  mov     rax, rdi
0x180004ee9  add     rsp, 20h
0x180004eed  pop     rdi
0x180004eee  retn
```
