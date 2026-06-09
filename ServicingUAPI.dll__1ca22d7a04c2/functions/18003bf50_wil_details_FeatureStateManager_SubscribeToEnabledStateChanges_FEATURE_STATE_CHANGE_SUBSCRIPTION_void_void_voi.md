# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18003bf50`
- end: `0x18003c05c`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `268`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18003c630`

## callees

- `0x18003bf50`
- `0x18003c188`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003bfe9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003bfe9`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18003bfcc`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18003bfcc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bf8d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bf8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c03b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c03b`

## string_xrefs

- `0x18003bfc5`: `ntdll.dll`
- `0x18003bfdf`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
