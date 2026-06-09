# XPathNodeIteratorWrapper::`vector deleting destructor'(uint)

- ea: `0x180003668`
- end: `0x180003697`
- name: `??_EXPathNodeIteratorWrapper@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(XPathNodeIteratorWrapper *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800034e0`

## callees

- `0x1800010b8`
- `0x180003420`
- `0x180003668`

## pseudocode

```c
XPathNodeIteratorWrapper *__fastcall XPathNodeIteratorWrapper::`vector deleting destructor'(
        XPathNodeIteratorWrapper *this,
        char a2)
{
  XPathNodeIteratorWrapper::~XPathNodeIteratorWrapper(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003668  mov     [rsp+arg_0], rbx
0x18000366d  push    rdi
0x18000366e  sub     rsp, 20h
0x180003672  mov     ebx, edx
0x180003674  mov     rdi, rcx
0x180003677  call    ??1XPathNodeIteratorWrapper@@UEAA@XZ; XPathNodeIteratorWrapper::~XPathNodeIteratorWrapper(void)
0x18000367c  test    bl, 1
0x18000367f  jz      short loc_180003689
0x180003681  mov     rcx, rdi; Block
0x180003684  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003689  mov     rbx, [rsp+28h+arg_0]
0x18000368e  mov     rax, rdi
0x180003691  add     rsp, 20h
0x180003695  pop     rdi
0x180003696  retn
```
