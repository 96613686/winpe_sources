# XPathQueryStringCompiler::CreateRelationalOrEqualityZeroOrOneNodeSetExpression<bool>(XPathQueryStringCompiler::ExpressionDispatchResult &,XPathQueryStringCompiler::ExpressionDispatchResult &,String &,XPathExpressionBase * *)

- ea: `0x180005c7c`
- end: `0x180005d91`
- name: `??$CreateRelationalOrEqualityZeroOrOneNodeSetExpression@_N@XPathQueryStringCompiler@@CAJAEAVExpressionDispatchResult@0@0AEAVString@@PEAPEAVXPathExpressionBase@@@Z`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008f04`

## callees

- `0x1800020b4`
- `0x180004b84`
- `0x1800054e0`
- `0x1800059d4`
- `0x180005c7c`
- `0x1800061fc`
- `0x180006f40`
- `0x180007258`
- `0x180008bdc`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::CreateRelationalOrEqualityZeroOrOneNodeSetExpression<bool>(
        XPathExpressionBase **a1,
        XPathExpressionBase **a2,
        __int64 a3,
        __int64 *a4)
{
  __int64 v8; // rax
  XPathExpressionBase *v9; // rcx
  char v10; // si
  struct IUnknown *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  _QWORD v16[3]; // [rsp+20h] [rbp-18h] BYREF
  struct IUnknown *v17; // [rsp+70h] [rbp+38h] BYREF

  if ( XPathExpressionBase::IsNodeSet(*a1) || XPathExpressionBase::IsNodeSet(*a2) )
  {
    v9 = *a1;
    v16[0] = 0;
    v17 = 0;
    if ( XPathExpressionBase::IsNodeSet(v9) )
    {
      v10 = 1;
      InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(
        v16,
        ((unsigned __int64)*a1 - 8) & ((unsigned __int128)-(__int128)(unsigned __int64)*a1 >> 64));
      v11 = (struct IUnknown *)*a2;
    }
    else
    {
      v10 = 0;
      InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(
        v16,
        ((unsigned __int64)*a2 - 8) & ((unsigned __int128)-(__int128)(unsigned __int64)*a2 >> 64));
      v11 = (struct IUnknown *)*a1;
    }
    if ( v11 )
      ATL::AtlComPtrAssign(&v17, v11);
    v12 = XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<bool>(a3);
    LOBYTE(v13) = v10;
    v14 = RelationalOrEqualityOneNodeSetOperandExpressionBase<RelationalOrEqualityOneNodeSetExpression<bool>,bool>::Allocate(
            v13,
            v12,
            v16[0],
            v17);
    *a4 = v14;
    if ( !v14 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
      InvasivePtr<UnionExpressionIterator>::Reset(v16);
      return 2147942414LL;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
    InvasivePtr<UnionExpressionIterator>::Reset(v16);
  }
  else
  {
    v8 = XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<bool>(a3);
    *a4 = BinaryOperationOnTwoSameOperandTypeExpressionTemplate<BinaryBooleanExpression,BooleanExpressionBase,bool>::Allocate(
            v8,
            *a1,
            *a2);
  }
  return 0;
}

```

## disassembly

