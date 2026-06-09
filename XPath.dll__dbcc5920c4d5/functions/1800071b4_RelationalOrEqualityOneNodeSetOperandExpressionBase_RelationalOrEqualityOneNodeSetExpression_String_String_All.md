# RelationalOrEqualityOneNodeSetOperandExpressionBase<RelationalOrEqualityOneNodeSetExpression<String>,String>::Allocate(bool,bool (*)(String,String),XPathNodeIteratorBase *,XPathExpressionBase *)

- ea: `0x1800071b4`
- end: `0x180007252`
- name: `?Allocate@?$RelationalOrEqualityOneNodeSetOperandExpressionBase@V?$RelationalOrEqualityOneNodeSetExpression@VString@@@@VString@@@@SAPEAV?$RelationalOrEqualityOneNodeSetExpression@VString@@@@_NP6A_NVString@@1@ZPEAVXPathNodeIteratorBase@@PEAVXPathExpressionBase@@@Z`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005b60`

## callees

- `0x180001078`
- `0x1800021a4`
- `0x180004b84`
- `0x1800059d4`
- `0x1800071b4`

## pseudocode

```c
_OWORD *__fastcall RelationalOrEqualityOneNodeSetOperandExpressionBase<RelationalOrEqualityOneNodeSetExpression<String>,String>::Allocate(
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
  *(_QWORD *)v9 = &RelationalOrEqualityOneNodeSetExpression<String>::`vftable';
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
0x1800071b4  push    rbx
0x1800071b6  push    rbp
0x1800071b7  push    rsi
0x1800071b8  push    rdi
0x1800071b9  push    r14
0x1800071bb  sub     rsp, 20h
0x1800071bf  mov     r14b, cl
0x1800071c2  mov     rdi, r9
0x1800071c5  mov     ecx, 30h ; '0'; Size
0x1800071ca  mov     rsi, r8
0x1800071cd  mov     rbp, rdx
0x1800071d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800071d5  mov     rbx, rax
0x1800071d8  test    rax, rax
0x1800071db  jz      short loc_180007242
0x1800071dd  xorps   xmm0, xmm0
0x1800071e0  movups  xmmword ptr [rax], xmm0
0x1800071e3  movups  xmmword ptr [rax+10h], xmm0
0x1800071e7  movups  xmmword ptr [rax+20h], xmm0
0x1800071eb  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathExpression@@@@6B@; const SimpleIUnknownImpl<IXPathExpression>::`vftable'
0x1800071f2  mov     [rbx], rax
0x1800071f5  mov     dword ptr [rbx+8], 1
0x1800071fc  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180007201  mov     qword ptr [rbx+20h], 0
0x180007209  lea     rax, ??_7?$RelationalOrEqualityOneNodeSetExpression@VString@@@@6B@; const RelationalOrEqualityOneNodeSetExpression<String>::`vftable'
0x180007210  mov     qword ptr [rbx+28h], 0
0x180007218  lea     rcx, [rbx+20h]
0x18000721c  mov     [rbx], rax
0x18000721f  mov     rdx, rsi
0x180007222  mov     [rbx+10h], r14b
0x180007226  mov     [rbx+18h], rbp
0x18000722a  call    ??$?4VXPathNodeIteratorBase@@@?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAAEAV0@PEAVXPathNodeIteratorBase@@@Z; InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(XPathNodeIteratorBase *)
0x18000722f  lea     rcx, [rbx+28h]; struct IUnknown **
0x180007233  cmp     [rcx], rdi
0x180007236  jz      short loc_180007244
0x180007238  mov     rdx, rdi; struct IUnknown *
0x18000723b  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180007240  jmp     short loc_180007244
0x180007242  xor     ebx, ebx
0x180007244  mov     rax, rbx
0x180007247  add     rsp, 20h
0x18000724b  pop     r14
0x18000724d  pop     rdi
0x18000724e  pop     rsi
0x18000724f  pop     rbp
0x180007250  pop     rbx
0x180007251  retn
```
