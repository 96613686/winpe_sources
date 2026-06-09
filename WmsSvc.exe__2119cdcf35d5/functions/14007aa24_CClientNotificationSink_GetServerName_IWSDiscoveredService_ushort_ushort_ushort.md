# CClientNotificationSink::GetServerName(IWSDiscoveredService *,ushort * *,ushort * *,ushort * *)

- ea: `0x14007aa24`
- end: `0x14007ae1c`
- name: `?GetServerName@CClientNotificationSink@@AEAAJPEAUIWSDiscoveredService@@PEAPEAG11@Z`
- size: `1016`
- prototype: `__int64 __fastcall(PCWSTR *this, struct IWSDiscoveredService *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x14007a200`
- `0x14007b1e0`

## callees

- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007aa24`
- `0x14007cbaa`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14007aaa6`
- `KERNEL32!IsDebuggerPresent` at `0x14007ab5b`
- `KERNEL32!IsDebuggerPresent` at `0x14007abba`
- `KERNEL32!IsDebuggerPresent` at `0x14007ac3b`
- `KERNEL32!IsDebuggerPresent` at `0x14007acd6`
- `KERNEL32!IsDebuggerPresent` at `0x14007aaa6`
- `KERNEL32!IsDebuggerPresent` at `0x14007ab5b`
- `KERNEL32!IsDebuggerPresent` at `0x14007abba`
- `KERNEL32!IsDebuggerPresent` at `0x14007ac3b`
- `KERNEL32!IsDebuggerPresent` at `0x14007acd6`
- `DNSAPI!DnsValidateName_W` at `0x14007adc9`
- `DNSAPI!DnsValidateName_W` at `0x14007adc9`
- `SHLWAPI!StrCmpW` at `0x14007ad62`
- `SHLWAPI!StrCmpW` at `0x14007ad62`

## string_xrefs

- `0x14007aa8b`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007ab40`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007ab9f`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007ac20`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007acaf`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007aa66`: `pService`
- `0x14007aaae`: `pService`

## pseudocode

```c

```
