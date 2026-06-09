# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000b6ec`
- end: `0x14000b7e4`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000c3c0`

## callees

- `0x14000b6ec`
- `0x14000b900`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b75b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b75b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b778`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b778`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b71c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b71c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b7ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b7ca`

## string_xrefs

- `0x14000b754`: `ntdll.dll`
- `0x14000b76e`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
