# StepCompositionIterator::~StepCompositionIterator(void)

- ea: `0x1800067f8`
- end: `0x180006831`
- name: `??1StepCompositionIterator@@UEAA@XZ`
- size: `57`
- prototype: `void __fastcall(StepCompositionIterator *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006cc0`

## callees

- `0x1800020b4`
- `0x180002398`
- `0x1800054e0`

## pseudocode

```c
void __fastcall StepCompositionIterator::~StepCompositionIterator(StepCompositionIterator *this)
{
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 6);
  InvasivePtr<UnionExpressionIterator>::Reset((char *)this + 40);
  InvasivePtr<UnionExpressionIterator>::Reset((char *)this + 32);
  *((_QWORD *)this + 1) = &SimpleIUnknownImpl<IXPathExpression>::`vftable';
  ModuleRefCounter::Release();
}

```

## disassembly

```asm
0x1800067f8  push    rbx
0x1800067fa  sub     rsp, 20h
0x1800067fe  mov     rbx, rcx
0x180006801  add     rcx, 30h ; '0'
0x180006805  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000680a  lea     rcx, [rbx+28h]
0x18000680e  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180006813  lea     rcx, [rbx+20h]
0x180006817  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x18000681c  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180006823  mov     [rbx+8], rax
0x180006827  add     rsp, 20h
0x18000682b  pop     rbx
0x18000682c  jmp     ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
```
