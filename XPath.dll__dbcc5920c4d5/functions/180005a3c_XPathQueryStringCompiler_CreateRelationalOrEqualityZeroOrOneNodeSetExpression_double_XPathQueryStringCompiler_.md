# XPathQueryStringCompiler::CreateRelationalOrEqualityZeroOrOneNodeSetExpression<double>(XPathQueryStringCompiler::ExpressionDispatchResult &,XPathQueryStringCompiler::ExpressionDispatchResult &,String &,XPathExpressionBase * *)

- ea: `0x180005a3c`
- end: `0x180005b5a`
- name: `??$CreateRelationalOrEqualityZeroOrOneNodeSetExpression@N@XPathQueryStringCompiler@@CAJAEAVExpressionDispatchResult@0@0AEAVString@@PEAPEAVXPathExpressionBase@@@Z`
- size: `286`
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
- `0x180005a10`
- `0x180005a3c`
- `0x18000615c`
- `0x180007110`
- `0x180008bdc`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::CreateRelationalOrEqualityZeroOrOneNodeSetExpression<double>(
        XPathExpressionBase **a1,
        XPathExpressionBase **a2,
        __int64 a3,
        __int64 *a4)
{
  __int64 v8; // rax
  int Binary; // eax
  unsigned int v10; // ecx
  XPathExpressionBase *v12; // rcx
  char v13; // si
  struct IUnknown *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  _QWORD v18[3]; // [rsp+20h] [rbp-18h] BYREF
  struct IUnknown *v19; // [rsp+70h] [rbp+38h] BYREF

  if ( XPathExpressionBase::IsNodeSet(*a1) || XPathExpressionBase::IsNodeSet(*a2) )
  {
    v12 = *a1;
    v18[0] = 0;
    v19 = 0;
    if ( XPathExpressionBase::IsNodeSet(v12) )
    {
      v13 = 1;
      InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(
        v18,
        ((unsigned __int64)*a1 - 8) & ((unsigned __int128)-(__int128)(unsigned __int64)*a1 >> 64));
      v14 = (struct IUnknown *)*a2;
    }
    else
    {
      v13 = 0;
      InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(
        v18,
        ((unsigned __int64)*a2 - 8) & ((unsigned __int128)-(__int128)(unsigned __int64)*a2 >> 64));
      v14 = (struct IUnknown *)*a1;
    }
    if ( v14 )
      ATL::AtlComPtrAssign(&v19, v14);
    v15 = XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<double>(a3);
    LOBYTE(v16) = v13;
    v17 = RelationalOrEqualityOneNodeSetOperandExpressionBase<RelationalOrEqualityOneNodeSetExpression<double>,double>::Allocate(
            v16,
            v15,
            v18[0],
            v19);
    *a4 = v17;
    if ( v17 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
      InvasivePtr<UnionExpressionIterator>::Reset(v18);
      return 0;
    }
    else
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
      InvasivePtr<UnionExpressionIterator>::Reset(v18);
      return 2147942414LL;
    }
  }
  else
  {
    v8 = XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<double>(a3);
    Binary = XPathQueryStringCompiler::CreateBinaryExpression<RelationalOrEqualityZeroNodeSetExpression<double>>(
               *a1,
               *a2,
               v8,
               a4);
    v10 = 0;
    if ( Binary < 0 )
      return (unsigned int)Binary;
    return v10;
  }
}

