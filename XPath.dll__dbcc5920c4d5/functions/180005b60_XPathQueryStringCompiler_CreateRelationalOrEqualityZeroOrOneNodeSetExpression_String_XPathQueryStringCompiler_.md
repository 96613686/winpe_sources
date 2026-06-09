# XPathQueryStringCompiler::CreateRelationalOrEqualityZeroOrOneNodeSetExpression<String>(XPathQueryStringCompiler::ExpressionDispatchResult &,XPathQueryStringCompiler::ExpressionDispatchResult &,String &,XPathExpressionBase * *)

- ea: `0x180005b60`
- end: `0x180005c75`
- name: `??$CreateRelationalOrEqualityZeroOrOneNodeSetExpression@VString@@@XPathQueryStringCompiler@@CAJAEAVExpressionDispatchResult@0@0AEAVString@@PEAPEAVXPathExpressionBase@@@Z`
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
- `0x180005b60`
- `0x1800061ac`
- `0x180006e90`
- `0x1800071b4`
- `0x180008bdc`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::CreateRelationalOrEqualityZeroOrOneNodeSetExpression<String>(
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
    v12 = XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<String>(a3);
    LOBYTE(v13) = v10;
    v14 = RelationalOrEqualityOneNodeSetOperandExpressionBase<RelationalOrEqualityOneNodeSetExpression<String>,String>::Allocate(
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
    v8 = XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<String>(a3);
    *a4 = BinaryOperationOnTwoSameOperandTypeExpressionTemplate<RelationalOrEqualityZeroNodeSetExpression<String>,BooleanExpressionBase,String>::Allocate(
            v8,
            *a1,
            *a2);
  }
  return 0;
}

```

## disassembly

```asm
0x180005b60  push    rbp
0x180005b62  push    rbx
0x180005b63  push    rsi
0x180005b64  push    rdi
0x180005b65  push    r14
0x180005b67  push    r15
0x180005b69  mov     rbp, rsp
0x180005b6c  sub     rsp, 38h
0x180005b70  mov     rbx, rcx
0x180005b73  mov     r14, r9
0x180005b76  mov     rcx, [rcx]; this
0x180005b79  mov     r15, r8
0x180005b7c  mov     rdi, rdx
0x180005b7f  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180005b84  test    al, al
0x180005b86  jnz     short loc_180005BB2
0x180005b88  mov     rcx, [rdi]; this
0x180005b8b  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180005b90  test    al, al
0x180005b92  jnz     short loc_180005BB2
0x180005b94  mov     rcx, r15
0x180005b97  call    ??$LookupRelationalOrEqualityOperatorFunc@VString@@@XPathQueryStringCompiler@@CAP6A_NVString@@0@ZAEAV1@@Z; XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<String>(String &)
0x180005b9c  mov     r8, [rdi]
0x180005b9f  mov     rcx, rax
0x180005ba2  mov     rdx, [rbx]
0x180005ba5  call    ?Allocate@?$BinaryOperationOnTwoSameOperandTypeExpressionTemplate@V?$RelationalOrEqualityZeroNodeSetExpression@VString@@@@VBooleanExpressionBase@@VString@@@@SAPEAV?$RelationalOrEqualityZeroNodeSetExpression@VString@@@@P6A_NVString@@0@ZPEAVXPathExpressionBase@@2@Z; BinaryOperationOnTwoSameOperandTypeExpressionTemplate<RelationalOrEqualityZeroNodeSetExpression<String>,BooleanExpressionBase,String>::Allocate(bool (*)(String,String),XPathExpressionBase *,XPathExpressionBase *)
0x180005baa  mov     [r14], rax
0x180005bad  jmp     loc_180005C66
0x180005bb2  mov     rcx, [rbx]; this
0x180005bb5  mov     [rbp+var_18], 0
0x180005bbd  mov     [rbp+arg_0], 0
0x180005bc5  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180005bca  test    al, al
0x180005bcc  jz      short loc_180005BEF
0x180005bce  mov     rax, [rbx]
0x180005bd1  mov     sil, 1
0x180005bd4  lea     rcx, [rax-8]
0x180005bd8  neg     rax
0x180005bdb  sbb     rdx, rdx
0x180005bde  and     rdx, rcx
0x180005be1  lea     rcx, [rbp+var_18]
0x180005be5  call    ??$?4VXPathNodeIteratorBase@@@?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAAEAV0@PEAVXPathNodeIteratorBase@@@Z; InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(XPathNodeIteratorBase *)
0x180005bea  mov     rdx, [rdi]
0x180005bed  jmp     short loc_180005C0E
0x180005bef  mov     rax, [rdi]
0x180005bf2  xor     sil, sil
0x180005bf5  lea     rcx, [rax-8]
0x180005bf9  neg     rax
0x180005bfc  sbb     rdx, rdx
0x180005bff  and     rdx, rcx
0x180005c02  lea     rcx, [rbp+var_18]
0x180005c06  call    ??$?4VXPathNodeIteratorBase@@@?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAAEAV0@PEAVXPathNodeIteratorBase@@@Z; InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(XPathNodeIteratorBase *)
0x180005c0b  mov     rdx, [rbx]; struct IUnknown *
0x180005c0e  test    rdx, rdx
0x180005c11  jz      short loc_180005C1C
0x180005c13  lea     rcx, [rbp+arg_0]; struct IUnknown **
0x180005c17  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180005c1c  mov     rcx, r15
0x180005c1f  call    ??$LookupRelationalOrEqualityOperatorFunc@VString@@@XPathQueryStringCompiler@@CAP6A_NVString@@0@ZAEAV1@@Z; XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<String>(String &)
0x180005c24  mov     r9, [rbp+arg_0]
0x180005c28  mov     rdx, rax
0x180005c2b  mov     r8, [rbp+var_18]
0x180005c2f  mov     cl, sil
0x180005c32  call    ?Allocate@?$RelationalOrEqualityOneNodeSetOperandExpressionBase@V?$RelationalOrEqualityOneNodeSetExpression@VString@@@@VString@@@@SAPEAV?$RelationalOrEqualityOneNodeSetExpression@VString@@@@_NP6A_NVString@@1@ZPEAVXPathNodeIteratorBase@@PEAVXPathExpressionBase@@@Z; RelationalOrEqualityOneNodeSetOperandExpressionBase<RelationalOrEqualityOneNodeSetExpression<String>,String>::Allocate(bool,bool (*)(String,String),XPathNodeIteratorBase *,XPathExpressionBase *)
0x180005c37  mov     [r14], rax
0x180005c3a  lea     rcx, [rbp+arg_0]
0x180005c3e  test    rax, rax
0x180005c41  jnz     short loc_180005C58
0x180005c43  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005c48  lea     rcx, [rbp+var_18]
0x180005c4c  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180005c51  mov     eax, 8007000Eh
0x180005c56  jmp     short loc_180005C68
0x180005c58  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005c5d  lea     rcx, [rbp+var_18]
0x180005c61  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180005c66  xor     eax, eax
0x180005c68  add     rsp, 38h
0x180005c6c  pop     r15
0x180005c6e  pop     r14
0x180005c70  pop     rdi
0x180005c71  pop     rsi
0x180005c72  pop     rbx
0x180005c73  pop     rbp
0x180005c74  retn
```
