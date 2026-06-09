# JoinStatusStorage::SaveJoinStatus(int,_CERT_CONTEXT const *,struct_join_status *,int)

- ea: `0x18008e124`
- end: `0x18008e3a3`
- name: `?SaveJoinStatus@JoinStatusStorage@@SAJHPEBU_CERT_CONTEXT@@PEAUstruct_join_status@@H@Z`
- size: `639`
- prototype: `static int(int, const struct _CERT_CONTEXT *, struct struct_join_status *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180092b20`

## callees

- `0x1800871b4`
- `0x1800873bc`
- `0x180087468`
- `0x18008a340`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aecc`
- `0x18008c6fc`
- `0x18008cfc4`
- `0x18008df30`
- `0x18008e124`
- `0x18008e3ac`
- `0x1800909c4`
- `0x180092250`
- `0x1800924b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008e363`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008e36c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008e363`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008e36c`

## string_xrefs

- `0x18008e26f`: `StringCompare`
- `0x18008e1e3`: `JoinStatusStorage::InitJoinStatusRegPath`
- `0x18008e30f`: `RegistryPath::Append`

## pseudocode

```c

```
