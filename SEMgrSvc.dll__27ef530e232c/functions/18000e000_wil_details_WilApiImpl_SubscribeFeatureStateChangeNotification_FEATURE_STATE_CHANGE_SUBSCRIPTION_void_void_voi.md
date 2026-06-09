# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000e000`
- end: `0x18000e10d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000d684`
- `0x18000d780`
- `0x18000e000`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e0a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e0a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e08a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e08a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e050`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e050`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e0f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e0f7`

## string_xrefs

- `0x18000e083`: `ntdll.dll`
- `0x18000e097`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
