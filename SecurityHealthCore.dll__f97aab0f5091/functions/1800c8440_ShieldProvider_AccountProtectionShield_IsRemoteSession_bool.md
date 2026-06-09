# ShieldProvider::AccountProtectionShield::IsRemoteSession(bool *)

- ea: `0x1800c8440`
- end: `0x1800c84e2`
- name: `?IsRemoteSession@AccountProtectionShield@ShieldProvider@@AEAAJPEA_N@Z`
- size: `162`
- prototype: `__int64 __fastcall(ShieldProvider::AccountProtectionShield *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800c8970`
- `0x1800c9520`

## callees

- `0x18000d7fc`
- `0x1800c8440`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800c8481`
- `KERNEL32!GetLastError` at `0x1800c8481`
- `ntdll!RtlGetActiveConsoleId` at `0x1800c84cb`
- `ntdll!RtlGetActiveConsoleId` at `0x1800c84cb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c8477`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c8477`

## pseudocode

```c

```
