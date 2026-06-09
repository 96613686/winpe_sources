# ContextNodeIterator::Reset(IXPathEvaluationContext *)

- ea: `0x18000ebb0`
- end: `0x18000ec39`
- name: `?Reset@ContextNodeIterator@@UEAAJPEAUIXPathEvaluationContext@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(ContextNodeIterator *__hidden this, struct IXPathEvaluationContext *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800021a4`
- `0x18000ebb0`
- `0x18000ee94`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ContextNodeIterator::Reset(ContextNodeIterator *this, struct IXPathEvaluationContext *a2)
{
  int v3; // ebx
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF
  struct IXPathNavigator *v6; // [rsp+40h] [rbp+18h] BYREF

  v5 = 0;
  v3 = (*(__int64 (__fastcall **)(struct IXPathEvaluationContext *, __int64 *))(*(_QWORD *)a2 + 24LL))(a2, &v5);
  if ( v3 >= 0 )
  {
    v6 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, struct IXPathNavigator **))(*(_QWORD *)v5 + 88LL))(v5, &v6);
    if ( v3 >= 0 )
    {
      SingletonIteratorBase::ResetWithContextNode(this, v6);
      v3 = 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v6);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000ebb0  mov     [rsp+arg_0], rbx
0x18000ebb5  push    rdi
0x18000ebb6  sub     rsp, 20h
0x18000ebba  mov     r8, rdx
0x18000ebbd  mov     rdi, rcx
0x18000ebc0  mov     [rsp+28h+arg_8], 0
0x18000ebc9  mov     rax, [rdx]
0x18000ebcc  lea     rdx, [rsp+28h+arg_8]
0x18000ebd1  mov     rcx, r8
0x18000ebd4  mov     rax, [rax+18h]
0x18000ebd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebdd  mov     ebx, eax
0x18000ebdf  test    eax, eax
0x18000ebe1  js      short loc_18000EC22
0x18000ebe3  mov     [rsp+28h+arg_10], 0
0x18000ebec  mov     rcx, [rsp+28h+arg_8]
0x18000ebf1  mov     rax, [rcx]
0x18000ebf4  lea     rdx, [rsp+28h+arg_10]
0x18000ebf9  mov     rax, [rax+58h]
0x18000ebfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec02  mov     ebx, eax
0x18000ec04  test    eax, eax
0x18000ec06  js      short loc_18000EC17
0x18000ec08  mov     rdx, [rsp+28h+arg_10]; struct IXPathNavigator *
0x18000ec0d  mov     rcx, rdi; this
0x18000ec10  call    ?ResetWithContextNode@SingletonIteratorBase@@IEAAJPEAUIXPathNavigator@@@Z; SingletonIteratorBase::ResetWithContextNode(IXPathNavigator *)
0x18000ec15  xor     ebx, ebx
0x18000ec17  lea     rcx, [rsp+28h+arg_10]
0x18000ec1c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ec21  nop
0x18000ec22  lea     rcx, [rsp+28h+arg_8]
0x18000ec27  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ec2c  mov     eax, ebx
0x18000ec2e  mov     rbx, [rsp+28h+arg_0]
0x18000ec33  add     rsp, 20h
0x18000ec37  pop     rdi
0x18000ec38  retn
```
