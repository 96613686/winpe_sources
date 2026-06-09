# ThreadSafeMap<_GUID,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>::RemoveValue(_GUID const &)

- ea: `0x1800065f8`
- end: `0x1800067f2`
- name: `?RemoveValue@?$ThreadSafeMap@U_GUID@@V?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@@QEAAXAEBU_GUID@@@Z`
- size: `506`
- prototype: `__int64 __fastcall(std::_Mutex_base *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ba00`

## callees

- `0x1800065f8`
- `0x1800067f8`
- `0x1800188ac`
- `0x180043a50`
- `0x180091010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800067ca`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800067d6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800067ca`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800067d6`
- `msvcp_win!_Mtx_lock` at `0x180006612`
- `msvcp_win!_Mtx_lock` at `0x180006612`
- `msvcp_win!_Mtx_unlock` at `0x18000674a`
- `msvcp_win!_Mtx_unlock` at `0x1800067ab`
- `msvcp_win!_Mtx_unlock` at `0x18000674a`
- `msvcp_win!_Mtx_unlock` at `0x1800067ab`

## pseudocode

```c

```
