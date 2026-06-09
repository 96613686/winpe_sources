# GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)

- ea: `0x1800956ec`
- end: `0x180095864`
- name: `?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z`
- size: `376`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, const struct _CERT_CONTEXT **, int, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800905ec`
- `0x1800954f0`

## callees

- `0x1800956ec`
- `0x18009586c`

## import_xrefs

- `DMCmnUtils!HexStringToBinary` at `0x180095724`
- `DMCmnUtils!HexStringToBinary` at `0x180095782`
- `DMCmnUtils!HexStringToBinary` at `0x180095724`
- `DMCmnUtils!HexStringToBinary` at `0x180095782`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180095752`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180095752`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009573d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180095807`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009573d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180095807`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009581c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009581c`
- `CRYPT32!CertCloseStore` at `0x180095832`
- `CRYPT32!CertCloseStore` at `0x180095832`
- `CRYPT32!CertFreeCertificateContext` at `0x180095846`
- `CRYPT32!CertFreeCertificateContext` at `0x180095846`

## pseudocode

```c

```
