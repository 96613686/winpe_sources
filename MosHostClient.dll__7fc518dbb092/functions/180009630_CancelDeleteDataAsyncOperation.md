# CancelDeleteDataAsyncOperation

- ea: `0x180009630`
- end: `0x18000963f`
- name: `CancelDeleteDataAsyncOperation`
- size: `15`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800094c0`

## pseudocode

```c
__int64 __fastcall CancelDeleteDataAsyncOperation(__int64 a1)
{
  return RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::Cancel(qword_18001C7C0, a1);
}

```

## disassembly

```asm
0x180009630  mov     rdx, rcx
0x180009633  lea     rcx, qword_18001C7C0
0x18000963a  jmp     ?Cancel@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@QEAAJPEAU_RPC_ASYNC_STATE@@@Z; RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::Cancel(_RPC_ASYNC_STATE *)
```
