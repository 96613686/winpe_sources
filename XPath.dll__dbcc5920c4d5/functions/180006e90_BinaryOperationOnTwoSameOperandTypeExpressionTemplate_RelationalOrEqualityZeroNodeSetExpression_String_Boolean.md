# BinaryOperationOnTwoSameOperandTypeExpressionTemplate<RelationalOrEqualityZeroNodeSetExpression<String>,BooleanExpressionBase,String>::Allocate(bool (*)(String,String),XPathExpressionBase *,XPathExpressionBase *)

- ea: `0x180006e90`
- end: `0x180006f3a`
- name: `?Allocate@?$BinaryOperationOnTwoSameOperandTypeExpressionTemplate@V?$RelationalOrEqualityZeroNodeSetExpression@VString@@@@VBooleanExpressionBase@@VString@@@@SAPEAV?$RelationalOrEqualityZeroNodeSetExpression@VString@@@@P6A_NVString@@0@ZPEAVXPathExpressionBase@@2@Z`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005b60`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180004b84`
- `0x180006e90`

## pseudocode

```c
struct IUnknown **__fastcall BinaryOperationOnTwoSameOperandTypeExpressionTemplate<RelationalOrEqualityZeroNodeSetExpression<String>,BooleanExpressionBase,String>::Allocate(
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
  *v7 = (struct IUnknown *)&RelationalOrEqualityZeroNodeSetExpression<String>::`vftable';
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
0x180006e90  push    rbx
0x180006e92  push    rbp
0x180006e93  push    rsi
0x180006e94  push    rdi
0x180006e95  sub     rsp, 28h
0x180006e99  mov     rbp, rcx
0x180006e9c  mov     rdi, r8
0x180006e9f  mov     ecx, 28h ; '('; Size
0x180006ea4  mov     rsi, rdx
0x180006ea7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006eac  mov     rbx, rax
0x180006eaf  test    rax, rax
0x180006eb2  jz      short loc_180006F2C
0x180006eb4  mov     qword ptr [rax+8], 0
0x180006ebc  mov     qword ptr [rax+10h], 0
0x180006ec4  mov     qword ptr [rax+18h], 0
0x180006ecc  mov     qword ptr [rax+20h], 0
0x180006ed4  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180006edb  mov     [rbx], rax
0x180006ede  mov     dword ptr [rbx+8], 1
0x180006ee5  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180006eea  mov     qword ptr [rbx+18h], 0
0x180006ef2  lea     rax, ??_7?$RelationalOrEqualityZeroNodeSetExpression@VString@@@@6B@; const RelationalOrEqualityZeroNodeSetExpression<String>::`vftable'
0x180006ef9  mov     qword ptr [rbx+20h], 0
0x180006f01  lea     rcx, [rbx+18h]; struct IUnknown **
0x180006f05  mov     [rbx], rax
0x180006f08  mov     [rbx+10h], rbp
0x180006f0c  cmp     [rcx], rsi
0x180006f0f  jz      short loc_180006F19
0x180006f11  mov     rdx, rsi; struct IUnknown *
0x180006f14  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180006f19  lea     rcx, [rbx+20h]; struct IUnknown **
0x180006f1d  cmp     [rcx], rdi
0x180006f20  jz      short loc_180006F2E
0x180006f22  mov     rdx, rdi; struct IUnknown *
0x180006f25  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180006f2a  jmp     short loc_180006F2E
0x180006f2c  xor     ebx, ebx
0x180006f2e  mov     rax, rbx
0x180006f31  add     rsp, 28h
0x180006f35  pop     rdi
0x180006f36  pop     rsi
0x180006f37  pop     rbp
0x180006f38  pop     rbx
0x180006f39  retn
```
