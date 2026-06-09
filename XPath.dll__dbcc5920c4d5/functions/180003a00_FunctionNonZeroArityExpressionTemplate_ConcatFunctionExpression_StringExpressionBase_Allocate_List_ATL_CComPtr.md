# FunctionNonZeroArityExpressionTemplate<ConcatFunctionExpression,StringExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180003a00`
- end: `0x180003ab7`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VConcatFunctionExpression@@VStringExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180003a00`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<ConcatFunctionExpression,StringExpressionBase>::Allocate(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rbx

  if ( *(_DWORD *)(a1 + 20) < 2u )
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
  *v6 = &ConcatFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180003a00  mov     [rsp+arg_0], rbx
0x180003a05  mov     [rsp+arg_8], rsi
0x180003a0a  push    rdi
0x180003a0b  sub     rsp, 20h
0x180003a0f  cmp     dword ptr [rcx+14h], 2
0x180003a13  mov     rsi, rdx
0x180003a16  mov     rdi, rcx
0x180003a19  jnb     short loc_180003A25
0x180003a1b  mov     eax, 80070057h
0x180003a20  jmp     loc_180003AA7
0x180003a25  mov     ecx, 28h ; '('; Size
0x180003a2a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a2f  mov     rbx, rax
0x180003a32  test    rax, rax
0x180003a35  jz      short loc_180003AA2
0x180003a37  mov     qword ptr [rax+8], 0
0x180003a3f  mov     qword ptr [rax+10h], 0
0x180003a47  mov     qword ptr [rax+18h], 0
0x180003a4f  mov     qword ptr [rax+20h], 0
0x180003a57  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180003a5e  mov     [rbx], rax
0x180003a61  mov     dword ptr [rbx+8], 1
0x180003a68  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180003a6d  lea     rax, ??_7ConcatFunctionExpression@@6B@; const ConcatFunctionExpression::`vftable'
0x180003a74  mov     qword ptr [rbx+10h], 0
0x180003a7c  mov     qword ptr [rbx+18h], 0
0x180003a84  lea     rcx, [rbx+10h]
0x180003a88  mov     qword ptr [rbx+20h], 0
0x180003a90  mov     rdx, rdi
0x180003a93  mov     [rbx], rax
0x180003a96  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x180003a9b  xor     eax, eax
0x180003a9d  mov     [rsi], rbx
0x180003aa0  jmp     short loc_180003AA7
0x180003aa2  mov     eax, 8007000Eh
0x180003aa7  mov     rbx, [rsp+28h+arg_0]
0x180003aac  mov     rsi, [rsp+28h+arg_8]
0x180003ab1  add     rsp, 20h
0x180003ab5  pop     rdi
0x180003ab6  retn
```
