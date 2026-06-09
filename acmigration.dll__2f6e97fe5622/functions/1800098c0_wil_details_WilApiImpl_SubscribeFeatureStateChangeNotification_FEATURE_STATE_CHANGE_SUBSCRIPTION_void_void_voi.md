# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800098c0`
- end: `0x1800099cd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000913c`
- `0x180009238`
- `0x1800098c0`
- `0x18006a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000994a`
- `KERNEL32!GetModuleHandleW` at `0x18000994a`
- `KERNEL32!GetProcAddress` at `0x180009961`
- `KERNEL32!GetProcAddress` at `0x180009961`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009910`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009910`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800099b7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800099b7`

## string_xrefs

- `0x180009943`: `ntdll.dll`
- `0x180009957`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
