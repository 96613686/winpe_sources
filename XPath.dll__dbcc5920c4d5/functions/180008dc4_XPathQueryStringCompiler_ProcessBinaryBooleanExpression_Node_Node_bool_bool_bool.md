# XPathQueryStringCompiler::ProcessBinaryBooleanExpression(Node *,Node *,bool (*)(bool,bool))

- ea: `0x180008dc4`
- end: `0x180008e47`
- name: `?ProcessBinaryBooleanExpression@XPathQueryStringCompiler@@AEAAJPEAVNode@@0P6A_N_N1@Z@Z`
- size: `131`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *__hidden this, struct Node *, struct Node *, bool (*)(bool, bool))`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001af0`
- `0x180001e90`

## callees

- `0x1800020b4`
- `0x180006f40`
- `0x180008dc4`
- `0x180008e50`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessBinaryBooleanExpression(
        XPathQueryStringCompiler *this,
        struct Node *a2,
        struct Node *a3,
        struct IUnknown *a4)
{
  struct IUnknown ***v4; // rsi
  int v6; // ebx
  struct IUnknown *v8[3]; // [rsp+30h] [rbp-18h] BYREF
  struct IUnknown *v9; // [rsp+50h] [rbp+8h] BYREF

  v4 = (struct IUnknown ***)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  v8[0] = 0;
  v9 = 0;
  v6 = XPathQueryStringCompiler::ProcessBinaryOperationOperandNodes(
         this,
         a2,
         a3,
         (struct XPathQueryStringCompiler::ExpressionDispatchResult *)v8,
         (struct XPathQueryStringCompiler::ExpressionDispatchResult *)&v9);
  if ( v6 >= 0 )
  {
    *v4 = BinaryOperationOnTwoSameOperandTypeExpressionTemplate<BinaryBooleanExpression,BooleanExpressionBase,bool>::Allocate(
            a4,
            v8[0],
            v9);
    v6 = 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v9);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180008dc4  mov     r11, rsp
0x180008dc7  mov     [r11+10h], rbx
0x180008dcb  mov     [r11+18h], rsi
0x180008dcf  push    rdi
0x180008dd0  sub     rsp, 40h
0x180008dd4  mov     rsi, [rcx+28h]
0x180008dd8  lea     rax, [r11+8]
0x180008ddc  mov     rdi, r9
0x180008ddf  mov     [r11-28h], rax
0x180008de3  lea     r9, [r11-18h]; struct XPathQueryStringCompiler::ExpressionDispatchResult *
0x180008de7  mov     qword ptr [rcx+28h], 0
0x180008def  mov     qword ptr [r11-18h], 0
0x180008df7  mov     qword ptr [r11+8], 0
0x180008dff  call    ?ProcessBinaryOperationOperandNodes@XPathQueryStringCompiler@@AEAAJPEAVNode@@0AEAVExpressionDispatchResult@1@1@Z; XPathQueryStringCompiler::ProcessBinaryOperationOperandNodes(Node *,Node *,XPathQueryStringCompiler::ExpressionDispatchResult &,XPathQueryStringCompiler::ExpressionDispatchResult &)
0x180008e04  mov     ebx, eax
0x180008e06  test    eax, eax
0x180008e08  js      short loc_180008E21
0x180008e0a  mov     r8, [rsp+48h+arg_0]
0x180008e0f  mov     rcx, rdi
0x180008e12  mov     rdx, [rsp+48h+var_18]
0x180008e17  call    ?Allocate@?$BinaryOperationOnTwoSameOperandTypeExpressionTemplate@VBinaryBooleanExpression@@VBooleanExpressionBase@@_N@@SAPEAVBinaryBooleanExpression@@P6A_N_N0@ZPEAVXPathExpressionBase@@2@Z; BinaryOperationOnTwoSameOperandTypeExpressionTemplate<BinaryBooleanExpression,BooleanExpressionBase,bool>::Allocate(bool (*)(bool,bool),XPathExpressionBase *,XPathExpressionBase *)
0x180008e1c  mov     [rsi], rax
0x180008e1f  xor     ebx, ebx
0x180008e21  lea     rcx, [rsp+48h+arg_0]
0x180008e26  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008e2b  lea     rcx, [rsp+48h+var_18]
0x180008e30  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008e35  mov     rsi, [rsp+48h+arg_10]
0x180008e3a  mov     eax, ebx
0x180008e3c  mov     rbx, [rsp+48h+arg_8]
0x180008e41  add     rsp, 40h
0x180008e45  pop     rdi
0x180008e46  retn
```
