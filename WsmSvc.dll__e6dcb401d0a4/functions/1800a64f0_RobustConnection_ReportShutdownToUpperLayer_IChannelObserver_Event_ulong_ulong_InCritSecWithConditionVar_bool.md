# RobustConnection::ReportShutdownToUpperLayer(IChannelObserver::Event,ulong,ulong,InCritSecWithConditionVar *,bool *)

- ea: `0x1800a64f0`
- end: `0x1800a6977`
- name: `?ReportShutdownToUpperLayer@RobustConnection@@MEAAXW4Event@IChannelObserver@@KKPEAVInCritSecWithConditionVar@@PEA_N@Z`
- size: `1159`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800a63f0`

## callees

- `0x180005d10`
- `0x1800520d0`
- `0x1800a64f0`
- `0x180112460`
- `0x180129650`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a66d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a6708`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a678d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a67bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a66d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a6708`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a678d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a67bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a6600`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a66a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a6600`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a66a3`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800a65e9`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800a668c`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800a65e9`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800a668c`

## string_xrefs

- `0x1800a66f5`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x1800a67aa`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`

## pseudocode

```c

```
