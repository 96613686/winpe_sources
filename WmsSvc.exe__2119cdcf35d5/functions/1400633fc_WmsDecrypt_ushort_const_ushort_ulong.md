# WmsDecrypt(ushort const *,ushort * *,ulong *)

- ea: `0x1400633fc`
- end: `0x140063793`
- name: `?WmsDecrypt@@YAJPEBGPEAPEAGPEAK@Z`
- size: `919`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140018740`
- `0x14001a290`
- `0x140021050`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140062fb8`
- `0x1400633fc`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14006375a`
- `KERNEL32!LocalFree` at `0x14006375a`
- `KERNEL32!GetLastError` at `0x140063481`
- `KERNEL32!GetLastError` at `0x140063481`
- `KERNEL32!IsDebuggerPresent` at `0x14006352b`
- `KERNEL32!IsDebuggerPresent` at `0x1400635e1`
- `KERNEL32!IsDebuggerPresent` at `0x14006366b`
- `KERNEL32!IsDebuggerPresent` at `0x14006370a`
- `KERNEL32!IsDebuggerPresent` at `0x14006352b`
- `KERNEL32!IsDebuggerPresent` at `0x1400635e1`
- `KERNEL32!IsDebuggerPresent` at `0x14006366b`
- `KERNEL32!IsDebuggerPresent` at `0x14006370a`
- `msvcrt!memcpy_s` at `0x1400636b6`
- `msvcrt!memcpy_s` at `0x1400636b6`
- `CRYPT32!CryptUnprotectData` at `0x140063477`
- `CRYPT32!CryptUnprotectData` at `0x140063477`

## string_xrefs

- `0x1400634a4`: `termsrv\wms\src\common\srcutils\wmscrypt.cpp`
- `0x14006350e`: `termsrv\wms\src\common\srcutils\wmscrypt.cpp`
- `0x1400635c4`: `termsrv\wms\src\common\srcutils\wmscrypt.cpp`
- `0x140063643`: `termsrv\wms\src\common\srcutils\wmscrypt.cpp`
- `0x1400636ed`: `termsrv\wms\src\common\srcutils\wmscrypt.cpp`
- `0x14006364d`: `pszTempPlainText`
- `0x1400636ce`: `pszTempPlainText[cchPlainText-1] == L'\0'`
- `0x140063712`: `pszTempPlainText[cchPlainText-1] == L'\0'`

## pseudocode

```c

```
