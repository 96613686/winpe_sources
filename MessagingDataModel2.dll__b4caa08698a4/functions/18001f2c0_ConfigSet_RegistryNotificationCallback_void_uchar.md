# ConfigSet::RegistryNotificationCallback(void *,uchar)

- ea: `0x18001f2c0`
- end: `0x18001f35e`
- name: `?RegistryNotificationCallback@ConfigSet@@CAXPEAXE@Z`
- size: `158`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18001e4e8`
- `0x18001f2c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f357`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f320`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f320`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f33a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f33a`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001f2ed`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001f2ed`

## string_xrefs

- `0x18001f309`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`

## pseudocode

```c

```