```asm
0x180005c7c  push    rbp
0x180005c7e  push    rbx
0x180005c7f  push    rsi
0x180005c80  push    rdi
0x180005c81  push    r14
0x180005c83  push    r15
0x180005c85  mov     rbp, rsp
0x180005c88  sub     rsp, 38h
0x180005c8c  mov     rbx, rcx
0x180005c8f  mov     r14, r9
0x180005c92  mov     rcx, [rcx]; this
0x180005c95  mov     r15, r8
0x180005c98  mov     rdi, rdx
0x180005c9b  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180005ca0  test    al, al
0x180005ca2  jnz     short loc_180005CCE
0x180005ca4  mov     rcx, [rdi]; this
0x180005ca7  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180005cac  test    al, al
0x180005cae  jnz     short loc_180005CCE
0x180005cb0  mov     rcx, r15
0x180005cb3  call    ??$LookupRelationalOrEqualityOperatorFunc@_N@XPathQueryStringCompiler@@CAP6A_N_N0@ZAEAVString@@@Z; XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<bool>(String &)
0x180005cb8  mov     r8, [rdi]
0x180005cbb  mov     rcx, rax
0x180005cbe  mov     rdx, [rbx]
0x180005cc1  call    ?Allocate@?$BinaryOperationOnTwoSameOperandTypeExpressionTemplate@VBinaryBooleanExpression@@VBooleanExpressionBase@@_N@@SAPEAVBinaryBooleanExpression@@P6A_N_N0@ZPEAVXPathExpressionBase@@2@Z; BinaryOperationOnTwoSameOperandTypeExpressionTemplate<BinaryBooleanExpression,BooleanExpressionBase,bool>::Allocate(bool (*)(bool,bool),XPathExpressionBase *,XPathExpressionBase *)
0x180005cc6  mov     [r14], rax
0x180005cc9  jmp     loc_180005D82
0x180005cce  mov     rcx, [rbx]; this
0x180005cd1  mov     [rbp+var_18], 0
0x180005cd9  mov     [rbp+arg_0], 0
0x180005ce1  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180005ce6  test    al, al
0x180005ce8  jz      short loc_180005D0B
0x180005cea  mov     rax, [rbx]
0x180005ced  mov     sil, 1
0x180005cf0  lea     rcx, [rax-8]
0x180005cf4  neg     rax
0x180005cf7  sbb     rdx, rdx
0x180005cfa  and     rdx, rcx
0x180005cfd  lea     rcx, [rbp+var_18]
0x180005d01  call    ??$?4VXPathNodeIteratorBase@@@?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAAEAV0@PEAVXPathNodeIteratorBase@@@Z; InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(XPathNodeIteratorBase *)
0x180005d06  mov     rdx, [rdi]
0x180005d09  jmp     short loc_180005D2A
0x180005d0b  mov     rax, [rdi]
0x180005d0e  xor     sil, sil
0x180005d11  lea     rcx, [rax-8]
0x180005d15  neg     rax
0x180005d18  sbb     rdx, rdx
0x180005d1b  and     rdx, rcx
0x180005d1e  lea     rcx, [rbp+var_18]
0x180005d22  call    ??$?4VXPathNodeIteratorBase@@@?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAAEAV0@PEAVXPathNodeIteratorBase@@@Z; InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(XPathNodeIteratorBase *)
0x180005d27  mov     rdx, [rbx]; struct IUnknown *
0x180005d2a  test    rdx, rdx
0x180005d2d  jz      short loc_180005D38
0x180005d2f  lea     rcx, [rbp+arg_0]; struct IUnknown **
0x180005d33  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180005d38  mov     rcx, r15
0x180005d3b  call    ??$LookupRelationalOrEqualityOperatorFunc@_N@XPathQueryStringCompiler@@CAP6A_N_N0@ZAEAVString@@@Z; XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<bool>(String &)
0x180005d40  mov     r9, [rbp+arg_0]
0x180005d44  mov     rdx, rax
0x180005d47  mov     r8, [rbp+var_18]
0x180005d4b  mov     cl, sil
0x180005d4e  call    ?Allocate@?$RelationalOrEqualityOneNodeSetOperandExpressionBase@V?$RelationalOrEqualityOneNodeSetExpression@_N@@_N@@SAPEAV?$RelationalOrEqualityOneNodeSetExpression@_N@@_NP6A_N00@ZPEAVXPathNodeIteratorBase@@PEAVXPathExpressionBase@@@Z; RelationalOrEqualityOneNodeSetOperandExpressionBase<RelationalOrEqualityOneNodeSetExpression<bool>,bool>::Allocate(bool,bool (*)(bool,bool),XPathNodeIteratorBase *,XPathExpressionBase *)
0x180005d53  mov     [r14], rax
0x180005d56  lea     rcx, [rbp+arg_0]
0x180005d5a  test    rax, rax
0x180005d5d  jnz     short loc_180005D74
0x180005d5f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005d64  lea     rcx, [rbp+var_18]
0x180005d68  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180005d6d  mov     eax, 8007000Eh
0x180005d72  jmp     short loc_180005D84
0x180005d74  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005d79  lea     rcx, [rbp+var_18]
0x180005d7d  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180005d82  xor     eax, eax
0x180005d84  add     rsp, 38h
0x180005d88  pop     r15
0x180005d8a  pop     r14
0x180005d8c  pop     rdi
0x180005d8d  pop     rsi
0x180005d8e  pop     rbx
0x180005d8f  pop     rbp
0x180005d90  retn
```
