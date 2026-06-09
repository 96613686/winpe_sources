# TOKEN_ENTRY::`scalar deleting destructor'(uint)

- ea: `0x180004380`
- end: `0x1800043af`
- name: `??_GTOKEN_ENTRY@@EEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(TOKEN_ENTRY *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1800029b8`
- `0x180004290`
- `0x180004380`

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
0x180004380  mov     [rsp+arg_0], rbx
0x180004385  push    rdi
0x180004386  sub     rsp, 20h
0x18000438a  mov     ebx, edx
0x18000438c  mov     rdi, rcx
0x18000438f  call    ??1TOKEN_ENTRY@@EEAA@XZ; TOKEN_ENTRY::~TOKEN_ENTRY(void)
0x180004394  test    bl, 1
0x180004397  jz      short loc_1800043A1
0x180004399  mov     rcx, rdi; Block
0x18000439c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800043a1  mov     rbx, [rsp+28h+arg_0]
0x1800043a6  mov     rax, rdi
0x1800043a9  add     rsp, 20h
0x1800043ad  pop     rdi
0x1800043ae  retn
```
