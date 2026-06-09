# FunctionNonZeroArityExpressionTemplate<SubstringAfterFunctionExpression,StringExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180004500`
- end: `0x1800045b7`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VSubstringAfterFunctionExpression@@VStringExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180004500`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<SubstringAfterFunctionExpression,StringExpressionBase>::Allocate(
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
  *v6 = &SubstringAfterFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180004500  mov     [rsp+arg_0], rbx
0x180004505  mov     [rsp+arg_8], rsi
0x18000450a  push    rdi
0x18000450b  sub     rsp, 20h
0x18000450f  cmp     dword ptr [rcx+14h], 2
0x180004513  mov     rsi, rdx
0x180004516  mov     rdi, rcx
0x180004519  jz      short loc_180004525
0x18000451b  mov     eax, 80070057h
0x180004520  jmp     loc_1800045A7
0x180004525  mov     ecx, 28h ; '('; Size
0x18000452a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000452f  mov     rbx, rax
0x180004532  test    rax, rax
0x180004535  jz      short loc_1800045A2
0x180004537  mov     qword ptr [rax+8], 0
0x18000453f  mov     qword ptr [rax+10h], 0
0x180004547  mov     qword ptr [rax+18h], 0
0x18000454f  mov     qword ptr [rax+20h], 0
0x180004557  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x18000455e  mov     [rbx], rax
0x180004561  mov     dword ptr [rbx+8], 1
0x180004568  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x18000456d  lea     rax, ??_7SubstringAfterFunctionExpression@@6B@; const SubstringAfterFunctionExpression::`vftable'
0x180004574  mov     qword ptr [rbx+10h], 0
0x18000457c  mov     qword ptr [rbx+18h], 0
0x180004584  lea     rcx, [rbx+10h]
0x180004588  mov     qword ptr [rbx+20h], 0
0x180004590  mov     rdx, rdi
0x180004593  mov     [rbx], rax
0x180004596  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x18000459b  xor     eax, eax
0x18000459d  mov     [rsi], rbx
0x1800045a0  jmp     short loc_1800045A7
0x1800045a2  mov     eax, 8007000Eh
0x1800045a7  mov     rbx, [rsp+28h+arg_0]
0x1800045ac  mov     rsi, [rsp+28h+arg_8]
0x1800045b1  add     rsp, 20h
0x1800045b5  pop     rdi
0x1800045b6  retn
```
