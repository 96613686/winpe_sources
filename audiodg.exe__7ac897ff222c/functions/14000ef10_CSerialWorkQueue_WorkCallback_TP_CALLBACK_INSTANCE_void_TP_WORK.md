# CSerialWorkQueue::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x14000ef10`
- end: `0x14000efbf`
- name: `?WorkCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `175`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000ef10`
- `0x14000f36c`
- `0x14005d4ac`
- `0x1400b5010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x14000ef66`
- `msvcp_win!_Mtx_unlock` at `0x14000ef66`
- `msvcp_win!_Mtx_lock` at `0x14000ef2f`
- `msvcp_win!_Mtx_lock` at `0x14000ef2f`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14000efb8`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14000efb8`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14000ef9e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14000efb1`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14000ef9e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14000efb1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x14000ef92`

## pseudocode

```c

```
