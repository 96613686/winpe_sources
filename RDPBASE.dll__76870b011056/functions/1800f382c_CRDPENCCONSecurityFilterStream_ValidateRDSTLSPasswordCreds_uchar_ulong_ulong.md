# CRDPENCCONSecurityFilterStream::ValidateRDSTLSPasswordCreds(uchar *,ulong,ulong *)

- ea: `0x1800f382c`
- end: `0x1800f3e60`
- name: `?ValidateRDSTLSPasswordCreds@CRDPENCCONSecurityFilterStream@@AEAAJPEAEKPEAK@Z`
- size: `1588`
- prototype: `__int64 __fastcall(CRDPENCCONSecurityFilterStream *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800f28cc`

## callees

- `0x180001aa0`
- `0x180005090`
- `0x180078820`
- `0x180089578`
- `0x180096fb8`
- `0x1800ecc38`
- `0x1800ef8e0`
- `0x1800f1d3c`
- `0x1800f382c`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3cb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3cb2`
- `SspiCli!LogonUserExExW` at `0x1800f3ca8`
- `SspiCli!LogonUserExExW` at `0x1800f3ca8`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x1800f3c66`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x1800f3c66`
- `SspiCli!SeciFreeCallContext` at `0x1800f3e46`
- `SspiCli!SeciFreeCallContext` at `0x1800f3e46`

## pseudocode

```c

```
