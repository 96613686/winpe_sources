# EfsFreeUserInfo

- ea: `0x1800254d4`
- end: `0x180025608`
- name: `EfsFreeUserInfo`
- size: `308`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180010720`
- `0x18001581c`
- `0x180016080`
- `0x180016490`
- `0x1800274b8`
- `0x18003818c`
- `0x180041c20`
- `0x180042814`
- `0x18004d2d0`

## callees

- `0x180010bf0`
- `0x1800254d4`
- `0x180035b14`
- `0x180063698`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025586`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x180025576`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x180025576`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002557c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002557c`
- `USERENV!UnloadUserProfile` at `0x1800255b7`
- `USERENV!UnloadUserProfile` at `0x1800255b7`
- `ntdll!NtClose` at `0x1800255da`
- `ntdll!NtClose` at `0x1800255da`
- `ntdll!NtSetInformationThread` at `0x1800255d1`
- `ntdll!NtSetInformationThread` at `0x1800255d1`
- `ntdll!RtlFreeUnicodeString` at `0x180025534`
- `ntdll!RtlFreeUnicodeString` at `0x180025534`

## pseudocode

```c

```
