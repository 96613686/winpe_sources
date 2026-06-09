# SetCoInstall(void)

- ea: `0x180089aac`
- end: `0x180089bd4`
- name: `?SetCoInstall@@YAJXZ`
- size: `296`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180074e2c`
- `0x1800b4b20`

## callees

- `0x180089aac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180089bc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180089bc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180089ac0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180089ac0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089b9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089b9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180089b0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180089b0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180089b3a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180089b3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089b5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089b66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089b5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089b66`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180089b7f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180089b7f`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180089bb3`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180089bb3`

## string_xrefs

- `0x180089b1b`: `UseCoInstall`
- `0x180089b78`: `ole32.dll`
- `0x180089b91`: `CoInstall`

## pseudocode

```c

```
