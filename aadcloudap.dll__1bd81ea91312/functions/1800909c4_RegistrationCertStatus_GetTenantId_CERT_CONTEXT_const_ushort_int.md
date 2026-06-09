# RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)

- ea: `0x1800909c4`
- end: `0x180090ade`
- name: `?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z`
- size: `282`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, unsigned __int16 **, int *)`
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800883b0`
- `0x18008d404`
- `0x18008e124`
- `0x18008fdec`
- `0x180090784`
- `0x180090ae4`

## callees

- `0x180085db4`
- `0x180089ebc`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aecc`
- `0x1800909c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180090a66`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180090ab2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180090a66`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180090ab2`

## string_xrefs

- `0x180090a8d`: `CopyStringW`
- `0x180090a35`: `RegistrationCertStatus::GetTenantIdExtensionValue`

## pseudocode

```c

```
