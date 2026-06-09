# EDPNotificationHost::_ShowOverrideDialog(HWND__ *,EDP_POLICY_RESULT,ushort const *)

- ea: `0x1802e0bdc`
- end: `0x1802e0f24`
- name: `?_ShowOverrideDialog@EDPNotificationHost@@AEAAJPEAUHWND__@@W4EDP_POLICY_RESULT@@PEBG@Z`
- size: `840`
- prototype: `int __high(HWND, enum EDP_POLICY_RESULT, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1802e03dc`

## callees

- `0x180009dd0`
- `0x1800378dc`
- `0x18013db04`
- `0x180142e10`
- `0x1802e0bdc`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802e0e4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802e0e4f`
- `USER32!MonitorFromWindow` at `0x1802e0ce9`
- `USER32!MonitorFromWindow` at `0x1802e0ce9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802e0c4e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802e0c4e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x1802e0e87`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x1802e0e87`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x1802e0e77`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x1802e0e77`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x1802e0e39`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x1802e0eb9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x1802e0e39`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x1802e0eb9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x1802e0d3d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x1802e0d3d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x1802e0c67`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x1802e0c67`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x1802e0d53`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x1802e0d53`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetMessageW` at `0x1802e0e9f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetMessageW` at `0x1802e0e9f`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x1802e0d13`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x1802e0d13`

## pseudocode

```c

```
