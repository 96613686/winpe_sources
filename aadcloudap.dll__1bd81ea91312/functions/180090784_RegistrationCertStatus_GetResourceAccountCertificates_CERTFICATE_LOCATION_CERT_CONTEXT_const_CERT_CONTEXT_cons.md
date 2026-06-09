# RegistrationCertStatus::GetResourceAccountCertificates(_CERTFICATE_LOCATION,_CERT_CONTEXT const *,_CERT_CONTEXT const * * *,ulong *)

- ea: `0x180090784`
- end: `0x1800909bc`
- name: `?GetResourceAccountCertificates@RegistrationCertStatus@@SAJW4_CERTFICATE_LOCATION@@PEBU_CERT_CONTEXT@@PEAPEAPEBU3@PEAK@Z`
- size: `568`
- prototype: `static int __high(enum _CERTFICATE_LOCATION, const struct _CERT_CONTEXT *, const struct _CERT_CONTEXT ***, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18008585c`

## callees

- `0x180089748`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aecc`
- `0x180090378`
- `0x1800905d0`
- `0x180090784`
- `0x1800909c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180090983`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009098d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180090983`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009098d`

## string_xrefs

- `0x180090888`: `CertificateUtil::DoesExtensionWithValueExist`

## pseudocode

```c

```
