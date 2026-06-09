# FunctionNonZeroArityExpressionTemplate<LocalNameFunctionExpression,StringExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180003d20`
- end: `0x180003ded`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VLocalNameFunctionExpression@@VStringExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180003d20`
- `0x180008bdc`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<LocalNameFunctionExpression,StringExpressionBase>::Allocate(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rbx

  if ( *(_DWORD *)(a1 + 20)
    && (*(_DWORD *)(a1 + 20) != 1 || !XPathExpressionBase::IsNodeSet(**(XPathExpressionBase ***)(a1 + 8))) )
  {
    return 2147942487LL;
  }
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
  *v6 = &LocalNameFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180003d20  mov     [rsp+arg_0], rbx
0x180003d25  mov     [rsp+arg_8], rsi
0x180003d2a  push    rdi
0x180003d2b  sub     rsp, 20h
0x180003d2f  cmp     dword ptr [rcx+14h], 0
0x180003d33  mov     rsi, rdx
0x180003d36  mov     rdi, rcx
0x180003d39  jz      short loc_180003D5B
0x180003d3b  cmp     dword ptr [rcx+14h], 1
0x180003d3f  jnz     short loc_180003D51
0x180003d41  mov     rcx, [rcx+8]
0x180003d45  mov     rcx, [rcx]; this
0x180003d48  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180003d4d  test    al, al
0x180003d4f  jnz     short loc_180003D5B
0x180003d51  mov     eax, 80070057h
0x180003d56  jmp     loc_180003DDD
0x180003d5b  mov     ecx, 28h ; '('; Size
0x180003d60  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003d65  mov     rbx, rax
0x180003d68  test    rax, rax
0x180003d6b  jz      short loc_180003DD8
0x180003d6d  mov     qword ptr [rax+8], 0
0x180003d75  mov     qword ptr [rax+10h], 0
0x180003d7d  mov     qword ptr [rax+18h], 0
0x180003d85  mov     qword ptr [rax+20h], 0
0x180003d8d  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180003d94  mov     [rbx], rax
0x180003d97  mov     dword ptr [rbx+8], 1
0x180003d9e  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180003da3  lea     rax, ??_7LocalNameFunctionExpression@@6B@; const LocalNameFunctionExpression::`vftable'
0x180003daa  mov     qword ptr [rbx+10h], 0
0x180003db2  mov     qword ptr [rbx+18h], 0
0x180003dba  lea     rcx, [rbx+10h]
0x180003dbe  mov     qword ptr [rbx+20h], 0
0x180003dc6  mov     rdx, rdi
0x180003dc9  mov     [rbx], rax
0x180003dcc  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x180003dd1  xor     eax, eax
0x180003dd3  mov     [rsi], rbx
0x180003dd6  jmp     short loc_180003DDD
0x180003dd8  mov     eax, 8007000Eh
0x180003ddd  mov     rbx, [rsp+28h+arg_0]
0x180003de2  mov     rsi, [rsp+28h+arg_8]
0x180003de7  add     rsp, 20h
0x180003deb  pop     rdi
0x180003dec  retn
```
