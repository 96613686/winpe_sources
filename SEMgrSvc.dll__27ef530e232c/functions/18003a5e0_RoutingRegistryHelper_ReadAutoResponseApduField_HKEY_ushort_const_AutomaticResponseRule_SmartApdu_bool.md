# RoutingRegistryHelper::ReadAutoResponseApduField(HKEY__ *,ushort const *,AutomaticResponseRule::SmartApdu &,bool)

- ea: `0x18003a5e0`
- end: `0x18003a871`
- name: `?ReadAutoResponseApduField@RoutingRegistryHelper@@CAJPEAUHKEY__@@PEBGAEAUSmartApdu@AutomaticResponseRule@@_N@Z`
- size: `657`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpValue, struct AutomaticResponseRule::SmartApdu *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18003901c`

## callees

- `0x1800049c4`
- `0x180004e4c`
- `0x180004ec0`
- `0x1800057c6`
- `0x180005840`
- `0x180005858`
- `0x180038634`
- `0x18003a5e0`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003a858`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003a858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a706`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003a66d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003a66d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a81a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a81a`
- `CRYPT32!CryptUnprotectData` at `0x18003a6fc`
- `CRYPT32!CryptUnprotectData` at `0x18003a6fc`

## pseudocode

```c

```
