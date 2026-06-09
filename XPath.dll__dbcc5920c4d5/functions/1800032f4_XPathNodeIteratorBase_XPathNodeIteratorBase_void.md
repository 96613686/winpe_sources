# XPathNodeIteratorBase::XPathNodeIteratorBase(void)

- ea: `0x1800032f4`
- end: `0x180003332`
- name: `??0XPathNodeIteratorBase@@QEAA@XZ`
- size: `62`
- prototype: `XPathNodeIteratorBase *__fastcall(XPathNodeIteratorBase *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180005068`
- `0x18000624c`
- `0x18000637c`
- `0x1800063d4`
- `0x180006440`
- `0x1800094f4`
- `0x1800096d8`
- `0x180009890`

## callees

- `0x1800021a4`

## pseudocode

```c
XPathNodeIteratorBase *__fastcall XPathNodeIteratorBase::XPathNodeIteratorBase(XPathNodeIteratorBase *this)
{
  *((_QWORD *)this + 1) = &SimpleIUnknownImpl<IXPathExpression>::`vftable';
  *((_DWORD *)this + 4) = 1;
  ModuleRefCounter::AddRef();
  *(_QWORD *)this = &XPathNodeIteratorBase::`vftable'{for `IXPathNodeIterator'};
  *((_QWORD *)this + 1) = &XPathNodeIteratorBase::`vftable'{for `XPathExpressionBase'};
  return this;
}

```

## disassembly

```asm
0x1800032f4  push    rbx
0x1800032f6  sub     rsp, 20h
0x1800032fa  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180003301  mov     rbx, rcx
0x180003304  mov     [rcx+8], rax
0x180003308  mov     dword ptr [rcx+10h], 1
0x18000330f  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180003314  lea     rax, ??_7XPathNodeIteratorBase@@6BIXPathNodeIterator@@@; const XPathNodeIteratorBase::`vftable'{for `IXPathNodeIterator'}
0x18000331b  mov     [rbx], rax
0x18000331e  lea     rax, ??_7XPathNodeIteratorBase@@6BXPathExpressionBase@@@; const XPathNodeIteratorBase::`vftable'{for `XPathExpressionBase'}
0x180003325  mov     [rbx+8], rax
0x180003329  mov     rax, rbx
0x18000332c  add     rsp, 20h
0x180003330  pop     rbx
0x180003331  retn
```
