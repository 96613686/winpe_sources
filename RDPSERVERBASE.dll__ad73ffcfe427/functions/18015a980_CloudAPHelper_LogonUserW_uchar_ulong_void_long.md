# CloudAPHelper::LogonUserW(uchar *,ulong,void * *,long *)

- ea: `0x18015a980`
- end: `0x18015ad02`
- name: `?LogonUserW@CloudAPHelper@@UEAAJPEAEKPEAPEAXPEAJ@Z`
- size: `898`
- prototype: `int(CloudAPHelper *__hidden this, unsigned __int8 *, unsigned int, void **, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000146c`
- `0x18000202c`
- `0x180004924`
- `0x18007e9e0`
- `0x18015a980`
- `0x18015ba00`
- `0x180161624`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x18015ace3`
- `SspiCli!LsaFreeReturnBuffer` at `0x18015ace3`
- `SspiCli!LsaLogonUser` at `0x18015ab96`
- `SspiCli!LsaLogonUser` at `0x18015ab96`

## string_xrefs

- `0x18015aa47`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015aae7`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015abe4`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015a9dc`: `Terminal Services API`
- `0x18015aabe`: `Missing paramter phToken`

## pseudocode

```c

```
