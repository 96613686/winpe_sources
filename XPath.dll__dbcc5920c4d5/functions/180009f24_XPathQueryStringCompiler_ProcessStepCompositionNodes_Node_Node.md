# XPathQueryStringCompiler::ProcessStepCompositionNodes(Node *,Node *)

- ea: `0x180009f24`
- end: `0x18000a08b`
- name: `?ProcessStepCompositionNodes@XPathQueryStringCompiler@@AEAAJPEAVNode@@0@Z`
- size: `359`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *__hidden this, Node *, struct Node *)`
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001a70`
- `0x180001ec0`
- `0x180006db0`

## callees

- `0x180001078`
- `0x1800020b4`
- `0x1800063d4`
- `0x180007f5c`
- `0x18000835c`
- `0x180008bdc`
- `0x180009f24`
- `0x18000a3a8`
- `0x18000f690`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessStepCompositionNodes(
        XPathQueryStringCompiler *this,
        Node *a2,
        struct Node *a3)
{
  _QWORD *v3; // rsi
  int v7; // ebx
  unsigned int Length; // ebx
  unsigned int v9; // eax
  int v10; // eax
  StepCompositionIterator *v11; // r10
  struct XPathNodeIteratorBase *v12; // r8
  struct XPathNodeIteratorBase *v13; // rdx
  StepCompositionIterator *v14; // rcx
  __int64 v16; // [rsp+40h] [rbp+8h] BYREF
  XPathExpressionBase *v17; // [rsp+58h] [rbp+20h] BYREF

