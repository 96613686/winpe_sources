# EfsUnloadUserProfile

- ea: `0x180026328`
- end: `0x18002644d`
- name: `EfsUnloadUserProfile`
- size: `293`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180010ac0`
- `0x18001581c`
- `0x1800392a0`

## callees

- `0x180024960`
- `0x180026328`
- `0x180063698`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026386`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026386`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026394`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263b1`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x180026356`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x180026356`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800263a7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800263a7`
- `USERENV!UnloadUserProfile` at `0x1800263e2`
- `USERENV!UnloadUserProfile` at `0x1800263e2`
- `ntdll!NtClose` at `0x180026435`
- `ntdll!NtClose` at `0x180026435`
- `ntdll!NtSetInformationThread` at `0x180026404`
- `ntdll!NtSetInformationThread` at `0x180026404`

## pseudocode

```c

```
