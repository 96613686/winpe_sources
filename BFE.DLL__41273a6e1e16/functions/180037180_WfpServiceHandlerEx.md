# WfpServiceHandlerEx

- ea: `0x180037180`
- end: `0x18003734d`
- name: `WfpServiceHandlerEx`
- size: `461`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x180012d8c`
- `0x1800135ac`
- `0x180037180`
- `0x180037354`
- `0x18003761c`
- `0x18004668c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008d009`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008d009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d01d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d01d`

## string_xrefs

- `0x18003728b`: `WfpServiceHandlerEx`
- `0x18003729f`: `WfpServiceHandlerEx`

## pseudocode

```c

```
