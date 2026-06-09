# WunderBar::CreateWunderBar(HWND__ *,IExplorerUISite *,IExplorerFrame *,IRenAccessExplorerFrame *,IExplorerNamespace *)

- ea: `0x1401f18f8`
- end: `0x1401f239b`
- name: `?CreateWunderBar@WunderBar@@QEAAJPEAUHWND__@@PEAUIExplorerUISite@@PEAUIExplorerFrame@@PEAUIRenAccessExplorerFrame@@PEAUIExplorerNamespace@@@Z`
- size: `2723`
- prototype: `__int64 __usercall@<rax>(WunderBar *__hidden this@<rcx>, HWND@<rdx>, struct IExplorerUISite *@<r8>, struct IExplorerFrame *@<r9>, struct IRenAccessExplorerFrame *, struct IExplorerNamespace *)`
- caller_count: `1`
- callee_count: `40`
- tags: `loader_planting`

## callers

- `0x1400aca90`

## callees

- `0x14001f620`
- `0x14009bcdc`
- `0x1400da630`
- `0x1400db970`
- `0x1400dd630`
- `0x1400e2bf8`
- `0x1400e3ae8`
- `0x1400f7b3c`
- `0x1400f8068`
- `0x1400f831c`
- `0x1400f83b0`
- `0x140103f1c`
- `0x1401b2b70`
- `0x1401c3f5c`
- `0x1401c43f4`
- `0x1401f18f8`
- `0x1401f239c`
- `0x1401f243c`
- `0x1401f24dc`
- `0x1401f254c`
- `0x1401f257c`
- `0x14020a9f0`
- `0x14020b19c`
- `0x14020b590`
- `0x1402425ac`
- `0x140244080`
- `0x140257e44`
- `0x1402c9178`
- `0x1402cee6c`
- `0x1402cf094`
- `0x1402cf0c4`
- `0x1402cf0f4`
- `0x1402cff0c`
- `0x1402d2490`
- `0x1402ed73c`
- `0x1402ee140`
- `0x140449950`
- `0x1404d2f08`
- `0x140503f00`
- `0x1407e99f0`

## import_xrefs

