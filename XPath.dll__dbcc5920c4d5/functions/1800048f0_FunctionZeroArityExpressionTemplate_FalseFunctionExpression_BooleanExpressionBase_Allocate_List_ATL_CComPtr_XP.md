# FunctionZeroArityExpressionTemplate<FalseFunctionExpression,BooleanExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x1800048f0`
- end: `0x180004955`
- name: `?Allocate@?$FunctionZeroArityExpressionTemplate@VFalseFunctionExpression@@VBooleanExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x1800048f0`

## pseudocode

```c
__int64 __fastcall FunctionZeroArityExpressionTemplate<FalseFunctionExpression,BooleanExpressionBase>::Allocate(
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
    *v4 = &FalseFunctionExpression::`vftable';
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
0x1800048f0  mov     [rsp+arg_0], rbx
0x1800048f5  push    rdi
0x1800048f6  sub     rsp, 20h
0x1800048fa  mov     ecx, 10h; Size
0x1800048ff  mov     rdi, rdx
0x180004902  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004907  mov     rbx, rax
0x18000490a  test    rax, rax
0x18000490d  jz      short loc_18000493E
0x18000490f  mov     qword ptr [rax+8], 0
0x180004917  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x18000491e  mov     [rbx], rax
0x180004921  mov     dword ptr [rbx+8], 1
0x180004928  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x18000492d  lea     rax, ??_7FalseFunctionExpression@@6B@; const FalseFunctionExpression::`vftable'
0x180004934  mov     [rbx], rax
0x180004937  xor     eax, eax
0x180004939  mov     [rdi], rbx
0x18000493c  jmp     short loc_18000494A
0x18000493e  mov     qword ptr [rdi], 0
0x180004945  mov     eax, 8007000Eh
0x18000494a  mov     rbx, [rsp+28h+arg_0]
0x18000494f  add     rsp, 20h
0x180004953  pop     rdi
0x180004954  retn
```
