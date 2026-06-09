# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000e130`
- end: `0x18000e23d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000d7cc`
- `0x18000d8c8`
- `0x18000e130`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e1d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e1d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e1ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e1ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e180`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e180`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e227`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e227`

## string_xrefs

- `0x18000e1b3`: `ntdll.dll`
- `0x18000e1c7`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
