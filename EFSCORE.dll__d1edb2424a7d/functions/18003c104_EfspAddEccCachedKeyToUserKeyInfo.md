# EfspAddEccCachedKeyToUserKeyInfo

- ea: `0x18003c104`
- end: `0x18003c3fa`
- name: `EfspAddEccCachedKeyToUserKeyInfo`
- size: `758`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180037df4`

## callees

- `0x180004f86`
- `0x1800102f0`
- `0x180010bf0`
- `0x18003c104`
- `0x180063698`

## import_xrefs

- `CRYPT32!CryptProtectMemory` at `0x18003c387`
- `CRYPT32!CryptProtectMemory` at `0x18003c387`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18003c325`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18003c325`
- `bcrypt!BCryptDestroyKey` at `0x18003c3b6`
- `bcrypt!BCryptDestroyKey` at `0x18003c3b6`
- `bcrypt!BCryptImportKey` at `0x18003c2d8`
- `bcrypt!BCryptImportKey` at `0x18003c2d8`
- `ntdll!RtlNtStatusToDosError` at `0x18003c2e7`
- `ntdll!RtlNtStatusToDosError` at `0x18003c334`
- `ntdll!RtlNtStatusToDosError` at `0x18003c2e7`
- `ntdll!RtlNtStatusToDosError` at `0x18003c334`
- `ntdll!RtlInitializeSRWLock` at `0x18003c349`
- `ntdll!RtlInitializeSRWLock` at `0x18003c349`

## pseudocode

```c

```
