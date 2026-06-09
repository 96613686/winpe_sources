# BinaryOperationOnTwoSameOperandTypeExpressionTemplate<BinaryArithmeticExpression,NumberExpressionBase,double>::Allocate(double (*)(double,double),XPathExpressionBase *,XPathExpressionBase *)

- ea: `0x180006ff0`
- end: `0x18000709a`
- name: `?Allocate@?$BinaryOperationOnTwoSameOperandTypeExpressionTemplate@VBinaryArithmeticExpression@@VNumberExpressionBase@@N@@SAPEAVBinaryArithmeticExpression@@P6ANNN@ZPEAVXPathExpressionBase@@1@Z`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008d28`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180004b84`
- `0x180006ff0`

## pseudocode

```c
struct IUnknown **__fastcall BinaryOperationOnTwoSameOperandTypeExpressionTemplate<BinaryArithmeticExpression,NumberExpressionBase,double>::Allocate(
        struct IUnknown *a1,
        struct IUnknown *a2,
        struct IUnknown *a3)
{
  struct IUnknown **v6; // rax
  struct IUnknown **v7; // rbx

  v6 = (struct IUnknown **)operator new(0x28u);
  v7 = v6;
  if ( !v6 )
    return 0;
  v6[1] = 0;
  v6[2] = 0;
  v6[3] = 0;
  v6[4] = 0;
  *v6 = (struct IUnknown *)&SimpleIUnknownImpl<IXPathExpression>::`vftable';
  *((_DWORD *)v6 + 2) = 1;
  ModuleRefCounter::AddRef();
  v7[3] = 0;
  v7[4] = 0;
  *v7 = (struct IUnknown *)&BinaryArithmeticExpression::`vftable';
  v7[2] = a1;
  if ( v7[3] != a2 )
    ATL::AtlComPtrAssign(v7 + 3, a2);
  if ( v7[4] != a3 )
    ATL::AtlComPtrAssign(v7 + 4, a3);
  return v7;
}

```

## disassembly

```asm
0x180006ff0  push    rbx
0x180006ff2  push    rbp
0x180006ff3  push    rsi
0x180006ff4  push    rdi
0x180006ff5  sub     rsp, 28h
0x180006ff9  mov     rbp, rcx
0x180006ffc  mov     rdi, r8
0x180006fff  mov     ecx, 28h ; '('; Size
0x180007004  mov     rsi, rdx
0x180007007  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000700c  mov     rbx, rax
0x18000700f  test    rax, rax
0x180007012  jz      short loc_18000708C
0x180007014  mov     qword ptr [rax+8], 0
0x18000701c  mov     qword ptr [rax+10h], 0
0x180007024  mov     qword ptr [rax+18h], 0
0x18000702c  mov     qword ptr [rax+20h], 0
0x180007034  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x18000703b  mov     [rbx], rax
0x18000703e  mov     dword ptr [rbx+8], 1
0x180007045  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x18000704a  mov     qword ptr [rbx+18h], 0
0x180007052  lea     rax, ??_7BinaryArithmeticExpression@@6B@; const BinaryArithmeticExpression::`vftable'
0x180007059  mov     qword ptr [rbx+20h], 0
0x180007061  lea     rcx, [rbx+18h]; struct IUnknown **
0x180007065  mov     [rbx], rax
0x180007068  mov     [rbx+10h], rbp
0x18000706c  cmp     [rcx], rsi
0x18000706f  jz      short loc_180007079
0x180007071  mov     rdx, rsi; struct IUnknown *
0x180007074  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180007079  lea     rcx, [rbx+20h]; struct IUnknown **
0x18000707d  cmp     [rcx], rdi
0x180007080  jz      short loc_18000708E
0x180007082  mov     rdx, rdi; struct IUnknown *
0x180007085  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000708a  jmp     short loc_18000708E
0x18000708c  xor     ebx, ebx
0x18000708e  mov     rax, rbx
0x180007091  add     rsp, 28h
0x180007095  pop     rdi
0x180007096  pop     rsi
0x180007097  pop     rbp
0x180007098  pop     rbx
0x180007099  retn
```
