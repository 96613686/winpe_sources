# _dynamic_initializer_for__g_mosDeleteDataAsyncHelper__

- ea: `0x180001dd0`
- end: `0x180001dfe`
- name: `_dynamic_initializer_for__g_mosDeleteDataAsyncHelper__`
- size: `46`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002900`
- `0x180008d44`

## pseudocode

```c
int dynamic_initializer_for__g_mosDeleteDataAsyncHelper__()
{
  RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>(
    qword_18001C7C0,
    DoDeleteDataAsync,
    OnMosGetDataAsyncComplete);
  return atexit(dynamic_atexit_destructor_for__g_mosDeleteDataAsyncHelper__);
}

```

## disassembly

```asm
0x180001dd0  sub     rsp, 28h
0x180001dd4  lea     r8, OnMosGetDataAsyncComplete
0x180001ddb  lea     rdx, DoDeleteDataAsync
0x180001de2  lea     rcx, qword_18001C7C0
0x180001de9  call    ??0?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@QEAA@P6AJPEAU_RPC_ASYNC_STATE@@PEAXPEAURPC_MOS_GET_DATA_ASYNC@@@ZP6AXJ_N2@Z@Z; RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>(long (*)(_RPC_ASYNC_STATE *,void *,RPC_MOS_GET_DATA_ASYNC *),void (*)(long,bool,RPC_MOS_GET_DATA_ASYNC *))
0x180001dee  lea     rcx, _dynamic_atexit_destructor_for__g_mosDeleteDataAsyncHelper__
0x180001df5  add     rsp, 28h
0x180001df9  jmp     atexit
```
