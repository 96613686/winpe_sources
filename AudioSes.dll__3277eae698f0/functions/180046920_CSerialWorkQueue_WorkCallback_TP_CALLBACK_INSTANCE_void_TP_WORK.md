# CSerialWorkQueue::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180046920`
- end: `0x1800469ab`
- name: `?WorkCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `139`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180046920`
- `0x1800469b4`
- `0x1800469e8`
- `0x1800d58b0`

## import_xrefs

- `msvcp_win!_Mtx_lock` at `0x18004693f`
- `msvcp_win!_Mtx_lock` at `0x18004693f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180046991`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800469a4`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180046991`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800469a4`
- `msvcp_win!_Mtx_unlock` at `0x180046962`
- `msvcp_win!_Mtx_unlock` at `0x180046962`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004697b`

## pseudocode

```c

```
