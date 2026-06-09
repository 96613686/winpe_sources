# XPathQueryStringCompiler::ProcessNode(Predicate__OpenBracket_PredicateExpr_CloseBracket *)

- ea: `0x1800094f4`
- end: `0x1800096cf`
- name: `?ProcessNode@XPathQueryStringCompiler@@QEAAJPEAVPredicate__OpenBracket_PredicateExpr_CloseBracket@@@Z`
- size: `475`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *__hidden this, struct Predicate__OpenBracket_PredicateExpr_CloseBracket *)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001ee0`

## callees

- `0x180001078`
- `0x1800020b4`
- `0x1800032c4`
- `0x1800032f4`
- `0x1800049d0`
- `0x180004b84`
- `0x180004bdc`
- `0x1800054e0`
- `0x180006de0`
- `0x18000835c`
- `0x180008c00`
- `0x180008cb4`
- `0x1800094f4`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessNode(
        XPathQueryStringCompiler *this,
        struct Predicate__OpenBracket_PredicateExpr_CloseBracket *a2)
{
  __int64 *v2; // rbx
  struct Node *v3; // rdx
  __int64 v4; // rbx
  struct IUnknown **v5; // r15
  int IteratorCompleteIfNecessary; // esi
  struct IUnknown *v7; // rdi
  struct IUnknown *v8; // r14
  XPathNodeIteratorBase *v9; // rax
  struct IUnknown *v10; // r14
  __int128 v12; // [rsp+20h] [rbp-28h] BYREF
  __int64 v13; // [rsp+30h] [rbp-18h]
  struct IUnknown *v14; // [rsp+80h] [rbp+38h] BYREF
  struct IUnknown *v15; // [rsp+88h] [rbp+40h] BYREF
  struct IUnknown *v16; // [rsp+90h] [rbp+48h] BYREF
  __int64 v17; // [rsp+98h] [rbp+50h] BYREF

  v2 = (__int64 *)*((_QWORD *)this + 3);
  v3 = *(struct Node **)(*((_QWORD *)a2 + 2) + 8LL);
  v15 = 0;
  *((_QWORD *)this + 3) = 0;
  v4 = *v2;
  v17 = v4;
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 16));
  v5 = (struct IUnknown **)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = &v15;
  *((_DWORD *)this + 12) = 5;
  IteratorCompleteIfNecessary = XPathQueryStringCompiler::Dispatch(this, v3);
  if ( IteratorCompleteIfNecessary >= 0 )
  {
    v7 = 0;
    v14 = 0;
    if ( XPathQueryStringCompiler::ExpressionDispatchResult::IsNumber((XPathQueryStringCompiler::ExpressionDispatchResult *)&v15) )
    {
      v8 = v15;
      v13 = 0;
      v16 = 0;
      v12 = 0;
      IteratorCompleteIfNecessary = FunctionZeroArityExpressionTemplate<PositionFunctionExpression,NumberExpressionBase>::Allocate(
                                      &v12,
                                      &v16);
      if ( IteratorCompleteIfNecessary >= 0 )
      {
        v7 = (struct IUnknown *)BinaryOperationOnTwoSameOperandTypeExpressionTemplate<RelationalOrEqualityZeroNodeSetExpression<double>,BooleanExpressionBase,double>::Allocate(
                                  BinaryOperationFunctions::IsEqual<double>,
                                  v16,
                                  v8);
        v14 = v7;
        IteratorCompleteIfNecessary = 0;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v16);
      List<ATL::CComPtr<XPathExpressionBase>>::Clear(&v12);
      if ( IteratorCompleteIfNecessary < 0 )
        goto LABEL_24;
    }
    else if ( v15 )
    {
      ATL::AtlComPtrAssign(&v14, v15);
      v7 = v14;
    }
    if ( ((unsigned __int8 (__fastcall *)(struct IUnknown *))v7->lpVtbl[4].QueryInterface)(v7) )
    {
      IteratorCompleteIfNecessary = XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(&v17);
      if ( IteratorCompleteIfNecessary < 0 )
        goto LABEL_24;
      v4 = v17;
    }
    v16 = 0;
    v9 = (XPathNodeIteratorBase *)operator new(0x30u);
    v10 = (struct IUnknown *)v9;
    if ( v9 )
    {
      XPathNodeIteratorBase::XPathNodeIteratorBase(v9);
      v10->lpVtbl = (struct IUnknownVtbl *)&PredicateIterator::`vftable'{for `IXPathNodeIterator'};
      v10[1].lpVtbl = (struct IUnknownVtbl *)&PredicateIterator::`vftable'{for `XPathExpressionBase'};
      v10[3].lpVtbl = (struct IUnknownVtbl *)v4;
      if ( v4 )
        _InterlockedIncrement((volatile signed __int32 *)(v4 + 16));
      ATL::CComPtrBase<XPathExpressionBase>::CComPtrBase<XPathExpressionBase>(&v10[4], v7);
      v10[5].lpVtbl = 0;
    }
    else
    {
      v10 = 0;
    }
    InvasivePtr<UnionExpressionIterator>::Reset(&v16);
    v16 = v10;
    if ( !v10 )
    {
      InvasivePtr<UnionExpressionIterator>::Reset(&v16);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v14);
      IteratorCompleteIfNecessary = -2147024882;
      goto LABEL_25;
    }
    if ( *v5 != &v10[1] )
      ATL::AtlComPtrAssign(v5, v10 + 1);
    InvasivePtr<UnionExpressionIterator>::Reset(&v16);
