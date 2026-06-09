# XPathNodeIteratorWrapper::~XPathNodeIteratorWrapper(void)

- ea: `0x180003420`
- end: `0x18000343f`
- name: `??1XPathNodeIteratorWrapper@@UEAA@XZ`
- size: `31`
- prototype: `void __fastcall(XPathNodeIteratorWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003668`

## callees

- `0x1800020b4`
- `0x1800033b8`

## pseudocode

```c
void __fastcall XPathNodeIteratorWrapper::~XPathNodeIteratorWrapper(XPathNodeIteratorWrapper *this)
{
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 4);
  XPathExpressionWrapperTemplate<XPathNodeIteratorWrapper,XPathNodeIteratorBase,IXPathNodeIterator>::~XPathExpressionWrapperTemplate<XPathNodeIteratorWrapper,XPathNodeIteratorBase,IXPathNodeIterator>((__int64)this);
}

```

## disassembly

```asm
0x180003420  push    rbx
0x180003422  sub     rsp, 20h
0x180003426  mov     rbx, rcx
0x180003429  add     rcx, 20h ; ' '
0x18000342d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003432  mov     rcx, rbx
0x180003435  add     rsp, 20h
0x180003439  pop     rbx
0x18000343a  jmp     ??1?$XPathExpressionWrapperTemplate@VXPathNodeIteratorWrapper@@VXPathNodeIteratorBase@@UIXPathNodeIterator@@@@UEAA@XZ; XPathExpressionWrapperTemplate<XPathNodeIteratorWrapper,XPathNodeIteratorBase,IXPathNodeIterator>::~XPathExpressionWrapperTemplate<XPathNodeIteratorWrapper,XPathNodeIteratorBase,IXPathNodeIterator>(void)
```
