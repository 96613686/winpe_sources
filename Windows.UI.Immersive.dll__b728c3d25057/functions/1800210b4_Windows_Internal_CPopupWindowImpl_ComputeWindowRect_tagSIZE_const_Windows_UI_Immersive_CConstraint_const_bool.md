# Windows::Internal::CPopupWindowImpl::_ComputeWindowRect(tagSIZE const &,Windows::UI::Immersive::CConstraint const &,bool)

- ea: `0x1800210b4`
- end: `0x18002134f`
- name: `?_ComputeWindowRect@CPopupWindowImpl@Internal@Windows@@AEAA?AUtagRECT@@AEBUtagSIZE@@AEBVCConstraint@Immersive@UI@3@_N@Z`
- size: `667`
- prototype: `struct tagRECT *(Windows::Internal::CPopupWindowImpl *__hidden this, struct tagRECT *__return_ptr __struct_ptr retstr, const struct tagSIZE *, const struct Windows::UI::Immersive::CConstraint *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800209f0`

## callees

- `0x1800210b4`
- `0x18004882c`
- `0x180050ba0`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021111`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021111`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002112a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002112a`
- `USER32!GetClientRect` at `0x180021190`
- `USER32!GetClientRect` at `0x180021190`
- `USER32!MonitorFromRect` at `0x1800210ef`
- `USER32!MonitorFromRect` at `0x1800210ef`
- `USER32!GetMonitorInfoW` at `0x18002115f`
- `USER32!GetMonitorInfoW` at `0x18002115f`
- `USER32!MapWindowPoints` at `0x1800211b0`
- `USER32!MapWindowPoints` at `0x1800211b0`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180021183`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180021199`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180021183`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180021199`

## pseudocode

```c

```
