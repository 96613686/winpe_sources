# cppwinrt_custom_lock::DecServiceRefCount(void)

- ea: `0x14001a420`
- end: `0x14001a4a1`
- name: `?DecServiceRefCount@cppwinrt_custom_lock@@YAIXZ`
- size: `129`
- prototype: `unsigned int __fastcall(cppwinrt_custom_lock *__hidden this)`
- caller_count: `14`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001c220`
- `0x14001c6bc`
- `0x14001d410`
- `0x14001d6b0`
- `0x140020e74`
- `0x14002456c`
- `0x1400331d8`
- `0x140033548`
- `0x14003a120`
- `0x14003a1e0`
- `0x14003a510`
- `0x14003c558`
- `0x14003c588`
- `0x14003f6a0`

## callees

- `0x140019d2c`
- `0x14001a378`
- `0x14001a4a8`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x14001a48c`
- `msvcp_win!_Mtx_unlock` at `0x14001a48c`
- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x14001a468`
- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x14001a468`

## string_xrefs

- `0x14001a441`: `refcount already at 0; Double release?`

## pseudocode

```c

```
