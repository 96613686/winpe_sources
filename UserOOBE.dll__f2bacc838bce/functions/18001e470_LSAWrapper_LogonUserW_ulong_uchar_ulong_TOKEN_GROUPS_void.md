# LSAWrapper::LogonUserW(ulong,uchar *,ulong,_TOKEN_GROUPS *,void * *)

- ea: `0x18001e470`
- end: `0x18001e59c`
- name: `?LogonUserW@LSAWrapper@@UEAAJKPEAEKPEAU_TOKEN_GROUPS@@PEAPEAX@Z`
- size: `300`
- prototype: `int(LSAWrapper *__hidden this, unsigned int, unsigned __int8 *, unsigned int, struct _TOKEN_GROUPS *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800032b0`
- `0x18001da40`
- `0x18001e470`
- `0x18001e97c`

## import_xrefs

- `ntdll!RtlInitString` at `0x18001e4ba`
- `ntdll!RtlInitString` at `0x18001e4ba`
- `SspiCli!LsaLogonUser` at `0x18001e557`
- `SspiCli!LsaLogonUser` at `0x18001e557`

## string_xrefs

- `0x18001e4af`: `UserOOBEBroker`

## pseudocode

```c

```
