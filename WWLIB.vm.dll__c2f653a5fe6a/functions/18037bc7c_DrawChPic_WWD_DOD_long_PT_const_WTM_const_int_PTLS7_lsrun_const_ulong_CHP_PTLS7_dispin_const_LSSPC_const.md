# DrawChPic(WWD *,DOD *,long,PT const *,WTM const *,int,PTLS7::lsrun const *,ulong,CHP *,PTLS7::dispin const *,LSSPC const *)

- ea: `0x18037bc7c`
- end: `0x18037d887`
- name: `?DrawChPic@@YAXPEAVWWD@@PEAVDOD@@JPEBUPT@@PEBUWTM@@HPEBVlsrun@PTLS7@@KPEAUCHP@@PEBUdispin@6@PEBVLSSPC@@@Z`
- size: `7179`
- prototype: `void __usercall(struct WWD *@<rcx>, struct DOD *@<rdx>, int@<r8d>, const struct PT *@<r9>, const struct WTM *, char, const struct PTLS7::lsrun *, unsigned int, struct CHP *, const struct PTLS7::dispin *, const struct LSSPC *)`
- caller_count: `1`
- callee_count: `57`
- tags: ``

## callers

- `0x180378810`

## callees

- `0x18002c58c`
- `0x180058ffc`
- `0x180071590`
- `0x180072100`
- `0x1800721e4`
- `0x1800723b0`
- `0x1800ac0b4`
- `0x1800fbb40`
- `0x180100c70`
- `0x180102000`
- `0x18010b258`
- `0x180111f28`
- `0x180118a1c`
- `0x1801c2858`
- `0x1801f71f0`
- `0x1801f72f4`
- `0x1801f7ce4`
- `0x1801f8fdc`
- `0x1801f9fb8`
- `0x180207174`
- `0x180212380`
- `0x180212474`
- `0x18025b0e4`
- `0x1802946b8`
- `0x1803765f0`
- `0x1803766b0`
- `0x1803768a8`
- `0x180376ac0`
- `0x180376d80`
- `0x180376f58`
- `0x180376ff8`
- `0x18037bb00`
- `0x18037bbec`
- `0x18037bc7c`
- `0x18037d888`
- `0x18037dbc0`
- `0x18037dc1c`
- `0x18037dc38`
- `0x18043a2c4`
- `0x18043a3e0`
- `0x18043a784`
- `0x1804406b0`
- `0x1804c9874`
- `0x1806744b8`
- `0x1808e8cfc`
- `0x180959a50`
- `0x180a65fe0`
- `0x180aa3700`
- `0x180b39034`
- `0x180b390ac`

## import_xrefs

