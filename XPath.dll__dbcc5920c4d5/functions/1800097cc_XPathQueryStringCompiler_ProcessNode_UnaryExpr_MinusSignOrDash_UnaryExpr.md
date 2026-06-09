# XPathQueryStringCompiler::ProcessNode(UnaryExpr__MinusSignOrDash_UnaryExpr *)

- ea: `0x1800097cc`
- end: `0x18000988a`
- name: `?ProcessNode@XPathQueryStringCompiler@@QEAAJPEAVUnaryExpr__MinusSignOrDash_UnaryExpr@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *__hidden this, struct UnaryExpr__MinusSignOrDash_UnaryExpr *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002060`

## callees

- `0x180001078`
- `0x1800020b4`
- `0x1800021a4`
- `0x1800032c4`
- `0x180007f5c`
- `0x18000835c`
- `0x180008c24`
- `0x1800097cc`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessNode(
        XPathQueryStringCompiler *this,
        struct UnaryExpr__MinusSignOrDash_UnaryExpr *a2)
{
  __int64 *v2; // rbp
  struct Node *v3; // rdx
  int v4; // ebx
  int IteratorCompleteIfNecessary; // esi
  _DWORD *v6; // rdi
  struct IUnknown *v7; // rbx
  struct IUnknown *v9; // [rsp+50h] [rbp+8h] BYREF

  v2 = (__int64 *)*((_QWORD *)this + 5);
  v3 = *(struct Node **)(*((_QWORD *)a2 + 2) + 8LL);
  *((_QWORD *)this + 5) = &v9;
  v9 = 0;
  *((_DWORD *)this + 12) = 5;
  v4 = XPathQueryStringCompiler::Dispatch(this, v3);
  if ( v4 >= 0 )
  {
    IteratorCompleteIfNecessary = XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(&v9);
    if ( IteratorCompleteIfNecessary < 0 )
      goto LABEL_7;
    v6 = operator new(0x18u);
    if ( v6 )
    {
      v7 = v9;
      *(_QWORD *)v6 = &SimpleIUnknownImpl<IXPathExpression>::`vftable';
      v6[2] = 1;
      ModuleRefCounter::AddRef();
      *(_QWORD *)v6 = &NegationExpression::`vftable';
      ATL::CComPtrBase<XPathExpressionBase>::CComPtrBase<XPathExpressionBase>(v6 + 4, v7);
    }
    else
    {
      v6 = 0;
    }
    ATL::CComPtrBase<StepCompositionIterator>::Attach(v2, (__int64)v6);
    v4 = -2147024882;
    if ( *v2 )
LABEL_7:
      v4 = IteratorCompleteIfNecessary;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800097cc  push    rbx
0x1800097ce  push    rbp
0x1800097cf  push    rsi
0x1800097d0  push    rdi
0x1800097d1  sub     rsp, 28h
0x1800097d5  mov     rax, [rdx+10h]
0x1800097d9  mov     rbp, [rcx+28h]
0x1800097dd  mov     rdx, [rax+8]; struct Node *
0x1800097e1  lea     rax, [rsp+48h+arg_0]
0x1800097e6  mov     [rcx+28h], rax
0x1800097ea  mov     [rsp+48h+arg_0], 0
0x1800097f3  mov     dword ptr [rcx+30h], 5
0x1800097fa  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x1800097ff  mov     ebx, eax
0x180009801  test    eax, eax
0x180009803  js      short loc_180009875
0x180009805  lea     rcx, [rsp+48h+arg_0]; struct IUnknown **
0x18000980a  call    ?MakeIteratorCompleteIfNecessary@XPathQueryStringCompiler@@CAJAEAV?$CComPtr@VXPathExpressionBase@@@ATL@@@Z; XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(ATL::CComPtr<XPathExpressionBase> &)
0x18000980f  mov     esi, eax
0x180009811  test    eax, eax
0x180009813  js      short loc_180009873
0x180009815  mov     ecx, 18h; Size
0x18000981a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000981f  mov     rdi, rax
0x180009822  test    rax, rax
0x180009825  jz      short loc_18000985A
0x180009827  mov     rbx, [rsp+48h+arg_0]
0x18000982c  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180009833  mov     [rdi], rax
0x180009836  mov     dword ptr [rdi+8], 1
0x18000983d  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180009842  lea     rax, ??_7NegationExpression@@6B@; const NegationExpression::`vftable'
0x180009849  mov     rdx, rbx
0x18000984c  lea     rcx, [rdi+10h]
0x180009850  mov     [rdi], rax
0x180009853  call    ??0?$CComPtrBase@VXPathExpressionBase@@@ATL@@IEAA@PEAVXPathExpressionBase@@@Z; ATL::CComPtrBase<XPathExpressionBase>::CComPtrBase<XPathExpressionBase>(XPathExpressionBase *)
0x180009858  jmp     short loc_18000985C
0x18000985a  xor     edi, edi
0x18000985c  mov     rdx, rdi
0x18000985f  mov     rcx, rbp
0x180009862  call    ?Attach@?$CComPtrBase@VStepCompositionIterator@@@ATL@@QEAAXPEAVStepCompositionIterator@@@Z; ATL::CComPtrBase<StepCompositionIterator>::Attach(StepCompositionIterator *)
0x180009867  cmp     qword ptr [rbp+0], 0
0x18000986c  mov     ebx, 8007000Eh
0x180009871  jz      short loc_180009875
0x180009873  mov     ebx, esi
0x180009875  lea     rcx, [rsp+48h+arg_0]
0x18000987a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000987f  mov     eax, ebx
0x180009881  add     rsp, 28h
0x180009885  pop     rdi
0x180009886  pop     rsi
0x180009887  pop     rbp
0x180009888  pop     rbx
0x180009889  retn
```
