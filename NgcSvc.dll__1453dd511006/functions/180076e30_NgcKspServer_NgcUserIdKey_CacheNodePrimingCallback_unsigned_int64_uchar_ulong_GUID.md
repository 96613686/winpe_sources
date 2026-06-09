# NgcKspServer::NgcUserIdKey::CacheNodePrimingCallback(unsigned __int64,uchar *,ulong,_GUID)

- ea: `0x180076e30`
- end: `0x1800770bd`
- name: `?CacheNodePrimingCallback@NgcUserIdKey@NgcKspServer@@CAJ_KPEAEKU_GUID@@@Z`
- size: `653`
- prototype: `static int(unsigned __int64, unsigned __int8 *, unsigned int, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting`

## callees

- `0x180028d18`
- `0x1800294c0`
- `0x18002fb30`
- `0x1800323d0`
- `0x180033350`
- `0x180033c84`
- `0x180038764`
- `0x18005cee0`
- `0x180069998`
- `0x1800762f0`
- `0x180076310`
- `0x180076688`
- `0x180076e30`
- `0x18008df98`

## import_xrefs

- `ntdll!RtlInitAnsiString` at `0x180076ed6`
- `ntdll!RtlInitAnsiString` at `0x180076ed6`
- `SspiCli!LsaLogonUser` at `0x180077002`
- `SspiCli!LsaLogonUser` at `0x180077002`
- `SspiCli!LsaFreeReturnBuffer` at `0x180076f89`
- `SspiCli!LsaFreeReturnBuffer` at `0x180076f89`
- `SspiCli!LsaConnectUntrusted` at `0x180076e7d`
- `SspiCli!LsaConnectUntrusted` at `0x180076e7d`

## string_xrefs

- `0x180076ec7`: `NgcPrimeLsaCacheNode`

## pseudocode

```c

```
