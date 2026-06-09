# FunctionNonZeroArityExpressionTemplate<TranslateFunctionExpression,StringExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180004830`
- end: `0x1800048e7`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VTranslateFunctionExpression@@VStringExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180004830`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<TranslateFunctionExpression,StringExpressionBase>::Allocate(
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
  *v6 = &TranslateFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180004830  mov     [rsp+arg_0], rbx
0x180004835  mov     [rsp+arg_8], rsi
0x18000483a  push    rdi
0x18000483b  sub     rsp, 20h
0x18000483f  cmp     dword ptr [rcx+14h], 3
0x180004843  mov     rsi, rdx
0x180004846  mov     rdi, rcx
0x180004849  jz      short loc_180004855
0x18000484b  mov     eax, 80070057h
0x180004850  jmp     loc_1800048D7
0x180004855  mov     ecx, 28h ; '('; Size
0x18000485a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000485f  mov     rbx, rax
0x180004862  test    rax, rax
0x180004865  jz      short loc_1800048D2
0x180004867  mov     qword ptr [rax+8], 0
0x18000486f  mov     qword ptr [rax+10h], 0
0x180004877  mov     qword ptr [rax+18h], 0
0x18000487f  mov     qword ptr [rax+20h], 0
0x180004887  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x18000488e  mov     [rbx], rax
0x180004891  mov     dword ptr [rbx+8], 1
0x180004898  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x18000489d  lea     rax, ??_7TranslateFunctionExpression@@6B@; const TranslateFunctionExpression::`vftable'
0x1800048a4  mov     qword ptr [rbx+10h], 0
0x1800048ac  mov     qword ptr [rbx+18h], 0
0x1800048b4  lea     rcx, [rbx+10h]
0x1800048b8  mov     qword ptr [rbx+20h], 0
0x1800048c0  mov     rdx, rdi
0x1800048c3  mov     [rbx], rax
0x1800048c6  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x1800048cb  xor     eax, eax
0x1800048cd  mov     [rsi], rbx
0x1800048d0  jmp     short loc_1800048D7
0x1800048d2  mov     eax, 8007000Eh
0x1800048d7  mov     rbx, [rsp+28h+arg_0]
0x1800048dc  mov     rsi, [rsp+28h+arg_8]
0x1800048e1  add     rsp, 20h
0x1800048e5  pop     rdi
0x1800048e6  retn
```
