# RelationalOrEqualityOneNodeSetOperandExpressionBase<RelationalOrEqualityOneNodeSetExpression<bool>,bool>::Allocate(bool,bool (*)(bool,bool),XPathNodeIteratorBase *,XPathExpressionBase *)

- ea: `0x180007258`
- end: `0x1800072f6`
- name: `?Allocate@?$RelationalOrEqualityOneNodeSetOperandExpressionBase@V?$RelationalOrEqualityOneNodeSetExpression@_N@@_N@@SAPEAV?$RelationalOrEqualityOneNodeSetExpression@_N@@_NP6A_N00@ZPEAVXPathNodeIteratorBase@@PEAVXPathExpressionBase@@@Z`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005c7c`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180004b84`
- `0x1800059d4`
- `0x180007258`

## pseudocode

```c
_OWORD *__fastcall RelationalOrEqualityOneNodeSetOperandExpressionBase<RelationalOrEqualityOneNodeSetExpression<bool>,bool>::Allocate(
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
  *(_QWORD *)v9 = &RelationalOrEqualityOneNodeSetExpression<bool>::`vftable';
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
0x180007258  push    rbx
0x18000725a  push    rbp
0x18000725b  push    rsi
0x18000725c  push    rdi
0x18000725d  push    r14
0x18000725f  sub     rsp, 20h
0x180007263  mov     r14b, cl
0x180007266  mov     rdi, r9
0x180007269  mov     ecx, 30h ; '0'; Size
0x18000726e  mov     rsi, r8
0x180007271  mov     rbp, rdx
0x180007274  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007279  mov     rbx, rax
0x18000727c  test    rax, rax
0x18000727f  jz      short loc_1800072E6
0x180007281  xorps   xmm0, xmm0
0x180007284  movups  xmmword ptr [rax], xmm0
0x180007287  movups  xmmword ptr [rax+10h], xmm0
0x18000728b  movups  xmmword ptr [rax+20h], xmm0
0x18000728f  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x180007296  mov     [rbx], rax
0x180007299  mov     dword ptr [rbx+8], 1
0x1800072a0  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x1800072a5  mov     qword ptr [rbx+20h], 0
0x1800072ad  lea     rax, ??_7?$RelationalOrEqualityOneNodeSetExpression@_N@@6B@; const RelationalOrEqualityOneNodeSetExpression<bool>::`vftable'
0x1800072b4  mov     qword ptr [rbx+28h], 0
0x1800072bc  lea     rcx, [rbx+20h]
0x1800072c0  mov     [rbx], rax
0x1800072c3  mov     rdx, rsi
0x1800072c6  mov     [rbx+10h], r14b
0x1800072ca  mov     [rbx+18h], rbp
0x1800072ce  call    ??$?4VXPathNodeIteratorBase@@@?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAAEAV0@PEAVXPathNodeIteratorBase@@@Z; InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(XPathNodeIteratorBase *)
0x1800072d3  lea     rcx, [rbx+28h]; struct IUnknown **
0x1800072d7  cmp     [rcx], rdi
0x1800072da  jz      short loc_1800072E8
0x1800072dc  mov     rdx, rdi; struct IUnknown *
0x1800072df  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800072e4  jmp     short loc_1800072E8
0x1800072e6  xor     ebx, ebx
0x1800072e8  mov     rax, rbx
0x1800072eb  add     rsp, 20h
0x1800072ef  pop     r14
0x1800072f1  pop     rdi
0x1800072f2  pop     rsi
0x1800072f3  pop     rbp
0x1800072f4  pop     rbx
0x1800072f5  retn
```
