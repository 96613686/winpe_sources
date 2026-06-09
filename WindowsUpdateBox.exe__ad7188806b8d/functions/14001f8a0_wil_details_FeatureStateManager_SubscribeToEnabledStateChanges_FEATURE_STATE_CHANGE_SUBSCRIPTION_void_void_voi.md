# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14001f8a0`
- end: `0x14001f9af`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `271`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140020b80`

## callees

- `0x14001f8a0`
- `0x14001fae4`
- `0x140082010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14001f91a`
- `KERNEL32!GetModuleHandleW` at `0x14001f91a`
- `KERNEL32!GetProcAddress` at `0x14001f937`
- `KERNEL32!GetProcAddress` at `0x14001f937`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001f8db`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001f8db`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001f989`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001f989`

## string_xrefs

- `0x14001f913`: `ntdll.dll`
- `0x14001f92d`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
