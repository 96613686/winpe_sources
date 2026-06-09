# FunctionNonZeroArityExpressionTemplate<BooleanFunctionExpression,BooleanExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x1800036f0`
- end: `0x1800037a7`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VBooleanFunctionExpression@@VBooleanExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x1800036f0`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<BooleanFunctionExpression,BooleanExpressionBase>::Allocate(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rbx

  if ( *(_DWORD *)(a1 + 20) != 1 )
    return 2147942487LL;
  v5 = operator new(0x28u);
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  v5[1] = 0;
  v5[2] = 0;
  v5[3] = 0;
  v5[4] = 0;
  *v5 = &SimpleIUnknownImpl<IXPathExpression>::`vftable';
  *((_DWORD *)v5 + 2) = 1;
  ModuleRefCounter::AddRef();
  v6[2] = 0;
  v6[3] = 0;
  v6[4] = 0;
  *v6 = &BooleanFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x1800036f0  mov     [rsp+arg_0], rbx
0x1800036f5  mov     [rsp+arg_8], rsi
0x1800036fa  push    rdi
0x1800036fb  sub     rsp, 20h
0x1800036ff  cmp     dword ptr [rcx+14h], 1
0x180003703  mov     rsi, rdx
0x180003706  mov     rdi, rcx
0x180003709  jz      short loc_180003715
0x18000370b  mov     eax, 80070057h
0x180003710  jmp     loc_180003797
0x180003715  mov     ecx, 28h ; '('; Size
0x18000371a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000371f  mov     rbx, rax
0x180003722  test    rax, rax
0x180003725  jz      short loc_180003792
0x180003727  mov     qword ptr [rax+8], 0
0x18000372f  mov     qword ptr [rax+10h], 0
0x180003737  mov     qword ptr [rax+18h], 0
0x18000373f  mov     qword ptr [rax+20h], 0
0x180003747  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x18000374e  mov     [rbx], rax
0x180003751  mov     dword ptr [rbx+8], 1
0x180003758  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x18000375d  lea     rax, ??_7BooleanFunctionExpression@@6B@; const BooleanFunctionExpression::`vftable'
0x180003764  mov     qword ptr [rbx+10h], 0
0x18000376c  mov     qword ptr [rbx+18h], 0
0x180003774  lea     rcx, [rbx+10h]
0x180003778  mov     qword ptr [rbx+20h], 0
0x180003780  mov     rdx, rdi
0x180003783  mov     [rbx], rax
0x180003786  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x18000378b  xor     eax, eax
0x18000378d  mov     [rsi], rbx
0x180003790  jmp     short loc_180003797
0x180003792  mov     eax, 8007000Eh
0x180003797  mov     rbx, [rsp+28h+arg_0]
0x18000379c  mov     rsi, [rsp+28h+arg_8]
0x1800037a1  add     rsp, 20h
0x1800037a5  pop     rdi
0x1800037a6  retn
```
