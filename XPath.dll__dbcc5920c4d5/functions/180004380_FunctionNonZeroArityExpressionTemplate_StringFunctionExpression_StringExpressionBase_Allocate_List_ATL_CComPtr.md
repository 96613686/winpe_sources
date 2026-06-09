# FunctionNonZeroArityExpressionTemplate<StringFunctionExpression,StringExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180004380`
- end: `0x180004437`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VStringFunctionExpression@@VStringExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180004380`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<StringFunctionExpression,StringExpressionBase>::Allocate(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rbx

  if ( *(_DWORD *)(a1 + 20) > 1u )
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
  *v6 = &StringFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180004380  mov     [rsp+arg_0], rbx
0x180004385  mov     [rsp+arg_8], rsi
0x18000438a  push    rdi
0x18000438b  sub     rsp, 20h
0x18000438f  cmp     dword ptr [rcx+14h], 1
0x180004393  mov     rsi, rdx
0x180004396  mov     rdi, rcx
0x180004399  jbe     short loc_1800043A5
0x18000439b  mov     eax, 80070057h
0x1800043a0  jmp     loc_180004427
0x1800043a5  mov     ecx, 28h ; '('; Size
0x1800043aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800043af  mov     rbx, rax
0x1800043b2  test    rax, rax
0x1800043b5  jz      short loc_180004422
0x1800043b7  mov     qword ptr [rax+8], 0
0x1800043bf  mov     qword ptr [rax+10h], 0
0x1800043c7  mov     qword ptr [rax+18h], 0
0x1800043cf  mov     qword ptr [rax+20h], 0
0x1800043d7  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x1800043de  mov     [rbx], rax
0x1800043e1  mov     dword ptr [rbx+8], 1
0x1800043e8  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x1800043ed  lea     rax, ??_7StringFunctionExpression@@6B@; const StringFunctionExpression::`vftable'
0x1800043f4  mov     qword ptr [rbx+10h], 0
0x1800043fc  mov     qword ptr [rbx+18h], 0
0x180004404  lea     rcx, [rbx+10h]
0x180004408  mov     qword ptr [rbx+20h], 0
0x180004410  mov     rdx, rdi
0x180004413  mov     [rbx], rax
0x180004416  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x18000441b  xor     eax, eax
0x18000441d  mov     [rsi], rbx
0x180004420  jmp     short loc_180004427
0x180004422  mov     eax, 8007000Eh
0x180004427  mov     rbx, [rsp+28h+arg_0]
0x18000442c  mov     rsi, [rsp+28h+arg_8]
0x180004431  add     rsp, 20h
0x180004435  pop     rdi
0x180004436  retn
```
