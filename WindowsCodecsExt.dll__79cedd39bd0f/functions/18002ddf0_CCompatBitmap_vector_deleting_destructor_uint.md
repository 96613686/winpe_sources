# CCompatBitmap::`vector deleting destructor'(uint)

- ea: `0x18002ddf0`
- end: `0x18002de24`
- name: `??_ECCompatBitmap@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CCompatBitmap *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180021a54`
- `0x18002dc48`
- `0x18002ddf0`

## pseudocode

```c
CCompatBitmap *__fastcall CCompatBitmap::`vector deleting destructor'(CCompatBitmap *this, char a2)
{
  CCompatBitmap::~CCompatBitmap(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18002ddf0  mov     [rsp+arg_0], rbx
0x18002ddf5  push    rdi
0x18002ddf6  sub     rsp, 20h
0x18002ddfa  mov     ebx, edx
0x18002ddfc  mov     rdi, rcx
0x18002ddff  call    ??1CCompatBitmap@@UEAA@XZ; CCompatBitmap::~CCompatBitmap(void)
0x18002de04  test    bl, 1
0x18002de07  jz      short loc_18002DE16
0x18002de09  mov     edx, 0B0h
0x18002de0e  mov     rcx, rdi; Block
0x18002de11  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002de16  mov     rbx, [rsp+28h+arg_0]
0x18002de1b  mov     rax, rdi
0x18002de1e  add     rsp, 20h
0x18002de22  pop     rdi
0x18002de23  retn
```
