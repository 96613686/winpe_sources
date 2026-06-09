# CTrace::InitSession(int)

- ea: `0x18001430c`
- end: `0x18001457d`
- name: `?InitSession@CTrace@@QEAAJH@Z`
- size: `625`
- prototype: `__int64 __fastcall(CTrace *__hidden this, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b150`

## callees

- `0x180003cf0`
- `0x18000d924`
- `0x18000f674`
- `0x18001430c`
- `0x18001881c`
- `0x18001a360`
- `0x18007cbb0`
- `0x18007ccd4`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180014437`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180014437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014441`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014508`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014508`
- `ADVAPI32!EnableTrace` at `0x180014483`
- `ADVAPI32!EnableTrace` at `0x180014483`

## string_xrefs

- `0x180014343`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x1800143ae`: `DoesTraceDirectoryExist FAILED`
- `0x1800143ee`: `OpenTracingLoggingOptionsKey FAILED`

## pseudocode

```c

```
