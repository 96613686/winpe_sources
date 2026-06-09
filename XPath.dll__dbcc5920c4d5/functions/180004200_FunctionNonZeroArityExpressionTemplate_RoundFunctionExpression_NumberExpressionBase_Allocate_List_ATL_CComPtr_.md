# FunctionNonZeroArityExpressionTemplate<RoundFunctionExpression,NumberExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180004200`
- end: `0x1800042b7`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VRoundFunctionExpression@@VNumberExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180004200`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<RoundFunctionExpression,NumberExpressionBase>::Allocate(
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
  *v6 = &RoundFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180004200  mov     [rsp+arg_0], rbx
0x180004205  mov     [rsp+arg_8], rsi
0x18000420a  push    rdi
0x18000420b  sub     rsp, 20h
0x18000420f  cmp     dword ptr [rcx+14h], 1
0x180004213  mov     rsi, rdx
0x180004216  mov     rdi, rcx
0x180004219  jz      short loc_180004225
0x18000421b  mov     eax, 80070057h
0x180004220  jmp     loc_1800042A7
0x180004225  mov     ecx, 28h ; '('; Size
0x18000422a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000422f  mov     rbx, rax
0x180004232  test    rax, rax
0x180004235  jz      short loc_1800042A2
0x180004237  mov     qword ptr [rax+8], 0
0x18000423f  mov     qword ptr [rax+10h], 0
0x180004247  mov     qword ptr [rax+18h], 0
0x18000424f  mov     qword ptr [rax+20h], 0
0x180004257  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x18000425e  mov     [rbx], rax
0x180004261  mov     dword ptr [rbx+8], 1
0x180004268  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x18000426d  lea     rax, ??_7RoundFunctionExpression@@6B@; const RoundFunctionExpression::`vftable'
0x180004274  mov     qword ptr [rbx+10h], 0
0x18000427c  mov     qword ptr [rbx+18h], 0
0x180004284  lea     rcx, [rbx+10h]
0x180004288  mov     qword ptr [rbx+20h], 0
0x180004290  mov     rdx, rdi
0x180004293  mov     [rbx], rax
0x180004296  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x18000429b  xor     eax, eax
0x18000429d  mov     [rsi], rbx
0x1800042a0  jmp     short loc_1800042A7
0x1800042a2  mov     eax, 8007000Eh
0x1800042a7  mov     rbx, [rsp+28h+arg_0]
0x1800042ac  mov     rsi, [rsp+28h+arg_8]
0x1800042b1  add     rsp, 20h
0x1800042b5  pop     rdi
0x1800042b6  retn
```
