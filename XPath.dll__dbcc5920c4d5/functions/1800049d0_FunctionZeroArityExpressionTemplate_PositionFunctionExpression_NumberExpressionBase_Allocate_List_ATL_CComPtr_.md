# FunctionZeroArityExpressionTemplate<PositionFunctionExpression,NumberExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x1800049d0`
- end: `0x180004a35`
- name: `?Allocate@?$FunctionZeroArityExpressionTemplate@VPositionFunctionExpression@@VNumberExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800094f4`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x1800049d0`

## pseudocode

```c
__int64 __fastcall FunctionZeroArityExpressionTemplate<PositionFunctionExpression,NumberExpressionBase>::Allocate(
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
    *v4 = &PositionFunctionExpression::`vftable';
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
0x1800049d0  mov     [rsp+arg_0], rbx
0x1800049d5  push    rdi
0x1800049d6  sub     rsp, 20h
0x1800049da  mov     ecx, 10h; Size
0x1800049df  mov     rdi, rdx
0x1800049e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800049e7  mov     rbx, rax
0x1800049ea  test    rax, rax
0x1800049ed  jz      short loc_180004A1E
0x1800049ef  mov     qword ptr [rax+8], 0
0x1800049f7  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x1800049fe  mov     [rbx], rax
0x180004a01  mov     dword ptr [rbx+8], 1
0x180004a08  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180004a0d  lea     rax, ??_7PositionFunctionExpression@@6B@; const PositionFunctionExpression::`vftable'
0x180004a14  mov     [rbx], rax
0x180004a17  xor     eax, eax
0x180004a19  mov     [rdi], rbx
0x180004a1c  jmp     short loc_180004A2A
0x180004a1e  mov     qword ptr [rdi], 0
0x180004a25  mov     eax, 8007000Eh
0x180004a2a  mov     rbx, [rsp+28h+arg_0]
0x180004a2f  add     rsp, 20h
0x180004a33  pop     rdi
0x180004a34  retn
```
