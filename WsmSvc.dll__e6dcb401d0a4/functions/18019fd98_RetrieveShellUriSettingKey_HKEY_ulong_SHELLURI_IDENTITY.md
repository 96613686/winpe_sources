# RetrieveShellUriSettingKey(HKEY__ *,ulong,SHELLURI_IDENTITY *)

- ea: `0x18019fd98`
- end: `0x1801a0001`
- name: `?RetrieveShellUriSettingKey@@YAHPEAUHKEY__@@KPEAVSHELLURI_IDENTITY@@@Z`
- size: `617`
- prototype: `__int64 __fastcall(HKEY, unsigned int, struct SHELLURI_IDENTITY *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040ee0`

## callees

- `0x180005d10`
- `0x180008920`
- `0x1800621e0`
- `0x1800bac30`
- `0x1800e334c`
- `0x180112380`
- `0x1801123a8`
- `0x1801133b0`
- `0x18012a93c`
- `0x18019fd98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fe7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fede`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019ffb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fe7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fede`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019ffb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fe46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fe46`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18019ff74`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18019ff74`

## string_xrefs

- `0x18019fdd6`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x18019ff10`: `onecore\admin\wmi\wmx\config\configutils.cpp`

## pseudocode

```c

```
