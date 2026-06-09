# CallCloudAPPackage(ulong,uchar *,ulong *,void * *)

- ea: `0x180067058`
- end: `0x1800671d9`
- name: `?CallCloudAPPackage@@YAJKPEAEPEAKPEAPEAX@Z`
- size: `385`
- prototype: `int(unsigned int, unsigned __int8 *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180066eac`

## callees

- `0x18005d488`
- `0x18005d508`
- `0x180067004`
- `0x180067058`
- `0x1800671e0`
- `0x18009318c`

## import_xrefs

- `ntdll!RtlInitString` at `0x18006711f`
- `ntdll!RtlInitString` at `0x18006711f`
- `SspiCli!LsaCallAuthenticationPackage` at `0x180067178`
- `SspiCli!LsaCallAuthenticationPackage` at `0x180067178`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180067131`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180067131`
- `SspiCli!LsaConnectUntrusted` at `0x1800670eb`
- `SspiCli!LsaConnectUntrusted` at `0x1800670eb`

## string_xrefs

- `0x1800670c0`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x180067101`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c

```
