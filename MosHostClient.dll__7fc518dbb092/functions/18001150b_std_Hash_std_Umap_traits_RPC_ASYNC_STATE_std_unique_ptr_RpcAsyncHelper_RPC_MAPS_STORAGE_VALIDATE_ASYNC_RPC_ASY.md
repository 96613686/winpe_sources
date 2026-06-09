# _std::_Hash_std::_Umap_traits__RPC_ASYNC_STATE___std::unique_ptr_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA____std::_Uhash_compare__RPC_ASYNC_STATE___std::hash__RPC_ASYNC_STATE____std::equal_to__RPC_ASYNC_STATE______std::allocator_std::pair__RPC_ASYNC_STATE___const_std::unique_ptr_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA________0___::_Try_emplace__RPC_ASYNC_STATE____::_1_::dtor$0

- ea: `0x18001150b`
- end: `0x180011517`
- name: `_std::_Hash_std::_Umap_traits__RPC_ASYNC_STATE___std::unique_ptr_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA____std::_Uhash_compare__RPC_ASYNC_STATE___std::hash__RPC_ASYNC_STATE____std::equal_to__RPC_ASYNC_STATE______std::allocator_std::pair__RPC_ASYNC_STATE___const_std::unique_ptr_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA________0___::_Try_emplace__RPC_ASYNC_STATE____::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000cb14`

## pseudocode

```c
void __fastcall std::_Hash_std::_Umap_traits__RPC_ASYNC_STATE___std::unique_ptr_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA____std::_Uhash_compare__RPC_ASYNC_STATE___std::hash__RPC_ASYNC_STATE____std::equal_to__RPC_ASYNC_STATE______std::allocator_std::pair__RPC_ASYNC_STATE___const_std::unique_ptr_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA________0___::_Try_emplace__RPC_ASYNC_STATE____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x18001150b  lea     rcx, [rdx+20h]
0x180011512  jmp     ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>(void)
```
