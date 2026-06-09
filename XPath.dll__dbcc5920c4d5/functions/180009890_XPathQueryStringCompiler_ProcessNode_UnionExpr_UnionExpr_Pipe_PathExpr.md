# XPathQueryStringCompiler::ProcessNode(UnionExpr__UnionExpr_Pipe_PathExpr *)

- ea: `0x180009890`
- end: `0x180009b16`
- name: `?ProcessNode@XPathQueryStringCompiler@@QEAAJPEAVUnionExpr__UnionExpr_Pipe_PathExpr@@@Z`
- size: `646`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *__hidden this, struct UnionExpr__UnionExpr_Pipe_PathExpr *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002080`

## callees

- `0x180001078`
- `0x1800020b4`
- `0x1800032f4`
- `0x180004b84`
- `0x1800054e0`
- `0x18000835c`
- `0x180008bdc`
- `0x180009890`
- `0x18000a3a8`
- `0x18000f690`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessNode(
        XPathQueryStringCompiler *this,
        struct UnionExpr__UnionExpr_Pipe_PathExpr *a2)
{
  struct Node *v2; // r14
  struct IUnknown **v4; // rsi
  struct Node *AddRef; // r15
  int v6; // ebx
  unsigned int Length; // eax
  struct Node v8; // rdx
  struct Node *v9; // rcx
  unsigned int v10; // ebx
  unsigned int v11; // eax
  int v12; // eax
  unsigned __int64 v13; // rbx
  XPathNodeIteratorBase *v14; // rax
  XPathNodeIteratorBase *v15; // rdi
  struct IUnknown *v16; // rdx
  _QWORD v18[3]; // [rsp+20h] [rbp-18h] BYREF
  struct IUnknown *v19; // [rsp+70h] [rbp+38h] BYREF
  XPathNodeIteratorBase *v20; // [rsp+78h] [rbp+40h] BYREF
  XPathExpressionBase *v21; // [rsp+80h] [rbp+48h] BYREF
  XPathExpressionBase *v22; // [rsp+88h] [rbp+50h] BYREF

  v2 = (struct Node *)*((_QWORD *)a2 + 2);
  v4 = (struct IUnknown **)*((_QWORD *)this + 5);
  AddRef = (struct Node *)v2[1].lpVtbl->AddRef;
  *((_QWORD *)this + 5) = &v22;
  v22 = 0;
  v21 = 0;
  *((_DWORD *)this + 12) = 5;
  v6 = XPathQueryStringCompiler::Dispatch(this, v2);
  if ( v6 >= 0 )
  {
    if ( !XPathExpressionBase::IsNodeSet(v22) )
    {
      Length = Node::GetLength(v2);
      v8.lpVtbl = v2->lpVtbl;
      v9 = v2;
      goto LABEL_4;
    }
    *((_DWORD *)this + 12) = 5;
    *((_QWORD *)this + 5) = &v21;
    v12 = XPathQueryStringCompiler::Dispatch(this, AddRef);
    if ( v12 < 0 )
    {
LABEL_5:
      v6 = v12;
      goto LABEL_29;
    }
    if ( !XPathExpressionBase::IsNodeSet(v21) )
    {
      Length = Node::GetLength(AddRef);
      v8.lpVtbl = AddRef->lpVtbl;
      v9 = AddRef;
LABEL_4:
      v10 = Length;
      v11 = ((__int64 (__fastcall *)(struct Node *))v8.lpVtbl->Release)(v9);
      v12 = ExceptionHelpers::SetCompilationException((const unsigned __int16 **)this + 2, v11, v10, 0x6Cu);
      if ( v12 >= 0 )
      {
        v6 = -2147024809;
        goto LABEL_29;
      }
      goto LABEL_5;
    }
    v13 = ((unsigned __int64)v22 - 8) & -(__int64)(v22 != 0);
    v18[0] = v13;
    if ( v13 )
      _InterlockedIncrement((volatile signed __int32 *)(v13 + 16));
    v19 = 0;
    if ( (**(unsigned int (__fastcall ***)(unsigned __int64, GUID *, struct IUnknown **))v13)(
           v13,
           &IID_IUnionExpressionIterator,
           &v19) == -2147467262 )
    {
      v20 = 0;
      v14 = (XPathNodeIteratorBase *)operator new(0x40u);
      v15 = v14;
      if ( v14 )
      {
        XPathNodeIteratorBase::XPathNodeIteratorBase(v14);
        *((_DWORD *)v15 + 8) = 0;
        *(_QWORD *)v15 = &UnionExpressionIterator::`vftable'{for `IXPathNodeIterator'};
        *((_QWORD *)v15 + 1) = &UnionExpressionIterator::`vftable'{for `XPathExpressionBase'};
        *((_QWORD *)v15 + 3) = &UnionExpressionIterator::`vftable';
        *((_QWORD *)v15 + 5) = 0;
        *((_QWORD *)v15 + 6) = 0;
        *((_QWORD *)v15 + 7) = 0;
      }
      else
      {
        v15 = 0;
      }
      InvasivePtr<UnionExpressionIterator>::Reset(&v20);
      v20 = v15;
      if ( !v15 )
      {
        InvasivePtr<UnionExpressionIterator>::Reset(&v20);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
        InvasivePtr<UnionExpressionIterator>::Reset(v18);
        v6 = -2147024882;
        goto LABEL_29;
      }
      v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*((_QWORD *)v15 + 3) + 24LL))((__int64)v15 + 24, v13);
      if ( v6 < 0 )
      {
        InvasivePtr<UnionExpressionIterator>::Reset(&v20);
LABEL_28:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
        InvasivePtr<UnionExpressionIterator>::Reset(v18);
        goto LABEL_29;
      }
      if ( v19 != (struct IUnknown *)((char *)v15 + 24) )
        ATL::AtlComPtrAssign(&v19, (struct IUnknown *)v15 + 3);
      if ( *v4 != (struct IUnknown *)((char *)v15 + 8) )
        ATL::AtlComPtrAssign(v4, (struct IUnknown *)v15 + 1);
      InvasivePtr<UnionExpressionIterator>::Reset(&v20);
    }
    else
    {
      v16 = (struct IUnknown *)((v13 + 8) & -(__int64)(v13 != 0));
      if ( *v4 != v16 )
        ATL::AtlComPtrAssign(v4, v16);
    }
    v6 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int64))v19->lpVtbl[1].QueryInterface)(
           v19,
           ((unsigned __int64)v21 - 8) & -(__int64)(v21 != 0));
    goto LABEL_28;
  }
LABEL_29:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v22);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009890  push    rbp
0x180009892  push    rbx
0x180009893  push    rsi
0x180009894  push    rdi
0x180009895  push    r14
0x180009897  push    r15
0x180009899  mov     rbp, rsp
0x18000989c  sub     rsp, 38h
0x1800098a0  mov     r14, [rdx+10h]
0x1800098a4  mov     rdi, rcx
0x1800098a7  mov     rsi, [rcx+28h]
0x1800098ab  mov     rdx, r14; struct Node *
0x1800098ae  mov     rax, [r14+8]
0x1800098b2  mov     r15, [rax+8]
0x1800098b6  lea     rax, [rbp+arg_18]
0x1800098ba  mov     [rcx+28h], rax
0x1800098be  mov     [rbp+arg_18], 0
0x1800098c6  mov     [rbp+arg_10], 0
0x1800098ce  mov     dword ptr [rcx+30h], 5
0x1800098d5  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x1800098da  mov     ebx, eax
0x1800098dc  test    eax, eax
0x1800098de  js      loc_180009AF5
0x1800098e4  mov     rcx, [rbp+arg_18]; this
0x1800098e8  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x1800098ed  test    al, al
0x1800098ef  jnz     short loc_180009929
0x1800098f1  mov     rcx, r14; this
0x1800098f4  call    ?GetLength@Node@@QEAAKXZ; Node::GetLength(void)
0x1800098f9  mov     rdx, [r14]
0x1800098fc  mov     rcx, r14
0x1800098ff  mov     ebx, eax
0x180009901  mov     rax, [rdx+10h]
0x180009905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000990a  lea     rcx, [rdi+10h]; struct String *
0x18000990e  mov     r9d, 6Ch ; 'l'; unsigned int
0x180009914  mov     r8d, ebx; unsigned int
0x180009917  mov     edx, eax; unsigned int
0x180009919  call    ?SetCompilationException@ExceptionHelpers@@SAJAEAVString@@KKI@Z; ExceptionHelpers::SetCompilationException(String &,ulong,ulong,uint)
0x18000991e  test    eax, eax
0x180009920  jns     short loc_180009964
0x180009922  mov     ebx, eax
0x180009924  jmp     loc_180009AF5
0x180009929  lea     rax, [rbp+arg_10]
0x18000992d  mov     dword ptr [rdi+30h], 5
0x180009934  mov     rdx, r15; struct Node *
0x180009937  mov     [rdi+28h], rax
0x18000993b  mov     rcx, rdi; this
0x18000993e  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x180009943  test    eax, eax
0x180009945  js      short loc_180009922
0x180009947  mov     rcx, [rbp+arg_10]; this
0x18000994b  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180009950  test    al, al
0x180009952  jnz     short loc_18000996E
0x180009954  mov     rcx, r15; this
0x180009957  call    ?GetLength@Node@@QEAAKXZ; Node::GetLength(void)
0x18000995c  mov     rdx, [r15]
0x18000995f  mov     rcx, r15
0x180009962  jmp     short loc_1800098FF
0x180009964  mov     ebx, 80070057h
0x180009969  jmp     loc_180009AF5
0x18000996e  mov     rax, [rbp+arg_18]
0x180009972  lea     rcx, [rax-8]
0x180009976  neg     rax
0x180009979  sbb     rbx, rbx
0x18000997c  and     rbx, rcx
0x18000997f  mov     [rbp+var_18], rbx
0x180009983  jz      short loc_180009989
0x180009985  lock inc dword ptr [rbx+10h]
0x180009989  mov     [rbp+arg_0], 0
0x180009991  lea     r8, [rbp+arg_0]
0x180009995  mov     rax, [rbx]
0x180009998  lea     rdx, ?IID_IUnionExpressionIterator@@3U_GUID@@B; _GUID const IID_IUnionExpressionIterator
0x18000999f  mov     rcx, rbx
0x1800099a2  mov     rax, [rax]
0x1800099a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099aa  cmp     eax, 80004002h
0x1800099af  jnz     loc_180009AA6
0x1800099b5  mov     ecx, 40h ; '@'; Size
0x1800099ba  mov     [rbp+arg_8], 0
0x1800099c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800099c7  mov     rdi, rax
0x1800099ca  test    rax, rax
0x1800099cd  jz      short loc_180009A18
0x1800099cf  mov     rcx, rax; this
0x1800099d2  call    ??0XPathNodeIteratorBase@@QEAA@XZ; XPathNodeIteratorBase::XPathNodeIteratorBase(void)
0x1800099d7  mov     dword ptr [rdi+20h], 0
0x1800099de  lea     rax, ??_7UnionExpressionIterator@@6BIXPathNodeIterator@@@; const UnionExpressionIterator::`vftable'{for `IXPathNodeIterator'}
0x1800099e5  mov     [rdi], rax
0x1800099e8  lea     rax, ??_7UnionExpressionIterator@@6BXPathExpressionBase@@@; const UnionExpressionIterator::`vftable'{for `XPathExpressionBase'}
0x1800099ef  mov     [rdi+8], rax
0x1800099f3  lea     rax, ??_7UnionExpressionIterator@@6B@; const UnionExpressionIterator::`vftable'
0x1800099fa  mov     [rdi+18h], rax
0x1800099fe  mov     qword ptr [rdi+28h], 0
0x180009a06  mov     qword ptr [rdi+30h], 0
0x180009a0e  mov     qword ptr [rdi+38h], 0
0x180009a16  jmp     short loc_180009A1A
0x180009a18  xor     edi, edi
0x180009a1a  lea     rcx, [rbp+arg_8]
0x180009a1e  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180009a23  mov     [rbp+arg_8], rdi
0x180009a27  test    rdi, rdi
0x180009a2a  jnz     short loc_180009A51
0x180009a2c  lea     rcx, [rbp+arg_8]
0x180009a30  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180009a35  lea     rcx, [rbp+arg_0]
0x180009a39  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009a3e  lea     rcx, [rbp+var_18]
0x180009a42  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180009a47  mov     ebx, 8007000Eh
0x180009a4c  jmp     loc_180009AF5
0x180009a51  lea     r14, [rdi+18h]
0x180009a55  mov     rdx, rbx
0x180009a58  mov     rax, [r14]
0x180009a5b  mov     rcx, r14
0x180009a5e  mov     rax, [rax+18h]
0x180009a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a67  mov     ebx, eax
0x180009a69  test    eax, eax
0x180009a6b  jns     short loc_180009A78
0x180009a6d  lea     rcx, [rbp+arg_8]
0x180009a71  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180009a76  jmp     short loc_180009AE3
0x180009a78  cmp     [rbp+arg_0], r14
0x180009a7c  jz      short loc_180009A8A
0x180009a7e  mov     rdx, r14; struct IUnknown *
0x180009a81  lea     rcx, [rbp+arg_0]; struct IUnknown **
0x180009a85  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180009a8a  lea     rdx, [rdi+8]; struct IUnknown *
0x180009a8e  cmp     [rsi], rdx
0x180009a91  jz      short loc_180009A9B
0x180009a93  mov     rcx, rsi; struct IUnknown **
0x180009a96  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180009a9b  lea     rcx, [rbp+arg_8]
0x180009a9f  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180009aa4  jmp     short loc_180009AC0
0x180009aa6  lea     rax, [rbx+8]
0x180009aaa  neg     rbx
0x180009aad  sbb     rdx, rdx
0x180009ab0  and     rdx, rax; struct IUnknown *
0x180009ab3  cmp     [rsi], rdx
0x180009ab6  jz      short loc_180009AC0
0x180009ab8  mov     rcx, rsi; struct IUnknown **
0x180009abb  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180009ac0  mov     rdx, [rbp+arg_10]
0x180009ac4  mov     rcx, [rbp+arg_0]
0x180009ac8  lea     rax, [rdx-8]
0x180009acc  neg     rdx
0x180009acf  mov     r8, [rcx]
0x180009ad2  sbb     rdx, rdx
0x180009ad5  and     rdx, rax
0x180009ad8  mov     rax, [r8+18h]
0x180009adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ae1  mov     ebx, eax
0x180009ae3  lea     rcx, [rbp+arg_0]
0x180009ae7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009aec  lea     rcx, [rbp+var_18]
0x180009af0  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180009af5  lea     rcx, [rbp+arg_10]
0x180009af9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009afe  lea     rcx, [rbp+arg_18]
0x180009b02  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009b07  mov     eax, ebx
0x180009b09  add     rsp, 38h
0x180009b0d  pop     r15
0x180009b0f  pop     r14
0x180009b11  pop     rdi
0x180009b12  pop     rsi
0x180009b13  pop     rbx
0x180009b14  pop     rbp
0x180009b15  retn
```
