# WunderBar::CreateWunderBar(HWND__ *,IExplorerUISite *,IExplorerFrame *,IRenAccessExplorerFrame *,IExplorerNamespace *)

- ea: `0x1401f20d8`
- end: `0x1401f2b7b`
- name: `?CreateWunderBar@WunderBar@@QEAAJPEAUHWND__@@PEAUIExplorerUISite@@PEAUIExplorerFrame@@PEAUIRenAccessExplorerFrame@@PEAUIExplorerNamespace@@@Z`
- size: `2723`
- prototype: `__int64 __usercall@<rax>(WunderBar *__hidden this@<rcx>, HWND@<rdx>, struct IExplorerUISite *@<r8>, struct IExplorerFrame *@<r9>, struct IRenAccessExplorerFrame *, struct IExplorerNamespace *)`
- caller_count: `1`
- callee_count: `40`
- tags: `loader_planting`

## callers

- `0x1400aca80`

## callees

- `0x14001f620`
- `0x14009bcdc`
- `0x1400da620`
- `0x1400db960`
- `0x1400dd620`
- `0x1400e2be8`
- `0x1400e3b28`
- `0x1400f7b7c`
- `0x1400f80a8`
- `0x1400f835c`
- `0x1400f83f0`
- `0x140103fac`
- `0x1401b2b90`
- `0x1401c3f7c`
- `0x1401c4414`
- `0x1401f20d8`
- `0x1401f2b7c`
- `0x1401f2c1c`
- `0x1401f2cbc`
- `0x1401f2d2c`
- `0x1401f2d5c`
- `0x14020b1d0`
- `0x14020b97c`
- `0x14020bd70`
- `0x140242d8c`
- `0x140244860`
- `0x140258654`
- `0x1402c99f8`
- `0x1402cf6ec`
- `0x1402cf914`
- `0x1402cf944`
- `0x1402cf974`
- `0x1402d078c`
- `0x1402d2d10`
- `0x1402edfbc`
- `0x1402ee9c0`
- `0x14044a370`
- `0x1404d3a88`
- `0x1405049f0`
- `0x1407e9990`

## import_xrefs

