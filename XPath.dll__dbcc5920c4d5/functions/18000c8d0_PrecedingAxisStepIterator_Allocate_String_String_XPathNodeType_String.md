# PrecedingAxisStepIterator::Allocate(String &,String &,XPathNodeType,String &)

- ea: `0x18000c8d0`
- end: `0x18000ca7f`
- name: `?Allocate@PrecedingAxisStepIterator@@SAPEAVXPathNodeIteratorBase@@AEAVString@@0W4XPathNodeType@@0@Z`
- size: `431`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800020b4`
- `0x1800054e0`
- `0x1800063d4`
- `0x180007390`
- `0x1800075c0`
- `0x180007880`
- `0x180007f5c`
- `0x18000c8d0`
- `0x180010fac`

## pseudocode

```c
__int64 __fastcall PrecedingAxisStepIterator::Allocate(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  struct XPathNodeIteratorBase *v8; // rdi
  struct XPathNodeIteratorBase *v10; // rbx
  StepCompositionIterator *v11; // rax
  struct XPathNodeIteratorBase *v12; // rbx
  struct XPathNodeIteratorBase *v13; // rdi
  StepCompositionIterator *v14; // rax
  __int64 v15; // rbx
  __int64 v16; // [rsp+20h] [rbp-30h] BYREF
  struct XPathNodeIteratorBase *v17; // [rsp+28h] [rbp-28h] BYREF
  struct XPathNodeIteratorBase *v18; // [rsp+30h] [rbp-20h] BYREF
  __int64 v19; // [rsp+38h] [rbp-18h] BYREF
  struct XPathNodeIteratorBase *v20; // [rsp+40h] [rbp-10h] BYREF
  struct XPathNodeIteratorBase *v21; // [rsp+48h] [rbp-8h] BYREF

  v16 = 0;
  v17 = 0;
  v8 = (struct XPathNodeIteratorBase *)((__int64 (__fastcall *)(__int64 *, __int64 *, __int64, __int64 *))StepIteratorTemplate<AncestorOrSelfAxisStepIterator>::Allocate)(
                                         &v16,
                                         &v16,
                                         7,
                                         &v16);
  InvasivePtr<UnionExpressionIterator>::Reset(&v17);
  v17 = v8;
  if ( !v8 )
    goto LABEL_2;
  v18 = 0;
  v10 = (struct XPathNodeIteratorBase *)StepIteratorTemplate<PrecedingSiblingAxisStepIterator>::Allocate(
                                          &v16,
                                          &v16,
                                          7,
                                          &v16);
  InvasivePtr<UnionExpressionIterator>::Reset(&v18);
  v18 = v10;
  if ( !v10 )
  {
LABEL_4:
    InvasivePtr<UnionExpressionIterator>::Reset(&v18);
LABEL_2:
    InvasivePtr<UnionExpressionIterator>::Reset(&v17);
    String::Reset((String *)&v16);
    return 0;
  }
  v20 = 0;
  v11 = (StepCompositionIterator *)operator new(0x38u);
  if ( v11 )
    v11 = StepCompositionIterator::StepCompositionIterator(v11, v8, v10, 1);
  ATL::CComPtrBase<StepCompositionIterator>::Attach(&v20, v11);
  v12 = v20;
  if ( !v20 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
    goto LABEL_4;
  }
  v21 = 0;
  v13 = (struct XPathNodeIteratorBase *)StepIteratorTemplate<DescendantOrSelfAxisStepIterator>::Allocate(a1, a2, a3, a4);
  InvasivePtr<UnionExpressionIterator>::Reset(&v21);
  v21 = v13;
  v19 = 0;
  v14 = (StepCompositionIterator *)operator new(0x38u);
  if ( v14 )
    v14 = StepCompositionIterator::StepCompositionIterator(v14, v12, v13, 0);
  ATL::CComPtrBase<StepCompositionIterator>::Attach(&v19, v14);
  v15 = v19;
  if ( v19 )
    v19 = 0;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  InvasivePtr<UnionExpressionIterator>::Reset(&v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
  InvasivePtr<UnionExpressionIterator>::Reset(&v18);
  InvasivePtr<UnionExpressionIterator>::Reset(&v17);
  String::Reset((String *)&v16);
  return v15;
}

```

## disassembly

```asm
0x18000c8d0  push    rbp
0x18000c8d2  push    rbx
0x18000c8d3  push    rsi
0x18000c8d4  push    rdi
0x18000c8d5  push    r12
0x18000c8d7  push    r14
0x18000c8d9  push    r15
0x18000c8db  mov     rbp, rsp
0x18000c8de  sub     rsp, 50h
0x18000c8e2  mov     rsi, r9
0x18000c8e5  mov     [rbp+var_30], 0
0x18000c8ed  mov     r14d, r8d
0x18000c8f0  mov     [rbp+var_28], 0
0x18000c8f8  mov     r15, rdx
0x18000c8fb  lea     r9, [rbp+var_30]
0x18000c8ff  mov     r12, rcx
0x18000c902  lea     rdx, [rbp+var_30]
0x18000c906  mov     ebx, 7
0x18000c90b  lea     rcx, [rbp+var_30]
0x18000c90f  mov     r8d, ebx
0x18000c912  call    ?Allocate@?$StepIteratorTemplate@VAncestorOrSelfAxisStepIterator@@@@SAPEAVXPathNodeIteratorBase@@AEAVString@@0W4XPathNodeType@@0@Z; StepIteratorTemplate<AncestorOrSelfAxisStepIterator>::Allocate(String &,String &,XPathNodeType,String &)
0x18000c917  lea     rcx, [rbp+var_28]
0x18000c91b  mov     rdi, rax
0x18000c91e  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x18000c923  mov     [rbp+var_28], rdi
0x18000c927  test    rdi, rdi
0x18000c92a  jnz     short loc_18000C945
0x18000c92c  lea     rcx, [rbp+var_28]
0x18000c930  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x18000c935  lea     rcx, [rbp+var_30]; this
0x18000c939  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c93e  xor     eax, eax
0x18000c940  jmp     loc_18000CA70
0x18000c945  lea     r9, [rbp+var_30]
0x18000c949  mov     [rbp+var_20], 0
0x18000c951  mov     r8d, ebx
0x18000c954  lea     rdx, [rbp+var_30]
0x18000c958  lea     rcx, [rbp+var_30]
0x18000c95c  call    ?Allocate@?$StepIteratorTemplate@VPrecedingSiblingAxisStepIterator@@@@SAPEAVXPathNodeIteratorBase@@AEAVString@@0W4XPathNodeType@@0@Z; StepIteratorTemplate<PrecedingSiblingAxisStepIterator>::Allocate(String &,String &,XPathNodeType,String &)
0x18000c961  lea     rcx, [rbp+var_20]
0x18000c965  mov     rbx, rax
0x18000c968  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x18000c96d  mov     [rbp+var_20], rbx
0x18000c971  test    rbx, rbx
0x18000c974  jnz     short loc_18000C981
0x18000c976  lea     rcx, [rbp+var_20]
0x18000c97a  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x18000c97f  jmp     short loc_18000C92C
0x18000c981  mov     ecx, 38h ; '8'; Size
0x18000c986  mov     [rbp+var_10], 0
0x18000c98e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c993  test    rax, rax
0x18000c996  jz      short loc_18000C9A9
0x18000c998  mov     r9b, 1; bool
0x18000c99b  mov     r8, rbx; struct XPathNodeIteratorBase *
0x18000c99e  mov     rdx, rdi; struct XPathNodeIteratorBase *
0x18000c9a1  mov     rcx, rax; this
0x18000c9a4  call    ??0StepCompositionIterator@@QEAA@PEAVXPathNodeIteratorBase@@0_N@Z; StepCompositionIterator::StepCompositionIterator(XPathNodeIteratorBase *,XPathNodeIteratorBase *,bool)
0x18000c9a9  mov     rdx, rax
0x18000c9ac  lea     rcx, [rbp+var_10]
0x18000c9b0  call    ?Attach@?$CComPtrBase@VStepCompositionIterator@@@ATL@@QEAAXPEAVStepCompositionIterator@@@Z; ATL::CComPtrBase<StepCompositionIterator>::Attach(StepCompositionIterator *)
0x18000c9b5  mov     rbx, [rbp+var_10]
0x18000c9b9  test    rbx, rbx
0x18000c9bc  jnz     short loc_18000C9C9
0x18000c9be  lea     rcx, [rbp+var_10]
0x18000c9c2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000c9c7  jmp     short loc_18000C976
0x18000c9c9  mov     r9, rsi
0x18000c9cc  mov     [rbp+var_8], 0
0x18000c9d4  mov     r8d, r14d
0x18000c9d7  mov     rdx, r15
0x18000c9da  mov     rcx, r12
0x18000c9dd  call    ?Allocate@?$StepIteratorTemplate@VDescendantOrSelfAxisStepIterator@@@@SAPEAVXPathNodeIteratorBase@@AEAVString@@0W4XPathNodeType@@0@Z; StepIteratorTemplate<DescendantOrSelfAxisStepIterator>::Allocate(String &,String &,XPathNodeType,String &)
0x18000c9e2  lea     rcx, [rbp+var_8]
0x18000c9e6  mov     rdi, rax
0x18000c9e9  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x18000c9ee  mov     ecx, 38h ; '8'; Size
0x18000c9f3  mov     [rbp+var_8], rdi
0x18000c9f7  mov     [rbp+var_18], 0
0x18000c9ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ca04  test    rax, rax
0x18000ca07  jz      short loc_18000CA1A
0x18000ca09  xor     r9d, r9d; bool
0x18000ca0c  mov     r8, rdi; struct XPathNodeIteratorBase *
0x18000ca0f  mov     rdx, rbx; struct XPathNodeIteratorBase *
0x18000ca12  mov     rcx, rax; this
0x18000ca15  call    ??0StepCompositionIterator@@QEAA@PEAVXPathNodeIteratorBase@@0_N@Z; StepCompositionIterator::StepCompositionIterator(XPathNodeIteratorBase *,XPathNodeIteratorBase *,bool)
0x18000ca1a  mov     rdx, rax
0x18000ca1d  lea     rcx, [rbp+var_18]
0x18000ca21  call    ?Attach@?$CComPtrBase@VStepCompositionIterator@@@ATL@@QEAAXPEAVStepCompositionIterator@@@Z; ATL::CComPtrBase<StepCompositionIterator>::Attach(StepCompositionIterator *)
0x18000ca26  mov     rbx, [rbp+var_18]
0x18000ca2a  test    rbx, rbx
0x18000ca2d  jz      short loc_18000CA37
0x18000ca2f  mov     [rbp+var_18], 0
0x18000ca37  lea     rcx, [rbp+var_18]
0x18000ca3b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ca40  lea     rcx, [rbp+var_8]
0x18000ca44  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x18000ca49  lea     rcx, [rbp+var_10]
0x18000ca4d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ca52  lea     rcx, [rbp+var_20]
0x18000ca56  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x18000ca5b  lea     rcx, [rbp+var_28]
0x18000ca5f  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x18000ca64  lea     rcx, [rbp+var_30]; this
0x18000ca68  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000ca6d  mov     rax, rbx
0x18000ca70  add     rsp, 50h
0x18000ca74  pop     r15
0x18000ca76  pop     r14
0x18000ca78  pop     r12
0x18000ca7a  pop     rdi
0x18000ca7b  pop     rsi
0x18000ca7c  pop     rbx
0x18000ca7d  pop     rbp
0x18000ca7e  retn
```
