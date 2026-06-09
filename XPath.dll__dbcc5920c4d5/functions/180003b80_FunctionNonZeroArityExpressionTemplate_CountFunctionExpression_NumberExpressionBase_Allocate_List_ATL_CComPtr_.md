# FunctionNonZeroArityExpressionTemplate<CountFunctionExpression,NumberExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180003b80`
- end: `0x180003c4c`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VCountFunctionExpression@@VNumberExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180003b80`
- `0x180008bdc`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<CountFunctionExpression,NumberExpressionBase>::Allocate(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  __int64 result; // rax

  if ( *(_DWORD *)(a1 + 20) != 1 || !XPathExpressionBase::IsNodeSet(**(XPathExpressionBase ***)(a1 + 8)) )
    return 2147942487LL;
  v4 = operator new(0x28u);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  v4[1] = 0;
  v4[2] = 0;
  v4[3] = 0;
  v4[4] = 0;
  *v4 = &SimpleIUnknownImpl<IXPathExpression>::`vftable';
  *((_DWORD *)v4 + 2) = 1;
  ModuleRefCounter::AddRef();
  v5[2] = 0;
  v5[3] = 0;
  v5[4] = 0;
  *v5 = &CountFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v5 + 2), a1);
  result = 0;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x180003b80  mov     [rsp+arg_0], rbx
0x180003b85  mov     [rsp+arg_8], rsi
0x180003b8a  push    rdi
0x180003b8b  sub     rsp, 20h
0x180003b8f  cmp     dword ptr [rcx+14h], 1
0x180003b93  mov     rsi, rdx
0x180003b96  mov     rdi, rcx
0x180003b99  jnz     loc_180003C37
0x180003b9f  mov     rcx, [rcx+8]
0x180003ba3  mov     rcx, [rcx]; this
0x180003ba6  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180003bab  test    al, al
0x180003bad  jz      loc_180003C37
0x180003bb3  mov     ecx, 28h ; '('; Size
0x180003bb8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003bbd  mov     rbx, rax
0x180003bc0  test    rax, rax
0x180003bc3  jz      short loc_180003C30
0x180003bc5  mov     qword ptr [rax+8], 0
0x180003bcd  mov     qword ptr [rax+10h], 0
0x180003bd5  mov     qword ptr [rax+18h], 0
0x180003bdd  mov     qword ptr [rax+20h], 0
0x180003be5  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180003bec  mov     [rbx], rax
0x180003bef  mov     dword ptr [rbx+8], 1
0x180003bf6  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180003bfb  lea     rax, ??_7CountFunctionExpression@@6B@; const CountFunctionExpression::`vftable'
0x180003c02  mov     qword ptr [rbx+10h], 0
0x180003c0a  mov     qword ptr [rbx+18h], 0
0x180003c12  lea     rcx, [rbx+10h]
0x180003c16  mov     qword ptr [rbx+20h], 0
0x180003c1e  mov     rdx, rdi
0x180003c21  mov     [rbx], rax
0x180003c24  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x180003c29  xor     eax, eax
0x180003c2b  mov     [rsi], rbx
0x180003c2e  jmp     short loc_180003C3C
0x180003c30  mov     eax, 8007000Eh
0x180003c35  jmp     short loc_180003C3C
0x180003c37  mov     eax, 80070057h
0x180003c3c  mov     rbx, [rsp+28h+arg_0]
0x180003c41  mov     rsi, [rsp+28h+arg_8]
0x180003c46  add     rsp, 20h
0x180003c4a  pop     rdi
0x180003c4b  retn
```
