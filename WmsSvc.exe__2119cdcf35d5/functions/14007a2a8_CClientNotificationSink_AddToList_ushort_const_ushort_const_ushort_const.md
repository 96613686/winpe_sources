# CClientNotificationSink::AddToList(ushort const *,ushort const *,ushort const *)

- ea: `0x14007a2a8`
- end: `0x14007a71c`
- name: `?AddToList@CClientNotificationSink@@AEAAJPEBG00@Z`
- size: `1140`
- prototype: `__int64 __fastcall(CClientNotificationSink *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14007a200`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x140015e1c`
- `0x140016268`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x14007a2a8`
- `0x14007be28`
- `0x14007c7c0`
- `0x14007e010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x14007a33a`
- `KERNEL32!GetTickCount64` at `0x14007a4b2`
- `KERNEL32!GetTickCount64` at `0x14007a33a`
- `KERNEL32!GetTickCount64` at `0x14007a4b2`
- `KERNEL32!IsDebuggerPresent` at `0x14007a3d3`
- `KERNEL32!IsDebuggerPresent` at `0x14007a569`
- `KERNEL32!IsDebuggerPresent` at `0x14007a61d`
- `KERNEL32!IsDebuggerPresent` at `0x14007a3d3`
- `KERNEL32!IsDebuggerPresent` at `0x14007a569`
- `KERNEL32!IsDebuggerPresent` at `0x14007a61d`
- `OLEAUT32!__imp_SysAllocString` at `0x14007a4f3`
- `OLEAUT32!__imp_SysAllocString` at `0x14007a501`
- `OLEAUT32!__imp_SysAllocString` at `0x14007a4f3`
- `OLEAUT32!__imp_SysAllocString` at `0x14007a501`
- `OLEAUT32!__imp_SysFreeString` at `0x14007a6e9`
- `OLEAUT32!__imp_SysFreeString` at `0x14007a6f2`
- `OLEAUT32!__imp_SysFreeString` at `0x14007a6e9`
- `OLEAUT32!__imp_SysFreeString` at `0x14007a6f2`
- `SHLWAPI!StrCmpW` at `0x14007a30c`
- `SHLWAPI!StrCmpW` at `0x14007a30c`

## string_xrefs

- `0x14007a3c4`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007a55a`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007a60e`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007a364`: `CClientNotificationSink::AddToList: Ignore notification as the server (%s) already exists in the list.\n`

## pseudocode

```c

```
