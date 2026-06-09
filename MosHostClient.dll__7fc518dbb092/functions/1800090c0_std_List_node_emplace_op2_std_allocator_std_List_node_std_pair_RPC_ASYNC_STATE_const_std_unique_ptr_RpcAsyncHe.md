# std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>(void)

- ea: `0x1800090c0`
- end: `0x180009143`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `131`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000819c`
- `0x1800112b9`

## callees

- `0x180002534`
- `0x1800029b4`
- `0x1800090c0`
- `0x180012010`

## pseudocode

```c
void __fastcall std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rdi
  _QWORD *v4; // rdi
  _QWORD *v5; // rbx
  _QWORD *v6; // rcx
  void *v7; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
  {
    v4 = *(_QWORD **)(v2 + 24);
    if ( v4 )
    {
      v5 = (_QWORD *)v4[2];
      if ( v5 )
      {
        v6 = (_QWORD *)v5[7];
        if ( v6 )
        {
          LOBYTE(a2) = v6 != v5;
          (*(void (__fastcall **)(_QWORD *, __int64))(*v6 + 32LL))(v6, a2);
          v5[7] = 0;
        }
        operator delete(v5);
      }
      operator delete(v4);
    }
  }
  v7 = *(void **)(a1 + 8);
  if ( v7 )
    operator delete(v7);
}

```

## disassembly

```asm
0x1800090c0  mov     [rsp+arg_0], rbx
0x1800090c5  mov     [rsp+arg_8], rsi
0x1800090ca  push    rdi
0x1800090cb  sub     rsp, 20h
0x1800090cf  mov     rdi, [rcx+8]
0x1800090d3  mov     rsi, rcx
0x1800090d6  test    rdi, rdi
0x1800090d9  jz      short loc_180009120
0x1800090db  mov     rdi, [rdi+18h]
0x1800090df  test    rdi, rdi
0x1800090e2  jz      short loc_180009120
0x1800090e4  mov     rbx, [rdi+10h]
0x1800090e8  test    rbx, rbx
0x1800090eb  jz      short loc_180009118
0x1800090ed  mov     rcx, [rbx+38h]
0x1800090f1  test    rcx, rcx
0x1800090f4  jz      short loc_180009110
0x1800090f6  mov     rax, [rcx]
0x1800090f9  cmp     rcx, rbx
0x1800090fc  setnz   dl
0x1800090ff  mov     rax, [rax+20h]
0x180009103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009108  mov     qword ptr [rbx+38h], 0
0x180009110  mov     rcx, rbx; Block
0x180009113  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009118  mov     rcx, rdi; Block
0x18000911b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009120  mov     rcx, [rsi+8]; Block
0x180009124  test    rcx, rcx
0x180009127  jz      short loc_180009133
0x180009129  mov     edx, 20h ; ' '
0x18000912e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009133  mov     rbx, [rsp+28h+arg_0]
0x180009138  mov     rsi, [rsp+28h+arg_8]
0x18000913d  add     rsp, 20h
0x180009141  pop     rdi
0x180009142  retn
```
