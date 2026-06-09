# HwndUtils::SendWmGetObject(HWND__ *,UIA_TIMEOUTDATA const &,uint,__int64 *)

- ea: `0x1800daec8`
- end: `0x1800db243`
- name: `?SendWmGetObject@HwndUtils@@SAJPEAUHWND__@@AEBUUIA_TIMEOUTDATA@@IPEA_J@Z`
- size: `891`
- prototype: `__int64 __fastcall(HWND hWnd, const struct UIA_TIMEOUTDATA *, unsigned int, __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180057efc`
- `0x1800cb948`

## callees

- `0x18002f580`
- `0x1800daec8`
- `0x1800db24c`
- `0x1800db428`
- `0x1800ddef0`
- `0x1801e8320`
- `0x1802c3491`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db163`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800daf51`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800daf96`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800daf51`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800daf96`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageTimeoutW` at `0x1800daff7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageTimeoutW` at `0x1800db07b`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageTimeoutW` at `0x1800daff7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageTimeoutW` at `0x1800db07b`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800daf2d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800daf7c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800db1b5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800daf2d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800daf7c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800db1b5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetParent` at `0x1800daf66`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetParent` at `0x1800daf66`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x1800db14c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageW` at `0x1800db14c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x1800dafbc`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x1800dafbc`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800db117`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800db117`

## string_xrefs

- `0x1800db02a`: `onecore\windows\accessibletech\uiautomationcore\hwndutils.cpp`
- `0x1800db0a2`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x1800db189`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x1800db1ef`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x1800db226`: `onecore\windows\accessibletech\common\basichwndutils.cpp`

## pseudocode

```c

```
