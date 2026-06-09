# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000d73c`
- end: `0x18000d834`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e4e0`

## callees

- `0x18000d73c`
- `0x18000d950`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d7c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d7c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d7ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d7ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d81a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d81a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d76c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d76c`

## string_xrefs

- `0x18000d7a4`: `ntdll.dll`
- `0x18000d7be`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
