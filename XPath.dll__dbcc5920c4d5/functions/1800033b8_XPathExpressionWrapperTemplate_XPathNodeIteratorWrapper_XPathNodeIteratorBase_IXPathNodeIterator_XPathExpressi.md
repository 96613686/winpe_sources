# XPathExpressionWrapperTemplate<XPathNodeIteratorWrapper,XPathNodeIteratorBase,IXPathNodeIterator>::~XPathExpressionWrapperTemplate<XPathNodeIteratorWrapper,XPathNodeIteratorBase,IXPathNodeIterator>(void)

- ea: `0x1800033b8`
- end: `0x1800033df`
- name: `??1?$XPathExpressionWrapperTemplate@VXPathNodeIteratorWrapper@@VXPathNodeIteratorBase@@UIXPathNodeIterator@@@@UEAA@XZ`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003420`

## callees

- `0x1800020b4`
- `0x180002398`

## pseudocode

```c
void __fastcall XPathExpressionWrapperTemplate<XPathNodeIteratorWrapper,XPathNodeIteratorBase,IXPathNodeIterator>::~XPathExpressionWrapperTemplate<XPathNodeIteratorWrapper,XPathNodeIteratorBase,IXPathNodeIterator>(
        __int64 a1)
{
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)(a1 + 24));
  *(_QWORD *)(a1 + 8) = &SimpleIUnknownImpl<IXPathExpression>::`vftable';
  ModuleRefCounter::Release();
}

```

## disassembly

```asm
0x1800033b8  push    rbx
0x1800033ba  sub     rsp, 20h
0x1800033be  mov     rbx, rcx
0x1800033c1  add     rcx, 18h
0x1800033c5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800033ca  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x1800033d1  mov     [rbx+8], rax
0x1800033d5  add     rsp, 20h
0x1800033d9  pop     rbx
0x1800033da  jmp     ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
```
