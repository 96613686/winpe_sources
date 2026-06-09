# CSerialWorkQueue::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180046b40`
- end: `0x180046c2f`
- name: `?WorkCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `239`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180046b40`
- `0x1800cdd70`
- `0x18016c010`

## import_xrefs

- `msvcp_win!_Mtx_lock` at `0x180046b5f`
- `msvcp_win!_Mtx_lock` at `0x180046b5f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180046c0e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180046c21`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180046c0e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180046c21`
- `msvcp_win!_Mtx_unlock` at `0x180046ba3`
- `msvcp_win!_Mtx_unlock` at `0x180046ba3`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180046c28`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180046c28`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180046c02`

## pseudocode

```c

```
