# XPathQueryStringCompiler::SimplifiedLocationPathNode::`vector deleting destructor'(uint)

- ea: `0x180006c50`
- end: `0x180006c7f`
- name: `??_ESimplifiedLocationPathNode@XPathQueryStringCompiler@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(XPathQueryStringCompiler::SimplifiedLocationPathNode *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800010b8`
- `0x180006798`
- `0x180006c50`

## pseudocode

```c
Node *__fastcall XPathQueryStringCompiler::SimplifiedLocationPathNode::`vector deleting destructor'(
        Node *this,
        char a2)
{
  XPathQueryStringCompiler::SimplifiedLocationPathNode::~SimplifiedLocationPathNode(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180006c50  mov     [rsp+arg_0], rbx
0x180006c55  push    rdi
0x180006c56  sub     rsp, 20h
0x180006c5a  mov     ebx, edx
0x180006c5c  mov     rdi, rcx
0x180006c5f  call    ??1SimplifiedLocationPathNode@XPathQueryStringCompiler@@UEAA@XZ; XPathQueryStringCompiler::SimplifiedLocationPathNode::~SimplifiedLocationPathNode(void)
0x180006c64  test    bl, 1
0x180006c67  jz      short loc_180006C71
0x180006c69  mov     rcx, rdi; Block
0x180006c6c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006c71  mov     rbx, [rsp+28h+arg_0]
0x180006c76  mov     rax, rdi
0x180006c79  add     rsp, 20h
0x180006c7d  pop     rdi
0x180006c7e  retn
```
