# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180030d4c`
- end: `0x180030e13`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800313d0`

## callees

- `0x18001a25c`
- `0x1800298d0`
- `0x180030d4c`
- `0x180030f10`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030d81`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030d81`

## string_xrefs

- `0x180030dac`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
