# CreateSelfSignedCertificate(_CERT_CONTEXT const * *,unsigned __int64,ulong,ushort const *,_CERT_EXTENSION *,ulong)

- ea: `0x180175f70`
- end: `0x180176156`
- name: `?CreateSelfSignedCertificate@@YAJPEAPEBU_CERT_CONTEXT@@_KKPEBGPEAU_CERT_EXTENSION@@K@Z`
- size: `486`
- prototype: `int(const struct _CERT_CONTEXT **, unsigned __int64, unsigned int, const unsigned __int16 *, struct _CERT_EXTENSION *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1801323f0`

## callees

- `0x18007e9e0`
- `0x18007f6a4`
- `0x180175f70`
- `0x18017615c`
- `0x1801762b8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180176043`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180176043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017607a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017607a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180176070`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1801760b8`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180176070`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1801760b8`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x1801760fc`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x1801760fc`
- `ncrypt!NCryptIsKeyHandle` at `0x180176012`
- `ncrypt!NCryptIsKeyHandle` at `0x180176012`

## pseudocode

```c

```
