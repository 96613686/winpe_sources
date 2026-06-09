# Service::Initialize(void)

- ea: `0x180003130`
- end: `0x1800032df`
- name: `?Initialize@Service@@UEAAJXZ`
- size: `431`
- prototype: `__int64 __fastcall(wil::details **this)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180003130`
- `0x1800032e8`
- `0x180003880`
- `0x18000cb8c`
- `0x18001a5b4`
- `0x1800203c4`
- `0x1800225a0`
- `0x18003a980`
- `0x18003a9b0`
- `0x18006a010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180003250`
- `msvcp_win!_Mtx_unlock` at `0x180003250`
- `ntdll!RtlPublishWnfStateData` at `0x18000329f`
- `ntdll!RtlPublishWnfStateData` at `0x18000329f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800031ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800031ac`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800031e1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800031e1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800031db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800031db`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800031ca`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800031ca`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180003198`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180003198`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x1800031b9`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x1800031b9`

## string_xrefs

- `0x1800031fc`: `{"text":"Failed to initialize service. hr = 0x%8X"}`

## pseudocode

```c

```
