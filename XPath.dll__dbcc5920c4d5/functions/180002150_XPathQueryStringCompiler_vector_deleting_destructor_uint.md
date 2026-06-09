# XPathQueryStringCompiler::`vector deleting destructor'(uint)

- ea: `0x180002150`
- end: `0x18000217f`
- name: `??_EXPathQueryStringCompiler@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(XPathQueryStringCompiler *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800010b8`
- `0x1800020d8`
- `0x180002150`

## pseudocode

```c
XPathQueryStringCompiler *__fastcall XPathQueryStringCompiler::`vector deleting destructor'(
        XPathQueryStringCompiler *this,
        char a2)
{
  XPathQueryStringCompiler::~XPathQueryStringCompiler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002150  mov     [rsp+arg_0], rbx
0x180002155  push    rdi
0x180002156  sub     rsp, 20h
0x18000215a  mov     ebx, edx
0x18000215c  mov     rdi, rcx
0x18000215f  call    ??1XPathQueryStringCompiler@@UEAA@XZ; XPathQueryStringCompiler::~XPathQueryStringCompiler(void)
0x180002164  test    bl, 1
0x180002167  jz      short loc_180002171
0x180002169  mov     rcx, rdi; Block
0x18000216c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002171  mov     rbx, [rsp+28h+arg_0]
0x180002176  mov     rax, rdi
0x180002179  add     rsp, 20h
0x18000217d  pop     rdi
0x18000217e  retn
```
