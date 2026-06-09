# Windows::FileSystem::ReFs::ReFsDedupService::StartVolumeEnumeration(void)

- ea: `0x140035fa4`
- end: `0x140036041`
- name: `?StartVolumeEnumeration@ReFsDedupService@ReFs@FileSystem@Windows@@AEAAXXZ`
- size: `157`
- prototype: `void __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140034660`
- `0x14003536c`

## callees

- `0x140019d2c`
- `0x14001a3c0`
- `0x14001c6bc`
- `0x140035fa4`
- `0x1400377cc`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x140035fd7`
- `msvcp_win!_Mtx_unlock` at `0x140035fd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036008`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x140035fb9`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x140035fb9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x140035ff1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x140035ff1`

## string_xrefs

- `0x14003602f`: `onecore\base\fs\refsdedupsvc\exe\refsdedupservice.cpp`

## pseudocode

```c

```
