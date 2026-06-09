# FunctionNonZeroArityExpressionTemplate<NameFunctionExpression,StringExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180003e00`
- end: `0x180003ecd`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VNameFunctionExpression@@VStringExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180003e00`
- `0x180008bdc`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<NameFunctionExpression,StringExpressionBase>::Allocate(
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
  *v6 = &NameFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180003e00  mov     [rsp+arg_0], rbx
0x180003e05  mov     [rsp+arg_8], rsi
0x180003e0a  push    rdi
0x180003e0b  sub     rsp, 20h
0x180003e0f  cmp     dword ptr [rcx+14h], 0
0x180003e13  mov     rsi, rdx
0x180003e16  mov     rdi, rcx
0x180003e19  jz      short loc_180003E3B
0x180003e1b  cmp     dword ptr [rcx+14h], 1
0x180003e1f  jnz     short loc_180003E31
0x180003e21  mov     rcx, [rcx+8]
0x180003e25  mov     rcx, [rcx]; this
0x180003e28  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180003e2d  test    al, al
0x180003e2f  jnz     short loc_180003E3B
0x180003e31  mov     eax, 80070057h
0x180003e36  jmp     loc_180003EBD
0x180003e3b  mov     ecx, 28h ; '('; Size
0x180003e40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003e45  mov     rbx, rax
0x180003e48  test    rax, rax
0x180003e4b  jz      short loc_180003EB8
0x180003e4d  mov     qword ptr [rax+8], 0
0x180003e55  mov     qword ptr [rax+10h], 0
0x180003e5d  mov     qword ptr [rax+18h], 0
0x180003e65  mov     qword ptr [rax+20h], 0
0x180003e6d  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180003e74  mov     [rbx], rax
0x180003e77  mov     dword ptr [rbx+8], 1
0x180003e7e  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180003e83  lea     rax, ??_7NameFunctionExpression@@6B@; const NameFunctionExpression::`vftable'
0x180003e8a  mov     qword ptr [rbx+10h], 0
0x180003e92  mov     qword ptr [rbx+18h], 0
0x180003e9a  lea     rcx, [rbx+10h]
0x180003e9e  mov     qword ptr [rbx+20h], 0
0x180003ea6  mov     rdx, rdi
0x180003ea9  mov     [rbx], rax
0x180003eac  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x180003eb1  xor     eax, eax
0x180003eb3  mov     [rsi], rbx
0x180003eb6  jmp     short loc_180003EBD
0x180003eb8  mov     eax, 8007000Eh
0x180003ebd  mov     rbx, [rsp+28h+arg_0]
0x180003ec2  mov     rsi, [rsp+28h+arg_8]
0x180003ec7  add     rsp, 20h
0x180003ecb  pop     rdi
0x180003ecc  retn
```
