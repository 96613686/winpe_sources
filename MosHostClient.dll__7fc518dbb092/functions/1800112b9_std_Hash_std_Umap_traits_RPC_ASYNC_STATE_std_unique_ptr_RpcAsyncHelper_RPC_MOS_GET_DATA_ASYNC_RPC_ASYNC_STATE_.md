# _std::_Hash_std::_Umap_traits__RPC_ASYNC_STATE___std::unique_ptr_RpcAsyncHelper_RPC_MOS_GET_DATA_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MOS_GET_DATA_ASYNC_::RPC_ASYNC_STATE_DATA____std::_Uhash_compare__RPC_ASYNC_STATE___std::hash__RPC_ASYNC_STATE____std::equal_to__RPC_ASYNC_STATE______std::allocator_std::pair__RPC_ASYNC_STATE___const_std::unique_ptr_RpcAsyncHelper_RPC_MOS_GET_DATA_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MOS_GET_DATA_ASYNC_::RPC_ASYNC_STATE_DATA________0___::_Try_emplace__RPC_ASYNC_STATE____::_1_::dtor$0

- ea: `0x1800112b9`
- end: `0x1800112c5`
- name: `_std::_Hash_std::_Umap_traits__RPC_ASYNC_STATE___std::unique_ptr_RpcAsyncHelper_RPC_MOS_GET_DATA_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MOS_GET_DATA_ASYNC_::RPC_ASYNC_STATE_DATA____std::_Uhash_compare__RPC_ASYNC_STATE___std::hash__RPC_ASYNC_STATE____std::equal_to__RPC_ASYNC_STATE______std::allocator_std::pair__RPC_ASYNC_STATE___const_std::unique_ptr_RpcAsyncHelper_RPC_MOS_GET_DATA_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MOS_GET_DATA_ASYNC_::RPC_ASYNC_STATE_DATA________0___::_Try_emplace__RPC_ASYNC_STATE____::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800090c0`

## pseudocode

```c
void __fastcall std::_Hash_std::_Umap_traits__RPC_ASYNC_STATE___std::unique_ptr_RpcAsyncHelper_RPC_MOS_GET_DATA_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MOS_GET_DATA_ASYNC_::RPC_ASYNC_STATE_DATA____std::_Uhash_compare__RPC_ASYNC_STATE___std::hash__RPC_ASYNC_STATE____std::equal_to__RPC_ASYNC_STATE______std::allocator_std::pair__RPC_ASYNC_STATE___const_std::unique_ptr_RpcAsyncHelper_RPC_MOS_GET_DATA_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MOS_GET_DATA_ASYNC_::RPC_ASYNC_STATE_DATA________0___::_Try_emplace__RPC_ASYNC_STATE____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>(
    a2 + 32,
    a2);
}

```

## disassembly

```asm
0x1800112b9  lea     rcx, [rdx+20h]
0x1800112c0  jmp     ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>(void)
```
