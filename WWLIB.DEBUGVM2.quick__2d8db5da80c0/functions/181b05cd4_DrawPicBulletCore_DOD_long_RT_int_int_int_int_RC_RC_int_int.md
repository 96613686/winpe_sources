# DrawPicBulletCore(DOD *,long,RT &,int,int,int,int,RC *,RC *,int,int)

- ea: `0x181b05cd4`
- end: `0x181b069a5`
- name: `?DrawPicBulletCore@@YAXPEAVDOD@@JAEAVRT@@HHHHPEAURC@@2HH@Z`
- size: `3281`
- prototype: `void __usercall(struct DOD *@<rcx>, int@<edx>, struct RT *@<r8>, int@<r9d>, int, int, int, struct RC *, struct RC *, int, int)`
- caller_count: `7`
- callee_count: `33`
- tags: ``

## callers

- `0x180652f18`
- `0x180bedd04`
- `0x180df70e0`
- `0x180dfac60`
- `0x181134a94`
- `0x1819ac114`
- `0x181fdf0c0`

## callees

- `0x180030318`
- `0x18004fcd8`
- `0x18005263c`
- `0x18005d850`
- `0x1800721e4`
- `0x1800723b0`
- `0x180100c70`
- `0x180115c60`
- `0x18011cc78`
- `0x180207174`
- `0x180294a50`
- `0x1803766b0`
- `0x18037bb00`
- `0x180436dd0`
- `0x1804406b0`
- `0x1804c9874`
- `0x18056bb6c`
- `0x1806744b8`
- `0x1806cc788`
- `0x1809a6c08`
- `0x1809a6cb0`
- `0x1809a6d08`
- `0x180c05bdc`
- `0x180c2946c`
- `0x180cc1e00`
- `0x180e9aafc`
- `0x180f0fc50`
- `0x180f765f0`
- `0x180f76618`
- `0x180fdef50`
- `0x181b04e70`
- `0x181b05cd4`
- `0x181b069a8`

## import_xrefs

