# GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)

- ea: `0x180092f44`
- end: `0x18009308b`
- name: `?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z`
- size: `327`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, const struct _CERT_CONTEXT **, int, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18008e108`
- `0x180092d8c`

## callees

- `0x180092f44`
- `0x180093094`

## import_xrefs

- `DMCmnUtils!HexStringToBinary` at `0x180092f7c`
- `DMCmnUtils!HexStringToBinary` at `0x180092fc8`
- `DMCmnUtils!HexStringToBinary` at `0x180092f7c`
- `DMCmnUtils!HexStringToBinary` at `0x180092fc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093056`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093056`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092f9e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092f9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092f8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180093047`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092f8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180093047`
- `CRYPT32!CertCloseStore` at `0x180093066`
- `CRYPT32!CertCloseStore` at `0x180093066`
- `CRYPT32!CertFreeCertificateContext` at `0x180093074`
- `CRYPT32!CertFreeCertificateContext` at `0x180093074`

## pseudocode

```c

```
