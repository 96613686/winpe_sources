# XPathException::`scalar deleting destructor'(uint)

- ea: `0x180011100`
- end: `0x18001112f`
- name: `??_GXPathException@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(XPathException *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1800010b8`
- `0x1800110b8`
- `0x180011100`

## pseudocode

```c
XPathException *__fastcall XPathException::`scalar deleting destructor'(XPathException *this, char a2)
{
  XPathException::~XPathException(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180011100  mov     [rsp+arg_0], rbx
0x180011105  push    rdi
0x180011106  sub     rsp, 20h
0x18001110a  mov     ebx, edx
0x18001110c  mov     rdi, rcx
0x18001110f  call    ??1XPathException@@UEAA@XZ; XPathException::~XPathException(void)
0x180011114  test    bl, 1
0x180011117  jz      short loc_180011121
0x180011119  mov     rcx, rdi; Block
0x18001111c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011121  mov     rbx, [rsp+28h+arg_0]
0x180011126  mov     rax, rdi
0x180011129  add     rsp, 20h
0x18001112d  pop     rdi
0x18001112e  retn
```
