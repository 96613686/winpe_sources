# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180034670`
- end: `0x18003476e`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `254`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800328bc`
- `0x1800329c0`
- `0x180034670`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800346b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800346b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180034760`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180034760`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800346f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800346f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003470a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003470a`

## string_xrefs

- `0x1800346ec`: `ntdll.dll`
- `0x180034700`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
