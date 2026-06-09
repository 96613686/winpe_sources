# XPathQueryStringCompiler::Compile(IXPathEvaluationContextExtension *,ushort const *,IXPathExpression * *)

- ea: `0x180008060`
- end: `0x1800080b0`
- name: `?Compile@XPathQueryStringCompiler@@UEAAJPEAUIXPathEvaluationContextExtension@@PEBGPEAPEAUIXPathExpression@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *this, struct IUnknown *, const unsigned __int16 *, struct IXPathExpression **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800020b4`
- `0x180008060`
- `0x1800080b8`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::Compile(
        XPathQueryStringCompiler *this,
        struct IUnknown *a2,
        const unsigned __int16 *a3,
        struct IXPathExpression **a4)
{
  int v5; // ebx
  struct XPathExpressionBase *v7[3]; // [rsp+20h] [rbp-18h] BYREF

  v7[0] = 0;
  v5 = XPathQueryStringCompiler::CompileInternal(this, a2, a3, v7);
  if ( v5 >= 0 )
  {
    v5 = 0;
    *a4 = v7[0];
    v7[0] = 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008060  mov     [rsp+arg_0], rbx
0x180008065  push    rdi
0x180008066  sub     rsp, 30h
0x18000806a  mov     rdi, r9
0x18000806d  mov     [rsp+38h+var_18], 0
0x180008076  lea     r9, [rsp+38h+var_18]; struct XPathExpressionBase **
0x18000807b  call    ?CompileInternal@XPathQueryStringCompiler@@AEAAJPEAUIXPathEvaluationContextExtension@@PEBGPEAPEAVXPathExpressionBase@@@Z; XPathQueryStringCompiler::CompileInternal(IXPathEvaluationContextExtension *,ushort const *,XPathExpressionBase * *)
0x180008080  mov     ebx, eax
0x180008082  test    eax, eax
0x180008084  js      short loc_180008099
0x180008086  mov     rax, [rsp+38h+var_18]
0x18000808b  xor     ebx, ebx
0x18000808d  mov     [rdi], rax
0x180008090  mov     [rsp+38h+var_18], 0
0x180008099  lea     rcx, [rsp+38h+var_18]
0x18000809e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800080a3  mov     eax, ebx
0x1800080a5  mov     rbx, [rsp+38h+arg_0]
0x1800080aa  add     rsp, 30h
0x1800080ae  pop     rdi
0x1800080af  retn
```
