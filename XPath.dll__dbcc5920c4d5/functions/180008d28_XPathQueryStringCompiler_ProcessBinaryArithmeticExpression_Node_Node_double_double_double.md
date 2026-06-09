# XPathQueryStringCompiler::ProcessBinaryArithmeticExpression(Node *,Node *,double (*)(double,double))

- ea: `0x180008d28`
- end: `0x180008dbb`
- name: `?ProcessBinaryArithmeticExpression@XPathQueryStringCompiler@@AEAAJPEAVNode@@0P6ANNN@Z@Z`
- size: `147`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *__hidden this, struct Node *, struct Node *, double (*)(double, double))`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001a90`
- `0x180001ac0`
- `0x180001cc0`

## callees

- `0x1800020b4`
- `0x180006ff0`
- `0x180008c24`
- `0x180008d28`
- `0x180008e50`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessBinaryArithmeticExpression(
        XPathQueryStringCompiler *this,
        struct Node *a2,
        struct Node *a3,
        double (*a4)(double, double))
{
  _QWORD *v4; // rsi
  int IteratorCompleteIfNecessary; // ebx
  struct IUnknown *v8[3]; // [rsp+30h] [rbp-18h] BYREF
  struct IUnknown *v9; // [rsp+70h] [rbp+28h] BYREF

  v4 = (_QWORD *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  v8[0] = 0;
  v9 = 0;
  IteratorCompleteIfNecessary = XPathQueryStringCompiler::ProcessBinaryOperationOperandNodes(
                                  this,
                                  a2,
                                  a3,
                                  (struct XPathQueryStringCompiler::ExpressionDispatchResult *)v8,
                                  (struct XPathQueryStringCompiler::ExpressionDispatchResult *)&v9);
  if ( IteratorCompleteIfNecessary >= 0 )
  {
    IteratorCompleteIfNecessary = XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(v8);
    if ( IteratorCompleteIfNecessary >= 0 )
    {
      IteratorCompleteIfNecessary = XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(&v9);
      if ( IteratorCompleteIfNecessary >= 0 )
      {
        *v4 = BinaryOperationOnTwoSameOperandTypeExpressionTemplate<BinaryArithmeticExpression,NumberExpressionBase,double>::Allocate(
                a4,
                v8[0],
                v9);
        IteratorCompleteIfNecessary = 0;
      }
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v9);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v8);
  return (unsigned int)IteratorCompleteIfNecessary;
}

```

## disassembly

```asm
0x180008d28  push    rbp
0x180008d2a  push    rbx
0x180008d2b  push    rsi
0x180008d2c  push    rdi
0x180008d2d  mov     rbp, rsp
0x180008d30  sub     rsp, 48h
0x180008d34  mov     rsi, [rcx+28h]
0x180008d38  lea     rax, [rbp+arg_0]
0x180008d3c  mov     rdi, r9
0x180008d3f  mov     [rsp+48h+var_28], rax; struct XPathQueryStringCompiler::ExpressionDispatchResult *
0x180008d44  lea     r9, [rbp+var_18]; struct XPathQueryStringCompiler::ExpressionDispatchResult *
0x180008d48  mov     qword ptr [rcx+28h], 0
0x180008d50  mov     [rbp+var_18], 0
0x180008d58  mov     [rbp+arg_0], 0
0x180008d60  call    ?ProcessBinaryOperationOperandNodes@XPathQueryStringCompiler@@AEAAJPEAVNode@@0AEAVExpressionDispatchResult@1@1@Z; XPathQueryStringCompiler::ProcessBinaryOperationOperandNodes(Node *,Node *,XPathQueryStringCompiler::ExpressionDispatchResult &,XPathQueryStringCompiler::ExpressionDispatchResult &)
0x180008d65  mov     ebx, eax
0x180008d67  test    eax, eax
0x180008d69  js      short loc_180008D9E
0x180008d6b  lea     rcx, [rbp+var_18]; struct IUnknown **
0x180008d6f  call    ?MakeIteratorCompleteIfNecessary@XPathQueryStringCompiler@@CAJAEAV?$CComPtr@VXPathExpressionBase@@@ATL@@@Z; XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(ATL::CComPtr<XPathExpressionBase> &)
0x180008d74  lea     rcx, [rbp+arg_0]; struct IUnknown **
0x180008d78  mov     ebx, eax
0x180008d7a  test    eax, eax
0x180008d7c  js      short loc_180008DA2
0x180008d7e  call    ?MakeIteratorCompleteIfNecessary@XPathQueryStringCompiler@@CAJAEAV?$CComPtr@VXPathExpressionBase@@@ATL@@@Z; XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(ATL::CComPtr<XPathExpressionBase> &)
0x180008d83  mov     ebx, eax
0x180008d85  test    eax, eax
0x180008d87  js      short loc_180008D9E
0x180008d89  mov     r8, [rbp+arg_0]
0x180008d8d  mov     rcx, rdi
0x180008d90  mov     rdx, [rbp+var_18]
0x180008d94  call    ?Allocate@?$BinaryOperationOnTwoSameOperandTypeExpressionTemplate@VBinaryArithmeticExpression@@VNumberExpressionBase@@N@@SAPEAVBinaryArithmeticExpression@@P6ANNN@ZPEAVXPathExpressionBase@@1@Z; BinaryOperationOnTwoSameOperandTypeExpressionTemplate<BinaryArithmeticExpression,NumberExpressionBase,double>::Allocate(double (*)(double,double),XPathExpressionBase *,XPathExpressionBase *)
0x180008d99  mov     [rsi], rax
0x180008d9c  xor     ebx, ebx
0x180008d9e  lea     rcx, [rbp+arg_0]
0x180008da2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008da7  lea     rcx, [rbp+var_18]
0x180008dab  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008db0  mov     eax, ebx
0x180008db2  add     rsp, 48h
0x180008db6  pop     rdi
0x180008db7  pop     rsi
0x180008db8  pop     rbx
0x180008db9  pop     rbp
0x180008dba  retn
```
