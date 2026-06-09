# WaasMedic::CAutoThreadPrivilegeHelper::~CAutoThreadPrivilegeHelper(void)

- ea: `0x18002a578`
- end: `0x18002a5ca`
- name: `??1CAutoThreadPrivilegeHelper@WaasMedic@@QEAA@XZ`
- size: `82`
- prototype: `void __fastcall(WaasMedic::CAutoThreadPrivilegeHelper *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18006133c`
- `0x18006313a`

## callees

- `0x18002543c`
- `0x18002a578`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a597`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a5be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a5be`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002a587`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002a587`

## string_xrefs

- `0x18002a59d`: `Failed to revert the thread token: 0%x08X`

## pseudocode

```c

```
