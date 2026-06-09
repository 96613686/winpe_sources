# std::unordered_map<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>::~unordered_map<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>(void)

- ea: `0x18000cc14`
- end: `0x18000cc34`
- name: `??1?$unordered_map@PEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@U?$hash@PEAU_RPC_ASYNC_STATE@@@3@U?$equal_to@PEAU_RPC_ASYNC_STATE@@@3@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@@std@@@3@@std@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18001151d`
- `0x1800115fc`
- `0x180011612`
- `0x18001163a`

## callees

- `0x180009050`
- `0x18000cb70`

## pseudocode

```c
void __fastcall std::unordered_map<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>::~unordered_map<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>(
        __int64 a1)
{
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>((char **)(a1 + 24));
  std::list<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>::~list<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>((void **)(a1 + 8));
}

```

## disassembly

```asm
0x18000cc14  push    rbx
0x18000cc16  sub     rsp, 20h
0x18000cc1a  mov     rbx, rcx
0x18000cc1d  add     rcx, 18h
0x18000cc21  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>(void)
0x18000cc26  lea     rcx, [rbx+8]
0x18000cc2a  add     rsp, 20h
0x18000cc2e  pop     rbx
0x18000cc2f  jmp     ??1?$list@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@@std@@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>::~list<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>(void)
```
