# std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>(void)

- ea: `0x18000cb14`
- end: `0x18000cb67`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `83`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001150b`

## callees

- `0x180002534`
- `0x1800029b4`
- `0x18000cb14`

## pseudocode

```c
void __fastcall std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rbx
  _QWORD *v3; // rbx
  void *v4; // rcx
  void *v5; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    v3 = *(_QWORD **)(v1 + 24);
    if ( v3 )
    {
      v4 = (void *)v3[2];
      if ( v4 )
        operator delete(v4);
      operator delete(v3);
    }
  }
  v5 = *(void **)(a1 + 8);
  if ( v5 )
    operator delete(v5);
}

```

## disassembly

```asm
0x18000cb14  mov     [rsp+arg_0], rbx
0x18000cb19  push    rdi
0x18000cb1a  sub     rsp, 20h
0x18000cb1e  mov     rbx, [rcx+8]
0x18000cb22  mov     rdi, rcx
0x18000cb25  test    rbx, rbx
0x18000cb28  jz      short loc_18000CB49
0x18000cb2a  mov     rbx, [rbx+18h]
0x18000cb2e  test    rbx, rbx
0x18000cb31  jz      short loc_18000CB49
0x18000cb33  mov     rcx, [rbx+10h]; Block
0x18000cb37  test    rcx, rcx
0x18000cb3a  jz      short loc_18000CB41
0x18000cb3c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cb41  mov     rcx, rbx; Block
0x18000cb44  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cb49  mov     rcx, [rdi+8]; Block
0x18000cb4d  test    rcx, rcx
0x18000cb50  jz      short loc_18000CB5C
0x18000cb52  mov     edx, 20h ; ' '
0x18000cb57  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cb5c  mov     rbx, [rsp+28h+arg_0]
0x18000cb61  add     rsp, 20h
0x18000cb65  pop     rdi
0x18000cb66  retn
```
