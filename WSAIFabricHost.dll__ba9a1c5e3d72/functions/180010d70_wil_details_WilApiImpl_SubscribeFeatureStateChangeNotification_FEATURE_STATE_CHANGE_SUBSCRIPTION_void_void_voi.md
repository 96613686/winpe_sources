# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180010d70`
- end: `0x180010e7d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180010898`
- `0x180010994`
- `0x180010d70`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010e11`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010e11`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010dfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010dfa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010dc0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010dc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010e67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010e67`

## string_xrefs

- `0x180010df3`: `ntdll.dll`
- `0x180010e07`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
