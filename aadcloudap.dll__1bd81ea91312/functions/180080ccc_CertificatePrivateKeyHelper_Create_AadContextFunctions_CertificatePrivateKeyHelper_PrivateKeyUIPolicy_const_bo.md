# CertificatePrivateKeyHelper::Create(AadContextFunctions *,CertificatePrivateKeyHelper::PrivateKeyUIPolicy const &,bool,CertificatePrivateKey &,_GUID *)

- ea: `0x180080ccc`
- end: `0x180080e2d`
- name: `?Create@CertificatePrivateKeyHelper@@SAJPEAVAadContextFunctions@@AEBUPrivateKeyUIPolicy@1@_NAEAVCertificatePrivateKey@@PEAU_GUID@@@Z`
- size: `353`
- prototype: `__int64 __usercall@<rax>(struct AadContextFunctions *@<rcx>, const struct CertificatePrivateKeyHelper::PrivateKeyUIPolicy *@<rdx>, bool@<r8b>, struct CertificatePrivateKey *@<r9>, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18004e82c`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180015188`
- `0x180071e14`
- `0x180080ccc`
- `0x180080e34`
- `0x180081208`
- `0x1800822c8`
- `0x180082418`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x180080dfb`
- `ncrypt!NCryptFreeObject` at `0x180080e09`
- `ncrypt!NCryptFreeObject` at `0x180080dfb`
- `ncrypt!NCryptFreeObject` at `0x180080e09`

## string_xrefs

- `0x180080d46`: `CertificatePrivateKeyHelper::Create`

## pseudocode

```c

```
