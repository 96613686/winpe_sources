# GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)

- ea: `0x14005187c`
- end: `0x1400519af`
- name: `?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z`
- size: `307`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, const struct _CERT_CONTEXT **, int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400516ec`

## callees

- `0x14005187c`
- `0x1400519b8`

## import_xrefs

- `DMCmnUtils!HexStringToBinary` at `0x1400518b4`
- `DMCmnUtils!HexStringToBinary` at `0x1400518fd`
- `DMCmnUtils!HexStringToBinary` at `0x1400518b4`
- `DMCmnUtils!HexStringToBinary` at `0x1400518fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005197a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005197a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400518d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400518d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400518c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14005196b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400518c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14005196b`
- `CRYPT32!CertFreeCertificateContext` at `0x140051998`
- `CRYPT32!CertFreeCertificateContext` at `0x140051998`
- `CRYPT32!CertCloseStore` at `0x14005198a`
- `CRYPT32!CertCloseStore` at `0x14005198a`

## pseudocode

```c

```
