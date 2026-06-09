# ServerFullDuplexChannel::OnEventSendCompleted(ulong,ulong)

- ea: `0x18002fd94`
- end: `0x1800301d6`
- name: `?OnEventSendCompleted@ServerFullDuplexChannel@@AEAAXKK@Z`
- size: `1090`
- prototype: `void __fastcall(ServerFullDuplexChannel *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e160`

## callees

- `0x180005d10`
- `0x180025d90`
- `0x180026310`
- `0x180026e80`
- `0x18002fd94`
- `0x18005a5b0`
- `0x180112460`
- `0x18011349c`
- `0x18011a6d4`
- `0x1801538f4`
- `0x18018b454`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fecf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ff01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ff34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fecf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ff01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ff34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fde5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fde5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fe7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fe7e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002fe6a`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002fe6a`

## string_xrefs

- `0x18002fef0`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x18002ff23`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x18002ffbc`: `onecore\admin\wmi\wmx\service\serverfullduplexchannel.cpp`

## pseudocode

```c

```
