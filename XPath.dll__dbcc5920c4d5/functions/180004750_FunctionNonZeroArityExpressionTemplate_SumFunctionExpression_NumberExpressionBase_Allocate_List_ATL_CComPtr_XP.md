# FunctionNonZeroArityExpressionTemplate<SumFunctionExpression,NumberExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180004750`
- end: `0x18000481c`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VSumFunctionExpression@@VNumberExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180004750`
- `0x180008bdc`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<SumFunctionExpression,NumberExpressionBase>::Allocate(
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
  *v5 = &SumFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v5 + 2), a1);
  result = 0;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x180004750  mov     [rsp+arg_0], rbx
0x180004755  mov     [rsp+arg_8], rsi
0x18000475a  push    rdi
0x18000475b  sub     rsp, 20h
0x18000475f  cmp     dword ptr [rcx+14h], 1
0x180004763  mov     rsi, rdx
0x180004766  mov     rdi, rcx
0x180004769  jnz     loc_180004807
0x18000476f  mov     rcx, [rcx+8]
0x180004773  mov     rcx, [rcx]; this
0x180004776  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x18000477b  test    al, al
0x18000477d  jz      loc_180004807
0x180004783  mov     ecx, 28h ; '('; Size
0x180004788  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000478d  mov     rbx, rax
0x180004790  test    rax, rax
0x180004793  jz      short loc_180004800
0x180004795  mov     qword ptr [rax+8], 0
0x18000479d  mov     qword ptr [rax+10h], 0
0x1800047a5  mov     qword ptr [rax+18h], 0
0x1800047ad  mov     qword ptr [rax+20h], 0
0x1800047b5  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x1800047bc  mov     [rbx], rax
0x1800047bf  mov     dword ptr [rbx+8], 1
0x1800047c6  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x1800047cb  lea     rax, ??_7SumFunctionExpression@@6B@; const SumFunctionExpression::`vftable'
0x1800047d2  mov     qword ptr [rbx+10h], 0
0x1800047da  mov     qword ptr [rbx+18h], 0
0x1800047e2  lea     rcx, [rbx+10h]
0x1800047e6  mov     qword ptr [rbx+20h], 0
0x1800047ee  mov     rdx, rdi
0x1800047f1  mov     [rbx], rax
0x1800047f4  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x1800047f9  xor     eax, eax
0x1800047fb  mov     [rsi], rbx
0x1800047fe  jmp     short loc_18000480C
0x180004800  mov     eax, 8007000Eh
0x180004805  jmp     short loc_18000480C
0x180004807  mov     eax, 80070057h
0x18000480c  mov     rbx, [rsp+28h+arg_0]
0x180004811  mov     rsi, [rsp+28h+arg_8]
0x180004816  add     rsp, 20h
0x18000481a  pop     rdi
0x18000481b  retn
```
