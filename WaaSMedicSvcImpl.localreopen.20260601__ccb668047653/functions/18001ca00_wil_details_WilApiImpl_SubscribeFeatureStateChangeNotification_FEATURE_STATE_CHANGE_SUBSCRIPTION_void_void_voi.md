# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18001ca00`
- end: `0x18001cb0d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18001c278`
- `0x18001c374`
- `0x18001ca00`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001caa1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001caa1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ca8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ca8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001caf7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001caf7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ca50`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ca50`

## string_xrefs

- `0x18001ca83`: `ntdll.dll`
- `0x18001ca97`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
