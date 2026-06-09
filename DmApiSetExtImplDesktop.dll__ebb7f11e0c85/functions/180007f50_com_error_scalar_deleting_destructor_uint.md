# _com_error::`scalar deleting destructor'(uint)

- ea: `0x180007f50`
- end: `0x180007f87`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `55`
- prototype: `void *__fastcall(_com_error *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007f04`
- `0x180007f50`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007f6c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007f6c`

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
0x180007f50  mov     [rsp+arg_0], rbx
0x180007f55  push    rdi
0x180007f56  sub     rsp, 20h
0x180007f5a  mov     ebx, edx
0x180007f5c  mov     rdi, rcx
0x180007f5f  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x180007f64  test    bl, 1
0x180007f67  jz      short loc_180007F78
0x180007f69  mov     rcx, rdi
0x180007f6c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007f73  nop     dword ptr [rax+rax+00h]
0x180007f78  mov     rbx, [rsp+28h+arg_0]
0x180007f7d  mov     rax, rdi
0x180007f80  add     rsp, 20h
0x180007f84  pop     rdi
0x180007f85  retn
```