- `KERNEL32!FindAtomW` at `0x1401f27f7`
- `KERNEL32!FindAtomW` at `0x1401f27f7`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f21b7`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f22b6`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f22e7`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f242c`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f245d`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f2ae3`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f21b7`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f22b6`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f22e7`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f242c`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f245d`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f2ae3`
- `USER32!SetWindowLongPtrA` at `0x1401f2573`
- `USER32!SetWindowLongPtrA` at `0x1401f2573`
- `Mso98Win32Client!__imp_?MsoHrLoadWunderBarStyles@@YAJPEAPEAVValue@NetUI@@@Z` at `0x1401f23a1`
- `Mso98Win32Client!__imp_?MsoHrLoadWunderBarStyles@@YAJPEAPEAVValue@NetUI@@@Z` at `0x1401f23a1`
- `mso40uiWin32Client!__imp_?GetPadding@Element@NetUI@@QEBAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1401f28ba`
- `mso40uiWin32Client!__imp_?GetPadding@Element@NetUI@@QEBAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1401f28ba`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1401f24a8`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1401f24a8`
- `mso40uiWin32Client!__imp_?EndDefer@Node@NetUI@@SAXXZ` at `0x1401f2432`
- `mso40uiWin32Client!__imp_?EndDefer@Node@NetUI@@SAXXZ` at `0x1401f2463`
- `mso40uiWin32Client!__imp_?EndDefer@Node@NetUI@@SAXXZ` at `0x1401f29aa`
- `mso40uiWin32Client!__imp_?EndDefer@Node@NetUI@@SAXXZ` at `0x1401f2432`
- `mso40uiWin32Client!__imp_?EndDefer@Node@NetUI@@SAXXZ` at `0x1401f2463`
- `mso40uiWin32Client!__imp_?EndDefer@Node@NetUI@@SAXXZ` at `0x1401f29aa`
- `mso40uiWin32Client!__imp_?Destroy@NUIDocument@NetUI@@QEAAXXZ` at `0x1401f2b0b`
- `mso40uiWin32Client!__imp_?Destroy@NUIDocument@NetUI@@QEAAXXZ` at `0x1401f2b0b`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x1401f21a4`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x1401f21a4`
- `mso40uiWin32Client!__imp_?FindSelfOrDescendent@Element@NetUI@@QEBAPEBV12@G@Z` at `0x1401f2803`
- `mso40uiWin32Client!__imp_?FindSelfOrDescendent@Element@NetUI@@QEBAPEBV12@G@Z` at `0x1401f2803`
- `mso40uiWin32Client!__imp_?CreateDocumentWindow@NUIDocument@NetUI@@SAJPEAUHINSTANCE__@@PEAUHWND__@@HHHHKIPEAVValue@2@PEAPEAV12@@Z` at `0x1401f2419`
- `mso40uiWin32Client!__imp_?CreateDocumentWindow@NUIDocument@NetUI@@SAJPEAUHINSTANCE__@@PEAUHWND__@@HHHHKIPEAVValue@2@PEAPEAV12@@Z` at `0x1401f2419`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@HWNDElement@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x1401f272f`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@HWNDElement@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x1401f277f`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@HWNDElement@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x1401f27c4`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@HWNDElement@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x1401f272f`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@HWNDElement@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x1401f277f`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@HWNDElement@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x1401f27c4`
- `mso40uiWin32Client!__imp_?FInitialized@NUIDocument@NetUI@@SA_NXZ` at `0x1401f21c5`
- `mso40uiWin32Client!__imp_?FInitialized@NUIDocument@NetUI@@SA_NXZ` at `0x1401f21c5`
- `mso40uiWin32Client!__imp_?AddDragDropHandler@HWNDElement@NetUI@@QEAAJPEAUIDragDropHandler@2@@Z` at `0x1401f275f`
- `mso40uiWin32Client!__imp_?AddDragDropHandler@HWNDElement@NetUI@@QEAAJPEAUIDragDropHandler@2@@Z` at `0x1401f275f`
- `mso40uiWin32Client!__imp_?SetNativeHWNDHost@NUIDocument@NetUI@@QEAAPEAVNativeHWNDHost@2@PEAV32@@Z` at `0x1401f25a5`
- `mso40uiWin32Client!__imp_?SetNativeHWNDHost@NUIDocument@NetUI@@QEAAPEAVNativeHWNDHost@2@PEAV32@@Z` at `0x1401f25a5`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1401f2440`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1401f2726`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1401f2776`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1401f27bb`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1401f2440`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1401f2726`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1401f2776`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1401f27bb`
- `mso40uiWin32Client!__imp_?AddEnterpriseDropTargetHandler@HWNDElement@NetUI@@QEAAJPEAUIEnterpriseDropTargetHandler@2@@Z` at `0x1401f27b2`
- `mso40uiWin32Client!__imp_?AddEnterpriseDropTargetHandler@HWNDElement@NetUI@@QEAAJPEAUIEnterpriseDropTargetHandler@2@@Z` at `0x1401f27b2`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f26d9`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f2820`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f284a`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f285d`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f2880`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f28cd`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f28f0`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f2913`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f2936`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f26d9`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f2820`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f284a`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f285d`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f2880`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f28cd`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f28f0`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f2913`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f2936`
- `mso40uiWin32Client!__imp_?OpenResourceA@NUIDocument@NetUI@@QEAA_NPEAUHINSTANCE__@@I0@Z` at `0x1401f258c`
- `mso40uiWin32Client!__imp_?OpenResourceA@NUIDocument@NetUI@@QEAA_NPEAUHINSTANCE__@@I0@Z` at `0x1401f258c`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1401f2396`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1401f28ac`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1401f2b32`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1401f2b48`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1401f2396`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1401f28ac`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1401f2b32`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1401f2b48`
- `mso40uiWin32Client!__imp_?Initialize@NUIDocument@NetUI@@SAJXZ` at `0x1401f21cf`
- `mso40uiWin32Client!__imp_?Initialize@NUIDocument@NetUI@@SAJXZ` at `0x1401f21cf`
- `mso40uiWin32Client!__imp_?StartDefer@Node@NetUI@@SAXXZ` at `0x1401f23d0`
- `mso40uiWin32Client!__imp_?StartDefer@Node@NetUI@@SAXXZ` at `0x1401f23d0`
- `mso40uiWin32Client!__imp_?GetWindowHWND@NUIDocument@NetUI@@QEBAPEAUHWND__@@XZ` at `0x1401f2561`
- `mso40uiWin32Client!__imp_?GetWindowHWND@NUIDocument@NetUI@@QEBAPEAUHWND__@@XZ` at `0x1401f2561`
- `Mso20Win32Client!__imp_??1ScopeHolder@ActivityScope@Mso@@QEAA@XZ` at `0x1401f2b53`
- `Mso20Win32Client!__imp_??1ScopeHolder@ActivityScope@Mso@@QEAA@XZ` at `0x1401f2b53`
- `Mso20Win32Client!__imp_??0ScopeHolder@ActivityScope@Mso@@QEAA@KPEB_W_NW4Severity@Logging@2@@Z` at `0x1401f2139`
- `Mso20Win32Client!__imp_??0ScopeHolder@ActivityScope@Mso@@QEAA@KPEB_W_NW4Severity@Logging@2@@Z` at `0x1401f2139`
- `Mso20Win32Client!__imp_REFTRACK_ReleaseNoRef` at `0x1401f22fc`
- `Mso20Win32Client!__imp_REFTRACK_ReleaseNoRef` at `0x1401f22fc`

## string_xrefs

- `0x1401f2129`: `WunderBar::CreateWunderBar`

## pseudocode

```c

```
