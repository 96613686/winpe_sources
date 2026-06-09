# CTSAPPSRVConfig::Cleanup(void)

- ea: `0x180035138`
- end: `0x180035200`
- name: `?Cleanup@CTSAPPSRVConfig@@AEAAJXZ`
- size: `200`
- prototype: `__int64 __fastcall(CTSAPPSRVConfig *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180035008`
- `0x180035210`

## callees

- `0x180003f30`
- `0x18001ec04`
- `0x180035138`
- `0x180035228`
- `0x1800356c0`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800351e8`
- `ntdll!RtlReleaseResource` at `0x1800351e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035193`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800351b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035193`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800351b3`
- `USERENV!UnregisterGPNotification` at `0x180035186`
- `USERENV!UnregisterGPNotification` at `0x180035186`

## string_xrefs

- `0x180035158`: `TerminateMonitorThread failed with 0x%x`

## pseudocode

```c

```
