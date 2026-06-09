# FunctionNonZeroArityExpressionTemplate<CountFunctionExpression,NumberExpressionBase>::~FunctionNonZeroArityExpressionTemplate<CountFunctionExpression,NumberExpressionBase>(void)

- ea: `0x18000334c`
- end: `0x180003372`
- name: `??1?$FunctionNonZeroArityExpressionTemplate@VCountFunctionExpression@@VNumberExpressionBase@@@@UEAA@XZ`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800035b0`

## callees

- `0x180002398`
- `0x180004bdc`

## pseudocode

```c
void __fastcall FunctionNonZeroArityExpressionTemplate<CountFunctionExpression,NumberExpressionBase>::~FunctionNonZeroArityExpressionTemplate<CountFunctionExpression,NumberExpressionBase>(
        _QWORD *a1)
{
  List<ATL::CComPtr<XPathExpressionBase>>::Clear((__int64)(a1 + 2));
  *a1 = &SimpleIUnknownImpl<IXPathExpression>::`vftable';
  ModuleRefCounter::Release();
}

```

## disassembly

```asm
0x18000334c  push    rbx
0x18000334e  sub     rsp, 20h
0x180003352  mov     rbx, rcx
0x180003355  add     rcx, 10h
0x180003359  call    ?Clear@?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAXXZ; List<ATL::CComPtr<XPathExpressionBase>>::Clear(void)
0x18000335e  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180003365  mov     [rbx], rax
0x180003368  add     rsp, 20h
0x18000336c  pop     rbx
0x18000336d  jmp     ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
```
