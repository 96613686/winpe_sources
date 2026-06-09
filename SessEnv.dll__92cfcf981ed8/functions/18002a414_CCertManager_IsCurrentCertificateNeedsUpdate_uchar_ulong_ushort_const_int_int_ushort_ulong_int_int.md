# CCertManager::IsCurrentCertificateNeedsUpdate(uchar *,ulong,ushort const *,int,int,ushort,ulong,int *,int *)

- ea: `0x18002a414`
- end: `0x18002a754`
- name: `?IsCurrentCertificateNeedsUpdate@CCertManager@@AEAAJPEAEKPEBGHHGKPEAH2@Z`
- size: `832`
- prototype: `__int64 __usercall@<rax>(CCertManager *__hidden this@<rcx>, unsigned __int8 *@<rdx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, int, int, unsigned __int16, unsigned int, int *, int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180003860`
- `0x18002b830`

## callees

- `0x180003f30`
- `0x180028ef0`
- `0x18002a414`
- `0x18003e87c`
- `0x18003e8cc`
- `0x18003f1f4`
- `0x18003f77c`
- `0x18003f834`
- `0x18003f91c`
- `0x18005b540`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a674`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a4f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a4f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a734`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a734`
- `CRYPT32!CertFreeCertificateContext` at `0x18002a726`
- `CRYPT32!CertFreeCertificateContext` at `0x18002a726`
- `CRYPT32!CertGetIntendedKeyUsage` at `0x18002a66a`
- `CRYPT32!CertGetIntendedKeyUsage` at `0x18002a66a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002a4d1`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002a507`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002a597`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002a4d1`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002a507`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002a597`

## string_xrefs

- `0x18002a4b0`: `CCertManager::IsCurrentCertificateNeedsUpdate`
- `0x18002a629`: `m_CertEnrollment.IsTemplateCertificate failed: 0x%x in %s`

## pseudocode

```c

```
