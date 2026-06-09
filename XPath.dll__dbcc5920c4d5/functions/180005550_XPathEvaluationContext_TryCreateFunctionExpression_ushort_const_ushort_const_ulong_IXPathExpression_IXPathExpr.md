# XPathEvaluationContext::TryCreateFunctionExpression(ushort const *,ushort const *,ulong,IXPathExpression * *,IXPathExpression * *)

- ea: `0x180005550`
- end: `0x180005699`
- name: `?TryCreateFunctionExpression@XPathEvaluationContext@@UEAAJPEBG0KPEAPEAUIXPathExpression@@1@Z`
- size: `329`
- prototype: `int(XPathEvaluationContext *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, struct IXPathExpression **, struct IXPathExpression **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800020b4`
- `0x180004aac`
- `0x180004bdc`
- `0x180004d24`
- `0x180005550`
- `0x1800056a0`

## pseudocode

```c
__int64 __fastcall XPathEvaluationContext::TryCreateFunctionExpression(
        __int64 **this,
        const unsigned __int16 *a2,
        char *a3,
        unsigned int a4,
        struct IXPathExpression **a5,
        struct IXPathExpression **a6)
{
  struct IXPathExpression **v9; // rbx
  struct IXPathExpression **v11; // rdi
  unsigned int i; // esi
  int ExpressionWrapper; // r14d
  int v14; // eax
  unsigned int v15; // ebx
  struct XPathExpressionBase *v16; // [rsp+30h] [rbp-20h] BYREF
  int v17[4]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v18; // [rsp+48h] [rbp-8h]
  struct XPathExpressionBase *v20; // [rsp+A0h] [rbp+50h] BYREF

  if ( !a3 || !*(_WORD *)a3 )
    return 2147942487LL;
  v9 = a5;
  if ( a4 )
  {
    if ( !a5 )
      return 2147942487LL;
  }
  else if ( a5 )
  {
    return 2147942487LL;
  }
  v11 = a6;
  if ( !a6 || *a6 )
    return 2147942487LL;
  v18 = 0;
  *(_OWORD *)v17 = 0;
  for ( i = 0; i < a4; ++i )
  {
    v20 = 0;
    ExpressionWrapper = XPathEvaluationContext::CreateExpressionWrapper(
                          (struct IUnknown *)v9[i],
                          (struct IUnknown ***)&v20);
    if ( ExpressionWrapper < 0
      || (ExpressionWrapper = List<ATL::CComPtr<XPathExpressionBase>>::Append((__int64)v17, (struct IUnknown **)&v20),
          ExpressionWrapper < 0) )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
      List<ATL::CComPtr<XPathExpressionBase>>::Clear((__int64)v17);
      return (unsigned int)ExpressionWrapper;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
  }
  v16 = 0;
  v14 = XPathEvaluationContext::TryCreateFunctionExpressionInternal(this[2], (__int64)a2, a3, (__int64)v17, &v16);
  v15 = v14;
  if ( v14 < 0 || v14 == 1 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v16);
    List<ATL::CComPtr<XPathExpressionBase>>::Clear((__int64)v17);
    return v15;
  }
  else
  {
    *v11 = v16;
    v16 = 0;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v16);
    List<ATL::CComPtr<XPathExpressionBase>>::Clear((__int64)v17);
    return 0;
  }
}

```

## disassembly

