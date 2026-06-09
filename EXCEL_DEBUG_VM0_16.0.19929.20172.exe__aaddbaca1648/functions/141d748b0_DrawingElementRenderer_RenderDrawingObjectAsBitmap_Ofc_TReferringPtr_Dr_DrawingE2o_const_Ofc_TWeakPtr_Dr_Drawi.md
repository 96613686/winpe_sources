# DrawingElementRenderer::RenderDrawingObjectAsBitmap(Ofc::TReferringPtr<Dr::DrawingE2o> const &,Ofc::TWeakPtr<Dr::DrawingElement const> const &,GEL::ImageFormat,int,Ofc::TCntPtr<GEL::IImage const> &,Ofc::CRect &)

- ea: `0x141d748b0`
- end: `0x141d752f2`
- name: `?RenderDrawingObjectAsBitmap@DrawingElementRenderer@@QEAAJAEBV?$TReferringPtr@VDrawingE2o@Dr@@@Ofc@@AEBV?$TWeakPtr@$$CBVDrawingElement@Dr@@@3@W4ImageFormat@GEL@@HAEAV?$TCntPtr@$$CBUIImage@GEL@@@3@AEAVCRect@3@@Z`
- size: `2626`
- prototype: `__int64 __usercall@<rax>(DrawingElementRenderer *this@<rcx>, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x141d6f200`

## callees

- `0x1401bc1e4`
- `0x1402039d0`
- `0x1402357a0`
- `0x14023dc10`
- `0x14023dcc0`
- `0x140435880`
- `0x1408cc550`
- `0x1408cfed0`
- `0x1416035e0`
- `0x141d73860`
- `0x141d74150`
- `0x141d74230`
- `0x141d74330`
- `0x141d74580`
- `0x141d745d0`
- `0x141d746e0`
- `0x141d748b0`
- `0x141d75a40`
- `0x141d75b40`

## import_xrefs

- `gfx!?Create@IBitmapTarget@Gfx@@SA?AV?$TCntPtr@UIBitmapTarget@Gfx@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBV?$TConvertibleDPI2@M@2@W4AlphaMode@ARC@@I@Z` at `0x141d74d91`
- `gfx!?Create@IBitmapTarget@Gfx@@SA?AV?$TCntPtr@UIBitmapTarget@Gfx@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBV?$TConvertibleDPI2@M@2@W4AlphaMode@ARC@@I@Z` at `0x141d74d91`
- `oart!__imp_?GetViewInfo@View@Art@@QEBAAEBUInfo@12@XZ` at `0x141d74d33`
- `oart!__imp_?GetViewInfo@View@Art@@QEBAAEBUInfo@12@XZ` at `0x141d74d33`
- `oart!__imp_?FDrawToTarget@View@Art@@QEAA_NAEAUITarget@Gfx@@AEBUVector@GEL@@PEBUIAbortSignal@4@_NPEBUIShapeFilter@4@PEBUIShape@4@@Z` at `0x141d74f4c`
- `oart!__imp_?FDrawToTarget@View@Art@@QEAA_NAEAUITarget@Gfx@@AEBUVector@GEL@@PEBUIAbortSignal@4@_NPEBUIShapeFilter@4@PEBUIShape@4@@Z` at `0x141d74f4c`
- `oart!__imp_?GetDefaultContentRenderingPolicy@View@Art@@QEBA?AW4RenderingPolicy@Gfx@@XZ` at `0x141d74cb2`
- `oart!__imp_?GetDefaultContentRenderingPolicy@View@Art@@QEBA?AW4RenderingPolicy@Gfx@@XZ` at `0x141d74cb2`
- `oart!__imp_??0Info@View@Art@@QEAA@XZ` at `0x141d749f9`
- `oart!__imp_??0Info@View@Art@@QEAA@XZ` at `0x141d749f9`
- `oart!__imp_?GetViewInfo@View@Art@@QEBAXAEAUInfo@12@@Z` at `0x141d74a14`
- `oart!__imp_?GetViewInfo@View@Art@@QEBAXAEAUInfo@12@@Z` at `0x141d74a14`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x141d749d0`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x141d749d0`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74a91`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74b40`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74bd0`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74c60`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d75103`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d751af`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d75280`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74a91`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74b40`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74bd0`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74c60`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d75103`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d751af`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d75280`
- `mso40uiWin32Client!__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z` at `0x141d74e71`
- `mso40uiWin32Client!__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z` at `0x141d74e71`
- `mso40uiWin32Client!__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ` at `0x141d74fb4`
- `mso40uiWin32Client!__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ` at `0x141d74fb4`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x141d74a03`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x141d74ca9`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x141d74d2a`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x141d74f21`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x141d74a03`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x141d74ca9`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x141d74d2a`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x141d74f21`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x141d74fc2`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x141d74fc2`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d749c0`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74a83`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74aa0`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74aab`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74ab6`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74b32`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74b4e`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74b60`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74b6b`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74bc2`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74be0`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74beb`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74bf6`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74c4f`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74c6e`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74c80`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74c8b`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d750f5`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d75111`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d75120`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d7512c`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d751a0`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d751c0`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d751cc`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d751d7`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d75271`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d7528e`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d75299`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d752a4`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d752b3`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d752c4`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d749c0`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74a83`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74aa0`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74aab`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74ab6`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74b32`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74b4e`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74b60`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74b6b`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74bc2`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74be0`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74beb`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74bf6`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74c4f`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74c6e`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74c80`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d74c8b`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d750f5`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d75111`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d75120`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d7512c`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d751a0`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d751c0`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d751cc`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d751d7`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d75271`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d7528e`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d75299`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d752a4`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d752b3`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x141d752c4`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x141d7492e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x141d74942`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x141d749eb`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x141d74cc4`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x141d74db3`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x141d7492e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x141d74942`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x141d749eb`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x141d74cc4`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x141d74db3`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141d74e40`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141d74e40`

## pseudocode

```c

```
