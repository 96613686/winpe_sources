# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180011640`
- end: `0x18001174d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180010f48`
- `0x180011044`
- `0x180011640`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800116e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800116e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800116ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800116ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011737`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011737`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011690`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011690`

## string_xrefs

- `0x1800116c3`: `ntdll.dll`
- `0x1800116d7`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
