# FunctionNonZeroArityExpressionTemplate<FloorFunctionExpression,NumberExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180003c60`
- end: `0x180003d17`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VFloorFunctionExpression@@VNumberExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180003c60`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<FloorFunctionExpression,NumberExpressionBase>::Allocate(
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
  *v6 = &FloorFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180003c60  mov     [rsp+arg_0], rbx
0x180003c65  mov     [rsp+arg_8], rsi
0x180003c6a  push    rdi
0x180003c6b  sub     rsp, 20h
0x180003c6f  cmp     dword ptr [rcx+14h], 1
0x180003c73  mov     rsi, rdx
0x180003c76  mov     rdi, rcx
0x180003c79  jz      short loc_180003C85
0x180003c7b  mov     eax, 80070057h
0x180003c80  jmp     loc_180003D07
0x180003c85  mov     ecx, 28h ; '('; Size
0x180003c8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003c8f  mov     rbx, rax
0x180003c92  test    rax, rax
0x180003c95  jz      short loc_180003D02
0x180003c97  mov     qword ptr [rax+8], 0
0x180003c9f  mov     qword ptr [rax+10h], 0
0x180003ca7  mov     qword ptr [rax+18h], 0
0x180003caf  mov     qword ptr [rax+20h], 0
0x180003cb7  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180003cbe  mov     [rbx], rax
0x180003cc1  mov     dword ptr [rbx+8], 1
0x180003cc8  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180003ccd  lea     rax, ??_7FloorFunctionExpression@@6B@; const FloorFunctionExpression::`vftable'
0x180003cd4  mov     qword ptr [rbx+10h], 0
0x180003cdc  mov     qword ptr [rbx+18h], 0
0x180003ce4  lea     rcx, [rbx+10h]
0x180003ce8  mov     qword ptr [rbx+20h], 0
0x180003cf0  mov     rdx, rdi
0x180003cf3  mov     [rbx], rax
0x180003cf6  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x180003cfb  xor     eax, eax
0x180003cfd  mov     [rsi], rbx
0x180003d00  jmp     short loc_180003D07
0x180003d02  mov     eax, 8007000Eh
0x180003d07  mov     rbx, [rsp+28h+arg_0]
0x180003d0c  mov     rsi, [rsp+28h+arg_8]
0x180003d11  add     rsp, 20h
0x180003d15  pop     rdi
0x180003d16  retn
```
