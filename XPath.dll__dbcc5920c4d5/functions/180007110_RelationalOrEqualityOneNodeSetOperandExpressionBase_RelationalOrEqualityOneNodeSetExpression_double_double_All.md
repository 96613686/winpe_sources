# RelationalOrEqualityOneNodeSetOperandExpressionBase<RelationalOrEqualityOneNodeSetExpression<double>,double>::Allocate(bool,bool (*)(double,double),XPathNodeIteratorBase *,XPathExpressionBase *)

- ea: `0x180007110`
- end: `0x1800071ae`
- name: `?Allocate@?$RelationalOrEqualityOneNodeSetOperandExpressionBase@V?$RelationalOrEqualityOneNodeSetExpression@N@@N@@SAPEAV?$RelationalOrEqualityOneNodeSetExpression@N@@_NP6A_NNN@ZPEAVXPathNodeIteratorBase@@PEAVXPathExpressionBase@@@Z`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005a3c`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180004b84`
- `0x1800059d4`
- `0x180007110`

## pseudocode

```c
_OWORD *__fastcall RelationalOrEqualityOneNodeSetOperandExpressionBase<RelationalOrEqualityOneNodeSetExpression<double>,double>::Allocate(
        char a1,
        __int64 a2,
        __int64 a3,
        struct IUnknown *a4)
{
  _OWORD *v8; // rax
  _OWORD *v9; // rbx

  v8 = operator new(0x30u);
  v9 = v8;
  if ( !v8 )
    return 0;
  *v8 = 0;
  v8[1] = 0;
  v8[2] = 0;
  *(_QWORD *)v8 = &SimpleIUnknownImpl<IXPathExpression>::`vftable';
  *((_DWORD *)v8 + 2) = 1;
  ModuleRefCounter::AddRef();
  *((_QWORD *)v9 + 4) = 0;
  *((_QWORD *)v9 + 5) = 0;
  *(_QWORD *)v9 = &RelationalOrEqualityOneNodeSetExpression<double>::`vftable';
  *((_BYTE *)v9 + 16) = a1;
  *((_QWORD *)v9 + 3) = a2;
  InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>((_QWORD *)v9 + 4, a3);
  if ( *((struct IUnknown **)v9 + 5) != a4 )
    ATL::AtlComPtrAssign((struct IUnknown **)v9 + 5, a4);
  return v9;
}

```

## disassembly

```asm
0x180007110  push    rbx
0x180007112  push    rbp
0x180007113  push    rsi
0x180007114  push    rdi
0x180007115  push    r14
0x180007117  sub     rsp, 20h
0x18000711b  mov     r14b, cl
0x18000711e  mov     rdi, r9
0x180007121  mov     ecx, 30h ; '0'; Size
0x180007126  mov     rsi, r8
0x180007129  mov     rbp, rdx
0x18000712c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007131  mov     rbx, rax
0x180007134  test    rax, rax
0x180007137  jz      short loc_18000719E
0x180007139  xorps   xmm0, xmm0
0x18000713c  movups  xmmword ptr [rax], xmm0
0x18000713f  movups  xmmword ptr [rax+10h], xmm0
0x180007143  movups  xmmword ptr [rax+20h], xmm0
0x180007147  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x18000714e  mov     [rbx], rax
0x180007151  mov     dword ptr [rbx+8], 1
0x180007158  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x18000715d  mov     qword ptr [rbx+20h], 0
0x180007165  lea     rax, ??_7?$RelationalOrEqualityOneNodeSetExpression@N@@6B@; const RelationalOrEqualityOneNodeSetExpression<double>::`vftable'
0x18000716c  mov     qword ptr [rbx+28h], 0
0x180007174  lea     rcx, [rbx+20h]
0x180007178  mov     [rbx], rax
0x18000717b  mov     rdx, rsi
0x18000717e  mov     [rbx+10h], r14b
0x180007182  mov     [rbx+18h], rbp
0x180007186  call    ??$?4VXPathNodeIteratorBase@@@?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAAEAV0@PEAVXPathNodeIteratorBase@@@Z; InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(XPathNodeIteratorBase *)
0x18000718b  lea     rcx, [rbx+28h]; struct IUnknown **
0x18000718f  cmp     [rcx], rdi
0x180007192  jz      short loc_1800071A0
0x180007194  mov     rdx, rdi; struct IUnknown *
0x180007197  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000719c  jmp     short loc_1800071A0
0x18000719e  xor     ebx, ebx
0x1800071a0  mov     rax, rbx
0x1800071a3  add     rsp, 20h
0x1800071a7  pop     r14
0x1800071a9  pop     rdi
0x1800071aa  pop     rsi
0x1800071ab  pop     rbp
0x1800071ac  pop     rbx
0x1800071ad  retn
```
