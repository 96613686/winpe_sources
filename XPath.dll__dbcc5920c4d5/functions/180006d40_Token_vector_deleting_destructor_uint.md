# Token::`vector deleting destructor'(uint)

- ea: `0x180006d40`
- end: `0x180006d6f`
- name: `??_EToken@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(Token *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1800010b8`
- `0x180006880`
- `0x180006d40`

## pseudocode

```c
Node *__fastcall Token::`vector deleting destructor'(Node *this, char a2)
{
  Token::~Token(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180006d40  mov     [rsp+arg_0], rbx
0x180006d45  push    rdi
0x180006d46  sub     rsp, 20h
0x180006d4a  mov     ebx, edx
0x180006d4c  mov     rdi, rcx
0x180006d4f  call    ??1Token@@UEAA@XZ; Token::~Token(void)
0x180006d54  test    bl, 1
0x180006d57  jz      short loc_180006D61
0x180006d59  mov     rcx, rdi; Block
0x180006d5c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006d61  mov     rbx, [rsp+28h+arg_0]
0x180006d66  mov     rax, rdi
0x180006d69  add     rsp, 20h
0x180006d6d  pop     rdi
0x180006d6e  retn
```
