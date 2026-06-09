# UfhResetArpShortcutData(ushort *,int)

- ea: `0x18003f710`
- end: `0x18003f89d`
- name: `?UfhResetArpShortcutData@@YAKPEAGH@Z`
- size: `397`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000acf0`
- `0x1800b2b50`

## callees

- `0x18003f710`
- `0x1800f0f64`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003f848`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003f848`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003f863`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003f863`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f78e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f7a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f871`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f78e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f7a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f871`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f774`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f774`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003f7e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003f7e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18003f7f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18003f7f6`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18003f804`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18003f804`

## pseudocode

```c

```
