# ConfigSet::RegistryNotificationCallback(void *,uchar)

- ea: `0x18002f620`
- end: `0x18002f6be`
- name: `?RegistryNotificationCallback@ConfigSet@@CAXPEAXE@Z`
- size: `158`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18002c580`
- `0x18002f620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f69a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f69a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f680`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f680`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f6b7`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002f64d`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002f64d`

## string_xrefs

- `0x18002f669`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`

## pseudocode

```c

```
