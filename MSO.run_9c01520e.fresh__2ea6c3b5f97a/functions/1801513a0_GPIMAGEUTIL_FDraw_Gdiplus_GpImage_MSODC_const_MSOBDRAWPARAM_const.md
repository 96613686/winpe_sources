# GPIMAGEUTIL::FDraw(Gdiplus::GpImage &,MSODC const *,MSOBDRAWPARAM const *)

- ea: `0x1801513a0`
- end: `0x180151dc6`
- name: `?FDraw@GPIMAGEUTIL@@SAHAEAVGpImage@Gdiplus@@PEBUMSODC@@PEBUMSOBDRAWPARAM@@@Z`
- size: `2598`
- prototype: `__int64 __fastcall(struct Gdiplus::GpImage *, const struct MSODC *, const struct MSOBDRAWPARAM *this)`
- caller_count: `8`
- callee_count: `19`
- tags: ``

## callers

- `0x18014cb00`
- `0x18023b600`
- `0x1803a5750`
- `0x180b6e400`
- `0x18110406c`
- `0x181218c70`
- `0x181218d30`
- `0x1812606a4`

## callees

- `0x18001d310`
- `0x18007edb0`
- `0x1801513a0`
- `0x180151dc8`
- `0x180151e90`
- `0x180151eec`
- `0x180151f80`
- `0x180152b54`
- `0x180152e60`
- `0x180154c70`
- `0x18015d180`
- `0x18015d220`
- `0x18016eca0`
- `0x1802449a8`
- `0x1803f04e0`
- `0x18046026c`
- `0x1809eb340`
- `0x181284ec8`
- `0x1812853a0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180151b46`
- `KERNEL32!SetLastError` at `0x180151b46`
- `mso40uiWin32Client!__imp_?SetGraphicsRenderingOptions@@YAXPEAVGpGraphics@Gdiplus@@KK@Z` at `0x18015187a`
- `mso40uiWin32Client!__imp_?SetGraphicsRenderingOptions@@YAXPEAVGpGraphics@Gdiplus@@KK@Z` at `0x18015187a`
- `mso40uiWin32Client!__imp_??0FPState@@QEAA@K@Z` at `0x1801513e2`
- `mso40uiWin32Client!__imp_??0FPState@@QEAA@K@Z` at `0x1801513e2`
- `mso40uiWin32Client!__imp_?GetPrefs@GELPREF@@YAAEAUPREFS@1@XZ` at `0x1801514d7`
- `mso40uiWin32Client!__imp_?GetPrefs@GELPREF@@YAAEAUPREFS@1@XZ` at `0x180151533`
- `mso40uiWin32Client!__imp_?GetPrefs@GELPREF@@YAAEAUPREFS@1@XZ` at `0x1801514d7`
- `mso40uiWin32Client!__imp_?GetPrefs@GELPREF@@YAAEAUPREFS@1@XZ` at `0x180151533`
- `mso40uiWin32Client!__imp_?GetMetafile@MSODC@@QEBAPEAVGpMetafile@Gdiplus@@XZ` at `0x180151a97`
- `mso40uiWin32Client!__imp_?GetMetafile@MSODC@@QEBAPEAVGpMetafile@Gdiplus@@XZ` at `0x180151a97`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180151653`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180151a87`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180151653`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180151a87`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x1801513ff`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x1801513ff`
- `USER32!GetDC` at `0x180151811`
- `USER32!GetDC` at `0x180151811`
- `USER32!ReleaseDC` at `0x180151da6`
- `USER32!ReleaseDC` at `0x180151da6`
- `gdiplus!GdipDisposeImage` at `0x1801518a7`
- `gdiplus!GdipDisposeImage` at `0x180151c74`
- `gdiplus!GdipDisposeImage` at `0x180151d96`
- `gdiplus!GdipDisposeImage` at `0x1801518a7`
- `gdiplus!GdipDisposeImage` at `0x180151c74`
- `gdiplus!GdipDisposeImage` at `0x180151d96`
- `gdiplus!GdipDeleteGraphics` at `0x180151a6e`
- `gdiplus!GdipDeleteGraphics` at `0x180151b8b`
- `gdiplus!GdipDeleteGraphics` at `0x180151c82`
- `gdiplus!GdipDeleteGraphics` at `0x180151d2c`
- `gdiplus!GdipDeleteGraphics` at `0x180151a6e`
- `gdiplus!GdipDeleteGraphics` at `0x180151b8b`
- `gdiplus!GdipDeleteGraphics` at `0x180151c82`
- `gdiplus!GdipDeleteGraphics` at `0x180151d2c`
- `gdiplus!GdipSetInterpolationMode` at `0x18015160d`
- `gdiplus!GdipSetInterpolationMode` at `0x180151710`
- `gdiplus!GdipSetInterpolationMode` at `0x180151c11`
- `gdiplus!GdipSetInterpolationMode` at `0x18015160d`
- `gdiplus!GdipSetInterpolationMode` at `0x180151710`
- `gdiplus!GdipSetInterpolationMode` at `0x180151c11`
- `gdiplus!GdipGetImageType` at `0x1801514a1`
- `gdiplus!GdipGetImageType` at `0x1801514a1`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18015185f`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18015185f`
- `gdiplus!GdipGetImageBounds` at `0x180151568`
- `gdiplus!GdipGetImageBounds` at `0x180151568`
- `gdiplus!GdipCreatePath` at `0x180151cd5`
- `gdiplus!GdipCreatePath` at `0x180151cd5`
- `gdiplus!GdipDeletePath` at `0x180151d43`
- `gdiplus!GdipDeletePath` at `0x180151d43`
- `gdiplus!GdipDeleteRegion` at `0x180151d39`
- `gdiplus!GdipDeleteRegion` at `0x180151d39`
- `gdiplus!GdipDeleteBrush` at `0x180151a66`
- `gdiplus!GdipDeleteBrush` at `0x180151b83`
- `gdiplus!GdipDeleteBrush` at `0x180151a66`
- `gdiplus!GdipDeleteBrush` at `0x180151b83`
- `gdiplus!GdipCreateSolidFill` at `0x180151a29`
- `gdiplus!GdipCreateSolidFill` at `0x180151a29`
- `gdiplus!GdipSetClipRegion` at `0x180151d24`
- `gdiplus!GdipSetClipRegion` at `0x180151d24`
- `gdiplus!GdipSaveGraphics` at `0x180151ca0`
- `gdiplus!GdipSaveGraphics` at `0x180151ca0`
- `gdiplus!GdipRestoreGraphics` at `0x180151d81`
- `gdiplus!GdipRestoreGraphics` at `0x180151d81`
- `gdiplus!GdipCreateImageAttributes` at `0x180151436`
- `gdiplus!GdipCreateImageAttributes` at `0x180151436`
- `gdiplus!GdipDisposeImageAttributes` at `0x180151646`
- `gdiplus!GdipDisposeImageAttributes` at `0x180151a79`
- `gdiplus!GdipDisposeImageAttributes` at `0x180151646`
- `gdiplus!GdipDisposeImageAttributes` at `0x180151a79`
- `gdiplus!GdipFillPolygon` at `0x180151a49`
- `gdiplus!GdipFillPolygon` at `0x180151a49`
- `gdiplus!GdipConvertToEmfPlus` at `0x1801517c9`
- `gdiplus!GdipConvertToEmfPlus` at `0x1801517c9`
- `gdiplus!GdipGetInterpolationMode` at `0x1801516ec`
- `gdiplus!GdipGetInterpolationMode` at `0x180151be4`
- `gdiplus!GdipGetInterpolationMode` at `0x1801516ec`
- `gdiplus!GdipGetInterpolationMode` at `0x180151be4`
- `gdiplus!GdipDrawImageRect` at `0x180151d71`
- `gdiplus!GdipDrawImageRect` at `0x180151d71`
- `gdiplus!GdipRecordMetafile` at `0x180151847`
- `gdiplus!GdipRecordMetafile` at `0x180151847`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x1801516cc`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x180151786`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x1801516cc`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x180151786`

## pseudocode

```c

```
