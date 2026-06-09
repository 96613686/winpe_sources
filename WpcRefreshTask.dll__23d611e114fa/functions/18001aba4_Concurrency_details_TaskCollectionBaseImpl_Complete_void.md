# Concurrency::details::_TaskCollectionBaseImpl::_Complete(void)

- ea: `0x18001aba4`
- end: `0x18001ac1e`
- name: `?_Complete@_TaskCollectionBaseImpl@details@Concurrency@@QEAAXXZ`
- size: `122`
- prototype: `void __fastcall(_Cnd_t this)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a6f0`
- `0x18001c070`
- `0x180031220`
- `0x180031a4c`
- `0x18005eff0`
- `0x18005fb98`

## callees

- `0x18001aba4`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001ac17`
- `msvcp_win!_Mtx_lock` at `0x18001abb5`
- `msvcp_win!_Mtx_lock` at `0x18001abb5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001abc4`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001abe6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001abc4`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001abe6`
- `msvcp_win!_Cnd_broadcast` at `0x18001ac03`
- `msvcp_win!_Cnd_broadcast` at `0x18001ac03`

## pseudocode

```c

```
