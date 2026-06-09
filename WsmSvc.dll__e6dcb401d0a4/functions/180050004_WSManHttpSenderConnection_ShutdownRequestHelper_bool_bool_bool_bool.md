# WSManHttpSenderConnection::ShutdownRequestHelper(bool,bool,bool,bool)

- ea: `0x180050004`
- end: `0x18005066d`
- name: `?ShutdownRequestHelper@WSManHttpSenderConnection@@AEAAX_N000@Z`
- size: `1641`
- prototype: `void __usercall(WSManHttpSenderConnection *__hidden this@<rcx>, bool@<dl>, bool@<r8b>, bool@<r9b>, bool)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x18004fdc0`
- `0x1801339d0`

## callees

- `0x180005d10`
- `0x180018878`
- `0x18002c580`
- `0x18004fbc0`
- `0x180050004`
- `0x1800520d0`
- `0x180067150`
- `0x1800a38d0`
- `0x1800c0cbc`
- `0x1800d3cdc`
- `0x1800dd5e8`
- `0x1800f1b20`
- `0x18011a6d4`
- `0x1801345dc`
- `0x18015c3e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800501ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800501fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005022a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050314`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800501ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800501fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005022a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050314`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800501c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800501c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005005a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005005a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800500e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050156`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800500e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050156`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800500cd`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800500cd`
- `WINHTTP!WinHttpCloseHandle` at `0x180050183`
- `WINHTTP!WinHttpCloseHandle` at `0x180050183`

## string_xrefs

- `0x1800501eb`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x180050219`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`

## pseudocode

```c

```
