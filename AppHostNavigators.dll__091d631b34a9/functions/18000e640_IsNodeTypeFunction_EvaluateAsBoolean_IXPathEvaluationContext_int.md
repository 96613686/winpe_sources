# IsNodeTypeFunction::EvaluateAsBoolean(IXPathEvaluationContext *,int *)

- ea: `0x18000e640`
- end: `0x18000e71b`
- name: `?EvaluateAsBoolean@IsNodeTypeFunction@@UEAAJPEAUIXPathEvaluationContext@@PEAH@Z`
- size: `219`
- prototype: `__int64 __fastcall(IsNodeTypeFunction *__hidden this, struct IXPathEvaluationContext *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800021a4`
- `0x18000e640`
- `0x180012ea8`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IsNodeTypeFunction::EvaluateAsBoolean(
        IsNodeTypeFunction *this,
        struct IXPathEvaluationContext *a2,
        int *a3)
{
  int v5; // edi
  int v7; // ebx
  __int64 v8[2]; // [rsp+20h] [rbp-10h] BYREF
  __int64 v9; // [rsp+50h] [rbp+20h] BYREF
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp+38h] BYREF

  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, struct IXPathEvaluationContext *, __int64 *))(**((_QWORD **)this + 2) + 48LL))(
         *((_QWORD *)this + 2),
         a2,
         &v9);
  if ( v5 >= 0 )
  {
    v10 = 0;
    v7 = (*(__int64 (__fastcall **)(struct IXPathEvaluationContext *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a2 + 24LL))(
           a2,
           &v10);
    if ( v7 >= 0 )
    {
      v8[0] = 0;
      v7 = (**v10)(v10, &GUID_3d64cfe8_0c68_4dc1_b5ac_1ab4d6ce43c0, v8);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v8[0] + 80LL))(v8[0], v9, a3);
        if ( v7 >= 0 )
          v7 = 0;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v8);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v10);
    ScopedBSTR::Reset((ScopedBSTR *)&v9);
    return (unsigned int)v7;
  }
  else
  {
    ScopedBSTR::Reset((ScopedBSTR *)&v9);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x18000e640  mov     [rsp-18h+arg_8], rbx
0x18000e645  push    rbp
0x18000e646  push    rsi
0x18000e647  push    rdi
0x18000e648  mov     rbp, rsp
0x18000e64b  sub     rsp, 30h
0x18000e64f  mov     rsi, r8
0x18000e652  mov     rbx, rdx
0x18000e655  mov     [rbp+arg_0], 0
0x18000e65d  mov     rcx, [rcx+10h]
0x18000e661  mov     rax, [rcx]
0x18000e664  lea     r8, [rbp+arg_0]
0x18000e668  mov     rax, [rax+30h]
0x18000e66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e671  mov     edi, eax
0x18000e673  test    eax, eax
0x18000e675  jns     short loc_18000E687
0x18000e677  lea     rcx, [rbp+arg_0]; this
0x18000e67b  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000e680  mov     eax, edi
0x18000e682  jmp     loc_18000E70E
0x18000e687  mov     [rbp+arg_18], 0
0x18000e68f  mov     rax, [rbx]
0x18000e692  lea     rdx, [rbp+arg_18]
0x18000e696  mov     rcx, rbx
0x18000e699  mov     rax, [rax+18h]
0x18000e69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6a2  mov     ebx, eax
0x18000e6a4  test    eax, eax
0x18000e6a6  js      short loc_18000E6F9
0x18000e6a8  mov     [rbp+var_10], 0
0x18000e6b0  mov     rcx, [rbp+arg_18]
0x18000e6b4  mov     rax, [rcx]
0x18000e6b7  lea     r8, [rbp+var_10]
0x18000e6bb  lea     rdx, _GUID_3d64cfe8_0c68_4dc1_b5ac_1ab4d6ce43c0
0x18000e6c2  mov     rax, [rax]
0x18000e6c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6ca  mov     ebx, eax
0x18000e6cc  test    eax, eax
0x18000e6ce  js      short loc_18000E6EF
0x18000e6d0  mov     rcx, [rbp+var_10]
0x18000e6d4  mov     rax, [rcx]
0x18000e6d7  mov     r8, rsi
0x18000e6da  mov     rdx, [rbp+arg_0]
0x18000e6de  mov     rax, [rax+50h]
0x18000e6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6e7  mov     ebx, eax
0x18000e6e9  test    eax, eax
0x18000e6eb  js      short loc_18000E6EF
0x18000e6ed  xor     ebx, ebx
0x18000e6ef  lea     rcx, [rbp+var_10]
0x18000e6f3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e6f8  nop
0x18000e6f9  lea     rcx, [rbp+arg_18]
0x18000e6fd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e702  nop
0x18000e703  lea     rcx, [rbp+arg_0]; this
0x18000e707  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000e70c  mov     eax, ebx
0x18000e70e  mov     rbx, [rsp+30h+arg_8]
0x18000e713  add     rsp, 30h
0x18000e717  pop     rdi
0x18000e718  pop     rsi
0x18000e719  pop     rbp
0x18000e71a  retn
```
