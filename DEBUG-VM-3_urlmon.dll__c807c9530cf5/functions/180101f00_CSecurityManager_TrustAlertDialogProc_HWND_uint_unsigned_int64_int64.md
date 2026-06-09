# CSecurityManager::TrustAlertDialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180101f00`
- end: `0x1801021de`
- name: `?TrustAlertDialogProc@CSecurityManager@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `734`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180084f68`
- `0x18009b9dc`
- `0x1800ffd90`
- `0x180101ab4`
- `0x180101ba0`
- `0x180101f00`
- `0x18010b020`
- `0x180110654`
- `0x180118760`
- `0x180118858`
- `0x1801188d4`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18010219e`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18010219e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180101f7c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180101f7c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180101fb2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180101fb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180101f94`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180101f94`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x18010204c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x18010204c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x180101f60`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x18010201a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x180101f60`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x18010201a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x180102154`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x180102154`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x180101fe7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x180101fe7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180102175`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180102175`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x180102144`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x180102144`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1801020d9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1801020d9`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x180102039`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x180102039`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180101fde`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1801020ce`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180102139`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180101fde`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1801020ce`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180102139`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!CheckDlgButton` at `0x1801020c6`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!CheckDlgButton` at `0x1801020c6`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x180102000`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x180102000`

## pseudocode

```c

```
