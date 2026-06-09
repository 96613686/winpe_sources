# BinaryOperationOnTwoSameOperandTypeExpressionTemplate<BinaryBooleanExpression,BooleanExpressionBase,bool>::Allocate(bool (*)(bool,bool),XPathExpressionBase *,XPathExpressionBase *)

- ea: `0x180006f40`
- end: `0x180006fea`
- name: `?Allocate@?$BinaryOperationOnTwoSameOperandTypeExpressionTemplate@VBinaryBooleanExpression@@VBooleanExpressionBase@@_N@@SAPEAVBinaryBooleanExpression@@P6A_N_N0@ZPEAVXPathExpressionBase@@2@Z`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005c7c`
- `0x180008dc4`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180004b84`
- `0x180006f40`

## pseudocode

```c
struct IUnknown **__fastcall BinaryOperationOnTwoSameOperandTypeExpressionTemplate<BinaryBooleanExpression,BooleanExpressionBase,bool>::Allocate(
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
  *v7 = (struct IUnknown *)&RelationalOrEqualityZeroNodeSetExpression<bool>::`vftable';
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
0x180006f40  push    rbx
0x180006f42  push    rbp
0x180006f43  push    rsi
0x180006f44  push    rdi
0x180006f45  sub     rsp, 28h
0x180006f49  mov     rbp, rcx
0x180006f4c  mov     rdi, r8
0x180006f4f  mov     ecx, 28h ; '('; Size
0x180006f54  mov     rsi, rdx
0x180006f57  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006f5c  mov     rbx, rax
0x180006f5f  test    rax, rax
0x180006f62  jz      short loc_180006FDC
0x180006f64  mov     qword ptr [rax+8], 0
0x180006f6c  mov     qword ptr [rax+10h], 0
0x180006f74  mov     qword ptr [rax+18h], 0
0x180006f7c  mov     qword ptr [rax+20h], 0
0x180006f84  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180006f8b  mov     [rbx], rax
0x180006f8e  mov     dword ptr [rbx+8], 1
0x180006f95  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180006f9a  mov     qword ptr [rbx+18h], 0
0x180006fa2  lea     rax, ??_7?$RelationalOrEqualityZeroNodeSetExpression@_N@@6B@; const RelationalOrEqualityZeroNodeSetExpression<bool>::`vftable'
0x180006fa9  mov     qword ptr [rbx+20h], 0
0x180006fb1  lea     rcx, [rbx+18h]; struct IUnknown **
0x180006fb5  mov     [rbx], rax
0x180006fb8  mov     [rbx+10h], rbp
0x180006fbc  cmp     [rcx], rsi
0x180006fbf  jz      short loc_180006FC9
0x180006fc1  mov     rdx, rsi; struct IUnknown *
0x180006fc4  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180006fc9  lea     rcx, [rbx+20h]; struct IUnknown **
0x180006fcd  cmp     [rcx], rdi
0x180006fd0  jz      short loc_180006FDE
0x180006fd2  mov     rdx, rdi; struct IUnknown *
0x180006fd5  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180006fda  jmp     short loc_180006FDE
0x180006fdc  xor     ebx, ebx
0x180006fde  mov     rax, rbx
0x180006fe1  add     rsp, 28h
0x180006fe5  pop     rdi
0x180006fe6  pop     rsi
0x180006fe7  pop     rbp
0x180006fe8  pop     rbx
0x180006fe9  retn
```
