# WaasMedic::UsoHelper::SeenErrorInLastNDays(uint,bool &)

- ea: `0x180056a90`
- end: `0x180057185`
- name: `?SeenErrorInLastNDays@UsoHelper@WaasMedic@@QEAAJIAEA_N@Z`
- size: `1781`
- prototype: `__int64 __fastcall(WaasMedic::UsoHelper *__hidden this, unsigned int, bool *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800387e0`
- `0x180051c80`

## callees

- `0x180003bb0`
- `0x180009a54`
- `0x18002543c`
- `0x1800280bc`
- `0x180028a74`
- `0x180030890`
- `0x1800308e0`
- `0x180030f54`
- `0x180030fbc`
- `0x180056a90`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180056ae4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180056bab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180056ae4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180056bab`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180056d8f`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180056d8f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180056af9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180056bbf`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180056dac`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180056af9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180056bbf`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180056dac`

## string_xrefs

- `0x18005706f`: `IsInstallErrorSeen`
- `0x1800570ab`: `Found test hook for impact level, will consider seenError to be : %s`

## pseudocode

```c

```
