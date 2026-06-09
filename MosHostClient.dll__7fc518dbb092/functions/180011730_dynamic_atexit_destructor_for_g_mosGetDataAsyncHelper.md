# _dynamic_atexit_destructor_for__g_mosGetDataAsyncHelper__

- ea: `0x180011730`
- end: `0x18001175d`
- name: `_dynamic_atexit_destructor_for__g_mosGetDataAsyncHelper__`
- size: `45`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009050`
- `0x18000914c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001173b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001173b`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_mosGetDataAsyncHelper__()
{
  DeleteCriticalSection(&stru_18001C890);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>((char **)qword_18001C868);
  std::list<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>::~list<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>((void **)qword_18001C858);
}

```

## disassembly

```asm
0x180011730  sub     rsp, 28h
0x180011734  lea     rcx, stru_18001C890; lpCriticalSection
0x18001173b  call    cs:__imp_DeleteCriticalSection
0x180011741  lea     rcx, qword_18001C868
0x180011748  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>(void)
0x18001174d  lea     rcx, qword_18001C858
0x180011754  add     rsp, 28h
0x180011758  jmp     ??1?$list@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@@std@@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>::~list<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>(void)
```
