# Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ImpersonateUser(void)

- ea: `0x18003c078`
- end: `0x18003c13a`
- name: `?ImpersonateUser@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@AEAA_NXZ`
- size: `194`
- prototype: `bool __fastcall(_Mtx_t this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003ba48`
- `0x18003c40c`
- `0x18003c73c`

## callees

- `0x18003c078`
- `0x18004b640`

## import_xrefs

- `ole32!CoGetCallContext` at `0x18003c0d9`
- `ole32!CoGetCallContext` at `0x18003c0d9`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003c0a6`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003c0c2`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003c0a6`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003c0c2`
- `MSVCP140!_Mtx_lock` at `0x18003c097`
- `MSVCP140!_Mtx_lock` at `0x18003c097`
- `MSVCP140!_Mtx_unlock` at `0x18003c0e6`
- `MSVCP140!_Mtx_unlock` at `0x18003c0f3`
- `MSVCP140!_Mtx_unlock` at `0x18003c0e6`
- `MSVCP140!_Mtx_unlock` at `0x18003c0f3`

## pseudocode

```c

```
