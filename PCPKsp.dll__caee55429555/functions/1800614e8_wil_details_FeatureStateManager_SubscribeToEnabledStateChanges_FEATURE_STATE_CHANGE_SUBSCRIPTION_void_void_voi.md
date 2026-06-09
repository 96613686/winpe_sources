# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800614e8`
- end: `0x1800615b0`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `200`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18005bbb0`

## callees

- `0x1800614e8`
- `0x1800615b8`
- `0x180079ef8`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061596`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061596`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180061518`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180061518`

## string_xrefs

- `0x180061544`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
