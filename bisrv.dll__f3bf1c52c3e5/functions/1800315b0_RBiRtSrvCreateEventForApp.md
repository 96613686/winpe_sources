# RBiRtSrvCreateEventForApp

- ea: `0x1800315b0`
- end: `0x1800317dc`
- name: `RBiRtSrvCreateEventForApp`
- size: `556`
- prototype: `__int64 __usercall@<rax>(RPC_BINDING_HANDLE BindingHandle@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000c928`
- `0x1800315b0`
- `0x1800317f0`
- `0x180031f20`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180031777`
- `ntdll!RtlFreeHeap` at `0x1800317bb`
- `ntdll!RtlFreeHeap` at `0x180031777`
- `ntdll!RtlFreeHeap` at `0x1800317bb`
- `ntdll!RtlAllocateHeap` at `0x1800317ce`
- `ntdll!RtlAllocateHeap` at `0x1800317ce`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180031610`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180031610`
- `RPCRT4!RpcRevertToSelf` at `0x180031693`
- `RPCRT4!RpcRevertToSelf` at `0x180031693`
- `RPCRT4!RpcImpersonateClient` at `0x180031660`
- `RPCRT4!RpcImpersonateClient` at `0x180031660`

## pseudocode

```c

```
