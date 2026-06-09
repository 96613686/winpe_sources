# CompletionIterator::~CompletionIterator(void)

- ea: `0x180006618`
- end: `0x180006651`
- name: `??1CompletionIterator@@UEAA@XZ`
- size: `57`
- prototype: `void __fastcall(CompletionIterator *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006b68`

## callees

- `0x1800020b4`
- `0x180002398`
- `0x1800054e0`
- `0x1800065ac`

## pseudocode

```c
void __fastcall CompletionIterator::~CompletionIterator(CompletionIterator *this)
{
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 14);
  InvasivePtr<UnionExpressionIterator>::Reset((char *)this + 96);
  OrderedSet<PositionData>::~OrderedSet<PositionData>((char *)this + 32);
  *((_QWORD *)this + 1) = &SimpleIUnknownImpl<IXPathExpression>::`vftable';
  ModuleRefCounter::Release();
}

```

## disassembly

```asm
0x180006618  push    rbx
0x18000661a  sub     rsp, 20h
0x18000661e  mov     rbx, rcx
0x180006621  add     rcx, 70h ; 'p'
0x180006625  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000662a  lea     rcx, [rbx+60h]
0x18000662e  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180006633  lea     rcx, [rbx+20h]
0x180006637  call    ??1?$OrderedSet@VPositionData@@@@UEAA@XZ; OrderedSet<PositionData>::~OrderedSet<PositionData>(void)
0x18000663c  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180006643  mov     [rbx+8], rax
0x180006647  add     rsp, 20h
0x18000664b  pop     rbx
0x18000664c  jmp     ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
```
