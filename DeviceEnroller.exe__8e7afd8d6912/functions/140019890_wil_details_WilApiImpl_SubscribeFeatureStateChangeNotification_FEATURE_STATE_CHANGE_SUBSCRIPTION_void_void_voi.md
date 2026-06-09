# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140019890`
- end: `0x14001999d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140018ce8`
- `0x140018de4`
- `0x140019890`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140019931`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140019931`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001991a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001991a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019987`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019987`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400198e0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400198e0`

## string_xrefs

- `0x140019913`: `ntdll.dll`
- `0x140019927`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
