# XPathNodeIteratorBase::`scalar deleting destructor'(uint)

- ea: `0x180003628`
- end: `0x180003662`
- name: `??_GXPathNodeIteratorBase@@UEAAPEAXI@Z`
- size: `58`
- prototype: `void *__fastcall(XPathNodeIteratorBase *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800034d0`

## callees

- `0x1800010b8`
- `0x180002398`
- `0x180003628`

## pseudocode

```c
XPathNodeIteratorBase *__fastcall XPathNodeIteratorBase::`scalar deleting destructor'(
        XPathNodeIteratorBase *this,
        char a2)
{
  *((_QWORD *)this + 1) = &SimpleIUnknownImpl<IXPathExpression>::`vftable';
  ModuleRefCounter::Release();
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003628  mov     [rsp+arg_0], rbx
0x18000362d  push    rdi
0x18000362e  sub     rsp, 20h
0x180003632  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180003639  mov     ebx, edx
0x18000363b  mov     [rcx+8], rax
0x18000363f  mov     rdi, rcx
0x180003642  call    ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
0x180003647  test    bl, 1
0x18000364a  jz      short loc_180003654
0x18000364c  mov     rcx, rdi; Block
0x18000364f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003654  mov     rbx, [rsp+28h+arg_0]
0x180003659  mov     rax, rdi
0x18000365c  add     rsp, 20h
0x180003660  pop     rdi
0x180003661  retn
```
