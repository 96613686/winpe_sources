# CreateSetupOneSettings(ushort const *,ushort const *,ISetupOneSettings * *)

- ea: `0x18005c8b8`
- end: `0x18005c9ad`
- name: `?CreateSetupOneSettings@@YAJPEBG0PEAPEAUISetupOneSettings@@@Z`
- size: `245`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct ISetupOneSettings **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18000febc`
- `0x1800346cc`

## callees

- `0x1800028f0`
- `0x18003714c`
- `0x18005bc2c`
- `0x18005c8b8`
- `0x18005dc50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005c912`
- `KERNEL32!GetLastError` at `0x18005c912`
- `WDSCORE!WdsSetupLogMessageW` at `0x18005c980`
- `WDSCORE!WdsSetupLogMessageW` at `0x18005c980`
- `WDSCORE!CurrentIP` at `0x18005c91a`
- `WDSCORE!CurrentIP` at `0x18005c91a`

## string_xrefs

- `0x18005c93f`: `CreateSetupOneSettings`

## pseudocode

```c

```
