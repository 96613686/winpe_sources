# CGraphicsCommandQueue::SubmitPresent(void *,D3D12_PRESENT *)

- ea: `0x180006bc0`
- end: `0x180007043`
- name: `?SubmitPresent@CGraphicsCommandQueue@@UEAAJPEAXPEAUD3D12_PRESENT@@@Z`
- size: `1155`
- prototype: `int(CGraphicsCommandQueue *__hidden this, void *, struct D3D12_PRESENT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800056d0`
- `0x180006bc0`
- `0x180007df0`
- `0x180008464`
- `0x1800084b4`
- `0x18000ac4c`
- `0x18007efa0`
- `0x1800bb480`
- `0x1800bc07c`
- `0x1800bc094`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180006d91`
- `msvcp_win!_Mtx_unlock` at `0x180006d91`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTPresent` at `0x180006cfe`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTSubmitPresentToHwQueue` at `0x180006d7c`

## string_xrefs

- `0x180006ecd`: `Driver didn't provide any HwQueues for a hardware scheduling command queue present.`

## pseudocode

```c

```
