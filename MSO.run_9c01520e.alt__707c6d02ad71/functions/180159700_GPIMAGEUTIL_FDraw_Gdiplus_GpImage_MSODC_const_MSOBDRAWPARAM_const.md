# GPIMAGEUTIL::FDraw(Gdiplus::GpImage &,MSODC const *,MSOBDRAWPARAM const *)

- ea: `0x180159700`
- end: `0x18015a126`
- name: `?FDraw@GPIMAGEUTIL@@SAHAEAVGpImage@Gdiplus@@PEBUMSODC@@PEBUMSOBDRAWPARAM@@@Z`
- size: `2598`
- prototype: `__int64 __fastcall(struct Gdiplus::GpImage *, const struct MSODC *, const struct MSOBDRAWPARAM *this)`
- caller_count: `8`
- callee_count: `19`
- tags: ``

## callers

- `0x180150650`
- `0x180239670`
- `0x1803a25f0`
- `0x180b6949c`
- `0x181103aac`
- `0x1812186b0`
- `0x181218770`
- `0x1812600e4`

## callees

- `0x18001d310`
- `0x18008e1d0`
- `0x180159660`
- `0x180159700`
- `0x18015a128`
- `0x18015a1f0`
- `0x18015a24c`
- `0x18015a2e0`
- `0x18015aec0`
- `0x18015afb8`
- `0x18015cc40`
- `0x18015cce0`
- `0x180245fc8`
- `0x1803ecf30`
- `0x18046096c`
- `0x180485240`
- `0x1809e5f50`
- `0x181284908`
- `0x181284de0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180159ea6`
- `KERNEL32!SetLastError` at `0x180159ea6`
- `mso40uiWin32Client!__imp_?SetGraphicsRenderingOptions@@YAXPEAVGpGraphics@Gdiplus@@KK@Z` at `0x180159bda`
- `mso40uiWin32Client!__imp_?SetGraphicsRenderingOptions@@YAXPEAVGpGraphics@Gdiplus@@KK@Z` at `0x180159bda`
- `mso40uiWin32Client!__imp_??0FPState@@QEAA@K@Z` at `0x180159742`
- `mso40uiWin32Client!__imp_??0FPState@@QEAA@K@Z` at `0x180159742`
- `mso40uiWin32Client!__imp_?GetPrefs@GELPREF@@YAAEAUPREFS@1@XZ` at `0x180159837`
- `mso40uiWin32Client!__imp_?GetPrefs@GELPREF@@YAAEAUPREFS@1@XZ` at `0x180159893`
- `mso40uiWin32Client!__imp_?GetPrefs@GELPREF@@YAAEAUPREFS@1@XZ` at `0x180159837`
- `mso40uiWin32Client!__imp_?GetPrefs@GELPREF@@YAAEAUPREFS@1@XZ` at `0x180159893`
- `mso40uiWin32Client!__imp_?GetMetafile@MSODC@@QEBAPEAVGpMetafile@Gdiplus@@XZ` at `0x180159df7`
- `mso40uiWin32Client!__imp_?GetMetafile@MSODC@@QEBAPEAVGpMetafile@Gdiplus@@XZ` at `0x180159df7`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x1801599b3`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180159de7`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x1801599b3`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180159de7`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x18015975f`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x18015975f`
- `USER32!GetDC` at `0x180159b71`
- `USER32!GetDC` at `0x180159b71`
- `USER32!ReleaseDC` at `0x18015a106`
- `USER32!ReleaseDC` at `0x18015a106`
- `gdiplus!GdipDisposeImage` at `0x180159c07`
- `gdiplus!GdipDisposeImage` at `0x180159fd4`
- `gdiplus!GdipDisposeImage` at `0x18015a0f6`
- `gdiplus!GdipDisposeImage` at `0x180159c07`
- `gdiplus!GdipDisposeImage` at `0x180159fd4`
- `gdiplus!GdipDisposeImage` at `0x18015a0f6`
- `gdiplus!GdipDeleteGraphics` at `0x180159dce`
- `gdiplus!GdipDeleteGraphics` at `0x180159eeb`
- `gdiplus!GdipDeleteGraphics` at `0x180159fe2`
- `gdiplus!GdipDeleteGraphics` at `0x18015a08c`
- `gdiplus!GdipDeleteGraphics` at `0x180159dce`
- `gdiplus!GdipDeleteGraphics` at `0x180159eeb`
- `gdiplus!GdipDeleteGraphics` at `0x180159fe2`
- `gdiplus!GdipDeleteGraphics` at `0x18015a08c`
- `gdiplus!GdipSetInterpolationMode` at `0x18015996d`
- `gdiplus!GdipSetInterpolationMode` at `0x180159a70`
- `gdiplus!GdipSetInterpolationMode` at `0x180159f71`
- `gdiplus!GdipSetInterpolationMode` at `0x18015996d`
- `gdiplus!GdipSetInterpolationMode` at `0x180159a70`
- `gdiplus!GdipSetInterpolationMode` at `0x180159f71`
- `gdiplus!GdipGetImageType` at `0x180159801`
- `gdiplus!GdipGetImageType` at `0x180159801`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180159bbf`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180159bbf`
- `gdiplus!GdipGetImageBounds` at `0x1801598c8`
- `gdiplus!GdipGetImageBounds` at `0x1801598c8`
- `gdiplus!GdipCreatePath` at `0x18015a035`
- `gdiplus!GdipCreatePath` at `0x18015a035`
- `gdiplus!GdipDeletePath` at `0x18015a0a3`
- `gdiplus!GdipDeletePath` at `0x18015a0a3`
- `gdiplus!GdipDeleteRegion` at `0x18015a099`
- `gdiplus!GdipDeleteRegion` at `0x18015a099`
- `gdiplus!GdipDeleteBrush` at `0x180159dc6`
- `gdiplus!GdipDeleteBrush` at `0x180159ee3`
- `gdiplus!GdipDeleteBrush` at `0x180159dc6`
- `gdiplus!GdipDeleteBrush` at `0x180159ee3`
- `gdiplus!GdipCreateSolidFill` at `0x180159d89`
- `gdiplus!GdipCreateSolidFill` at `0x180159d89`
- `gdiplus!GdipSetClipRegion` at `0x18015a084`
- `gdiplus!GdipSetClipRegion` at `0x18015a084`
- `gdiplus!GdipSaveGraphics` at `0x18015a000`
- `gdiplus!GdipSaveGraphics` at `0x18015a000`
- `gdiplus!GdipRestoreGraphics` at `0x18015a0e1`
- `gdiplus!GdipRestoreGraphics` at `0x18015a0e1`
- `gdiplus!GdipCreateImageAttributes` at `0x180159796`
- `gdiplus!GdipCreateImageAttributes` at `0x180159796`
- `gdiplus!GdipDisposeImageAttributes` at `0x1801599a6`
- `gdiplus!GdipDisposeImageAttributes` at `0x180159dd9`
- `gdiplus!GdipDisposeImageAttributes` at `0x1801599a6`
- `gdiplus!GdipDisposeImageAttributes` at `0x180159dd9`
- `gdiplus!GdipFillPolygon` at `0x180159da9`
- `gdiplus!GdipFillPolygon` at `0x180159da9`
- `gdiplus!GdipConvertToEmfPlus` at `0x180159b29`
- `gdiplus!GdipConvertToEmfPlus` at `0x180159b29`
- `gdiplus!GdipGetInterpolationMode` at `0x180159a4c`
- `gdiplus!GdipGetInterpolationMode` at `0x180159f44`
- `gdiplus!GdipGetInterpolationMode` at `0x180159a4c`
- `gdiplus!GdipGetInterpolationMode` at `0x180159f44`
- `gdiplus!GdipDrawImageRect` at `0x18015a0d1`
- `gdiplus!GdipDrawImageRect` at `0x18015a0d1`
- `gdiplus!GdipRecordMetafile` at `0x180159ba7`
- `gdiplus!GdipRecordMetafile` at `0x180159ba7`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x180159a2c`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x180159ae6`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x180159a2c`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x180159ae6`

## pseudocode

```c

```
