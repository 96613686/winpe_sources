# _com_error::`scalar deleting destructor'(uint)

- ea: `0x1400088e0`
- end: `0x140008914`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `52`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140002954`
- `0x140008890`
- `0x1400088e0`

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
0x1400088e0  mov     [rsp+arg_0], rbx
0x1400088e5  push    rdi
0x1400088e6  sub     rsp, 20h
0x1400088ea  mov     ebx, edx
0x1400088ec  mov     rdi, rcx
0x1400088ef  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x1400088f4  test    bl, 1
0x1400088f7  jz      short loc_140008906
0x1400088f9  mov     edx, 20h ; ' '
0x1400088fe  mov     rcx, rdi; Block
0x140008901  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140008906  mov     rbx, [rsp+28h+arg_0]
0x14000890b  mov     rax, rdi
0x14000890e  add     rsp, 20h
0x140008912  pop     rdi
0x140008913  retn
```
