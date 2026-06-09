# StatelessCodecWorkItem::Initialize(IRdpImageCompressor *,int,uchar,IRdpBoundsAccumulator *,RdpSurface *,PixelMap *,IRdpPipeEvents *)

- ea: `0x1800b4f90`
- end: `0x1800b5340`
- name: `?Initialize@StatelessCodecWorkItem@@EEAAJPEAUIRdpImageCompressor@@HEPEAVIRdpBoundsAccumulator@@PEAVRdpSurface@@PEAVPixelMap@@PEAVIRdpPipeEvents@@@Z`
- size: `944`
- prototype: `__int64 __fastcall(StatelessCodecWorkItem *__hidden this, struct IRdpImageCompressor *, int, unsigned __int8, struct IRdpBoundsAccumulator *, struct RdpSurface *, struct PixelMap *, struct IRdpPipeEvents *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800b3068`

## callees

- `0x180010cd8`
- `0x180010d6c`
- `0x18002d8f4`
- `0x180076090`
- `0x180077aa0`
- `0x180079724`
- `0x180079770`
- `0x18007cf90`
- `0x18008b9e8`
- `0x1800b4f90`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800b52f5`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800b5321`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800b52f5`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800b5321`

## string_xrefs

- `0x1800b51b9`: `failed to create workItem BA`
- `0x1800b4fd6`: `pCompressor`
- `0x1800b5079`: `pImageToCompress`
- `0x1800b5294`: `SetMaxCompressionMode failed`

## pseudocode

```c

```