```

## disassembly

```asm
0x180005a3c  push    rbp
0x180005a3e  push    rbx
0x180005a3f  push    rsi
0x180005a40  push    rdi
0x180005a41  push    r14
0x180005a43  push    r15
0x180005a45  mov     rbp, rsp
0x180005a48  sub     rsp, 38h
0x180005a4c  mov     rbx, rcx
0x180005a4f  mov     r14, r9
0x180005a52  mov     rcx, [rcx]; this
0x180005a55  mov     r15, r8
0x180005a58  mov     rdi, rdx
0x180005a5b  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180005a60  test    al, al
0x180005a62  jnz     short loc_180005A97
0x180005a64  mov     rcx, [rdi]; this
0x180005a67  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180005a6c  test    al, al
0x180005a6e  jnz     short loc_180005A97
0x180005a70  mov     rcx, r15
0x180005a73  call    ??$LookupRelationalOrEqualityOperatorFunc@N@XPathQueryStringCompiler@@CAP6A_NNN@ZAEAVString@@@Z; XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<double>(String &)
0x180005a78  mov     rdx, [rdi]
0x180005a7b  mov     r9, r14
0x180005a7e  mov     rcx, [rbx]
0x180005a81  mov     r8, rax
0x180005a84  call    ??$CreateBinaryExpression@V?$RelationalOrEqualityZeroNodeSetExpression@N@@@XPathQueryStringCompiler@@CAJPEAVXPathExpressionBase@@0P6A_NNN@ZPEAPEAV1@@Z; XPathQueryStringCompiler::CreateBinaryExpression<RelationalOrEqualityZeroNodeSetExpression<double>>(XPathExpressionBase *,XPathExpressionBase *,bool (*)(double,double),XPathExpressionBase * *)
0x180005a89  xor     ecx, ecx
0x180005a8b  test    eax, eax
0x180005a8d  cmovs   ecx, eax
0x180005a90  mov     eax, ecx
0x180005a92  jmp     loc_180005B4D
0x180005a97  mov     rcx, [rbx]; this
0x180005a9a  mov     [rbp+var_18], 0
0x180005aa2  mov     [rbp+arg_0], 0
0x180005aaa  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180005aaf  test    al, al
0x180005ab1  jz      short loc_180005AD4
0x180005ab3  mov     rax, [rbx]
0x180005ab6  mov     sil, 1
0x180005ab9  lea     rcx, [rax-8]
0x180005abd  neg     rax
0x180005ac0  sbb     rdx, rdx
0x180005ac3  and     rdx, rcx
0x180005ac6  lea     rcx, [rbp+var_18]
0x180005aca  call    ??$?4VXPathNodeIteratorBase@@@?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAAEAV0@PEAVXPathNodeIteratorBase@@@Z; InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(XPathNodeIteratorBase *)
0x180005acf  mov     rdx, [rdi]
0x180005ad2  jmp     short loc_180005AF3
0x180005ad4  mov     rax, [rdi]
0x180005ad7  xor     sil, sil
0x180005ada  lea     rcx, [rax-8]
0x180005ade  neg     rax
0x180005ae1  sbb     rdx, rdx
0x180005ae4  and     rdx, rcx
0x180005ae7  lea     rcx, [rbp+var_18]
0x180005aeb  call    ??$?4VXPathNodeIteratorBase@@@?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAAEAV0@PEAVXPathNodeIteratorBase@@@Z; InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(XPathNodeIteratorBase *)
0x180005af0  mov     rdx, [rbx]; struct IUnknown *
0x180005af3  test    rdx, rdx
0x180005af6  jz      short loc_180005B01
0x180005af8  lea     rcx, [rbp+arg_0]; struct IUnknown **
0x180005afc  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180005b01  mov     rcx, r15
0x180005b04  call    ??$LookupRelationalOrEqualityOperatorFunc@N@XPathQueryStringCompiler@@CAP6A_NNN@ZAEAVString@@@Z; XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<double>(String &)
0x180005b09  mov     r9, [rbp+arg_0]
0x180005b0d  mov     rdx, rax
0x180005b10  mov     r8, [rbp+var_18]
0x180005b14  mov     cl, sil
0x180005b17  call    ?Allocate@?$RelationalOrEqualityOneNodeSetOperandExpressionBase@V?$RelationalOrEqualityOneNodeSetExpression@N@@N@@SAPEAV?$RelationalOrEqualityOneNodeSetExpression@N@@_NP6A_NNN@ZPEAVXPathNodeIteratorBase@@PEAVXPathExpressionBase@@@Z; RelationalOrEqualityOneNodeSetOperandExpressionBase<RelationalOrEqualityOneNodeSetExpression<double>,double>::Allocate(bool,bool (*)(double,double),XPathNodeIteratorBase *,XPathExpressionBase *)
0x180005b1c  mov     [r14], rax
0x180005b1f  lea     rcx, [rbp+arg_0]
0x180005b23  test    rax, rax
0x180005b26  jnz     short loc_180005B3D
0x180005b28  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005b2d  lea     rcx, [rbp+var_18]
0x180005b31  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180005b36  mov     eax, 8007000Eh
0x180005b3b  jmp     short loc_180005B4D
0x180005b3d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005b42  lea     rcx, [rbp+var_18]
0x180005b46  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180005b4b  xor     eax, eax
0x180005b4d  add     rsp, 38h
0x180005b51  pop     r15
0x180005b53  pop     r14
0x180005b55  pop     rdi
0x180005b56  pop     rsi
0x180005b57  pop     rbx
0x180005b58  pop     rbp
0x180005b59  retn
```
