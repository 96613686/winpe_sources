# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180013630`
- end: `0x18001373d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18001316c`
- `0x180013268`
- `0x180013630`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800136d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800136d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800136ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800136ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013680`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013680`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013727`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013727`

## string_xrefs

- `0x1800136b3`: `ntdll.dll`
- `0x1800136c7`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
