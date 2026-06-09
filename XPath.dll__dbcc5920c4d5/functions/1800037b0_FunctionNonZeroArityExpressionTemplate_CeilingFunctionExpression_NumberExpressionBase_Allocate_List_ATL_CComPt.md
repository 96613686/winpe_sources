# FunctionNonZeroArityExpressionTemplate<CeilingFunctionExpression,NumberExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x1800037b0`
- end: `0x180003867`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VCeilingFunctionExpression@@VNumberExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x1800037b0`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<CeilingFunctionExpression,NumberExpressionBase>::Allocate(
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
  *v6 = &CeilingFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x1800037b0  mov     [rsp+arg_0], rbx
0x1800037b5  mov     [rsp+arg_8], rsi
0x1800037ba  push    rdi
0x1800037bb  sub     rsp, 20h
0x1800037bf  cmp     dword ptr [rcx+14h], 1
0x1800037c3  mov     rsi, rdx
0x1800037c6  mov     rdi, rcx
0x1800037c9  jz      short loc_1800037D5
0x1800037cb  mov     eax, 80070057h
0x1800037d0  jmp     loc_180003857
0x1800037d5  mov     ecx, 28h ; '('; Size
0x1800037da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800037df  mov     rbx, rax
0x1800037e2  test    rax, rax
0x1800037e5  jz      short loc_180003852
0x1800037e7  mov     qword ptr [rax+8], 0
0x1800037ef  mov     qword ptr [rax+10h], 0
0x1800037f7  mov     qword ptr [rax+18h], 0
0x1800037ff  mov     qword ptr [rax+20h], 0
0x180003807  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x18000380e  mov     [rbx], rax
0x180003811  mov     dword ptr [rbx+8], 1
0x180003818  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x18000381d  lea     rax, ??_7CeilingFunctionExpression@@6B@; const CeilingFunctionExpression::`vftable'
0x180003824  mov     qword ptr [rbx+10h], 0
0x18000382c  mov     qword ptr [rbx+18h], 0
0x180003834  lea     rcx, [rbx+10h]
0x180003838  mov     qword ptr [rbx+20h], 0
0x180003840  mov     rdx, rdi
0x180003843  mov     [rbx], rax
0x180003846  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x18000384b  xor     eax, eax
0x18000384d  mov     [rsi], rbx
0x180003850  jmp     short loc_180003857
0x180003852  mov     eax, 8007000Eh
0x180003857  mov     rbx, [rsp+28h+arg_0]
0x18000385c  mov     rsi, [rsp+28h+arg_8]
0x180003861  add     rsp, 20h
0x180003865  pop     rdi
0x180003866  retn
```