- `oart!__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18037cdac`
- `oart!__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18037cdac`
- `oart!__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18037cde8`
- `oart!__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18037cde8`
- `oart!__imp_?GetBlip@ImageHostingE2o@Art@@QEBAAEBVBlip@2@XZ` at `0x18037c8e9`
- `oart!__imp_?GetBlip@ImageHostingE2o@Art@@QEBAAEBVBlip@2@XZ` at `0x18037c8e9`
- `oart!__imp_?GetImage@Blip@Art@@QEBA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@XZ` at `0x18037c8fa`
- `oart!__imp_?GetImage@Blip@Art@@QEBA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@XZ` at `0x18037c8fa`
- `KERNEL32!GetLastError` at `0x18037d080`
- `KERNEL32!GetLastError` at `0x18037d080`
- `KERNEL32!SetLastError` at `0x18037d08e`
- `KERNEL32!SetLastError` at `0x18037d08e`
- `KERNEL32!TlsGetValue` at `0x18037c0cd`
- `KERNEL32!TlsGetValue` at `0x18037c12b`
- `KERNEL32!TlsGetValue` at `0x18037c39e`
- `KERNEL32!TlsGetValue` at `0x18037c3ad`
- `KERNEL32!TlsGetValue` at `0x18037c55a`
- `KERNEL32!TlsGetValue` at `0x18037d5b5`
- `KERNEL32!TlsGetValue` at `0x18037d5fc`
- `KERNEL32!TlsGetValue` at `0x18037d6e9`
- `KERNEL32!TlsGetValue` at `0x18037d7b9`
- `KERNEL32!TlsGetValue` at `0x18037c0cd`
- `KERNEL32!TlsGetValue` at `0x18037c12b`
- `KERNEL32!TlsGetValue` at `0x18037c39e`
- `KERNEL32!TlsGetValue` at `0x18037c3ad`
- `KERNEL32!TlsGetValue` at `0x18037c55a`
- `KERNEL32!TlsGetValue` at `0x18037d5b5`
- `KERNEL32!TlsGetValue` at `0x18037d5fc`
- `KERNEL32!TlsGetValue` at `0x18037d6e9`
- `KERNEL32!TlsGetValue` at `0x18037d7b9`
- `MSO!__imp_?MsoFDrawingInGroup@@YA_NPEBUIMsoDrawing@@PEBUIMsoDrawingGroup@@@Z` at `0x18037cfdb`
- `MSO!__imp_?MsoFDrawingInGroup@@YA_NPEBUIMsoDrawing@@PEBUIMsoDrawingGroup@@@Z` at `0x18037cfdb`
- `mso40uiWin32Client!__imp_?MsoInitSviAngle@@YAXPEAUMSOSVI@@JHH@Z` at `0x18037d202`
- `mso40uiWin32Client!__imp_?MsoInitSviAngle@@YAXPEAUMSOSVI@@JHH@Z` at `0x18037d202`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x18037c835`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x18037c835`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037c84b`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037c84b`
- `mso40uiWin32Client!__imp_??0MSODC@@QEAA@XZ` at `0x18037bdb5`
- `mso40uiWin32Client!__imp_??0MSODC@@QEAA@XZ` at `0x18037bdb5`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x18037c888`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x18037c888`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x18037c8e0`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x18037c8e0`
- `mso40uiWin32Client!__imp_??1MSODC@@QEAA@XZ` at `0x18037c810`
- `mso40uiWin32Client!__imp_??1MSODC@@QEAA@XZ` at `0x18037c9f4`
- `mso40uiWin32Client!__imp_??1MSODC@@QEAA@XZ` at `0x18037cb42`
- `mso40uiWin32Client!__imp_??1MSODC@@QEAA@XZ` at `0x18037d840`
- `mso40uiWin32Client!__imp_??1MSODC@@QEAA@XZ` at `0x18037c810`
- `mso40uiWin32Client!__imp_??1MSODC@@QEAA@XZ` at `0x18037c9f4`
- `mso40uiWin32Client!__imp_??1MSODC@@QEAA@XZ` at `0x18037cb42`
- `mso40uiWin32Client!__imp_??1MSODC@@QEAA@XZ` at `0x18037d840`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037c38a`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037c802`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037c896`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037c968`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037c976`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037c9e6`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037ca62`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037ca70`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037cacb`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037cb34`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037d832`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037c38a`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037c802`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037c896`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037c968`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037c976`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037c9e6`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037ca62`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037ca70`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037cacb`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037cb34`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18037d832`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18037c6ac`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18037c6ac`
- `Mso20Win32Client!__imp_?MsoInitAbort@@YAXPEAUMSOABORT@@@Z` at `0x18037d07a`
- `Mso20Win32Client!__imp_?MsoInitAbort@@YAXPEAUMSOABORT@@@Z` at `0x18037d07a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18037c67a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18037c67a`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18037c349`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18037c5a8`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18037c73c`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18037ccda`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18037c349`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18037c5a8`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18037c73c`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18037ccda`
- `Mso20Win32Client!__imp_?SendErrorTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x18037c698`
- `Mso20Win32Client!__imp_?SendErrorTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x18037c698`

## pseudocode

```c

```
