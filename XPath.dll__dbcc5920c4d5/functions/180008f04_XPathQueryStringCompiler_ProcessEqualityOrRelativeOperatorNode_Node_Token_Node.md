# XPathQueryStringCompiler::ProcessEqualityOrRelativeOperatorNode(Node *,Token *,Node *)

- ea: `0x180008f04`
- end: `0x18000915d`
- name: `?ProcessEqualityOrRelativeOperatorNode@XPathQueryStringCompiler@@AEAAJPEAVNode@@PEAVToken@@0@Z`
- size: `601`
- prototype: `int(XPathQueryStringCompiler *__hidden this, struct Node *, struct Token *, struct Node *)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001c40`

## callees

- `0x180001078`
- `0x1800020b4`
- `0x1800021a4`
- `0x180005a3c`
- `0x180005b60`
- `0x180005c7c`
- `0x1800061ac`
- `0x180007f5c`
- `0x1800083b4`
- `0x180008b60`
- `0x180008bdc`
- `0x180008c00`
- `0x180008e50`
- `0x180008f04`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessEqualityOrRelativeOperatorNode(
        XPathQueryStringCompiler *this,
        struct Node *a2,
        const WCHAR **a3,
        struct Node *a4)
{
  _QWORD *v4; // r15
  int v6; // esi
  bool v7; // r12
  _DWORD *v8; // rdi
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rbx
  __int64 v11; // r14
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // r12
  __int64 v15; // rbx
  int v16; // eax
  XPathExpressionBase *v18[2]; // [rsp+30h] [rbp-10h] BYREF
  XPathExpressionBase *v19; // [rsp+70h] [rbp+30h] BYREF

