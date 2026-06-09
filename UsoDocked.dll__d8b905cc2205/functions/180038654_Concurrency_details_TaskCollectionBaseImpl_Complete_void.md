# Concurrency::details::_TaskCollectionBaseImpl::_Complete(void)

- ea: `0x180038654`
- end: `0x1800386ce`
- name: `?_Complete@_TaskCollectionBaseImpl@details@Concurrency@@QEAAXXZ`
- size: `122`
- prototype: `void __fastcall(_Cnd_t this)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037ed0`
- `0x1800380c0`
- `0x180039300`
- `0x180039394`

## callees

- `0x180038654`

## import_xrefs

- `msvcp_win!_Cnd_broadcast` at `0x1800386b3`
- `msvcp_win!_Cnd_broadcast` at `0x1800386b3`
- `msvcp_win!_Mtx_unlock` at `0x1800386c7`
- `msvcp_win!_Mtx_lock` at `0x180038665`
- `msvcp_win!_Mtx_lock` at `0x180038665`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180038674`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180038696`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180038674`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180038696`

## pseudocode

```c

```
