# TraceOutputSettings::~TraceOutputSettings(void)

- ea: `0x18000b430`
- end: `0x18000b602`
- name: `??1TraceOutputSettings@@QEAA@XZ`
- size: `466`
- prototype: `void __fastcall(TraceOutputSettings *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180083a70`

## callees

- `0x180003cf0`
- `0x18000b430`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b488`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b488`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b476`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b5f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b476`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b5f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b43d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b4f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b43d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b4f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b528`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b504`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b504`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b5e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b5e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b45e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b5c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b45e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b5c9`
- `KERNEL32!UnregisterWaitEx` at `0x18000b51e`
- `KERNEL32!UnregisterWaitEx` at `0x18000b51e`

## string_xrefs

- `0x18000b4df`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18000b54d`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18000b582`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18000b498`: `Failed receiving the RegistryChangeListenerFinished event`
- `0x18000b4b4`: `Successfully received the RegistryChangeListenerFinished event`
- `0x18000b562`: `Successfully unregistered for registry change notifications`

## pseudocode

```c

```
