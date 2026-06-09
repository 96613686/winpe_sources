# Common::ReportFatalException(unsigned __int64,ulong,Common::FATAL_FAILURE_REASON_TYPE,ulong)

- ea: `0x1800466f4`
- end: `0x180046788`
- name: `?ReportFatalException@Common@@YAX_KKW4FATAL_FAILURE_REASON_TYPE@1@K@Z`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800466e4`

## callees

- `0x1800466f4`
- `0x180046790`
- `0x18004c9d0`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180046722`
- `ntdll!NtQuerySystemInformation` at `0x180046722`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004676d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004676d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18004cde8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18004cde8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004cdda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004cdda`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18004673e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18004673e`

## pseudocode

```c

```
