# SafeOuterMessagePump(void *,HWND__ *)

- ea: `0x1400686c8`
- end: `0x14006887b`
- name: `?SafeOuterMessagePump@@YAJPEAXPEAUHWND__@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(void *, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140025330`

## callees

- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x1400686c8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140068728`
- `KERNEL32!GetLastError` at `0x140068728`
- `KERNEL32!IsDebuggerPresent` at `0x14006877e`
- `KERNEL32!IsDebuggerPresent` at `0x14006877e`
- `USER32!DispatchMessageW` at `0x1400687c9`
- `USER32!DispatchMessageW` at `0x140068833`
- `USER32!DispatchMessageW` at `0x1400687c9`
- `USER32!DispatchMessageW` at `0x140068833`
- `USER32!PeekMessageW` at `0x1400687df`
- `USER32!PeekMessageW` at `0x140068849`
- `USER32!PeekMessageW` at `0x1400687df`
- `USER32!PeekMessageW` at `0x140068849`
- `USER32!TranslateMessage` at `0x1400687bf`
- `USER32!TranslateMessage` at `0x140068829`
- `USER32!TranslateMessage` at `0x1400687bf`
- `USER32!TranslateMessage` at `0x140068829`
- `USER32!MsgWaitForMultipleObjects` at `0x140068712`
- `USER32!MsgWaitForMultipleObjects` at `0x140068712`

## string_xrefs

- `0x140068761`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x14006878c`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400687f2`: `termsrv\wms\src\common\srcutils\srcutils.cpp`

## pseudocode

```c

```
