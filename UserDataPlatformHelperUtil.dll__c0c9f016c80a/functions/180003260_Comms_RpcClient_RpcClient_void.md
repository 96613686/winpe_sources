# Comms::RpcClient::~RpcClient(void)

- ea: `0x180003260`
- end: `0x180003265`
- name: `??1RpcClient@Comms@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(__int64 this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800031bc`

## pseudocode

```c
// attributes: thunk
void __fastcall Comms::RpcClient::~RpcClient(__int64 this)
{
  utl::vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>::~vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>(this);
}

```

## disassembly

```asm
0x180003260  jmp     ??1?$vector@UBinders@RpcClient@Comms@@V?$allocator@UBinders@RpcClient@Comms@@@utl@@@utl@@QEAA@XZ; utl::vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>::~vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>(void)
```
