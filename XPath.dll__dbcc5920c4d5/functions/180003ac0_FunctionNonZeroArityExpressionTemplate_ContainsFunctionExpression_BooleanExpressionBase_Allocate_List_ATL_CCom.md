# FunctionNonZeroArityExpressionTemplate<ContainsFunctionExpression,BooleanExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180003ac0`
- end: `0x180003b77`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VContainsFunctionExpression@@VBooleanExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180003ac0`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<ContainsFunctionExpression,BooleanExpressionBase>::Allocate(
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
  *v6 = &ContainsFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180003ac0  mov     [rsp+arg_0], rbx
0x180003ac5  mov     [rsp+arg_8], rsi
0x180003aca  push    rdi
0x180003acb  sub     rsp, 20h
0x180003acf  cmp     dword ptr [rcx+14h], 2
0x180003ad3  mov     rsi, rdx
0x180003ad6  mov     rdi, rcx
0x180003ad9  jz      short loc_180003AE5
0x180003adb  mov     eax, 80070057h
0x180003ae0  jmp     loc_180003B67
0x180003ae5  mov     ecx, 28h ; '('; Size
0x180003aea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003aef  mov     rbx, rax
0x180003af2  test    rax, rax
0x180003af5  jz      short loc_180003B62
0x180003af7  mov     qword ptr [rax+8], 0
0x180003aff  mov     qword ptr [rax+10h], 0
0x180003b07  mov     qword ptr [rax+18h], 0
0x180003b0f  mov     qword ptr [rax+20h], 0
0x180003b17  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180003b1e  mov     [rbx], rax
0x180003b21  mov     dword ptr [rbx+8], 1
0x180003b28  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180003b2d  lea     rax, ??_7ContainsFunctionExpression@@6B@; const ContainsFunctionExpression::`vftable'
0x180003b34  mov     qword ptr [rbx+10h], 0
0x180003b3c  mov     qword ptr [rbx+18h], 0
0x180003b44  lea     rcx, [rbx+10h]
0x180003b48  mov     qword ptr [rbx+20h], 0
0x180003b50  mov     rdx, rdi
0x180003b53  mov     [rbx], rax
0x180003b56  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x180003b5b  xor     eax, eax
0x180003b5d  mov     [rsi], rbx
0x180003b60  jmp     short loc_180003B67
0x180003b62  mov     eax, 8007000Eh
0x180003b67  mov     rbx, [rsp+28h+arg_0]
0x180003b6c  mov     rsi, [rsp+28h+arg_8]
0x180003b71  add     rsp, 20h
0x180003b75  pop     rdi
0x180003b76  retn
```
