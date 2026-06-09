# FunctionNonZeroArityExpressionTemplate<StringLengthFunctionExpression,NumberExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180004440`
- end: `0x1800044f7`
- name: `?Allocate@?$FunctionNonZeroArityExpressionTemplate@VStringLengthFunctionExpression@@VNumberExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180003448`
- `0x180004440`

## pseudocode

```c
__int64 __fastcall FunctionNonZeroArityExpressionTemplate<StringLengthFunctionExpression,NumberExpressionBase>::Allocate(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rbx

  if ( *(_DWORD *)(a1 + 20) > 1u )
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
  *v6 = &StringLengthFunctionExpression::`vftable';
  List<ATL::CComPtr<XPathExpressionBase>>::operator=((__int64)(v6 + 2), a1);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180004440  mov     [rsp+arg_0], rbx
0x180004445  mov     [rsp+arg_8], rsi
0x18000444a  push    rdi
0x18000444b  sub     rsp, 20h
0x18000444f  cmp     dword ptr [rcx+14h], 1
0x180004453  mov     rsi, rdx
0x180004456  mov     rdi, rcx
0x180004459  jbe     short loc_180004465
0x18000445b  mov     eax, 80070057h
0x180004460  jmp     loc_1800044E7
0x180004465  mov     ecx, 28h ; '('; Size
0x18000446a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000446f  mov     rbx, rax
0x180004472  test    rax, rax
0x180004475  jz      short loc_1800044E2
0x180004477  mov     qword ptr [rax+8], 0
0x18000447f  mov     qword ptr [rax+10h], 0
0x180004487  mov     qword ptr [rax+18h], 0
0x18000448f  mov     qword ptr [rax+20h], 0
0x180004497  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x18000449e  mov     [rbx], rax
0x1800044a1  mov     dword ptr [rbx+8], 1
0x1800044a8  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x1800044ad  lea     rax, ??_7StringLengthFunctionExpression@@6B@; const StringLengthFunctionExpression::`vftable'
0x1800044b4  mov     qword ptr [rbx+10h], 0
0x1800044bc  mov     qword ptr [rbx+18h], 0
0x1800044c4  lea     rcx, [rbx+10h]
0x1800044c8  mov     qword ptr [rbx+20h], 0
0x1800044d0  mov     rdx, rdi
0x1800044d3  mov     [rbx], rax
0x1800044d6  call    ??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z; List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)
0x1800044db  xor     eax, eax
0x1800044dd  mov     [rsi], rbx
0x1800044e0  jmp     short loc_1800044E7
0x1800044e2  mov     eax, 8007000Eh
0x1800044e7  mov     rbx, [rsp+28h+arg_0]
0x1800044ec  mov     rsi, [rsp+28h+arg_8]
0x1800044f1  add     rsp, 20h
0x1800044f5  pop     rdi
0x1800044f6  retn
```
