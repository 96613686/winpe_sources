# GPIMAGEUTIL::FDraw(Gdiplus::GpImage &,MSODC const *,MSOBDRAWPARAM const *)

- ea: `0x1800fe2d0`
- end: `0x1800fecf6`
- name: `?FDraw@GPIMAGEUTIL@@SAHAEAVGpImage@Gdiplus@@PEBUMSODC@@PEBUMSOBDRAWPARAM@@@Z`
- size: `2598`
- prototype: `__int64 __fastcall(struct Gdiplus::GpImage *, const struct MSODC *, const struct MSOBDRAWPARAM *this)`
- caller_count: `8`
- callee_count: `19`
- tags: ``

## callers

- `0x1800fbdd0`
- `0x180228370`
- `0x18059c240`
- `0x180b41c84`
- `0x18117a568`
- `0x18125d7a0`
- `0x18125d860`
- `0x1812ac748`

## callees

- `0x180037480`
- `0x18005f23c`
- `0x18009b760`
- `0x18009c080`
- `0x1800acae0`
- `0x1800fd43c`
- `0x1800fd498`
- `0x1800fd560`
- `0x1800fd5f0`
- `0x1800fd6e8`
- `0x1800fe2d0`
- `0x1800fecf8`
- `0x180116160`
- `0x180239aa0`
- `0x18023c2e0`
- `0x180977f1c`
- `0x180a2fafc`
- `0x1812d2278`
- `0x1812d2744`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800fea76`
- `KERNEL32!SetLastError` at `0x1800fea76`
- `mso40uiWin32Client!__imp_?SetGraphicsRenderingOptions@@YAXPEAVGpGraphics@Gdiplus@@KK@Z` at `0x1800fe7aa`
- `mso40uiWin32Client!__imp_?SetGraphicsRenderingOptions@@YAXPEAVGpGraphics@Gdiplus@@KK@Z` at `0x1800fe7aa`
- `mso40uiWin32Client!__imp_??0FPState@@QEAA@K@Z` at `0x1800fe312`
- `mso40uiWin32Client!__imp_??0FPState@@QEAA@K@Z` at `0x1800fe312`
- `mso40uiWin32Client!__imp_?GetPrefs@GELPREF@@YAAEAUPREFS@1@XZ` at `0x1800fe407`
- `mso40uiWin32Client!__imp_?GetPrefs@GELPREF@@YAAEAUPREFS@1@XZ` at `0x1800fe463`
- `mso40uiWin32Client!__imp_?GetPrefs@GELPREF@@YAAEAUPREFS@1@XZ` at `0x1800fe407`
- `mso40uiWin32Client!__imp_?GetPrefs@GELPREF@@YAAEAUPREFS@1@XZ` at `0x1800fe463`
- `mso40uiWin32Client!__imp_?GetMetafile@MSODC@@QEBAPEAVGpMetafile@Gdiplus@@XZ` at `0x1800fe9c7`
- `mso40uiWin32Client!__imp_?GetMetafile@MSODC@@QEBAPEAVGpMetafile@Gdiplus@@XZ` at `0x1800fe9c7`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x1800fe583`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x1800fe9b7`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x1800fe583`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x1800fe9b7`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x1800fe32f`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x1800fe32f`
- `USER32!GetDC` at `0x1800fe741`
- `USER32!GetDC` at `0x1800fe741`
- `USER32!ReleaseDC` at `0x1800fecd6`
- `USER32!ReleaseDC` at `0x1800fecd6`
- `gdiplus!GdipDisposeImage` at `0x1800fe7d7`
- `gdiplus!GdipDisposeImage` at `0x1800feba4`
- `gdiplus!GdipDisposeImage` at `0x1800fecc6`
- `gdiplus!GdipDisposeImage` at `0x1800fe7d7`
- `gdiplus!GdipDisposeImage` at `0x1800feba4`
- `gdiplus!GdipDisposeImage` at `0x1800fecc6`
- `gdiplus!GdipDeleteGraphics` at `0x1800fe99e`
- `gdiplus!GdipDeleteGraphics` at `0x1800feabb`
- `gdiplus!GdipDeleteGraphics` at `0x1800febb2`
- `gdiplus!GdipDeleteGraphics` at `0x1800fec5c`
- `gdiplus!GdipDeleteGraphics` at `0x1800fe99e`
- `gdiplus!GdipDeleteGraphics` at `0x1800feabb`
- `gdiplus!GdipDeleteGraphics` at `0x1800febb2`
- `gdiplus!GdipDeleteGraphics` at `0x1800fec5c`
- `gdiplus!GdipSetInterpolationMode` at `0x1800fe53d`
- `gdiplus!GdipSetInterpolationMode` at `0x1800fe640`
- `gdiplus!GdipSetInterpolationMode` at `0x1800feb41`
- `gdiplus!GdipSetInterpolationMode` at `0x1800fe53d`
- `gdiplus!GdipSetInterpolationMode` at `0x1800fe640`
- `gdiplus!GdipSetInterpolationMode` at `0x1800feb41`
- `gdiplus!GdipGetImageType` at `0x1800fe3d1`
- `gdiplus!GdipGetImageType` at `0x1800fe3d1`
- `gdiplus!GdipGetImageGraphicsContext` at `0x1800fe78f`
- `gdiplus!GdipGetImageGraphicsContext` at `0x1800fe78f`
- `gdiplus!GdipGetImageBounds` at `0x1800fe498`
- `gdiplus!GdipGetImageBounds` at `0x1800fe498`
- `gdiplus!GdipCreatePath` at `0x1800fec05`
- `gdiplus!GdipCreatePath` at `0x1800fec05`
- `gdiplus!GdipDeletePath` at `0x1800fec73`
- `gdiplus!GdipDeletePath` at `0x1800fec73`
- `gdiplus!GdipDeleteRegion` at `0x1800fec69`
- `gdiplus!GdipDeleteRegion` at `0x1800fec69`
- `gdiplus!GdipDeleteBrush` at `0x1800fe996`
- `gdiplus!GdipDeleteBrush` at `0x1800feab3`
- `gdiplus!GdipDeleteBrush` at `0x1800fe996`
- `gdiplus!GdipDeleteBrush` at `0x1800feab3`
- `gdiplus!GdipCreateSolidFill` at `0x1800fe959`
- `gdiplus!GdipCreateSolidFill` at `0x1800fe959`
- `gdiplus!GdipSetClipRegion` at `0x1800fec54`
- `gdiplus!GdipSetClipRegion` at `0x1800fec54`
- `gdiplus!GdipSaveGraphics` at `0x1800febd0`
- `gdiplus!GdipSaveGraphics` at `0x1800febd0`
- `gdiplus!GdipRestoreGraphics` at `0x1800fecb1`
- `gdiplus!GdipRestoreGraphics` at `0x1800fecb1`
- `gdiplus!GdipCreateImageAttributes` at `0x1800fe366`
- `gdiplus!GdipCreateImageAttributes` at `0x1800fe366`
- `gdiplus!GdipDisposeImageAttributes` at `0x1800fe576`
- `gdiplus!GdipDisposeImageAttributes` at `0x1800fe9a9`
- `gdiplus!GdipDisposeImageAttributes` at `0x1800fe576`
- `gdiplus!GdipDisposeImageAttributes` at `0x1800fe9a9`
- `gdiplus!GdipFillPolygon` at `0x1800fe979`
- `gdiplus!GdipFillPolygon` at `0x1800fe979`
- `gdiplus!GdipConvertToEmfPlus` at `0x1800fe6f9`
- `gdiplus!GdipConvertToEmfPlus` at `0x1800fe6f9`
- `gdiplus!GdipGetInterpolationMode` at `0x1800fe61c`
- `gdiplus!GdipGetInterpolationMode` at `0x1800feb14`
- `gdiplus!GdipGetInterpolationMode` at `0x1800fe61c`
- `gdiplus!GdipGetInterpolationMode` at `0x1800feb14`
- `gdiplus!GdipDrawImageRect` at `0x1800feca1`
- `gdiplus!GdipDrawImageRect` at `0x1800feca1`
- `gdiplus!GdipRecordMetafile` at `0x1800fe777`
- `gdiplus!GdipRecordMetafile` at `0x1800fe777`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x1800fe5fc`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x1800fe6b6`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x1800fe5fc`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x1800fe6b6`

## pseudocode

```c

```
