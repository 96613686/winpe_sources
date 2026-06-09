# CGraphicsCommandQueue::AcquireKeyedMutex(ID3D12Object *,unsigned __int64,ulong,void *,uint)

- ea: `0x18005ece0`
- end: `0x18005eeab`
- name: `?AcquireKeyedMutex@CGraphicsCommandQueue@@UEAAJPEAUID3D12Object@@_KKPEAXI@Z`
- size: `459`
- prototype: `int(CGraphicsCommandQueue *__hidden this, struct ID3D12Object *, unsigned __int64, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800ebf20`

## callees

- `0x180007df0`
- `0x18000ac4c`
- `0x18000b010`
- `0x18005ece0`
- `0x18005eeb4`
- `0x18005ef04`
- `0x18008f544`
- `0x180262020`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18005ee0b`
- `msvcp_win!_Mtx_unlock` at `0x18005ee15`
- `msvcp_win!_Mtx_unlock` at `0x18005ee0b`
- `msvcp_win!_Mtx_unlock` at `0x18005ee15`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTAcquireKeyedMutex2` at `0x18005ed7a`

## pseudocode

```c

```
