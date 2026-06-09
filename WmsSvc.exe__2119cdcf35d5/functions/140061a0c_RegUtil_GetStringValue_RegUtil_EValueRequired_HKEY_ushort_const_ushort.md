# RegUtil::GetStringValue(RegUtil::EValueRequired,HKEY__ *,ushort const *,ushort * *)

- ea: `0x140061a0c`
- end: `0x140061cde`
- name: `?GetStringValue@RegUtil@@YAJW4EValueRequired@1@PEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `722`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140002a0c`
- `0x14001a290`
- `0x14002933c`
- `0x14002eaa0`
- `0x14002feb4`
- `0x1400331d8`
- `0x140035158`
- `0x14004f690`
- `0x14004f8f0`
- `0x1400532b0`
- `0x140066ac8`
- `0x1400675d8`
- `0x14006d494`
- `0x14007490c`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140061a0c`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x140061a55`
- `ADVAPI32!RegGetValueW` at `0x140061c44`
- `ADVAPI32!RegGetValueW` at `0x140061a55`
- `ADVAPI32!RegGetValueW` at `0x140061c44`
- `KERNEL32!IsDebuggerPresent` at `0x140061ab9`
- `KERNEL32!IsDebuggerPresent` at `0x140061b66`
- `KERNEL32!IsDebuggerPresent` at `0x140061be4`
- `KERNEL32!IsDebuggerPresent` at `0x140061c93`
- `KERNEL32!IsDebuggerPresent` at `0x140061ab9`
- `KERNEL32!IsDebuggerPresent` at `0x140061b66`
- `KERNEL32!IsDebuggerPresent` at `0x140061be4`
- `KERNEL32!IsDebuggerPresent` at `0x140061c93`

## string_xrefs

- `0x140061a96`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140061b4e`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140061bbd`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140061c70`: `termsrv\wms\src\common\srcutils\registry.cpp`

## pseudocode

```c

```
