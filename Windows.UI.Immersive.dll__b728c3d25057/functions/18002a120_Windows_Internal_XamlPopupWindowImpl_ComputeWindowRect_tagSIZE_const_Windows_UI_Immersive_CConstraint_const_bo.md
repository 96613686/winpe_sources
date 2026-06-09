# Windows::Internal::XamlPopupWindowImpl::_ComputeWindowRect(tagSIZE const &,Windows::UI::Immersive::CConstraint const &,bool)

- ea: `0x18002a120`
- end: `0x18002a3c5`
- name: `?_ComputeWindowRect@XamlPopupWindowImpl@Internal@Windows@@AEAA?AUtagRECT@@AEBUtagSIZE@@AEBVCConstraint@Immersive@UI@3@_N@Z`
- size: `677`
- prototype: `struct tagRECT *__fastcall(Windows::Internal::XamlPopupWindowImpl *__hidden this, struct tagRECT *__return_ptr __struct_ptr retstr, const struct tagSIZE *, const struct Windows::UI::Immersive::CConstraint *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180029c94`

## callees

- `0x18002a120`
- `0x1800341c0`
- `0x180047b28`
- `0x180050ba0`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002a17d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002a17d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a196`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a196`
- `USER32!GetClientRect` at `0x18002a20d`
- `USER32!GetClientRect` at `0x18002a20d`
- `USER32!MonitorFromRect` at `0x18002a15b`
- `USER32!MonitorFromRect` at `0x18002a15b`
- `USER32!GetMonitorInfoW` at `0x18002a1dd`
- `USER32!GetMonitorInfoW` at `0x18002a1dd`
- `USER32!MapWindowPoints` at `0x18002a22c`
- `USER32!MapWindowPoints` at `0x18002a22c`

## pseudocode

```c

```
