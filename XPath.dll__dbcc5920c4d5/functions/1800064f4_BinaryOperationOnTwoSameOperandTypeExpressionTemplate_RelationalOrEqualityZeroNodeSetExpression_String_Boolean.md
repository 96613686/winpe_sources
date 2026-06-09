# BinaryOperationOnTwoSameOperandTypeExpressionTemplate<RelationalOrEqualityZeroNodeSetExpression<String>,BooleanExpressionBase,String>::~BinaryOperationOnTwoSameOperandTypeExpressionTemplate<RelationalOrEqualityZeroNodeSetExpression<String>,BooleanExpressionBase,String>(void)

- ea: `0x1800064f4`
- end: `0x180006523`
- name: `??1?$BinaryOperationOnTwoSameOperandTypeExpressionTemplate@V?$RelationalOrEqualityZeroNodeSetExpression@VString@@@@VBooleanExpressionBase@@VString@@@@UEAA@XZ`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006ac0`

## callees

- `0x1800020b4`
- `0x180002398`

## pseudocode

```c
void __fastcall BinaryOperationOnTwoSameOperandTypeExpressionTemplate<RelationalOrEqualityZeroNodeSetExpression<String>,BooleanExpressionBase,String>::~BinaryOperationOnTwoSameOperandTypeExpressionTemplate<RelationalOrEqualityZeroNodeSetExpression<String>,BooleanExpressionBase,String>(
        _QWORD *a1)
{
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a1 + 4);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a1 + 3);
  *a1 = &SimpleIUnknownImpl<IXPathExpression>::`vftable';
  ModuleRefCounter::Release();
}

```

## disassembly

```asm
0x1800064f4  push    rbx
0x1800064f6  sub     rsp, 20h
0x1800064fa  mov     rbx, rcx
0x1800064fd  add     rcx, 20h ; ' '
0x180006501  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006506  lea     rcx, [rbx+18h]
0x18000650a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000650f  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180006516  mov     [rbx], rax
0x180006519  add     rsp, 20h
0x18000651d  pop     rbx
0x18000651e  jmp     ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
```