- `KERNEL32!FindAtomW` at `0x1401f2017`
- `KERNEL32!FindAtomW` at `0x1401f2017`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f19d7`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f1ad6`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f1b07`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f1c4c`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f1c7d`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f2303`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f19d7`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f1ad6`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f1b07`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f1c4c`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f1c7d`
- `OLMAPI32!EtwTraceErrorTag` at `0x1401f2303`
- `USER32!SetWindowLongPtrA` at `0x1401f1d93`
- `USER32!SetWindowLongPtrA` at `0x1401f1d93`
- `Mso98Win32Client!__imp_?MsoHrLoadWunderBarStyles@@YAJPEAPEAVValue@NetUI@@@Z` at `0x1401f1bc1`
- `Mso98Win32Client!__imp_?MsoHrLoadWunderBarStyles@@YAJPEAPEAVValue@NetUI@@@Z` at `0x1401f1bc1`
- `mso40uiWin32Client!__imp_?GetPadding@Element@NetUI@@QEBAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1401f20da`
- `mso40uiWin32Client!__imp_?GetPadding@Element@NetUI@@QEBAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1401f20da`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1401f1cc8`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1401f1cc8`
- `mso40uiWin32Client!__imp_?EndDefer@Node@NetUI@@SAXXZ` at `0x1401f1c52`
- `mso40uiWin32Client!__imp_?EndDefer@Node@NetUI@@SAXXZ` at `0x1401f1c83`
- `mso40uiWin32Client!__imp_?EndDefer@Node@NetUI@@SAXXZ` at `0x1401f21ca`
- `mso40uiWin32Client!__imp_?EndDefer@Node@NetUI@@SAXXZ` at `0x1401f1c52`
- `mso40uiWin32Client!__imp_?EndDefer@Node@NetUI@@SAXXZ` at `0x1401f1c83`
- `mso40uiWin32Client!__imp_?EndDefer@Node@NetUI@@SAXXZ` at `0x1401f21ca`
- `mso40uiWin32Client!__imp_?Destroy@NUIDocument@NetUI@@QEAAXXZ` at `0x1401f232b`
- `mso40uiWin32Client!__imp_?Destroy@NUIDocument@NetUI@@QEAAXXZ` at `0x1401f232b`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x1401f19c4`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x1401f19c4`
- `mso40uiWin32Client!__imp_?FindSelfOrDescendent@Element@NetUI@@QEBAPEBV12@G@Z` at `0x1401f2023`
- `mso40uiWin32Client!__imp_?FindSelfOrDescendent@Element@NetUI@@QEBAPEBV12@G@Z` at `0x1401f2023`
- `mso40uiWin32Client!__imp_?CreateDocumentWindow@NUIDocument@NetUI@@SAJPEAUHINSTANCE__@@PEAUHWND__@@HHHHKIPEAVValue@2@PEAPEAV12@@Z` at `0x1401f1c39`
- `mso40uiWin32Client!__imp_?CreateDocumentWindow@NUIDocument@NetUI@@SAJPEAUHINSTANCE__@@PEAUHWND__@@HHHHKIPEAVValue@2@PEAPEAV12@@Z` at `0x1401f1c39`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@HWNDElement@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x1401f1f4f`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@HWNDElement@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x1401f1f9f`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@HWNDElement@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x1401f1fe4`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@HWNDElement@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x1401f1f4f`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@HWNDElement@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x1401f1f9f`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@HWNDElement@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x1401f1fe4`
- `mso40uiWin32Client!__imp_?FInitialized@NUIDocument@NetUI@@SA_NXZ` at `0x1401f19e5`
- `mso40uiWin32Client!__imp_?FInitialized@NUIDocument@NetUI@@SA_NXZ` at `0x1401f19e5`
- `mso40uiWin32Client!__imp_?AddDragDropHandler@HWNDElement@NetUI@@QEAAJPEAUIDragDropHandler@2@@Z` at `0x1401f1f7f`
- `mso40uiWin32Client!__imp_?AddDragDropHandler@HWNDElement@NetUI@@QEAAJPEAUIDragDropHandler@2@@Z` at `0x1401f1f7f`
- `mso40uiWin32Client!__imp_?SetNativeHWNDHost@NUIDocument@NetUI@@QEAAPEAVNativeHWNDHost@2@PEAV32@@Z` at `0x1401f1dc5`
- `mso40uiWin32Client!__imp_?SetNativeHWNDHost@NUIDocument@NetUI@@QEAAPEAVNativeHWNDHost@2@PEAV32@@Z` at `0x1401f1dc5`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1401f1c60`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1401f1f46`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1401f1f96`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1401f1fdb`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1401f1c60`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1401f1f46`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1401f1f96`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1401f1fdb`
- `mso40uiWin32Client!__imp_?AddEnterpriseDropTargetHandler@HWNDElement@NetUI@@QEAAJPEAUIEnterpriseDropTargetHandler@2@@Z` at `0x1401f1fd2`
- `mso40uiWin32Client!__imp_?AddEnterpriseDropTargetHandler@HWNDElement@NetUI@@QEAAJPEAUIEnterpriseDropTargetHandler@2@@Z` at `0x1401f1fd2`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f1ef9`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f2040`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f206a`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f207d`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f20a0`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f20ed`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f2110`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f2133`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f2156`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f1ef9`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f2040`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f206a`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f207d`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f20a0`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f20ed`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f2110`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f2133`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x1401f2156`
- `mso40uiWin32Client!__imp_?OpenResourceA@NUIDocument@NetUI@@QEAA_NPEAUHINSTANCE__@@I0@Z` at `0x1401f1dac`
- `mso40uiWin32Client!__imp_?OpenResourceA@NUIDocument@NetUI@@QEAA_NPEAUHINSTANCE__@@I0@Z` at `0x1401f1dac`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1401f1bb6`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1401f20cc`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1401f2352`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1401f2368`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1401f1bb6`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1401f20cc`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1401f2352`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1401f2368`
- `mso40uiWin32Client!__imp_?Initialize@NUIDocument@NetUI@@SAJXZ` at `0x1401f19ef`
- `mso40uiWin32Client!__imp_?Initialize@NUIDocument@NetUI@@SAJXZ` at `0x1401f19ef`
- `mso40uiWin32Client!__imp_?StartDefer@Node@NetUI@@SAXXZ` at `0x1401f1bf0`
- `mso40uiWin32Client!__imp_?StartDefer@Node@NetUI@@SAXXZ` at `0x1401f1bf0`
- `mso40uiWin32Client!__imp_?GetWindowHWND@NUIDocument@NetUI@@QEBAPEAUHWND__@@XZ` at `0x1401f1d81`
- `mso40uiWin32Client!__imp_?GetWindowHWND@NUIDocument@NetUI@@QEBAPEAUHWND__@@XZ` at `0x1401f1d81`
- `Mso20Win32Client!__imp_??1ScopeHolder@ActivityScope@Mso@@QEAA@XZ` at `0x1401f2373`
- `Mso20Win32Client!__imp_??1ScopeHolder@ActivityScope@Mso@@QEAA@XZ` at `0x1401f2373`
- `Mso20Win32Client!__imp_??0ScopeHolder@ActivityScope@Mso@@QEAA@KPEB_W_NW4Severity@Logging@2@@Z` at `0x1401f1959`
- `Mso20Win32Client!__imp_??0ScopeHolder@ActivityScope@Mso@@QEAA@KPEB_W_NW4Severity@Logging@2@@Z` at `0x1401f1959`
- `Mso20Win32Client!__imp_REFTRACK_ReleaseNoRef` at `0x1401f1b1c`
- `Mso20Win32Client!__imp_REFTRACK_ReleaseNoRef` at `0x1401f1b1c`

## string_xrefs

- `0x1401f1949`: `WunderBar::CreateWunderBar`

## pseudocode

```c

```
