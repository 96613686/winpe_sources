# RBiPtSrvQueryBrokeredEvent

- ea: `0x18000af90`
- end: `0x18000b0d5`
- name: `RBiPtSrvQueryBrokeredEvent`
- size: `325`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, void *Source1)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000ac6c`
- `0x18000af90`
- `0x18000c928`
- `0x180094662`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000b09f`
- `ntdll!RtlFreeHeap` at `0x18000b09f`
- `ntdll!RtlAllocateHeap` at `0x18000b06f`
- `ntdll!RtlAllocateHeap` at `0x18000b06f`
- `RPCRT4!RpcRevertToSelf` at `0x18000b01b`
- `RPCRT4!RpcRevertToSelf` at `0x18000b01b`
- `RPCRT4!RpcImpersonateClient` at `0x18000afe2`
- `RPCRT4!RpcImpersonateClient` at `0x18000afe2`

## pseudocode

```c

```