```asm
0x180005550  mov     [rsp-38h+arg_8], rbx
0x180005555  mov     [rsp-38h+arg_0], rcx
0x18000555a  push    rbp
0x18000555b  push    rsi
0x18000555c  push    rdi
0x18000555d  push    r12
0x18000555f  push    r13
0x180005561  push    r14
0x180005563  push    r15
0x180005565  mov     rbp, rsp
0x180005568  sub     rsp, 50h
0x18000556c  xor     r14d, r14d
0x18000556f  mov     r12d, r9d
0x180005572  mov     r15, r8
0x180005575  mov     r13, rdx
0x180005578  test    r8, r8
0x18000557b  jz      short loc_180005591
0x18000557d  cmp     [r8], r14w
0x180005581  jz      short loc_180005591
0x180005583  mov     rbx, [rbp+arg_20]
0x180005587  test    r9d, r9d
0x18000558a  jnz     short loc_1800055AE
0x18000558c  test    rbx, rbx
0x18000558f  jz      short loc_1800055B3
0x180005591  mov     eax, 80070057h
0x180005596  mov     rbx, [rsp+50h+arg_8]
0x18000559e  add     rsp, 50h
0x1800055a2  pop     r15
0x1800055a4  pop     r14
0x1800055a6  pop     r13
0x1800055a8  pop     r12
0x1800055aa  pop     rdi
0x1800055ab  pop     rsi
0x1800055ac  pop     rbp
0x1800055ad  retn
0x1800055ae  test    rbx, rbx
0x1800055b1  jz      short loc_180005591
0x1800055b3  mov     rdi, [rbp+arg_28]
0x1800055b7  test    rdi, rdi
0x1800055ba  jz      short loc_180005591
0x1800055bc  cmp     [rdi], r14
0x1800055bf  jnz     short loc_180005591
0x1800055c1  xorps   xmm0, xmm0
0x1800055c4  mov     [rbp+var_8], r14
0x1800055c8  movdqu  xmmword ptr [rbp+var_18], xmm0
0x1800055cd  mov     esi, r14d
0x1800055d0  cmp     esi, r12d
0x1800055d3  jnb     short loc_18000562D
0x1800055d5  mov     ecx, esi
0x1800055d7  lea     rdx, [rbp+arg_10]; struct XPathExpressionBase **
0x1800055db  mov     [rbp+arg_10], r14
0x1800055df  mov     rcx, [rbx+rcx*8]; struct IUnknown *
0x1800055e3  call    ?CreateExpressionWrapper@XPathEvaluationContext@@CAJPEAUIUnknown@@PEAPEAVXPathExpressionBase@@@Z; XPathEvaluationContext::CreateExpressionWrapper(IUnknown *,XPathExpressionBase * *)
0x1800055e8  mov     r14d, eax
0x1800055eb  test    eax, eax
0x1800055ed  js      short loc_180005613
0x1800055ef  lea     rdx, [rbp+arg_10]
0x1800055f3  lea     rcx, [rbp+var_18]
0x1800055f7  call    ?Append@?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAJAEAV?$CComPtr@VXPathExpressionBase@@@ATL@@@Z; List<ATL::CComPtr<XPathExpressionBase>>::Append(ATL::CComPtr<XPathExpressionBase> &)
0x1800055fc  lea     rcx, [rbp+arg_10]
0x180005600  mov     r14d, eax
0x180005603  test    eax, eax
0x180005605  js      short loc_180005617
0x180005607  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000560c  inc     esi
0x18000560e  xor     r14d, r14d
0x180005611  jmp     short loc_1800055D0
0x180005613  lea     rcx, [rbp+arg_10]
0x180005617  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000561c  lea     rcx, [rbp+var_18]
0x180005620  call    ?Clear@?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAXXZ; List<ATL::CComPtr<XPathExpressionBase>>::Clear(void)
0x180005625  mov     eax, r14d
0x180005628  jmp     loc_180005596
0x18000562d  mov     rcx, [rbp+arg_0]
0x180005631  lea     rax, [rbp+var_20]
0x180005635  lea     r9, [rbp+var_18]; int
0x180005639  mov     [rbp+var_20], r14
0x18000563d  mov     r8, r15; int
0x180005640  mov     [rsp+50h+var_30], rax; struct XPathExpressionBase **
0x180005645  mov     rdx, r13; int
0x180005648  mov     rcx, [rcx+10h]; int
0x18000564c  call    ?TryCreateFunctionExpressionInternal@XPathEvaluationContext@@SAJPEAUIXPathEvaluationContextExtension@@PEBG1AEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z; XPathEvaluationContext::TryCreateFunctionExpressionInternal(IXPathEvaluationContextExtension *,ushort const *,ushort const *,List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)
0x180005651  mov     ebx, eax
0x180005653  test    eax, eax
0x180005655  js      short loc_180005680
0x180005657  cmp     eax, 1
0x18000565a  jz      short loc_180005680
0x18000565c  mov     rax, [rbp+var_20]
0x180005660  lea     rcx, [rbp+var_20]
0x180005664  mov     [rdi], rax
0x180005667  mov     [rbp+var_20], r14
0x18000566b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005670  lea     rcx, [rbp+var_18]
0x180005674  call    ?Clear@?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAXXZ; List<ATL::CComPtr<XPathExpressionBase>>::Clear(void)
0x180005679  xor     eax, eax
0x18000567b  jmp     loc_180005596
0x180005680  lea     rcx, [rbp+var_20]
0x180005684  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005689  lea     rcx, [rbp+var_18]
0x18000568d  call    ?Clear@?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAXXZ; List<ATL::CComPtr<XPathExpressionBase>>::Clear(void)
0x180005692  mov     eax, ebx
0x180005694  jmp     loc_180005596
```
