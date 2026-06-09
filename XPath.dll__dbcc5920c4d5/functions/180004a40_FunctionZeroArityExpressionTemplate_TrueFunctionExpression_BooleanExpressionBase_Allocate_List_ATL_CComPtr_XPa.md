# FunctionZeroArityExpressionTemplate<TrueFunctionExpression,BooleanExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180004a40`
- end: `0x180004aa5`
- name: `?Allocate@?$FunctionZeroArityExpressionTemplate@VTrueFunctionExpression@@VBooleanExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180004a40`

## pseudocode

```c
__int64 __fastcall FunctionZeroArityExpressionTemplate<TrueFunctionExpression,BooleanExpressionBase>::Allocate(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  __int64 result; // rax

  v3 = operator new(0x10u);
  v4 = v3;
  if ( v3 )
  {
    v3[1] = 0;
    *v3 = &SimpleIUnknownImpl<IXPathExpression>::`vftable';
    *((_DWORD *)v3 + 2) = 1;
    ModuleRefCounter::AddRef();
    *v4 = &TrueFunctionExpression::`vftable';
    result = 0;
    *a2 = v4;
  }
  else
  {
    *a2 = 0;
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180004a40  mov     [rsp+arg_0], rbx
0x180004a45  push    rdi
0x180004a46  sub     rsp, 20h
0x180004a4a  mov     ecx, 10h; Size
0x180004a4f  mov     rdi, rdx
0x180004a52  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004a57  mov     rbx, rax
0x180004a5a  test    rax, rax
0x180004a5d  jz      short loc_180004A8E
0x180004a5f  mov     qword ptr [rax+8], 0
0x180004a67  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180004a6e  mov     [rbx], rax
0x180004a71  mov     dword ptr [rbx+8], 1
0x180004a78  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180004a7d  lea     rax, ??_7TrueFunctionExpression@@6B@; const TrueFunctionExpression::`vftable'
0x180004a84  mov     [rbx], rax
0x180004a87  xor     eax, eax
0x180004a89  mov     [rdi], rbx
0x180004a8c  jmp     short loc_180004A9A
0x180004a8e  mov     qword ptr [rdi], 0
0x180004a95  mov     eax, 8007000Eh
0x180004a9a  mov     rbx, [rsp+28h+arg_0]
0x180004a9f  add     rsp, 20h
0x180004aa3  pop     rdi
0x180004aa4  retn
```