  v3 = (_QWORD *)*((_QWORD *)this + 5);
  v17 = 0;
  *((_QWORD *)this + 5) = &v17;
  *((_DWORD *)this + 12) = 5;
  v7 = XPathQueryStringCompiler::Dispatch(this, a2);
  if ( v7 >= 0 )
  {
    if ( XPathExpressionBase::IsNodeSet(v17) )
    {
      v16 = 0;
      *((_QWORD *)this + 5) = &v16;
      *((_DWORD *)this + 12) = 5;
      v7 = XPathQueryStringCompiler::Dispatch(this, a3);
      if ( v7 >= 0 )
      {
        v11 = (StepCompositionIterator *)operator new(0x38u);
        if ( v11 )
        {
          if ( v16 )
            v12 = (struct XPathNodeIteratorBase *)(v16 - 8);
          else
            v12 = 0;
          if ( v17 )
            v13 = (XPathExpressionBase *)((char *)v17 - 8);
          else
            v13 = 0;
          v14 = StepCompositionIterator::StepCompositionIterator(v11, v13, v12, 1);
        }
        else
        {
          v14 = 0;
        }
        ATL::CComPtrBase<StepCompositionIterator>::Attach(v3, ((unsigned __int64)v14 + 8) & -(__int64)(v14 != 0));
        if ( *v3 )
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
          v7 = 0;
        }
        else
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
          v7 = -2147024882;
        }
      }
      else
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
      }
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
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009f24  mov     rax, rsp
0x180009f27  mov     [rax+10h], rbx
0x180009f2b  mov     [rax+18h], rbp
0x180009f2f  push    rsi
0x180009f30  push    rdi
0x180009f31  push    r14
0x180009f33  sub     rsp, 20h
0x180009f37  mov     rsi, [rcx+28h]
0x180009f3b  mov     rbp, r8
0x180009f3e  mov     qword ptr [rax+20h], 0
0x180009f46  lea     rax, [rax+20h]
0x180009f4a  mov     [rcx+28h], rax
0x180009f4e  mov     r14, rdx
0x180009f51  mov     rdi, rcx
0x180009f54  mov     dword ptr [rcx+30h], 5
0x180009f5b  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x180009f60  mov     ebx, eax
0x180009f62  test    eax, eax
0x180009f64  js      loc_18000A06C
0x180009f6a  mov     rcx, [rsp+38h+arg_18]; this
0x180009f6f  call    ?IsNodeSet@XPathExpressionBase@@QEAA_NXZ; XPathExpressionBase::IsNodeSet(void)
0x180009f74  test    al, al
0x180009f76  jnz     short loc_180009FBA
0x180009f78  mov     rcx, r14; this
0x180009f7b  call    ?GetLength@Node@@QEAAKXZ; Node::GetLength(void)
0x180009f80  mov     rcx, [r14]
0x180009f83  mov     ebx, eax
0x180009f85  mov     rax, [rcx+10h]
0x180009f89  mov     rcx, r14
0x180009f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f91  lea     rcx, [rdi+10h]; struct String *
0x180009f95  mov     r9d, 6Ch ; 'l'; unsigned int
0x180009f9b  mov     r8d, ebx; unsigned int
0x180009f9e  mov     edx, eax; unsigned int
0x180009fa0  call    ?SetCompilationException@ExceptionHelpers@@SAJAEAVString@@KKI@Z; ExceptionHelpers::SetCompilationException(String &,ulong,ulong,uint)
0x180009fa5  test    eax, eax
0x180009fa7  jns     short loc_180009FB0
0x180009fa9  mov     ebx, eax
0x180009fab  jmp     loc_18000A06C
0x180009fb0  mov     ebx, 80070057h
0x180009fb5  jmp     loc_18000A06C
0x180009fba  lea     rax, [rsp+38h+arg_0]
0x180009fbf  mov     [rsp+38h+arg_0], 0
0x180009fc8  mov     rdx, rbp; struct Node *
0x180009fcb  mov     [rdi+28h], rax
0x180009fcf  mov     rcx, rdi; this
0x180009fd2  mov     dword ptr [rdi+30h], 5
0x180009fd9  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x180009fde  mov     ebx, eax
0x180009fe0  test    eax, eax
0x180009fe2  jns     short loc_180009FF0
0x180009fe4  lea     rcx, [rsp+38h+arg_0]
0x180009fe9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009fee  jmp     short loc_18000A06C
0x180009ff0  mov     ecx, 38h ; '8'; Size
0x180009ff5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009ffa  mov     r10, rax
0x180009ffd  test    rax, rax
0x18000a000  jz      short loc_18000A037
0x18000a002  mov     rcx, [rsp+38h+arg_0]
0x18000a007  test    rcx, rcx
0x18000a00a  jz      short loc_18000A012
0x18000a00c  lea     r8, [rcx-8]
0x18000a010  jmp     short loc_18000A015
0x18000a012  xor     r8d, r8d; struct XPathNodeIteratorBase *
0x18000a015  mov     rax, [rsp+38h+arg_18]
0x18000a01a  test    rax, rax
0x18000a01d  jz      short loc_18000A025
0x18000a01f  lea     rdx, [rax-8]
0x18000a023  jmp     short loc_18000A027
0x18000a025  xor     edx, edx; struct XPathNodeIteratorBase *
0x18000a027  mov     r9b, 1; bool
0x18000a02a  mov     rcx, r10; this
0x18000a02d  call    ??0StepCompositionIterator@@QEAA@PEAVXPathNodeIteratorBase@@0_N@Z; StepCompositionIterator::StepCompositionIterator(XPathNodeIteratorBase *,XPathNodeIteratorBase *,bool)
0x18000a032  mov     rcx, rax
0x18000a035  jmp     short loc_18000A039
0x18000a037  xor     ecx, ecx
0x18000a039  lea     rax, [rcx+8]
0x18000a03d  neg     rcx
0x18000a040  mov     rcx, rsi
0x18000a043  sbb     rdx, rdx
0x18000a046  and     rdx, rax
0x18000a049  call    ?Attach@?$CComPtrBase@VStepCompositionIterator@@@ATL@@QEAAXPEAVStepCompositionIterator@@@Z; ATL::CComPtrBase<StepCompositionIterator>::Attach(StepCompositionIterator *)
0x18000a04e  cmp     qword ptr [rsi], 0
0x18000a052  lea     rcx, [rsp+38h+arg_0]
0x18000a057  jnz     short loc_18000A065
0x18000a059  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a05e  mov     ebx, 8007000Eh
0x18000a063  jmp     short loc_18000A06C
0x18000a065  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a06a  xor     ebx, ebx
0x18000a06c  lea     rcx, [rsp+38h+arg_18]
0x18000a071  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a076  mov     rbp, [rsp+38h+arg_10]
0x18000a07b  mov     eax, ebx
0x18000a07d  mov     rbx, [rsp+38h+arg_8]
0x18000a082  add     rsp, 20h
0x18000a086  pop     r14
0x18000a088  pop     rdi
0x18000a089  pop     rsi
0x18000a08a  retn
```
