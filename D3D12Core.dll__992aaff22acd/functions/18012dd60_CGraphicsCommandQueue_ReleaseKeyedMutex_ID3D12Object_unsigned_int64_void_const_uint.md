# CGraphicsCommandQueue::ReleaseKeyedMutex(ID3D12Object *,unsigned __int64,void const *,uint)

- ea: `0x18012dd60`
- end: `0x18012df0d`
- name: `?ReleaseKeyedMutex@CGraphicsCommandQueue@@UEAAJPEAUID3D12Object@@_KPEBXI@Z`
- size: `429`
- prototype: `int(CGraphicsCommandQueue *__hidden this, struct ID3D12Object *, unsigned __int64, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800fa360`

## callees

- `0x180007df0`
- `0x18000ac4c`
- `0x18000b010`
- `0x18005ef04`
- `0x18009cde0`
- `0x18012cf1c`
- `0x18012dd60`
- `0x180262020`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18012ddfb`
- `msvcp_win!_Mtx_unlock` at `0x18012de05`
- `msvcp_win!_Mtx_unlock` at `0x18012deb3`
- `msvcp_win!_Mtx_unlock` at `0x18012debd`
- `msvcp_win!_Mtx_unlock` at `0x18012ddfb`
- `msvcp_win!_Mtx_unlock` at `0x18012de05`
- `msvcp_win!_Mtx_unlock` at `0x18012deb3`
- `msvcp_win!_Mtx_unlock` at `0x18012debd`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTReleaseKeyedMutex2` at `0x18012de86`

## pseudocode

```c

```
