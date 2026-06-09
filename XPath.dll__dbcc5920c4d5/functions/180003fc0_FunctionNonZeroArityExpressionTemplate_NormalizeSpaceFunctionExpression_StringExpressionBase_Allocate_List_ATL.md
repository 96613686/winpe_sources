# FunctionNonZeroArityExpressionTemplate<NormalizeSpaceFunctionExpression,StringExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180003fc0`
- end: `0x180004077`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VNormalizeSpaceFunctionExpression@@VStringExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180003fc0`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<NormalizeSpaceFunctionExpression,StringExpressionBase>::Allocate(
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
  *v6 = &NormalizeSpaceFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180003fc0  mov     [rsp+arg_0], rbx
0x180003fc5  mov     [rsp+arg_8], rsi
0x180003fca  push    rdi
0x180003fcb  sub     rsp, 20h
0x180003fcf  cmp     dword ptr [rcx+14h], 1
0x180003fd3  mov     rsi, rdx
0x180003fd6  mov     rdi, rcx
0x180003fd9  jbe     short loc_180003FE5
0x180003fdb  mov     eax, 80070057h
0x180003fe0  jmp     loc_180004067
0x180003fe5  mov     ecx, 28h ; '('; Size
0x180003fea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003fef  mov     rbx, rax
0x180003ff2  test    rax, rax
0x180003ff5  jz      short loc_180004062
0x180003ff7  mov     qword ptr [rax+8], 0
0x180003fff  mov     qword ptr [rax+10h], 0
0x180004007  mov     qword ptr [rax+18h], 0
0x18000400f  mov     qword ptr [rax+20h], 0
0x180004017  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x18000401e  mov     [rbx], rax
0x180004021  mov     dword ptr [rbx+8], 1
0x180004028  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x18000402d  lea     rax, ??_7NormalizeSpaceFunctionExpression@@6B@; const NormalizeSpaceFunctionExpression::`vftable'
0x180004034  mov     qword ptr [rbx+10h], 0
0x18000403c  mov     qword ptr [rbx+18h], 0
0x180004044  lea     rcx, [rbx+10h]
0x180004048  mov     qword ptr [rbx+20h], 0
0x180004050  mov     rdx, rdi
0x180004053  mov     [rbx], rax
0x180004056  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x18000405b  xor     eax, eax
0x18000405d  mov     [rsi], rbx
0x180004060  jmp     short loc_180004067
0x180004062  mov     eax, 8007000Eh
0x180004067  mov     rbx, [rsp+28h+arg_0]
0x18000406c  mov     rsi, [rsp+28h+arg_8]
0x180004071  add     rsp, 20h
0x180004075  pop     rdi
0x180004076  retn
```