  v4 = (_QWORD *)*((_QWORD *)this + 5);
  v18[0] = 0;
  v19 = 0;
  *((_QWORD *)this + 5) = 0;
  v6 = XPathQueryStringCompiler::ProcessBinaryOperationOperandNodes(
         this,
         a2,
         a4,
         (struct XPathQueryStringCompiler::ExpressionDispatchResult *)v18,
         (struct XPathQueryStringCompiler::ExpressionDispatchResult *)&v19);
  if ( v6 < 0 )
    goto LABEL_26;
  if ( XPathExpressionBase::IsNodeSet(v18[0]) && XPathExpressionBase::IsNodeSet(v19) )
  {
    if ( *((_DWORD *)a3 + 7) == 49 )
    {
      v7 = WideCharStringTemplate<String>::Equals(a3 + 6, L"=");
      v8 = operator new(0x28u);
      if ( v8 )
      {
        v9 = (unsigned __int64)v18[0] - 8;
        v10 = ((unsigned __int64)v19 - 8) & -(__int64)(v19 != 0);
        v11 = -(__int64)(v18[0] != 0);
        *(_QWORD *)v8 = &SimpleIUnknownImpl<IXPathExpression>::`vftable';
        v12 = v9 & v11;
        v8[2] = 1;
        ModuleRefCounter::AddRef();
        *((_BYTE *)v8 + 16) = v7;
        *(_QWORD *)v8 = &EqualityTwoNodeSetsExpression::`vftable';
        *((_QWORD *)v8 + 3) = v12;
        if ( v12 )
          _InterlockedIncrement((volatile signed __int32 *)(v12 + 16));
        *((_QWORD *)v8 + 4) = v10;
        if ( v10 )
          _InterlockedIncrement((volatile signed __int32 *)(v10 + 16));
        goto LABEL_16;
      }
    }
    else
    {
      v8 = operator new(0x28u);
      if ( v8 )
      {
        v13 = ((unsigned __int64)v19 - 8) & -(__int64)(v19 != 0);
        v14 = ((unsigned __int64)v18[0] - 8) & -(__int64)(v18[0] != 0);
        v15 = XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<String>(a3 + 6);
        *(_QWORD *)v8 = &SimpleIUnknownImpl<IXPathExpression>::`vftable';
        v8[2] = 1;
        ModuleRefCounter::AddRef();
        *((_QWORD *)v8 + 2) = v15;
        *(_QWORD *)v8 = &RelationalTwoNodeSetsExpression::`vftable';
        *((_QWORD *)v8 + 3) = v14;
        if ( v14 )
          _InterlockedIncrement((volatile signed __int32 *)(v14 + 16));
        *((_QWORD *)v8 + 4) = v13;
        if ( v13 )
          _InterlockedIncrement((volatile signed __int32 *)(v13 + 16));
        goto LABEL_16;
      }
    }
    v8 = 0;
LABEL_16:
    ATL::CComPtrBase<StepCompositionIterator>::Attach(v4, v8);
    if ( !*v4 )
      v6 = -2147024882;
    goto LABEL_26;
  }
  if ( XPathQueryStringCompiler::ExpressionDispatchResult::IsBoolean((XPathQueryStringCompiler::ExpressionDispatchResult *)v18)
    || XPathQueryStringCompiler::ExpressionDispatchResult::IsBoolean((XPathQueryStringCompiler::ExpressionDispatchResult *)&v19) )
  {
    v16 = XPathQueryStringCompiler::CreateRelationalOrEqualityZeroOrOneNodeSetExpression<bool>(v18, &v19, a3 + 6, v4);
  }
  else if ( XPathQueryStringCompiler::ExpressionDispatchResult::IsNumber((XPathQueryStringCompiler::ExpressionDispatchResult *)v18)
         || XPathQueryStringCompiler::ExpressionDispatchResult::IsNumber((XPathQueryStringCompiler::ExpressionDispatchResult *)&v19) )
  {
    v16 = XPathQueryStringCompiler::CreateRelationalOrEqualityZeroOrOneNodeSetExpression<double>(v18, &v19, a3 + 6, v4);
  }
  else
  {
    v16 = XPathQueryStringCompiler::CreateRelationalOrEqualityZeroOrOneNodeSetExpression<String>(v18, &v19, a3 + 6, v4);
  }
  v6 = v16;
LABEL_26:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180008f04  mov     [rsp-28h+arg_8], rbx
0x180008f09  mov     [rsp-28h+arg_10], rsi
0x180008f0e  push    rbp
0x180008f0f  push    rdi
0x180008f10  push    r12
0x180008f12  push    r14
0x180008f14  push    r15
0x180008f16  mov     rbp, rsp
0x180008f19  sub     rsp, 40h
0x180008f1d  mov     r15, [rcx+28h]
0x180008f21  mov     rbx, r8
0x180008f24  mov     rax, r9
0x180008f27  mov     [rbp+var_10], 0
0x180008f2f  lea     r8, [rbp+arg_0]
0x180008f33  mov     [rbp+arg_0], 0
0x180008f3b  mov     [rsp+40h+var_20], r8; struct XPathQueryStringCompiler::ExpressionDispatchResult *
0x180008f40  lea     r9, [rbp+var_10]; struct XPathQueryStringCompiler::ExpressionDispatchResult *
0x180008f44  mov     r8, rax; struct Node *
0x180008f47  mov     qword ptr [rcx+28h], 0
0x180008f4f  call    ?ProcessBinaryOperationOperandNodes@XPathQueryStringCompiler@@AEAAJPEAVNode@@0AEAVExpressionDispatchResult@1@1@Z; XPathQueryStringCompiler::ProcessBinaryOperationOperandNodes(Node *,Node *,XPathQueryStringCompiler::ExpressionDispatchResult &,XPathQueryStringCompiler::ExpressionDispatchResult &)
0x180008f54  mov     esi, eax
0x180008f56  test    eax, eax
0x180008f58  js      loc_180009130
0x180008f5e  mov     rcx, [rbp+var_10]; this
0x180008f62  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180008f67  test    al, al
0x180008f69  jz      loc_1800090BA
0x180008f6f  mov     rcx, [rbp+arg_0]; this
0x180008f73  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180008f78  test    al, al
0x180008f7a  jz      loc_1800090BA
0x180008f80  cmp     dword ptr [rbx+1Ch], 31h ; '1'
0x180008f84  jnz     loc_18000901D
0x180008f8a  lea     rcx, [rbx+30h]
0x180008f8e  lea     rdx, asc_180017160; "="
0x180008f95  call    ?Equals@?$WideCharStringTemplate@VString@@@@QEBA_NPEBG@Z; WideCharStringTemplate<String>::Equals(ushort const *)
0x180008f9a  mov     ecx, 28h ; '('; Size
0x180008f9f  mov     r12b, al
0x180008fa2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008fa7  mov     rdi, rax
0x180008faa  test    rax, rax
0x180008fad  jz      loc_1800090A0
0x180008fb3  mov     rcx, [rbp+arg_0]
0x180008fb7  mov     rax, [rbp+var_10]
0x180008fbb  lea     rdx, [rcx-8]
0x180008fbf  neg     rcx
0x180008fc2  lea     rcx, [rax-8]
0x180008fc6  sbb     rbx, rbx
0x180008fc9  and     rbx, rdx
0x180008fcc  neg     rax
0x180008fcf  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180008fd6  sbb     r14, r14
0x180008fd9  mov     [rdi], rax
0x180008fdc  and     r14, rcx
0x180008fdf  mov     dword ptr [rdi+8], 1
0x180008fe6  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180008feb  mov     [rdi+10h], r12b
0x180008fef  lea     rax, ??_7EqualityTwoNodeSetsExpression@@6B@; const EqualityTwoNodeSetsExpression::`vftable'
0x180008ff6  mov     [rdi], rax
0x180008ff9  mov     [rdi+18h], r14
0x180008ffd  test    r14, r14
0x180009000  jz      short loc_180009007
0x180009002  lock inc dword ptr [r14+10h]
0x180009007  mov     [rdi+20h], rbx
0x18000900b  test    rbx, rbx
0x18000900e  jz      loc_1800090A2
0x180009014  lock inc dword ptr [rbx+10h]
0x180009018  jmp     loc_1800090A2
0x18000901d  mov     ecx, 28h ; '('; Size
0x180009022  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009027  mov     rdi, rax
0x18000902a  test    rax, rax
0x18000902d  jz      short loc_1800090A0
0x18000902f  mov     rax, [rbp+arg_0]
0x180009033  lea     rcx, [rax-8]
0x180009037  neg     rax
0x18000903a  mov     rax, [rbp+var_10]
0x18000903e  sbb     r14, r14
0x180009041  and     r14, rcx
0x180009044  lea     rcx, [rax-8]
0x180009048  neg     rax
0x18000904b  sbb     r12, r12
0x18000904e  and     r12, rcx
0x180009051  lea     rcx, [rbx+30h]
0x180009055  call    ??$LookupRelationalOrEqualityOperatorFunc@VString@@@XPathQueryStringCompiler@@CAP6A_NVString@@0@ZAEAV1@@Z; XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<String>(String &)
0x18000905a  mov     rbx, rax
0x18000905d  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180009064  mov     [rdi], rax
0x180009067  mov     dword ptr [rdi+8], 1
0x18000906e  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180009073  mov     [rdi+10h], rbx
0x180009077  lea     rax, ??_7RelationalTwoNodeSetsExpression@@6B@; const RelationalTwoNodeSetsExpression::`vftable'
0x18000907e  mov     [rdi], rax
0x180009081  mov     [rdi+18h], r12
0x180009085  test    r12, r12
0x180009088  jz      short loc_180009090
0x18000908a  lock inc dword ptr [r12+10h]
0x180009090  mov     [rdi+20h], r14
0x180009094  test    r14, r14
0x180009097  jz      short loc_1800090A2
0x180009099  lock inc dword ptr [r14+10h]
0x18000909e  jmp     short loc_1800090A2
0x1800090a0  xor     edi, edi
0x1800090a2  mov     rdx, rdi
0x1800090a5  mov     rcx, r15
0x1800090a8  call    ?Attach@?$CComPtrBase@VStepCompositionIterator@@@ATL@@QEAAXPEAVStepCompositionIterator@@@Z; ATL::CComPtrBase<StepCompositionIterator>::Attach(StepCompositionIterator *)
0x1800090ad  cmp     qword ptr [r15], 0
0x1800090b1  jnz     short loc_180009130
0x1800090b3  mov     esi, 8007000Eh
0x1800090b8  jmp     short loc_180009130
0x1800090ba  lea     rcx, [rbp+var_10]; this
0x1800090be  call    ?IsBoolean@ExpressionDispatchResult@XPathQueryStringCompiler@@QEAA_NXZ; XPathQueryStringCompiler::ExpressionDispatchResult::IsBoolean(void)
0x1800090c3  test    al, al
0x1800090c5  jnz     short loc_18000911A
0x1800090c7  lea     rcx, [rbp+arg_0]; this
0x1800090cb  call    ?IsBoolean@ExpressionDispatchResult@XPathQueryStringCompiler@@QEAA_NXZ; XPathQueryStringCompiler::ExpressionDispatchResult::IsBoolean(void)
0x1800090d0  test    al, al
0x1800090d2  jnz     short loc_18000911A
0x1800090d4  lea     rcx, [rbp+var_10]; this
0x1800090d8  call    ?IsNumber@ExpressionDispatchResult@XPathQueryStringCompiler@@QEAA_NXZ; XPathQueryStringCompiler::ExpressionDispatchResult::IsNumber(void)
0x1800090dd  test    al, al
0x1800090df  jnz     short loc_180009104
0x1800090e1  lea     rcx, [rbp+arg_0]; this
0x1800090e5  call    ?IsNumber@ExpressionDispatchResult@XPathQueryStringCompiler@@QEAA_NXZ; XPathQueryStringCompiler::ExpressionDispatchResult::IsNumber(void)
0x1800090ea  test    al, al
0x1800090ec  jnz     short loc_180009104
0x1800090ee  lea     r8, [rbx+30h]
0x1800090f2  mov     r9, r15
0x1800090f5  lea     rdx, [rbp+arg_0]
0x1800090f9  lea     rcx, [rbp+var_10]
0x1800090fd  call    ??$CreateRelationalOrEqualityZeroOrOneNodeSetExpression@VString@@@XPathQueryStringCompiler@@CAJAEAVExpressionDispatchResult@0@0AEAVString@@PEAPEAVXPathExpressionBase@@@Z; XPathQueryStringCompiler::CreateRelationalOrEqualityZeroOrOneNodeSetExpression<String>(XPathQueryStringCompiler::ExpressionDispatchResult &,XPathQueryStringCompiler::ExpressionDispatchResult &,String &,XPathExpressionBase * *)
0x180009102  jmp     short loc_18000912E
0x180009104  lea     r8, [rbx+30h]
0x180009108  mov     r9, r15
0x18000910b  lea     rdx, [rbp+arg_0]
0x18000910f  lea     rcx, [rbp+var_10]
0x180009113  call    ??$CreateRelationalOrEqualityZeroOrOneNodeSetExpression@N@XPathQueryStringCompiler@@CAJAEAVExpressionDispatchResult@0@0AEAVString@@PEAPEAVXPathExpressionBase@@@Z; XPathQueryStringCompiler::CreateRelationalOrEqualityZeroOrOneNodeSetExpression<double>(XPathQueryStringCompiler::ExpressionDispatchResult &,XPathQueryStringCompiler::ExpressionDispatchResult &,String &,XPathExpressionBase * *)
0x180009118  jmp     short loc_18000912E
0x18000911a  lea     r8, [rbx+30h]
0x18000911e  mov     r9, r15
0x180009121  lea     rdx, [rbp+arg_0]
0x180009125  lea     rcx, [rbp+var_10]
0x180009129  call    ??$CreateRelationalOrEqualityZeroOrOneNodeSetExpression@_N@XPathQueryStringCompiler@@CAJAEAVExpressionDispatchResult@0@0AEAVString@@PEAPEAVXPathExpressionBase@@@Z; XPathQueryStringCompiler::CreateRelationalOrEqualityZeroOrOneNodeSetExpression<bool>(XPathQueryStringCompiler::ExpressionDispatchResult &,XPathQueryStringCompiler::ExpressionDispatchResult &,String &,XPathExpressionBase * *)
0x18000912e  mov     esi, eax
0x180009130  lea     rcx, [rbp+arg_0]
0x180009134  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009139  lea     rcx, [rbp+var_10]
0x18000913d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009142  lea     r11, [rsp+40h+var_s0]
0x180009147  mov     eax, esi
0x180009149  mov     rbx, [r11+38h]
0x18000914d  mov     rsi, [r11+40h]
0x180009151  mov     rsp, r11
0x180009154  pop     r15
0x180009156  pop     r14
0x180009158  pop     r12
0x18000915a  pop     rdi
0x18000915b  pop     rbp
0x18000915c  retn
```
