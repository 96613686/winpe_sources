# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140063030`
- end: `0x14006313d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140062934`
- `0x140062a30`
- `0x140063030`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1400630ba`
- `KERNEL32!GetModuleHandleW` at `0x1400630ba`
- `KERNEL32!GetProcAddress` at `0x1400630d1`
- `KERNEL32!GetProcAddress` at `0x1400630d1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140063080`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140063080`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140063127`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140063127`

## string_xrefs

- `0x1400630b3`: `ntdll.dll`
- `0x1400630c7`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
