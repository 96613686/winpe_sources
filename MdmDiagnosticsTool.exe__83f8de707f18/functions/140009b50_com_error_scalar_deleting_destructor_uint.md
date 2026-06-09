# _com_error::`scalar deleting destructor'(uint)

- ea: `0x140009b50`
- end: `0x140009b87`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `55`
- prototype: `void *__fastcall(_com_error *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140009b00`
- `0x140009b50`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140009b6c`
- `msvcrt!??3@YAXPEAX@Z` at `0x140009b6c`

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
0x140009b50  mov     [rsp+arg_0], rbx
0x140009b55  push    rdi
0x140009b56  sub     rsp, 20h
0x140009b5a  mov     ebx, edx
0x140009b5c  mov     rdi, rcx
0x140009b5f  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x140009b64  test    bl, 1
0x140009b67  jz      short loc_140009B78
0x140009b69  mov     rcx, rdi
0x140009b6c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140009b73  nop     dword ptr [rax+rax+00h]
0x140009b78  mov     rbx, [rsp+28h+arg_0]
0x140009b7d  mov     rax, rdi
0x140009b80  add     rsp, 20h
0x140009b84  pop     rdi
0x140009b85  retn
```
