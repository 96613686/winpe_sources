# WUComTimeout::ComTimeout::s_TimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x140044940`
- end: `0x14004498b`
- name: `?s_TimerCallback@ComTimeout@WUComTimeout@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `75`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400154b4`
- `0x140044940`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCancelCall` at `0x140044952`
- `api-ms-win-core-com-l1-1-0!CoCancelCall` at `0x140044952`

## string_xrefs

- `0x14004495e`: `ComTimeout::s_TimerCallback was not able to cancel the COM call`

## pseudocode

```c

```
