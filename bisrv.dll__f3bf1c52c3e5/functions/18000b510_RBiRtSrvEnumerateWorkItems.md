# RBiRtSrvEnumerateWorkItems

- ea: `0x18000b510`
- end: `0x18000b7a0`
- name: `RBiRtSrvEnumerateWorkItems`
- size: `656`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000a960`
- `0x18000b0e0`
- `0x18000b510`
- `0x18000c928`
- `0x18000d560`
- `0x18004df58`
- `0x180094662`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlWaitOnAddress` at `0x18000b718`
- `ntdll!RtlWaitOnAddress` at `0x18000b718`
- `ntdll!RtlFreeHeap` at `0x18000b6c3`
- `ntdll!RtlFreeHeap` at `0x18000b6c3`
- `ntdll!RtlAllocateHeap` at `0x18000b68a`
- `ntdll!RtlAllocateHeap` at `0x18000b68a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000b6cb`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000b6cb`
- `RPCRT4!RpcRevertToSelf` at `0x18000b59d`
- `RPCRT4!RpcRevertToSelf` at `0x18000b59d`
- `RPCRT4!RpcImpersonateClient` at `0x18000b567`
- `RPCRT4!RpcImpersonateClient` at `0x18000b567`

## pseudocode

```c

```
