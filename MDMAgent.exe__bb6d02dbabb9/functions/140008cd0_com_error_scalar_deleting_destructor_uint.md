# _com_error::`scalar deleting destructor'(uint)

- ea: `0x140008cd0`
- end: `0x140008d05`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `53`
- prototype: `void *__fastcall(_com_error *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400029e4`
- `0x140008c78`
- `0x140008cd0`

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
0x140008cd0  mov     [rsp+arg_0], rbx
0x140008cd5  push    rdi
0x140008cd6  sub     rsp, 20h
0x140008cda  mov     ebx, edx
0x140008cdc  mov     rdi, rcx
0x140008cdf  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x140008ce4  test    bl, 1
0x140008ce7  jz      short loc_140008CF6
0x140008ce9  mov     edx, 20h ; ' '
0x140008cee  mov     rcx, rdi; Block
0x140008cf1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140008cf6  mov     rbx, [rsp+28h+arg_0]
0x140008cfb  mov     rax, rdi
0x140008cfe  add     rsp, 20h
0x140008d02  pop     rdi
0x140008d03  retn
```
