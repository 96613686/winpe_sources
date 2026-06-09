# FullDuplexChannel::Acknowledge(void)

- ea: `0x1800c7250`
- end: `0x1800c7504`
- name: `?Acknowledge@FullDuplexChannel@@UEAAXXZ`
- size: `692`
- prototype: `void __fastcall(FullDuplexChannel *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180005d10`
- `0x1800c7250`
- `0x180123604`
- `0x180123660`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c7373`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c739e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c73c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c7373`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c739e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c73c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c728c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c728c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c72fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c72fb`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800c72e7`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800c72e7`

## string_xrefs

- `0x1800c738d`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x1800c73b8`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`

## pseudocode

```c

```
