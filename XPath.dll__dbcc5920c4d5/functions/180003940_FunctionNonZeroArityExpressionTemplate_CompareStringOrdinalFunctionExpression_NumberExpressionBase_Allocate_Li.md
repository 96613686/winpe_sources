# FunctionNonZeroArityExpressionTemplate<CompareStringOrdinalFunctionExpression,NumberExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180003940`
- end: `0x1800039f7`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VCompareStringOrdinalFunctionExpression@@VNumberExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180003940`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<CompareStringOrdinalFunctionExpression,NumberExpressionBase>::Allocate(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rbx

  if ( *(_DWORD *)(a1 + 20) != 3 )
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
  *v6 = &CompareStringOrdinalFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180003940  mov     [rsp+arg_0], rbx
0x180003945  mov     [rsp+arg_8], rsi
0x18000394a  push    rdi
0x18000394b  sub     rsp, 20h
0x18000394f  cmp     dword ptr [rcx+14h], 3
0x180003953  mov     rsi, rdx
0x180003956  mov     rdi, rcx
0x180003959  jz      short loc_180003965
0x18000395b  mov     eax, 80070057h
0x180003960  jmp     loc_1800039E7
0x180003965  mov     ecx, 28h ; '('; Size
0x18000396a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000396f  mov     rbx, rax
0x180003972  test    rax, rax
0x180003975  jz      short loc_1800039E2
0x180003977  mov     qword ptr [rax+8], 0
0x18000397f  mov     qword ptr [rax+10h], 0
0x180003987  mov     qword ptr [rax+18h], 0
0x18000398f  mov     qword ptr [rax+20h], 0
0x180003997  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x18000399e  mov     [rbx], rax
0x1800039a1  mov     dword ptr [rbx+8], 1
0x1800039a8  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x1800039ad  lea     rax, ??_7CompareStringOrdinalFunctionExpression@@6B@; const CompareStringOrdinalFunctionExpression::`vftable'
0x1800039b4  mov     qword ptr [rbx+10h], 0
0x1800039bc  mov     qword ptr [rbx+18h], 0
0x1800039c4  lea     rcx, [rbx+10h]
0x1800039c8  mov     qword ptr [rbx+20h], 0
0x1800039d0  mov     rdx, rdi
0x1800039d3  mov     [rbx], rax
0x1800039d6  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x1800039db  xor     eax, eax
0x1800039dd  mov     [rsi], rbx
0x1800039e0  jmp     short loc_1800039E7
0x1800039e2  mov     eax, 8007000Eh
0x1800039e7  mov     rbx, [rsp+28h+arg_0]
0x1800039ec  mov     rsi, [rsp+28h+arg_8]
0x1800039f1  add     rsp, 20h
0x1800039f5  pop     rdi
0x1800039f6  retn
```
