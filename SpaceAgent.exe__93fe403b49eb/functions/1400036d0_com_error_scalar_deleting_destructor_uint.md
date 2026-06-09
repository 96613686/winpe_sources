# _com_error::`scalar deleting destructor'(uint)

- ea: `0x1400036d0`
- end: `0x1400036ff`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `47`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001200`
- `0x140003680`
- `0x1400036d0`

## pseudocode

```c
_com_error *__fastcall _com_error::`scalar deleting destructor'(_com_error *this, char a2)
{
  _com_error::~_com_error(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1400036d0  mov     [rsp+arg_0], rbx
0x1400036d5  push    rdi
0x1400036d6  sub     rsp, 20h
0x1400036da  mov     ebx, edx
0x1400036dc  mov     rdi, rcx
0x1400036df  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x1400036e4  test    bl, 1
0x1400036e7  jz      short loc_1400036F1
0x1400036e9  mov     rcx, rdi; Block
0x1400036ec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400036f1  mov     rbx, [rsp+28h+arg_0]
0x1400036f6  mov     rax, rdi
0x1400036f9  add     rsp, 20h
0x1400036fd  pop     rdi
0x1400036fe  retn
```
