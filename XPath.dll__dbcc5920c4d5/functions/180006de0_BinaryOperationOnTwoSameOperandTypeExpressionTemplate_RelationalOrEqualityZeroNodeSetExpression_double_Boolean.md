# BinaryOperationOnTwoSameOperandTypeExpressionTemplate<RelationalOrEqualityZeroNodeSetExpression<double>,BooleanExpressionBase,double>::Allocate(bool (*)(double,double),XPathExpressionBase *,XPathExpressionBase *)

- ea: `0x180006de0`
- end: `0x180006e8a`
- name: `?Allocate@?$BinaryOperationOnTwoSameOperandTypeExpressionTemplate@V?$RelationalOrEqualityZeroNodeSetExpression@N@@VBooleanExpressionBase@@N@@SAPEAV?$RelationalOrEqualityZeroNodeSetExpression@N@@P6A_NNN@ZPEAVXPathExpressionBase@@1@Z`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005a10`
- `0x1800094f4`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180004b84`
- `0x180006de0`

## pseudocode

```c
struct IUnknown **__fastcall BinaryOperationOnTwoSameOperandTypeExpressionTemplate<RelationalOrEqualityZeroNodeSetExpression<double>,BooleanExpressionBase,double>::Allocate(
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
  *v7 = (struct IUnknown *)&RelationalOrEqualityZeroNodeSetExpression<double>::`vftable';
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
0x180006de0  push    rbx
0x180006de2  push    rbp
0x180006de3  push    rsi
0x180006de4  push    rdi
0x180006de5  sub     rsp, 28h
0x180006de9  mov     rbp, rcx
0x180006dec  mov     rdi, r8
0x180006def  mov     ecx, 28h ; '('; Size
0x180006df4  mov     rsi, rdx
0x180006df7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006dfc  mov     rbx, rax
0x180006dff  test    rax, rax
0x180006e02  jz      short loc_180006E7C
0x180006e04  mov     qword ptr [rax+8], 0
0x180006e0c  mov     qword ptr [rax+10h], 0
0x180006e14  mov     qword ptr [rax+18h], 0
0x180006e1c  mov     qword ptr [rax+20h], 0
0x180006e24  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180006e2b  mov     [rbx], rax
0x180006e2e  mov     dword ptr [rbx+8], 1
0x180006e35  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180006e3a  mov     qword ptr [rbx+18h], 0
0x180006e42  lea     rax, ??_7?$RelationalOrEqualityZeroNodeSetExpression@N@@6B@; const RelationalOrEqualityZeroNodeSetExpression<double>::`vftable'
0x180006e49  mov     qword ptr [rbx+20h], 0
0x180006e51  lea     rcx, [rbx+18h]; struct IUnknown **
0x180006e55  mov     [rbx], rax
0x180006e58  mov     [rbx+10h], rbp
0x180006e5c  cmp     [rcx], rsi
0x180006e5f  jz      short loc_180006E69
0x180006e61  mov     rdx, rsi; struct IUnknown *
0x180006e64  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180006e69  lea     rcx, [rbx+20h]; struct IUnknown **
0x180006e6d  cmp     [rcx], rdi
0x180006e70  jz      short loc_180006E7E
0x180006e72  mov     rdx, rdi; struct IUnknown *
0x180006e75  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180006e7a  jmp     short loc_180006E7E
0x180006e7c  xor     ebx, ebx
0x180006e7e  mov     rax, rbx
0x180006e81  add     rsp, 28h
0x180006e85  pop     rdi
0x180006e86  pop     rsi
0x180006e87  pop     rbp
0x180006e88  pop     rbx
0x180006e89  retn
```