- `oart!__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x181b062a1`
- `oart!__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x181b062a1`
- `oart!__imp_?AddE2o@View@Art@@QEAA?AV?$TWeakPtr@VIE2oView@Art@@@Ofc@@AEBV?$TWeakPtr@VIE2o@Art@@@4@_N@Z` at `0x181b06693`
- `oart!__imp_?AddE2o@View@Art@@QEAA?AV?$TWeakPtr@VIE2oView@Art@@@Ofc@@AEBV?$TWeakPtr@VIE2o@Art@@@4@_N@Z` at `0x181b06693`
- `oart!__imp_?FDrawToTarget@View@Art@@QEAA_NAEAUITarget@Gfx@@AEBUVector@GEL@@1PEBUIAbortSignal@4@_NPEBUIShapeFilter@4@PEBUIShape@4@@Z` at `0x181b06793`
- `oart!__imp_?FDrawToTarget@View@Art@@QEAA_NAEAUITarget@Gfx@@AEBUVector@GEL@@1PEBUIAbortSignal@4@_NPEBUIShapeFilter@4@PEBUIShape@4@@Z` at `0x181b06793`
- `oart!__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x181b062e0`
- `oart!__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x181b062e0`
- `oart!__imp_?Validate@View@Art@@QEAA_NXZ` at `0x181b066b2`
- `oart!__imp_?Validate@View@Art@@QEAA_NXZ` at `0x181b066b2`
- `oart!__imp_??0Info@View@Art@@QEAA@XZ` at `0x181b06537`
- `oart!__imp_??0Info@View@Art@@QEAA@XZ` at `0x181b06537`
- `oart!__imp_?Create@View@Art@@SA?AV?$TSharedPtr@VView@Art@@@Ofc@@AEBUInfo@12@AEBUITarget@Gfx@@@Z` at `0x181b06671`
- `oart!__imp_?Create@View@Art@@SA?AV?$TSharedPtr@VView@Art@@@Ofc@@AEBUInfo@12@AEBUITarget@Gfx@@@Z` at `0x181b06671`
- `oart!__imp_?GetBlip@ImageHostingE2o@Art@@QEBAAEBVBlip@2@XZ` at `0x181b05fad`
- `oart!__imp_?GetBlip@ImageHostingE2o@Art@@QEBAAEBVBlip@2@XZ` at `0x181b05fad`
- `oart!__imp_?GetViewInfo@View@Art@@QEBAXAEAUInfo@12@@Z` at `0x181b06556`
- `oart!__imp_?GetViewInfo@View@Art@@QEBAXAEAUInfo@12@@Z` at `0x181b06556`
- `oart!__imp_?GetImage@Blip@Art@@QEBA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@XZ` at `0x181b05fbe`
- `oart!__imp_?GetImage@Blip@Art@@QEBA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@XZ` at `0x181b05fbe`
- `KERNEL32!MulDiv` at `0x181b06043`
- `KERNEL32!MulDiv` at `0x181b0608b`
- `KERNEL32!MulDiv` at `0x181b06043`
- `KERNEL32!MulDiv` at `0x181b0608b`
- `KERNEL32!TlsGetValue` at `0x181b0621b`
- `KERNEL32!TlsGetValue` at `0x181b0621b`
- `gfx!?Create@IDCTarget@Gfx@@SA?AV?$TCntPtr@UIDCTarget@Gfx@@@Mso@@PEAUHDC__@@W4AlphaMode@ARC@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x181b06658`
- `gfx!?Create@IDCTarget@Gfx@@SA?AV?$TCntPtr@UIDCTarget@Gfx@@@Mso@@PEAUHDC__@@W4AlphaMode@ARC@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x181b06658`
- `MSO!__imp_?MsoPidgFromHsp@@YAPEAUIMsoDrawing@@PEAUMSOSP@@@Z` at `0x181b061a3`
- `MSO!__imp_?MsoPidgFromHsp@@YAPEAUIMsoDrawing@@PEAUMSOSP@@@Z` at `0x181b061a3`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x181b05f12`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x181b05f12`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b05f22`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b0669e`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b05f22`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b0669e`
- `mso40uiWin32Client!__imp_?MsoDestroyDc@@YAXPEAUMSODC@@@Z` at `0x181b06924`
- `mso40uiWin32Client!__imp_?MsoDestroyDc@@YAXPEAUMSODC@@@Z` at `0x181b06924`
- `mso40uiWin32Client!__imp_??0MSODC@@QEAA@XZ` at `0x181b05da6`
- `mso40uiWin32Client!__imp_??0MSODC@@QEAA@XZ` at `0x181b05da6`
- `mso40uiWin32Client!__imp_?MsoFillDcObj@@YAXPEAUMSODC@@PEAUHDC__@@W4MSOGELDCINFO@@PEAUHPALETTE__@@KP6AHPEAX@Z4K@Z` at `0x181b068d6`
- `mso40uiWin32Client!__imp_?MsoFillDcObj@@YAXPEAUMSODC@@PEAUHDC__@@W4MSOGELDCINFO@@PEAUHPALETTE__@@KP6AHPEAX@Z4K@Z` at `0x181b068d6`
- `mso40uiWin32Client!__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z` at `0x181b06701`
- `mso40uiWin32Client!__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z` at `0x181b06701`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x181b05f58`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x181b05f58`
- `mso40uiWin32Client!__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ` at `0x181b067d2`
- `mso40uiWin32Client!__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ` at `0x181b067d2`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x181b05fa4`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x181b06545`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x181b0667d`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x181b066a9`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x181b06756`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x181b05fa4`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x181b06545`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x181b0667d`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x181b066a9`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x181b06756`
- `mso40uiWin32Client!__imp_??1MSODC@@QEAA@XZ` at `0x181b06141`
- `mso40uiWin32Client!__imp_??1MSODC@@QEAA@XZ` at `0x181b0695e`
- `mso40uiWin32Client!__imp_??1MSODC@@QEAA@XZ` at `0x181b06141`
- `mso40uiWin32Client!__imp_??1MSODC@@QEAA@XZ` at `0x181b0695e`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x181b067e0`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x181b067e0`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b05f66`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b060ca`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b060d5`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b06128`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b06133`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b06151`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b0683e`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b06891`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b0694f`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b05f66`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b060ca`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b060d5`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b06128`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b06133`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b06151`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b0683e`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b06891`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x181b0694f`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x181b066ce`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x181b066ce`
- `Mso20Win32Client!__imp_?MsoOffsetRect@Platform@Mso@@YAHPEAUtagRECT@@HH@Z` at `0x181b0645b`
- `Mso20Win32Client!__imp_?MsoOffsetRect@Platform@Mso@@YAHPEAUtagRECT@@HH@Z` at `0x181b0647b`
- `Mso20Win32Client!__imp_?MsoOffsetRect@Platform@Mso@@YAHPEAUtagRECT@@HH@Z` at `0x181b064df`
- `Mso20Win32Client!__imp_?MsoOffsetRect@Platform@Mso@@YAHPEAUtagRECT@@HH@Z` at `0x181b0645b`
- `Mso20Win32Client!__imp_?MsoOffsetRect@Platform@Mso@@YAHPEAUtagRECT@@HH@Z` at `0x181b0647b`
- `Mso20Win32Client!__imp_?MsoOffsetRect@Platform@Mso@@YAHPEAUtagRECT@@HH@Z` at `0x181b064df`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x181b05e9c`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x181b064fb`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x181b05e9c`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x181b064fb`

## pseudocode

```c

```
