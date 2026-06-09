# FunctionNonZeroArityExpressionTemplate<SubstringFunctionExpression,StringExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180004680`
- end: `0x18000473c`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VSubstringFunctionExpression@@VStringExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180004680`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<SubstringFunctionExpression,StringExpressionBase>::Allocate(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rbx

  if ( (unsigned int)(*(_DWORD *)(a1 + 20) - 2) > 1 )
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
  *v6 = &SubstringFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180004680  mov     [rsp+arg_0], rbx
0x180004685  mov     [rsp+arg_8], rsi
0x18000468a  push    rdi
0x18000468b  sub     rsp, 20h
0x18000468f  mov     eax, [rcx+14h]
0x180004692  mov     rsi, rdx
0x180004695  sub     eax, 2
0x180004698  mov     rdi, rcx
0x18000469b  cmp     eax, 1
0x18000469e  jbe     short loc_1800046AA
0x1800046a0  mov     eax, 80070057h
0x1800046a5  jmp     loc_18000472C
0x1800046aa  mov     ecx, 28h ; '('; Size
0x1800046af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800046b4  mov     rbx, rax
0x1800046b7  test    rax, rax
0x1800046ba  jz      short loc_180004727
0x1800046bc  mov     qword ptr [rax+8], 0
0x1800046c4  mov     qword ptr [rax+10h], 0
0x1800046cc  mov     qword ptr [rax+18h], 0
0x1800046d4  mov     qword ptr [rax+20h], 0
0x1800046dc  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x1800046e3  mov     [rbx], rax
0x1800046e6  mov     dword ptr [rbx+8], 1
0x1800046ed  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x1800046f2  lea     rax, ??_7SubstringFunctionExpression@@6B@; const SubstringFunctionExpression::`vftable'
0x1800046f9  mov     qword ptr [rbx+10h], 0
0x180004701  mov     qword ptr [rbx+18h], 0
0x180004709  lea     rcx, [rbx+10h]
0x18000470d  mov     qword ptr [rbx+20h], 0
0x180004715  mov     rdx, rdi
0x180004718  mov     [rbx], rax
0x18000471b  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x180004720  xor     eax, eax
0x180004722  mov     [rsi], rbx
0x180004725  jmp     short loc_18000472C
0x180004727  mov     eax, 8007000Eh
0x18000472c  mov     rbx, [rsp+28h+arg_0]
0x180004731  mov     rsi, [rsp+28h+arg_8]
0x180004736  add     rsp, 20h
0x18000473a  pop     rdi
0x18000473b  retn
```
