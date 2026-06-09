# SystemSettings::DataModel::SystemLocaleManager::HandleSystemLocaleChange(ushort *,bool)

- ea: `0x140043284`
- end: `0x140043331`
- name: `?HandleSystemLocaleChange@SystemLocaleManager@DataModel@SystemSettings@@SAJPEAG_N@Z`
- size: `173`
- prototype: `__int64 __fastcall(LPCWSTR lpLocaleName, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x140020120`

## callees

- `0x140005f30`
- `0x140043284`
- `0x140043338`

## import_xrefs

- `KERNEL32!LocaleNameToLCID` at `0x1400432a5`
- `KERNEL32!LocaleNameToLCID` at `0x1400432a5`
- `KERNEL32!GetLocaleInfoEx` at `0x1400432e8`
- `KERNEL32!GetLocaleInfoEx` at `0x1400432fe`
- `KERNEL32!GetLocaleInfoEx` at `0x1400432e8`
- `KERNEL32!GetLocaleInfoEx` at `0x1400432fe`
- `KERNEL32!NlsUpdateSystemLocale` at `0x14004330a`
- `KERNEL32!NlsUpdateSystemLocale` at `0x14004330a`

## pseudocode

```c

```
