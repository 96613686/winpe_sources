# SHGetCorrectOwnerSid

- ea: `0x1800187f0`
- end: `0x180018e3e`
- name: `SHGetCorrectOwnerSid`
- size: `1614`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18018a0d0`

## callees

- `0x180018280`
- `0x180018470`
- `0x1800186d0`
- `0x1800187f0`
- `0x180018e44`
- `0x180018ecc`
- `0x18012c710`
- `0x18012c990`
- `0x180136974`
- `0x1802b7710`
- `0x18030758c`
- `0x1803a4cb0`
- `0x1803a518c`
- `0x1803a57e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018934`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018972`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018934`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018972`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018c7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018e33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018c7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018e33`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018850`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018850`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001898c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001898c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018adc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018adc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018ac5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018ac5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018c71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018c71`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180018a23`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180018a23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800189cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800189cb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018a81`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018a81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018b70`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018b70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018d40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018e01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018d40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018e01`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180018d11`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180018d11`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018c97`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018d29`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018c97`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018d29`

## string_xrefs

- `0x180018a50`: `ProfileImagePath`

## pseudocode

```c

```
