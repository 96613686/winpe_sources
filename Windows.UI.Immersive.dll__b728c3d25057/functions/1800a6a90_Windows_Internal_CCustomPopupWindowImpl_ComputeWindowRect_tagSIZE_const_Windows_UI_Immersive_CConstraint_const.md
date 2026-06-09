# Windows::Internal::CCustomPopupWindowImpl::_ComputeWindowRect(tagSIZE const &,Windows::UI::Immersive::CConstraint const &,bool)

- ea: `0x1800a6a90`
- end: `0x1800a6d1e`
- name: `?_ComputeWindowRect@CCustomPopupWindowImpl@Internal@Windows@@AEAA?AUtagRECT@@AEBUtagSIZE@@AEBVCConstraint@Immersive@UI@3@_N@Z`
- size: `654`
- prototype: `struct tagRECT *(Windows::Internal::CCustomPopupWindowImpl *__hidden this, struct tagRECT *__return_ptr __struct_ptr retstr, const struct tagSIZE *, const struct Windows::UI::Immersive::CConstraint *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800a686c`

## callees

- `0x18004882c`
- `0x180050ba0`
- `0x1800a5cb8`
- `0x1800a6a90`
- `0x1800e5010`

## import_xrefs

- `USER32!GetClientRect` at `0x1800a6b69`
- `USER32!GetClientRect` at `0x1800a6b69`
- `USER32!MonitorFromRect` at `0x1800a6acb`
- `USER32!MonitorFromRect` at `0x1800a6acb`
- `USER32!GetMonitorInfoW` at `0x1800a6b31`
- `USER32!GetMonitorInfoW` at `0x1800a6b31`
- `USER32!MapWindowPoints` at `0x1800a6b8c`
- `USER32!MapWindowPoints` at `0x1800a6b8c`

## pseudocode

```c

```
