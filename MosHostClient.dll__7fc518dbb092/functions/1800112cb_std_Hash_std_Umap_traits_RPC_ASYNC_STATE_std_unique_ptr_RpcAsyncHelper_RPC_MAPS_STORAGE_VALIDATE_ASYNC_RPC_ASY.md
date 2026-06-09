# _std::_Hash_std::_Umap_traits__RPC_ASYNC_STATE___std::unique_ptr_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA____std::_Uhash_compare__RPC_ASYNC_STATE___std::hash__RPC_ASYNC_STATE____std::equal_to__RPC_ASYNC_STATE______std::allocator_std::pair__RPC_ASYNC_STATE___const_std::unique_ptr_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA________0___::_Try_emplace__RPC_ASYNC_STATE____::_1_::dtor$1

- ea: `0x1800112cb`
- end: `0x1800112d7`
- name: `_std::_Hash_std::_Umap_traits__RPC_ASYNC_STATE___std::unique_ptr_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA____std::_Uhash_compare__RPC_ASYNC_STATE___std::hash__RPC_ASYNC_STATE____std::equal_to__RPC_ASYNC_STATE______std::allocator_std::pair__RPC_ASYNC_STATE___const_std::unique_ptr_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA________0___::_Try_emplace__RPC_ASYNC_STATE____::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008ff4`

## pseudocode

```c
void __fastcall std::_Hash_std::_Umap_traits__RPC_ASYNC_STATE___std::unique_ptr_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA____std::_Uhash_compare__RPC_ASYNC_STATE___std::hash__RPC_ASYNC_STATE____std::equal_to__RPC_ASYNC_STATE______std::allocator_std::pair__RPC_ASYNC_STATE___const_std::unique_ptr_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA_std::default_delete_RpcAsyncHelper_RPC_MAPS_STORAGE_VALIDATE_ASYNC_::RPC_ASYNC_STATE_DATA________0___::_Try_emplace__RPC_ASYNC_STATE____::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x1800112cb  lea     rcx, [rdx+20h]
0x1800112d2  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>(void)
```
