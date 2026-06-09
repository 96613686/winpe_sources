# FunctionNonZeroArityExpressionTemplate<NamespaceUriFunctionExpression,StringExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180003ee0`
- end: `0x180003fad`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VNamespaceUriFunctionExpression@@VStringExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180003ee0`
- `0x180008bdc`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<NamespaceUriFunctionExpression,StringExpressionBase>::Allocate(
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
  *v6 = &NamespaceUriFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180003ee0  mov     [rsp+arg_0], rbx
0x180003ee5  mov     [rsp+arg_8], rsi
0x180003eea  push    rdi
0x180003eeb  sub     rsp, 20h
0x180003eef  cmp     dword ptr [rcx+14h], 0
0x180003ef3  mov     rsi, rdx
0x180003ef6  mov     rdi, rcx
0x180003ef9  jz      short loc_180003F1B
0x180003efb  cmp     dword ptr [rcx+14h], 1
0x180003eff  jnz     short loc_180003F11
0x180003f01  mov     rcx, [rcx+8]
0x180003f05  mov     rcx, [rcx]; this
0x180003f08  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180003f0d  test    al, al
0x180003f0f  jnz     short loc_180003F1B
0x180003f11  mov     eax, 80070057h
0x180003f16  jmp     loc_180003F9D
0x180003f1b  mov     ecx, 28h ; '('; Size
0x180003f20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003f25  mov     rbx, rax
0x180003f28  test    rax, rax
0x180003f2b  jz      short loc_180003F98
0x180003f2d  mov     qword ptr [rax+8], 0
0x180003f35  mov     qword ptr [rax+10h], 0
0x180003f3d  mov     qword ptr [rax+18h], 0
0x180003f45  mov     qword ptr [rax+20h], 0
0x180003f4d  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180003f54  mov     [rbx], rax
0x180003f57  mov     dword ptr [rbx+8], 1
0x180003f5e  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180003f63  lea     rax, ??_7NamespaceUriFunctionExpression@@6B@; const NamespaceUriFunctionExpression::`vftable'
0x180003f6a  mov     qword ptr [rbx+10h], 0
0x180003f72  mov     qword ptr [rbx+18h], 0
0x180003f7a  lea     rcx, [rbx+10h]
0x180003f7e  mov     qword ptr [rbx+20h], 0
0x180003f86  mov     rdx, rdi
0x180003f89  mov     [rbx], rax
0x180003f8c  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x180003f91  xor     eax, eax
0x180003f93  mov     [rsi], rbx
0x180003f96  jmp     short loc_180003F9D
0x180003f98  mov     eax, 8007000Eh
0x180003f9d  mov     rbx, [rsp+28h+arg_0]
0x180003fa2  mov     rsi, [rsp+28h+arg_8]
0x180003fa7  add     rsp, 20h
0x180003fab  pop     rdi
0x180003fac  retn
```
