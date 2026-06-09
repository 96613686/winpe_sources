# GetEnrollmentClientContext(_GUID,ulong *,void * *,_CERT_CONTEXT const * *)

- ea: `0x18008e108`
- end: `0x18008e250`
- name: `?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z`
- size: `328`
- prototype: `int(struct _GUID *__struct_ptr, unsigned int *, void **, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18004c16c`

## callees

- `0x180017284`
- `0x180030068`
- `0x18003c17c`
- `0x18008e108`
- `0x180092f44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008e1a1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008e1a1`
- `dmEnrollEngine!GetEnrollmentClientCertThumbprint` at `0x18008e14c`
- `dmEnrollEngine!GetEnrollmentClientCertThumbprint` at `0x18008e14c`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x18008e18c`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x18008e18c`
- `dmEnrollEngine!GetEnrollmentSID` at `0x18008e1c3`
- `dmEnrollEngine!GetEnrollmentSID` at `0x18008e1c3`

## pseudocode

```c

```
