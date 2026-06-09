# SipcEndpoint::CreateServerEndpoint(SipcServer *,SipcPort *,void *,void *,ulong,ulong,void (*)(ISIPCEndpoint *,SIPC_BUFFER_STATUS,SIPC_BUFFER_INFO const *,SIPC_BUFFER_INFO const *,void *),void (*)(ISIPCEndpoint *,SIPC_ENDPOINT_STATUS,void *),void *,SipcEndpoint * *)

- ea: `0x180027dfc`
- end: `0x180027f13`
- name: `?CreateServerEndpoint@SipcEndpoint@@SAJPEAVSipcServer@@PEAVSipcPort@@PEAX2KKP6AXPEAUISIPCEndpoint@@W4SIPC_BUFFER_STATUS@@PEBUSIPC_BUFFER_INFO@@52@ZP6AX3W4SIPC_ENDPOINT_STATUS@@2@Z2PEAPEAV1@@Z`
- size: `279`
- prototype: `__int64 __fastcall(struct SipcServer *, struct SipcPort *, void *, void *, unsigned int, unsigned int, void (__high *)(struct ISIPCEndpoint *, enum SIPC_BUFFER_STATUS, const struct SIPC_BUFFER_INFO *, const struct SIPC_BUFFER_INFO *, void *), void (__high *)(struct ISIPCEndpoint *, enum SIPC_ENDPOINT_STATUS, void *), void *, struct SipcEndpoint **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180025940`

## callees

- `0x180024c48`
- `0x180027dfc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180027e35`
- `ntdll!RtlAllocateHeap` at `0x180027e35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027eb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027edf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027eb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027edf`

## pseudocode

```c

```
