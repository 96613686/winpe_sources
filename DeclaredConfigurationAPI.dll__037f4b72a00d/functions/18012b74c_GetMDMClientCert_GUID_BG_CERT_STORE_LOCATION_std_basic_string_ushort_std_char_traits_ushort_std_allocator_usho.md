# GetMDMClientCert(_GUID,BG_CERT_STORE_LOCATION &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool &,ushort * *)

- ea: `0x18012b74c`
- end: `0x18012b941`
- name: `?GetMDMClientCert@@YAJU_GUID@@AEAW4BG_CERT_STORE_LOCATION@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_NPEAPEAG@Z`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x18012a874`

## callees

- `0x18000df6c`
- `0x18000e5d0`
- `0x18000f0cc`
- `0x1800117dc`
- `0x180019d38`
- `0x18012b0f4`
- `0x18012b74c`
- `0x18012c77c`

## import_xrefs

- `CRYPT32!CertCloseStore` at `0x18012b90e`
- `CRYPT32!CertCloseStore` at `0x18012b90e`
- `CRYPT32!CertFreeCertificateContext` at `0x18012b8f9`
- `CRYPT32!CertFreeCertificateContext` at `0x18012b8f9`
- `dmEnrollEngine!GetEnrollmentClientCertThumbprint` at `0x18012b810`
- `dmEnrollEngine!GetEnrollmentClientCertThumbprint` at `0x18012b810`
- `dmEnrollEngine!GetEnrollmentSID` at `0x18012b884`
- `dmEnrollEngine!GetEnrollmentSID` at `0x18012b884`
- `dmEnrollEngine!__imp_?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z` at `0x18012b85a`
- `dmEnrollEngine!__imp_?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z` at `0x18012b85a`

## string_xrefs

- `0x18012b890`: `GetMDMClientCert - Failed to get enrollment User SID : 0x%1!x!`

## pseudocode

```c

```
