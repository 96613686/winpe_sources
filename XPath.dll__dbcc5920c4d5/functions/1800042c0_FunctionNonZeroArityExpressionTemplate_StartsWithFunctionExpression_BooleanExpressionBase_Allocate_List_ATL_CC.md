# FunctionNonZeroArityExpressionTemplate<StartsWithFunctionExpression,BooleanExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x1800042c0`
- end: `0x180004377`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VStartsWithFunctionExpression@@VBooleanExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x1800042c0`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<StartsWithFunctionExpression,BooleanExpressionBase>::Allocate(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rbx

  if ( *(_DWORD *)(a1 + 20) != 2 )
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
  *v6 = &StartsWithFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x1800042c0  mov     [rsp+arg_0], rbx
0x1800042c5  mov     [rsp+arg_8], rsi
0x1800042ca  push    rdi
0x1800042cb  sub     rsp, 20h
0x1800042cf  cmp     dword ptr [rcx+14h], 2
0x1800042d3  mov     rsi, rdx
0x1800042d6  mov     rdi, rcx
0x1800042d9  jz      short loc_1800042E5
0x1800042db  mov     eax, 80070057h
0x1800042e0  jmp     loc_180004367
0x1800042e5  mov     ecx, 28h ; '('; Size
0x1800042ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800042ef  mov     rbx, rax
0x1800042f2  test    rax, rax
0x1800042f5  jz      short loc_180004362
0x1800042f7  mov     qword ptr [rax+8], 0
0x1800042ff  mov     qword ptr [rax+10h], 0
0x180004307  mov     qword ptr [rax+18h], 0
0x18000430f  mov     qword ptr [rax+20h], 0
0x180004317  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x18000431e  mov     [rbx], rax
0x180004321  mov     dword ptr [rbx+8], 1
0x180004328  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x18000432d  lea     rax, ??_7StartsWithFunctionExpression@@6B@; const StartsWithFunctionExpression::`vftable'
0x180004334  mov     qword ptr [rbx+10h], 0
0x18000433c  mov     qword ptr [rbx+18h], 0
0x180004344  lea     rcx, [rbx+10h]
0x180004348  mov     qword ptr [rbx+20h], 0
0x180004350  mov     rdx, rdi
0x180004353  mov     [rbx], rax
0x180004356  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x18000435b  xor     eax, eax
0x18000435d  mov     [rsi], rbx
0x180004360  jmp     short loc_180004367
0x180004362  mov     eax, 8007000Eh
0x180004367  mov     rbx, [rsp+28h+arg_0]
0x18000436c  mov     rsi, [rsp+28h+arg_8]
0x180004371  add     rsp, 20h
0x180004375  pop     rdi
0x180004376  retn
```
