# GetEnrollmentClientContext(_GUID,ulong *,void * *,_CERT_CONTEXT const * *)

- ea: `0x1800905ec`
- end: `0x180090751`
- name: `?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z`
- size: `357`
- prototype: `int(struct _GUID *__struct_ptr, unsigned int *, void **, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18004c440`

## callees

- `0x180017a88`
- `0x18002ecd8`
- `0x18003b93c`
- `0x1800905ec`
- `0x1800956ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180090695`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180090695`
- `dmEnrollEngine!GetEnrollmentClientCertThumbprint` at `0x180090630`
- `dmEnrollEngine!GetEnrollmentClientCertThumbprint` at `0x180090630`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x180090676`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x180090676`
- `dmEnrollEngine!GetEnrollmentSID` at `0x1800906bd`
- `dmEnrollEngine!GetEnrollmentSID` at `0x1800906bd`

## pseudocode

```c

```
