# std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>::~unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>(void)

- ea: `0x18000cbe4`
- end: `0x18000cc0e`
- name: `??1?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@@std@@@std@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180011571`

## callees

- `0x180002534`
- `0x18000cbe4`

## pseudocode

```c
void __fastcall std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>::~unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  void *v2; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v2 = (void *)v1[2];
    if ( v2 )
      operator delete(v2);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000cbe4  push    rbx
0x18000cbe6  sub     rsp, 20h
0x18000cbea  mov     rbx, [rcx]
0x18000cbed  test    rbx, rbx
0x18000cbf0  jz      short loc_18000CC08
0x18000cbf2  mov     rcx, [rbx+10h]; Block
0x18000cbf6  test    rcx, rcx
0x18000cbf9  jz      short loc_18000CC00
0x18000cbfb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cc00  mov     rcx, rbx; Block
0x18000cc03  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cc08  add     rsp, 20h
0x18000cc0c  pop     rbx
0x18000cc0d  retn
```
