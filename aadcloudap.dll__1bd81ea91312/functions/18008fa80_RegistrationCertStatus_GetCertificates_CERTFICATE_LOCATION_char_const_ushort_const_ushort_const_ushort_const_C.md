# RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,_CERT_CONTEXT const * * *,ulong *)

- ea: `0x18008fa80`
- end: `0x18008fde3`
- name: `?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `867`
- prototype: `static int __high(enum _CERTFICATE_LOCATION, const char *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _CERT_CONTEXT ***, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18008f858`
- `0x18008fdec`

## callees

- `0x180004a24`
- `0x180005f24`
- `0x1800873bc`
- `0x1800898e8`
- `0x18008a300`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aecc`
- `0x18008fa80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008fcac`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008fdaa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008fcac`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008fdaa`

## string_xrefs

- `0x18008fb94`: `StringCompare`

## pseudocode

```c

```
