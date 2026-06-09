# _com_error::`scalar deleting destructor'(uint)

- ea: `0x18001c720`
- end: `0x18001c755`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `53`
- prototype: `void *__fastcall(_com_error *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001cc8`
- `0x18001c6c8`
- `0x18001c720`

## pseudocode

```c
_com_error *__fastcall _com_error::`scalar deleting destructor'(_com_error *this, char a2)
{
  _com_error::~_com_error(this);
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x20);
  return this;
}

```

## disassembly

```asm
0x18001c720  mov     [rsp+arg_0], rbx
0x18001c725  push    rdi
0x18001c726  sub     rsp, 20h
0x18001c72a  mov     ebx, edx
0x18001c72c  mov     rdi, rcx
0x18001c72f  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x18001c734  test    bl, 1
0x18001c737  jz      short loc_18001C746
0x18001c739  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x18001c73e  mov     rcx, rdi; void *
0x18001c741  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c746  mov     rbx, [rsp+28h+arg_0]
0x18001c74b  mov     rax, rdi
0x18001c74e  add     rsp, 20h
0x18001c752  pop     rdi
0x18001c753  retn
```
