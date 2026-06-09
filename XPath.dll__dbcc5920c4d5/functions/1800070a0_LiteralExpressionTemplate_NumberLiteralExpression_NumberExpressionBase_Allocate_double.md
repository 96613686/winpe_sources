# LiteralExpressionTemplate<NumberLiteralExpression,NumberExpressionBase>::Allocate(double)

- ea: `0x1800070a0`
- end: `0x180007107`
- name: `?Allocate@?$LiteralExpressionTemplate@VNumberLiteralExpression@@VNumberExpressionBase@@@@SAPEAVNumberLiteralExpression@@N@Z`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009d30`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x1800070a0`

## pseudocode

```c
double *__fastcall LiteralExpressionTemplate<NumberLiteralExpression,NumberExpressionBase>::Allocate(double a1)
{
  double *v1; // rax
  double *v2; // rbx

  v1 = (double *)operator new(0x18u);
  v2 = v1;
  if ( !v1 )
    return 0;
  v1[1] = 0.0;
  v1[2] = 0.0;
  *(_QWORD *)v1 = &SimpleIUnknownImpl<IXPathExpression>::`vftable';
  *((_DWORD *)v1 + 2) = 1;
  ModuleRefCounter::AddRef();
  *(_QWORD *)v2 = &NumberLiteralExpression::`vftable';
  v2[2] = a1;
  return v2;
}

```

## disassembly

```asm
0x1800070a0  push    rbx
0x1800070a2  sub     rsp, 30h
0x1800070a6  movaps  [rsp+38h+var_18], xmm6
0x1800070ab  mov     ecx, 18h; Size
0x1800070b0  movaps  xmm6, xmm0
0x1800070b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800070b8  mov     rbx, rax
0x1800070bb  test    rax, rax
0x1800070be  jz      short loc_1800070F7
0x1800070c0  mov     qword ptr [rax+8], 0
0x1800070c8  mov     qword ptr [rax+10h], 0
0x1800070d0  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x1800070d7  mov     [rbx], rax
0x1800070da  mov     dword ptr [rbx+8], 1
0x1800070e1  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x1800070e6  lea     rax, ??_7NumberLiteralExpression@@6B@; const NumberLiteralExpression::`vftable'
0x1800070ed  mov     [rbx], rax
0x1800070f0  movsd   qword ptr [rbx+10h], xmm6
0x1800070f5  jmp     short loc_1800070F9
0x1800070f7  xor     ebx, ebx
0x1800070f9  movaps  xmm6, [rsp+38h+var_18]
0x1800070fe  mov     rax, rbx
0x180007101  add     rsp, 30h
0x180007105  pop     rbx
0x180007106  retn
```
