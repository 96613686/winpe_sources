# Windows::Internal::CPopupWindowImpl::_ComputeLayout(Windows::UI::Immersive::CConstraint const &,bool)

- ea: `0x1800209f0`
- end: `0x180020ea6`
- name: `?_ComputeLayout@CPopupWindowImpl@Internal@Windows@@AEAAXAEBVCConstraint@Immersive@UI@3@_N@Z`
- size: `1206`
- prototype: `void __fastcall(Windows::Internal::CPopupWindowImpl *__hidden this, const struct Windows::UI::Immersive::CConstraint *, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800207b0`
- `0x1800926b8`

## callees

- `0x1800209f0`
- `0x180020eac`
- `0x1800210b4`
- `0x180021358`
- `0x180044cb8`
- `0x180050ba0`
- `0x18007fd38`
- `0x1800d98f8`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180020b3d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180020b3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180020b53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180020b53`
- `USER32!MonitorFromRect` at `0x180020b17`
- `USER32!MonitorFromRect` at `0x180020b17`
- `USER32!IsRectEmpty` at `0x180020c2d`
- `USER32!IsRectEmpty` at `0x180020c2d`
- `USER32!GetWindowRect` at `0x180020bbf`
- `USER32!GetWindowRect` at `0x180020bbf`
- `api-ms-win-shcore-scaling-l1-1-1!GetScaleFactorForMonitor` at `0x180020b29`
- `api-ms-win-shcore-scaling-l1-1-1!GetScaleFactorForMonitor` at `0x180020b29`
- `DUI70!?GetWidth@Element@DirectUI@@QEAAHXZ` at `0x180020d77`
- `DUI70!?GetWidth@Element@DirectUI@@QEAAHXZ` at `0x180020d77`
- `DUI70!?SetX@Element@DirectUI@@QEAAJH@Z` at `0x180020d8b`
- `DUI70!?SetX@Element@DirectUI@@QEAAJH@Z` at `0x180020d8b`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180020a60`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180020a60`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180020a54`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180020a54`
- `DUI70!EnableAnimations` at `0x180020d96`
- `DUI70!EnableAnimations` at `0x180020d96`
- `DUI70!DisableAnimations` at `0x180020c90`
- `DUI70!DisableAnimations` at `0x180020c90`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x180020cf6`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x180020d11`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x180020cf6`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x180020d11`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x180020d02`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x180020d20`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x180020d02`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x180020d20`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180020c99`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180020c99`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180020a9a`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180020cc7`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180020a9a`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180020cc7`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180020c85`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180020db8`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180020c85`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180020db8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180020ce1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180020d4e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180020ce1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180020d4e`
- `DUI70!StrToID` at `0x180020cd5`
- `DUI70!StrToID` at `0x180020d42`
- `DUI70!StrToID` at `0x180020cd5`
- `DUI70!StrToID` at `0x180020d42`
- `DUser!SetWindowResizeFlag` at `0x180020caf`
- `DUser!SetWindowResizeFlag` at `0x180020da6`
- `DUser!SetWindowResizeFlag` at `0x180020caf`
- `DUser!SetWindowResizeFlag` at `0x180020da6`

## pseudocode

```c

```
