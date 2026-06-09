# WmsBase64Encode(ulong,uchar *,ushort * *,ulong *)

- ea: `0x1400631e8`
- end: `0x1400633f4`
- name: `?WmsBase64Encode@@YAJKPEAEPEAPEAGPEAK@Z`
- size: `524`
- prototype: `__int64 __fastcall(DWORD cbBinary, BYTE *pbBinary, unsigned __int16 **, unsigned int *)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140002454`
- `0x14000308c`
- `0x140040108`
- `0x14004257c`
- `0x14006379c`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x1400631e8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140063235`
- `KERNEL32!GetLastError` at `0x1400633ae`
- `KERNEL32!GetLastError` at `0x140063235`
- `KERNEL32!GetLastError` at `0x1400633ae`
- `KERNEL32!IsDebuggerPresent` at `0x140063290`
- `KERNEL32!IsDebuggerPresent` at `0x140063359`
- `KERNEL32!IsDebuggerPresent` at `0x140063290`
- `KERNEL32!IsDebuggerPresent` at `0x140063359`
- `CRYPT32!CryptBinaryToStringW` at `0x140063225`
- `CRYPT32!CryptBinaryToStringW` at `0x1400633a4`
- `CRYPT32!CryptBinaryToStringW` at `0x140063225`
- `CRYPT32!CryptBinaryToStringW` at `0x1400633a4`

## string_xrefs

- `0x140063265`: `termsrv\wms\src\common\srcutils\wmscrypt.cpp`
- `0x140063335`: `termsrv\wms\src\common\srcutils\wmscrypt.cpp`
- `0x14006333c`: `pszTemp`

## pseudocode

```c

```
