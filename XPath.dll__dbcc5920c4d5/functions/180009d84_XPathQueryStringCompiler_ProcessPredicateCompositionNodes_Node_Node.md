# XPathQueryStringCompiler::ProcessPredicateCompositionNodes(Node *,Node *)

- ea: `0x180009d84`
- end: `0x180009eae`
- name: `?ProcessPredicateCompositionNodes@XPathQueryStringCompiler@@AEAAJPEAVNode@@0@Z`
- size: `298`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *__hidden this, Node *, struct Node *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001c60`

## callees

- `0x1800020b4`
- `0x180004b84`
- `0x1800054e0`
- `0x1800059d4`
- `0x18000835c`
- `0x180008bdc`
- `0x180009d84`
- `0x18000a3a8`
- `0x18000f690`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessPredicateCompositionNodes(
        XPathQueryStringCompiler *this,
        Node *a2,
        struct Node *a3)
{
  struct IUnknown **v3; // rsi
  int v7; // ebx
  unsigned int Length; // ebx
  unsigned int v9; // eax
  int v10; // eax
  struct IUnknown *v12[2]; // [rsp+20h] [rbp-10h] BYREF
  XPathExpressionBase *v13; // [rsp+60h] [rbp+30h] BYREF
  __int64 v14; // [rsp+78h] [rbp+48h] BYREF

  v3 = (struct IUnknown **)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = &v13;
  v13 = 0;
  *((_DWORD *)this + 12) = 5;
  v7 = XPathQueryStringCompiler::Dispatch(this, a2);
  if ( v7 >= 0 )
  {
    if ( XPathExpressionBase::IsNodeSet(v13) )
    {
      v12[0] = 0;
      v14 = 0;
      InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(
        &v14,
        ((unsigned __int64)v13 - 8) & ((unsigned __int128)-(__int128)(unsigned __int64)v13 >> 64));
      *((_DWORD *)this + 8) = 7;
      *((_QWORD *)this + 3) = &v14;
      *((_DWORD *)this + 12) = 5;
      *((_QWORD *)this + 5) = v12;
      v7 = XPathQueryStringCompiler::Dispatch(this, a3);
      if ( v7 >= 0 && *v3 != v12[0] )
        ATL::AtlComPtrAssign(v3, v12[0]);
      InvasivePtr<UnionExpressionIterator>::Reset(&v14);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v12);
    }
    else
    {
      Length = Node::GetLength(a2);
      v9 = ((__int64 (__fastcall *)(Node *))a2->lpVtbl->Release)(a2);
      v10 = ExceptionHelpers::SetCompilationException((const unsigned __int16 **)this + 2, v9, Length, 0x6Cu);
      if ( v10 >= 0 )
        v7 = -2147024809;
      else
        v7 = v10;
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009d84  mov     [rsp-28h+arg_8], rbx
0x180009d89  push    rbp
0x180009d8a  push    rsi
0x180009d8b  push    rdi
0x180009d8c  push    r14
0x180009d8e  push    r15
0x180009d90  mov     rbp, rsp
0x180009d93  sub     rsp, 30h
0x180009d97  mov     rsi, [rcx+28h]
0x180009d9b  lea     rax, [rbp+arg_0]
0x180009d9f  mov     [rcx+28h], rax
0x180009da3  mov     r15, r8
0x180009da6  mov     r14, rdx
0x180009da9  mov     [rbp+arg_0], 0
0x180009db1  mov     rdi, rcx
0x180009db4  mov     dword ptr [rcx+30h], 5
0x180009dbb  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x180009dc0  mov     ebx, eax
0x180009dc2  test    eax, eax
0x180009dc4  js      loc_180009E92
0x180009dca  mov     rcx, [rbp+arg_0]; this
0x180009dce  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180009dd3  test    al, al
0x180009dd5  jnz     short loc_180009E16
0x180009dd7  mov     rcx, r14; this
0x180009dda  call    ?GetLength@Node@@QEAAKXZ; Node::GetLength(void)
0x180009ddf  mov     rcx, [r14]
0x180009de2  mov     ebx, eax
0x180009de4  mov     rax, [rcx+10h]
0x180009de8  mov     rcx, r14
0x180009deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009df0  lea     rcx, [rdi+10h]; struct String *
0x180009df4  mov     r9d, 6Ch ; 'l'; unsigned int
0x180009dfa  mov     r8d, ebx; unsigned int
0x180009dfd  mov     edx, eax; unsigned int
0x180009dff  call    ?SetCompilationException@ExceptionHelpers@@SAJAEAVString@@KKI@Z; ExceptionHelpers::SetCompilationException(String &,ulong,ulong,uint)
0x180009e04  test    eax, eax
0x180009e06  jns     short loc_180009E0F
0x180009e08  mov     ebx, eax
0x180009e0a  jmp     loc_180009E92
0x180009e0f  mov     ebx, 80070057h
0x180009e14  jmp     short loc_180009E92
0x180009e16  mov     rax, [rbp+arg_0]
0x180009e1a  mov     [rbp+var_10], 0
0x180009e22  mov     [rbp+arg_18], 0
0x180009e2a  lea     rcx, [rax-8]
0x180009e2e  neg     rax
0x180009e31  sbb     rdx, rdx
0x180009e34  and     rdx, rcx
0x180009e37  lea     rcx, [rbp+arg_18]
0x180009e3b  call    ??$?4VXPathNodeIteratorBase@@@?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAAEAV0@PEAVXPathNodeIteratorBase@@@Z; InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(XPathNodeIteratorBase *)
0x180009e40  mov     dword ptr [rdi+20h], 7
0x180009e47  lea     rax, [rbp+arg_18]
0x180009e4b  mov     [rdi+18h], rax
0x180009e4f  mov     rdx, r15; struct Node *
0x180009e52  lea     rax, [rbp+var_10]
0x180009e56  mov     dword ptr [rdi+30h], 5
0x180009e5d  mov     rcx, rdi; this
0x180009e60  mov     [rdi+28h], rax
0x180009e64  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x180009e69  mov     ebx, eax
0x180009e6b  test    eax, eax
0x180009e6d  js      short loc_180009E80
0x180009e6f  mov     rdx, [rbp+var_10]; struct IUnknown *
0x180009e73  cmp     [rsi], rdx
0x180009e76  jz      short loc_180009E80
0x180009e78  mov     rcx, rsi; struct IUnknown **
0x180009e7b  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180009e80  lea     rcx, [rbp+arg_18]
0x180009e84  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180009e89  lea     rcx, [rbp+var_10]
0x180009e8d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009e92  lea     rcx, [rbp+arg_0]
0x180009e96  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009e9b  mov     eax, ebx
0x180009e9d  mov     rbx, [rsp+30h+arg_8]
0x180009ea2  add     rsp, 30h
0x180009ea6  pop     r15
0x180009ea8  pop     r14
0x180009eaa  pop     rdi
0x180009eab  pop     rsi
0x180009eac  pop     rbp
0x180009ead  retn
```
