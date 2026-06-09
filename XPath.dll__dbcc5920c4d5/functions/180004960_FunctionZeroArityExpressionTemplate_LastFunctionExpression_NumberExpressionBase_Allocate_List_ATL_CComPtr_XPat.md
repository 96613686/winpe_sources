# FunctionZeroArityExpressionTemplate<LastFunctionExpression,NumberExpressionBase>::Allocate(List<ATL::CComPtr<XPathExpressionBase>> &,XPathExpressionBase * *)

- ea: `0x180004960`
- end: `0x1800049c5`
- name: `?Allocate@?$FunctionZeroArityExpressionTemplate@VLastFunctionExpression@@VNumberExpressionBase@@@@SAJAEAV?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@PEAPEAVXPathExpressionBase@@@Z`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800056a0`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180004960`

## pseudocode

```c
__int64 __fastcall FunctionZeroArityExpressionTemplate<LastFunctionExpression,NumberExpressionBase>::Allocate(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  __int64 result; // rax

  v3 = operator new(0x10u);
  v4 = v3;
  if ( v3 )
  {
    v3[1] = 0;
    *v3 = &SimpleIUnknownImpl<IXPathExpression>::`vftable';
    *((_DWORD *)v3 + 2) = 1;
    ModuleRefCounter::AddRef();
    *v4 = &LastFunctionExpression::`vftable';
    result = 0;
    *a2 = v4;
  }
  else
  {
    *a2 = 0;
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180004960  mov     [rsp+arg_0], rbx
0x180004965  push    rdi
0x180004966  sub     rsp, 20h
0x18000496a  mov     ecx, 10h; Size
0x18000496f  mov     rdi, rdx
0x180004972  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004977  mov     rbx, rax
0x18000497a  test    rax, rax
0x18000497d  jz      short loc_1800049AE
0x18000497f  mov     qword ptr [rax+8], 0
0x180004987  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x18000498e  mov     [rbx], rax
0x180004991  mov     dword ptr [rbx+8], 1
0x180004998  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x18000499d  lea     rax, ??_7LastFunctionExpression@@6B@; const LastFunctionExpression::`vftable'
0x1800049a4  mov     [rbx], rax
0x1800049a7  xor     eax, eax
0x1800049a9  mov     [rdi], rbx
0x1800049ac  jmp     short loc_1800049BA
0x1800049ae  mov     qword ptr [rdi], 0
0x1800049b5  mov     eax, 8007000Eh
0x1800049ba  mov     rbx, [rsp+28h+arg_0]
0x1800049bf  add     rsp, 20h
0x1800049c3  pop     rdi
0x1800049c4  retn
```
