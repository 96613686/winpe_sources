# RdpSurface::CreateWatermarkingBitmap(ushort *,uint,uint,uint,uint)

- ea: `0x180087594`
- end: `0x180087b3f`
- name: `?CreateWatermarkingBitmap@RdpSurface@@QEAAJPEAGIIII@Z`
- size: `1451`
- prototype: `__int64 __fastcall(RdpSurface *__hidden this, unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800a00c0`

## callees

- `0x180076090`
- `0x180079724`
- `0x180079770`
- `0x18007a1d4`
- `0x180087594`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180087744`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180087744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087752`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087752`
- `OLEAUT32!__imp_VariantInit` at `0x1800875d4`
- `OLEAUT32!__imp_VariantInit` at `0x1800875d4`
- `OLEAUT32!__imp_VariantClear` at `0x1800876d0`
- `OLEAUT32!__imp_VariantClear` at `0x1800876d0`

## string_xrefs

- `0x18008764c`: `RdpQrCodeHelperDllHandle`
- `0x18008773a`: `QrCodeHelper_CreateInstance`
- `0x1800877a0`: `Failed to load proc address QrCodeHelper_CreateInstance`
- `0x1800877f2`: `QrCodeHelper_CreateInstance failed`
- `0x180087871`: `Failed to create QRCode for watermarking`

## pseudocode

```c

```
