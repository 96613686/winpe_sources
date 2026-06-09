# SHQueryToken<_TOKEN_PRIVILEGES>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_PRIVILEGES * *)

- ea: `0x18023398c`
- end: `0x180233ae1`
- name: `??$SHQueryToken@U_TOKEN_PRIVILEGES@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_PRIVILEGES@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180233c40`

## callees

- `0x18011acc0`
- `0x18023398c`
- `0x180233e18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180233a27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180233a8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180233a27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180233a8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180233ac7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180233ac7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180233a3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180233aad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180233a3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180233aad`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180233a13`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180233a7b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180233a13`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180233a7b`

## pseudocode

```c

```
