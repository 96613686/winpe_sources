# FullDuplexChannel::ProcessEventMsgAvailable(ulong,ulong,bool *,bool)

- ea: `0x18002dda4`
- end: `0x18002e152`
- name: `?ProcessEventMsgAvailable@FullDuplexChannel@@IEAA_NKKPEA_N_N@Z`
- size: `942`
- prototype: `bool __fastcall(FullDuplexChannel *__hidden this, unsigned int, unsigned int, bool *, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18002cf80`
- `0x18002e434`

## callees

- `0x180005d10`
- `0x18002dda4`
- `0x180057de0`
- `0x180112460`
- `0x18011349c`
- `0x18011a6d4`
- `0x18012c3c0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002df1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002df96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002df1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002df96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002de02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002de02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002de5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002de5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002de09`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002de09`

## string_xrefs

- `0x18002df34`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`

## pseudocode

```c

```
