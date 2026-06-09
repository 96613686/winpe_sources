# NgcUtils::ProcessPriorityManager::ResetPriorityCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180020720`
- end: `0x1800207ae`
- name: `?ResetPriorityCallback@ProcessPriorityManager@NgcUtils@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `142`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180018194`
- `0x180018c44`
- `0x180020720`
- `0x18003b650`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180020746`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180020746`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020735`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020735`

## string_xrefs

- `0x18002075b`: `onecore\ds\security\ngc\utils\common\lib\processutils.cpp`

## pseudocode

```c

```
