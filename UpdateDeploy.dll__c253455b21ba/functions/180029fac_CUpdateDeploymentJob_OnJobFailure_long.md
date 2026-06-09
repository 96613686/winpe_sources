# CUpdateDeploymentJob::OnJobFailure(long)

- ea: `0x180029fac`
- end: `0x18002a1b8`
- name: `?OnJobFailure@CUpdateDeploymentJob@@AEAAJJ@Z`
- size: `524`
- prototype: `__int64 __fastcall(CUpdateDeploymentJob *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002cdd4`

## callees

- `0x1800110fc`
- `0x180011b44`
- `0x1800294e4`
- `0x180029fac`
- `0x1800330b8`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a056`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a056`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a199`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a199`

## string_xrefs

- `0x18002a0d9`: `Setting the update %ws.%d final status to indicate failure`
- `0x18002a12e`: `Failed to set the update %ws.%d status to indicate commit failure`

## pseudocode

```c

```
