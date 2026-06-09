# FunctionNonZeroArityExpressionTemplate<SubstringBeforeFunctionExpression,StringExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x1800045c0`
- end: `0x180004677`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VSubstringBeforeFunctionExpression@@VStringExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x1800045c0`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<SubstringBeforeFunctionExpression,StringExpressionBase>::Allocate(
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
  *v6 = &SubstringBeforeFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x1800045c0  mov     [rsp+arg_0], rbx
0x1800045c5  mov     [rsp+arg_8], rsi
0x1800045ca  push    rdi
0x1800045cb  sub     rsp, 20h
0x1800045cf  cmp     dword ptr [rcx+14h], 2
0x1800045d3  mov     rsi, rdx
0x1800045d6  mov     rdi, rcx
0x1800045d9  jz      short loc_1800045E5
0x1800045db  mov     eax, 80070057h
0x1800045e0  jmp     loc_180004667
0x1800045e5  mov     ecx, 28h ; '('; Size
0x1800045ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800045ef  mov     rbx, rax
0x1800045f2  test    rax, rax
0x1800045f5  jz      short loc_180004662
0x1800045f7  mov     qword ptr [rax+8], 0
0x1800045ff  mov     qword ptr [rax+10h], 0
0x180004607  mov     qword ptr [rax+18h], 0
0x18000460f  mov     qword ptr [rax+20h], 0
0x180004617  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x18000461e  mov     [rbx], rax
0x180004621  mov     dword ptr [rbx+8], 1
0x180004628  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x18000462d  lea     rax, ??_7SubstringBeforeFunctionExpression@@6B@; const SubstringBeforeFunctionExpression::`vftable'
0x180004634  mov     qword ptr [rbx+10h], 0
0x18000463c  mov     qword ptr [rbx+18h], 0
0x180004644  lea     rcx, [rbx+10h]
0x180004648  mov     qword ptr [rbx+20h], 0
0x180004650  mov     rdx, rdi
0x180004653  mov     [rbx], rax
0x180004656  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x18000465b  xor     eax, eax
0x18000465d  mov     [rsi], rbx
0x180004660  jmp     short loc_180004667
0x180004662  mov     eax, 8007000Eh
0x180004667  mov     rbx, [rsp+28h+arg_0]
0x18000466c  mov     rsi, [rsp+28h+arg_8]
0x180004671  add     rsp, 20h
0x180004675  pop     rdi
0x180004676  retn
```
