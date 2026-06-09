# EfspLoadMasterKeyHistoryConfiguration(HKEY__ *,_EFS_MKHISTORY_CONFIGURATION *)

- ea: `0x180020f24`
- end: `0x1800211a3`
- name: `?EfspLoadMasterKeyHistoryConfiguration@@YAKPEAUHKEY__@@PEAU_EFS_MKHISTORY_CONFIGURATION@@@Z`
- size: `639`
- prototype: `unsigned int __fastcall(HKEY hkey, struct _EFS_MKHISTORY_CONFIGURATION *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800211ac`
- `0x1800227a8`
- `0x180023154`

## callees

- `0x1800102f0`
- `0x18001ee88`
- `0x180020b80`
- `0x180020f24`
- `0x180036d20`
- `0x180063698`
- `0x18006389c`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002109c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002109c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020f79`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020fec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021061`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020f79`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020fec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021061`
- `CRYPT32!CertFreeCertificateContext` at `0x180021188`
- `CRYPT32!CertFreeCertificateContext` at `0x180021188`

## pseudocode

```c

```
