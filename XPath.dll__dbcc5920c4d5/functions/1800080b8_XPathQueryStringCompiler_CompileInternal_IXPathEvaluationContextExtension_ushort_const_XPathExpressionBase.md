# XPathQueryStringCompiler::CompileInternal(IXPathEvaluationContextExtension *,ushort const *,XPathExpressionBase * *)

- ea: `0x1800080b8`
- end: `0x1800081dd`
- name: `?CompileInternal@XPathQueryStringCompiler@@AEAAJPEAUIXPathEvaluationContextExtension@@PEBGPEAPEAVXPathExpressionBase@@@Z`
- size: `293`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *this, struct IUnknown *, const unsigned __int16 *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008060`
- `0x18000a280`

## callees

- `0x1800020b4`
- `0x180004b84`
- `0x180007fac`
- `0x1800080b8`
- `0x18000835c`
- `0x180008bdc`
- `0x180008c24`
- `0x18000a240`
- `0x18000f138`
- `0x180010ee0`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::CompileInternal(
        XPathQueryStringCompiler *this,
        struct IUnknown *a2,
        const unsigned __int16 *a3,
        struct IUnknown **a4)
{
  int IteratorCompleteIfNecessary; // ebx
  struct IUnknown **v8; // rbx
  int v9; // edi
  struct Node *v11; // [rsp+20h] [rbp-28h] BYREF
  __int128 v12; // [rsp+28h] [rbp-20h] BYREF
  __int64 v13; // [rsp+38h] [rbp-10h]
  struct IUnknown *v14; // [rsp+80h] [rbp+38h] BYREF

  v13 = 0;
  v11 = 0;
  v12 = 0;
  IteratorCompleteIfNecessary = String::Initialize((XPathQueryStringCompiler *)((char *)this + 16), a3);
  if ( IteratorCompleteIfNecessary >= 0 )
  {
    IteratorCompleteIfNecessary = Parser::Parse((Parser *)&v12, (XPathQueryStringCompiler *)((char *)this + 16));
    if ( IteratorCompleteIfNecessary >= 0 )
    {
      *((_DWORD *)this + 12) = 5;
      v8 = (struct IUnknown **)((char *)this + 56);
      *((_QWORD *)this + 5) = &v14;
      v14 = 0;
      if ( *((struct IUnknown **)this + 7) != a2 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 7, a2);
      v9 = XPathQueryStringCompiler::Dispatch(this, v11);
      if ( v9 < 0 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
        InvasivePtr<Node>::Reset(&v11);
        List<ParserState>::Clear(&v12);
        return (unsigned int)v9;
      }
      if ( *v8 )
        ATL::AtlComPtrAssign(v8, 0);
      if ( !XPathExpressionBase::IsNodeSet((XPathExpressionBase *)v14)
        || (IteratorCompleteIfNecessary = XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(&v14),
            IteratorCompleteIfNecessary >= 0) )
      {
        IteratorCompleteIfNecessary = 0;
        *a4 = v14;
        v14 = 0;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
    }
  }
  InvasivePtr<Node>::Reset(&v11);
  List<ParserState>::Clear(&v12);
  return (unsigned int)IteratorCompleteIfNecessary;
}

```

## disassembly

```asm
0x1800080b8  push    rbp
0x1800080ba  push    rbx
0x1800080bb  push    rsi
0x1800080bc  push    rdi
0x1800080bd  push    r14
0x1800080bf  push    r15
0x1800080c1  mov     rbp, rsp
0x1800080c4  sub     rsp, 48h
0x1800080c8  mov     rsi, rdx
0x1800080cb  mov     [rbp+var_10], 0
0x1800080d3  mov     rdi, rcx
0x1800080d6  mov     [rbp+var_28], 0
0x1800080de  xorps   xmm0, xmm0
0x1800080e1  mov     rdx, r8; unsigned __int16 *
0x1800080e4  add     rcx, 10h; this
0x1800080e8  mov     r15, r9
0x1800080eb  movdqu  [rbp+var_20], xmm0
0x1800080f0  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x1800080f5  mov     ebx, eax
0x1800080f7  test    eax, eax
0x1800080f9  js      loc_1800081BC
0x1800080ff  lea     r8, [rbp+var_28]
0x180008103  lea     rdx, [rdi+10h]; struct String *
0x180008107  lea     rcx, [rbp+var_20]; this
0x18000810b  call    ?Parse@Parser@@QEAAJAEAVString@@AEAV?$InvasivePtr@VNode@@@@@Z; Parser::Parse(String &,InvasivePtr<Node> &)
0x180008110  mov     ebx, eax
0x180008112  test    eax, eax
0x180008114  js      loc_1800081BC
0x18000811a  lea     rax, [rbp+arg_0]
0x18000811e  mov     dword ptr [rdi+30h], 5
0x180008125  lea     rbx, [rdi+38h]
0x180008129  mov     [rdi+28h], rax
0x18000812d  mov     [rbp+arg_0], 0
0x180008135  cmp     [rbx], rsi
0x180008138  jz      short loc_180008145
0x18000813a  mov     rdx, rsi; struct IUnknown *
0x18000813d  mov     rcx, rbx; struct IUnknown **
0x180008140  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180008145  mov     rdx, [rbp+var_28]; struct Node *
0x180008149  mov     rcx, rdi; this
0x18000814c  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x180008151  mov     edi, eax
0x180008153  test    eax, eax
0x180008155  jns     short loc_180008176
0x180008157  lea     rcx, [rbp+arg_0]
0x18000815b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008160  lea     rcx, [rbp+var_28]
0x180008164  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180008169  lea     rcx, [rbp+var_20]
0x18000816d  call    ?Clear@?$List@UParserState@@@@QEAAXXZ; List<ParserState>::Clear(void)
0x180008172  mov     eax, edi
0x180008174  jmp     short loc_1800081D0
0x180008176  cmp     qword ptr [rbx], 0
0x18000817a  jz      short loc_180008186
0x18000817c  xor     edx, edx; struct IUnknown *
0x18000817e  mov     rcx, rbx; struct IUnknown **
0x180008181  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180008186  mov     rcx, [rbp+arg_0]; this
0x18000818a  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x18000818f  test    al, al
0x180008191  jz      short loc_1800081A2
0x180008193  lea     rcx, [rbp+arg_0]; struct IUnknown **
0x180008197  call    ?MakeIteratorCompleteIfNecessary@XPathQueryStringCompiler@@CAJAEAV?$CComPtr@VXPathExpressionBase@@@ATL@@@Z; XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(ATL::CComPtr<XPathExpressionBase> &)
0x18000819c  mov     ebx, eax
0x18000819e  test    eax, eax
0x1800081a0  js      short loc_1800081B3
0x1800081a2  mov     rax, [rbp+arg_0]
0x1800081a6  xor     ebx, ebx
0x1800081a8  mov     [r15], rax
0x1800081ab  mov     [rbp+arg_0], 0
0x1800081b3  lea     rcx, [rbp+arg_0]
0x1800081b7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800081bc  lea     rcx, [rbp+var_28]
0x1800081c0  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x1800081c5  lea     rcx, [rbp+var_20]
0x1800081c9  call    ?Clear@?$List@UParserState@@@@QEAAXXZ; List<ParserState>::Clear(void)
0x1800081ce  mov     eax, ebx
0x1800081d0  add     rsp, 48h
0x1800081d4  pop     r15
0x1800081d6  pop     r14
0x1800081d8  pop     rdi
0x1800081d9  pop     rsi
0x1800081da  pop     rbx
0x1800081db  pop     rbp
0x1800081dc  retn
```
