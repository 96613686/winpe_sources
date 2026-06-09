# SEReader::ApplyCardEmulationPolicy(void)

- ea: `0x1800166b0`
- end: `0x18001686e`
- name: `?ApplyCardEmulationPolicy@SEReader@@AEAAJXZ`
- size: `446`
- prototype: `__int64 __fastcall(SEReader *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180017094`
- `0x180017f70`

## callees

- `0x180001008`
- `0x180001194`
- `0x1800166b0`
- `0x1800178e0`
- `0x180017be4`
- `0x180065aa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016841`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016859`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016841`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016859`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800166d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800167e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800166d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800167e7`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001681f`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001681f`

## string_xrefs

- `0x18001670d`: `Read user selected card emulation state.`
- `0x1800166fb`: `SEReader::ApplyCardEmulationPolicy`

## pseudocode

```c

```
