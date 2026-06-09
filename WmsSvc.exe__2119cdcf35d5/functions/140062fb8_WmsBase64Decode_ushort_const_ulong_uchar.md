# WmsBase64Decode(ushort const *,ulong *,uchar * *)

- ea: `0x140062fb8`
- end: `0x1400631e1`
- name: `?WmsBase64Decode@@YAJPEBGPEAKPEAPEAE@Z`
- size: `553`
- prototype: `__int64 __fastcall(LPCWSTR pszString, unsigned int *, unsigned __int8 **)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140002454`
- `0x140002a0c`
- `0x14003e19c`
- `0x14003e5c0`
- `0x1400633fc`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140062fb8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140063014`
- `KERNEL32!GetLastError` at `0x14006318f`
- `KERNEL32!GetLastError` at `0x140063014`
- `KERNEL32!GetLastError` at `0x14006318f`
- `KERNEL32!IsDebuggerPresent` at `0x14006306f`
- `KERNEL32!IsDebuggerPresent` at `0x140063125`
- `KERNEL32!IsDebuggerPresent` at `0x14006306f`
- `KERNEL32!IsDebuggerPresent` at `0x140063125`
- `CRYPT32!CryptStringToBinaryW` at `0x140063004`
- `CRYPT32!CryptStringToBinaryW` at `0x140063185`
- `CRYPT32!CryptStringToBinaryW` at `0x140063004`
- `CRYPT32!CryptStringToBinaryW` at `0x140063185`

## string_xrefs

- `0x140063044`: `termsrv\wms\src\common\srcutils\wmscrypt.cpp`
- `0x140063101`: `termsrv\wms\src\common\srcutils\wmscrypt.cpp`
- `0x140063108`: `pbTemp`

## pseudocode

```c

```
