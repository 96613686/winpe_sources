# CRDPENCCONSecurityFilterStream::ValidateRDSTLSLogonCert(uchar *,ulong,ulong *)

- ea: `0x1800f2dd8`
- end: `0x1800f3826`
- name: `?ValidateRDSTLSLogonCert@CRDPENCCONSecurityFilterStream@@AEAAJPEAEKPEAK@Z`
- size: `2638`
- prototype: `__int64 __fastcall(CRDPENCCONSecurityFilterStream *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800f28cc`

## callees

- `0x180001aa0`
- `0x180002550`
- `0x180003158`
- `0x180003fcc`
- `0x180004714`
- `0x180004a94`
- `0x180005090`
- `0x1800787d4`
- `0x180078820`
- `0x180078c20`
- `0x18007966c`
- `0x180089578`
- `0x180096fb8`
- `0x1800ecc38`
- `0x1800ee0b4`
- `0x1800eedd0`
- `0x1800ef8e0`
- `0x1800f2084`
- `0x1800f2dd8`
- `0x180162010`

## import_xrefs

- `SspiCli!LsaDeregisterLogonProcess` at `0x1800f3762`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800f3762`
- `SspiCli!LsaConnectUntrusted` at `0x1800f33c6`
- `SspiCli!LsaConnectUntrusted` at `0x1800f33c6`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x1800f309e`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x1800f309e`
- `SspiCli!LsaLogonUser` at `0x1800f34cf`
- `SspiCli!LsaLogonUser` at `0x1800f34cf`
- `SspiCli!SeciFreeCallContext` at `0x1800f37fe`
- `SspiCli!SeciFreeCallContext` at `0x1800f37fe`

## string_xrefs

- `0x1800f3158`: `Terminal Services API`
- `0x1800f312c`: `Using NGC validation path`
- `0x1800f30d8`: `Used legacy CAPI path`
- `0x1800f31cc`: `Could not allocate tempCert variable`

## pseudocode

```c

```
