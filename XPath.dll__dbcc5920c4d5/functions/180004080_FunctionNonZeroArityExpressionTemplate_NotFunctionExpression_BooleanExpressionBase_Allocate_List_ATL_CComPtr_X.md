# FunctionNonZeroArityExpressionTemplate<NotFunctionExpression,BooleanExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180004080`
- end: `0x180004137`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VNotFunctionExpression@@VBooleanExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180004080`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<NotFunctionExpression,BooleanExpressionBase>::Allocate(
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
  *v6 = &NotFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180004080  mov     [rsp+arg_0], rbx
0x180004085  mov     [rsp+arg_8], rsi
0x18000408a  push    rdi
0x18000408b  sub     rsp, 20h
0x18000408f  cmp     dword ptr [rcx+14h], 1
0x180004093  mov     rsi, rdx
0x180004096  mov     rdi, rcx
0x180004099  jz      short loc_1800040A5
0x18000409b  mov     eax, 80070057h
0x1800040a0  jmp     loc_180004127
0x1800040a5  mov     ecx, 28h ; '('; Size
0x1800040aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800040af  mov     rbx, rax
0x1800040b2  test    rax, rax
0x1800040b5  jz      short loc_180004122
0x1800040b7  mov     qword ptr [rax+8], 0
0x1800040bf  mov     qword ptr [rax+10h], 0
0x1800040c7  mov     qword ptr [rax+18h], 0
0x1800040cf  mov     qword ptr [rax+20h], 0
0x1800040d7  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x1800040de  mov     [rbx], rax
0x1800040e1  mov     dword ptr [rbx+8], 1
0x1800040e8  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x1800040ed  lea     rax, ??_7NotFunctionExpression@@6B@; const NotFunctionExpression::`vftable'
0x1800040f4  mov     qword ptr [rbx+10h], 0
0x1800040fc  mov     qword ptr [rbx+18h], 0
0x180004104  lea     rcx, [rbx+10h]
0x180004108  mov     qword ptr [rbx+20h], 0
0x180004110  mov     rdx, rdi
0x180004113  mov     [rbx], rax
0x180004116  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x18000411b  xor     eax, eax
0x18000411d  mov     [rsi], rbx
0x180004120  jmp     short loc_180004127
0x180004122  mov     eax, 8007000Eh
0x180004127  mov     rbx, [rsp+28h+arg_0]
0x18000412c  mov     rsi, [rsp+28h+arg_8]
0x180004131  add     rsp, 20h
0x180004135  pop     rdi
0x180004136  retn
```
