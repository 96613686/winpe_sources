# CLocationGnssAdapter::AgnssHandlePositionInjection(GNSS_AGNSS_INJECT *,long *,AgnssRequestState &)

- ea: `0x1800daca0`
- end: `0x1800db192`
- name: `?AgnssHandlePositionInjection@CLocationGnssAdapter@@AEAAJPEAUGNSS_AGNSS_INJECT@@PEAJAEAW4AgnssRequestState@@@Z`
- size: `1266`
- prototype: `__int64 __fastcall(CLocationGnssAdapter *__hidden this, struct GNSS_AGNSS_INJECT *, int *, enum AgnssRequestState *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800a1088`

## callees

- `0x180012398`
- `0x180046104`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x1800daca0`
- `0x1800dc800`
- `0x1800df99c`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dad20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dad20`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800dae96`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800dae96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800db160`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800db160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800daec2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800daec2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dae84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800daea2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dae84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800daea2`

## string_xrefs

- `0x1800daf67`: `Coarse position response should never come from Gnss`

## pseudocode

```c

```
