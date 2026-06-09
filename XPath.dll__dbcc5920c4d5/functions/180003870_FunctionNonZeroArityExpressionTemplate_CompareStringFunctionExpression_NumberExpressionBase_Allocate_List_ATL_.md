# FunctionNonZeroArityExpressionTemplate<CompareStringFunctionExpression,NumberExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180003870`
- end: `0x18000392c`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VCompareStringFunctionExpression@@VNumberExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180003870`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<CompareStringFunctionExpression,NumberExpressionBase>::Allocate(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rbx

  if ( (unsigned int)(*(_DWORD *)(a1 + 20) - 3) > 9 )
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
  *v6 = &CompareStringFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180003870  mov     [rsp+arg_0], rbx
0x180003875  mov     [rsp+arg_8], rsi
0x18000387a  push    rdi
0x18000387b  sub     rsp, 20h
0x18000387f  mov     eax, [rcx+14h]
0x180003882  mov     rsi, rdx
0x180003885  sub     eax, 3
0x180003888  mov     rdi, rcx
0x18000388b  cmp     eax, 9
0x18000388e  jbe     short loc_18000389A
0x180003890  mov     eax, 80070057h
0x180003895  jmp     loc_18000391C
0x18000389a  mov     ecx, 28h ; '('; Size
0x18000389f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800038a4  mov     rbx, rax
0x1800038a7  test    rax, rax
0x1800038aa  jz      short loc_180003917
0x1800038ac  mov     qword ptr [rax+8], 0
0x1800038b4  mov     qword ptr [rax+10h], 0
0x1800038bc  mov     qword ptr [rax+18h], 0
0x1800038c4  mov     qword ptr [rax+20h], 0
0x1800038cc  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x1800038d3  mov     [rbx], rax
0x1800038d6  mov     dword ptr [rbx+8], 1
0x1800038dd  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x1800038e2  lea     rax, ??_7CompareStringFunctionExpression@@6B@; const CompareStringFunctionExpression::`vftable'
0x1800038e9  mov     qword ptr [rbx+10h], 0
0x1800038f1  mov     qword ptr [rbx+18h], 0
0x1800038f9  lea     rcx, [rbx+10h]
0x1800038fd  mov     qword ptr [rbx+20h], 0
0x180003905  mov     rdx, rdi
0x180003908  mov     [rbx], rax
0x18000390b  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x180003910  xor     eax, eax
0x180003912  mov     [rsi], rbx
0x180003915  jmp     short loc_18000391C
0x180003917  mov     eax, 8007000Eh
0x18000391c  mov     rbx, [rsp+28h+arg_0]
0x180003921  mov     rsi, [rsp+28h+arg_8]
0x180003926  add     rsp, 20h
0x18000392a  pop     rdi
0x18000392b  retn
```
