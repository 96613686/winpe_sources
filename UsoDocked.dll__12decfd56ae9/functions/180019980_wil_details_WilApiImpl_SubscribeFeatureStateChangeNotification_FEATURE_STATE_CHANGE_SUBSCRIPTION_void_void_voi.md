# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180019980`
- end: `0x180019a8d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180019114`
- `0x180019210`
- `0x180019980`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019a21`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019a21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019a0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019a0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800199d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800199d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019a77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019a77`

## string_xrefs

- `0x180019a03`: `ntdll.dll`
- `0x180019a17`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
