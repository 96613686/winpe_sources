# CheckInstalledVersionHint(HKEY__ *,CLocalComponentInfo *,ulong,ulong)

- ea: `0x18007679c`
- end: `0x180076a92`
- name: `?CheckInstalledVersionHint@@YAJPEAUHKEY__@@PEAVCLocalComponentInfo@@KK@Z`
- size: `758`
- prototype: `__int64 __fastcall(HKEY hKey, struct CLocalComponentInfo *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180076470`
- `0x180076b88`
- `0x1800c89e8`

## callees

- `0x1800150e0`
- `0x180030880`
- `0x18007679c`
- `0x180076a98`
- `0x18011baa0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18007694d`
- `msvcrt!memcpy_s` at `0x18007694d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076818`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076872`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076818`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076872`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180076a21`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180076a21`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800768f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18007697b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800769b9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800768f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18007697b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800769b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076a50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076a60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076a50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076a60`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x180076a2f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x180076a2f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18007692f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18007692f`
- `api-ms-win-http-time-l1-1-0!InternetTimeToSystemTimeA` at `0x18007691b`
- `api-ms-win-http-time-l1-1-0!InternetTimeToSystemTimeA` at `0x18007691b`

## string_xrefs

- `0x180076868`: `InstalledVersion`

## pseudocode

```c

```
