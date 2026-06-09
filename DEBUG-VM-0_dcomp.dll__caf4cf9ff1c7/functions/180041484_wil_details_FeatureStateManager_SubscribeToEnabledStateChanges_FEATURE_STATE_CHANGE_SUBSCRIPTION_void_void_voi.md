# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180041484`
- end: `0x180041548`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `196`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180041450`

## callees

- `0x180041484`
- `0x180041598`
- `0x1800420a4`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800414e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800414e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800414b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800414b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004152e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004152e`

## string_xrefs

- `0x1800414e2`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