LABEL_24:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v14);
  }
LABEL_25:
  InvasivePtr<UnionExpressionIterator>::Reset(&v17);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v15);
  return (unsigned int)IteratorCompleteIfNecessary;
}

```

## disassembly

```asm
0x1800094f4  push    rbp
0x1800094f6  push    rbx
0x1800094f7  push    rsi
0x1800094f8  push    rdi
0x1800094f9  push    r14
0x1800094fb  push    r15
0x1800094fd  mov     rbp, rsp
0x180009500  sub     rsp, 48h
0x180009504  mov     rax, [rdx+10h]
0x180009508  mov     rbx, [rcx+18h]
0x18000950c  mov     rdx, [rax+8]; struct Node *
0x180009510  mov     [rbp+arg_8], 0
0x180009518  mov     qword ptr [rcx+18h], 0
0x180009520  mov     rbx, [rbx]
0x180009523  mov     [rbp+arg_18], rbx
0x180009527  test    rbx, rbx
0x18000952a  jz      short loc_180009530
0x18000952c  lock inc dword ptr [rbx+10h]
0x180009530  mov     r15, [rcx+28h]
0x180009534  lea     rax, [rbp+arg_8]
0x180009538  mov     [rcx+28h], rax
0x18000953c  mov     dword ptr [rcx+30h], 5
0x180009543  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x180009548  mov     esi, eax
0x18000954a  test    eax, eax
0x18000954c  js      loc_1800096AE
0x180009552  xor     edi, edi
0x180009554  lea     rcx, [rbp+arg_8]; this
0x180009558  mov     [rbp+arg_0], rdi
0x18000955c  call    ?IsNumber@ExpressionDispatchResult@XPathQueryStringCompiler@@QEAA_NXZ; XPathQueryStringCompiler::ExpressionDispatchResult::IsNumber(void)
0x180009561  test    al, al
0x180009563  jz      short loc_1800095C3
0x180009565  mov     r14, [rbp+arg_8]
0x180009569  lea     rdx, [rbp+arg_10]
0x18000956d  xorps   xmm0, xmm0
0x180009570  mov     [rbp+var_18], rdi
0x180009574  lea     rcx, [rbp+var_28]
0x180009578  mov     [rbp+arg_10], rdi
0x18000957c  movdqu  [rbp+var_28], xmm0
0x180009581  call    ?Allocate@?$FunctionZeroArityExpressionTemplate@VPositionFunctionExpression@@VNumberExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z; FunctionZeroArityExpressionTemplate<PositionFunctionExpression,NumberExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)
0x180009586  mov     esi, eax
0x180009588  test    eax, eax
0x18000958a  js      short loc_1800095A8
0x18000958c  mov     rdx, [rbp+arg_10]
0x180009590  lea     rcx, ??$IsEqual@N@BinaryOperationFunctions@@SA_NNN@Z; BinaryOperationFunctions::IsEqual<double>(double,double)
0x180009597  mov     r8, r14
0x18000959a  call    ?Allocate@?$BinaryOperationOnTwoSameOperandTypeExpressionTemplate@V?$RelationalOrEqualityZeroNodeSetExpression@N@@VBooleanExpressionBase@@N@@SAPEAV?$RelationalOrEqualityZeroNodeSetExpression@N@@P6A_NNN@ZPEAVXPathExpressionBase@@1@Z; BinaryOperationOnTwoSameOperandTypeExpressionTemplate<RelationalOrEqualityZeroNodeSetExpression<double>,BooleanExpressionBase,double>::Allocate(bool (*)(double,double),XPathExpressionBase *,XPathExpressionBase *)
0x18000959f  mov     rdi, rax
0x1800095a2  mov     [rbp+arg_0], rax
0x1800095a6  xor     esi, esi
0x1800095a8  lea     rcx, [rbp+arg_10]
0x1800095ac  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800095b1  lea     rcx, [rbp+var_28]
0x1800095b5  call    ?Clear@?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAXXZ; List<ATL::CComPtr<XPathExpressionBase>>::Clear(void)
0x1800095ba  test    esi, esi
0x1800095bc  jns     short loc_1800095D9
0x1800095be  jmp     loc_1800096A5
0x1800095c3  mov     rdx, [rbp+arg_8]; struct IUnknown *
0x1800095c7  test    rdx, rdx
0x1800095ca  jz      short loc_1800095D9
0x1800095cc  lea     rcx, [rbp+arg_0]; struct IUnknown **
0x1800095d0  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800095d5  mov     rdi, [rbp+arg_0]
0x1800095d9  mov     rax, [rdi]
0x1800095dc  mov     rcx, rdi
0x1800095df  mov     rax, [rax+60h]
0x1800095e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095e8  test    al, al
0x1800095ea  jz      short loc_180009603
0x1800095ec  lea     rcx, [rbp+arg_18]
0x1800095f0  call    ?MakeIteratorCompleteIfNecessary@XPathQueryStringCompiler@@CAJAEAV?$InvasivePtr@VXPathNodeIteratorBase@@@@@Z; XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(InvasivePtr<XPathNodeIteratorBase> &)
0x1800095f5  mov     esi, eax
0x1800095f7  test    eax, eax
0x1800095f9  js      loc_1800096A5
0x1800095ff  mov     rbx, [rbp+arg_18]
0x180009603  mov     ecx, 30h ; '0'; Size
0x180009608  mov     [rbp+arg_10], 0
0x180009610  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009615  mov     r14, rax
0x180009618  test    rax, rax
0x18000961b  jz      short loc_18000965D
0x18000961d  mov     rcx, rax; this
0x180009620  call    ??0XPathNodeIteratorBase@@QEAA@XZ; XPathNodeIteratorBase::XPathNodeIteratorBase(void)
0x180009625  lea     rax, ??_7PredicateIterator@@6BIXPathNodeIterator@@@; const PredicateIterator::`vftable'{for `IXPathNodeIterator'}
0x18000962c  mov     [r14], rax
0x18000962f  lea     rax, ??_7PredicateIterator@@6BXPathExpressionBase@@@; const PredicateIterator::`vftable'{for `XPathExpressionBase'}
0x180009636  mov     [r14+8], rax
0x18000963a  mov     [r14+18h], rbx
0x18000963e  test    rbx, rbx
0x180009641  jz      short loc_180009647
0x180009643  lock inc dword ptr [rbx+10h]
0x180009647  lea     rcx, [r14+20h]
0x18000964b  mov     rdx, rdi
0x18000964e  call    ??0?$CComPtrBase@VXPathExpressionBase@@@ATL@@IEAA@PEAVXPathExpressionBase@@@Z; ATL::CComPtrBase<XPathExpressionBase>::CComPtrBase<XPathExpressionBase>(XPathExpressionBase *)
0x180009653  mov     qword ptr [r14+28h], 0
0x18000965b  jmp     short loc_180009660
0x18000965d  xor     r14d, r14d
0x180009660  lea     rcx, [rbp+arg_10]
0x180009664  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180009669  mov     [rbp+arg_10], r14
0x18000966d  test    r14, r14
0x180009670  jnz     short loc_18000968B
0x180009672  lea     rcx, [rbp+arg_10]
0x180009676  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x18000967b  lea     rcx, [rbp+arg_0]
0x18000967f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009684  mov     esi, 8007000Eh
0x180009689  jmp     short loc_1800096AE
0x18000968b  lea     rdx, [r14+8]; struct IUnknown *
0x18000968f  cmp     [r15], rdx
0x180009692  jz      short loc_18000969C
0x180009694  mov     rcx, r15; struct IUnknown **
0x180009697  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000969c  lea     rcx, [rbp+arg_10]
0x1800096a0  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x1800096a5  lea     rcx, [rbp+arg_0]
0x1800096a9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800096ae  lea     rcx, [rbp+arg_18]
0x1800096b2  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x1800096b7  lea     rcx, [rbp+arg_8]
0x1800096bb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800096c0  mov     eax, esi
0x1800096c2  add     rsp, 48h
0x1800096c6  pop     r15
0x1800096c8  pop     r14
0x1800096ca  pop     rdi
0x1800096cb  pop     rsi
0x1800096cc  pop     rbx
0x1800096cd  pop     rbp
0x1800096ce  retn
```
