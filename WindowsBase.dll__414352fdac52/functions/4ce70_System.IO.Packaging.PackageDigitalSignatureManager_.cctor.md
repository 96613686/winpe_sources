# System.IO.Packaging.PackageDigitalSignatureManager::.cctor

- ea: `0x4ce70`
- end: `0x4ced1`
- name: `System.IO.Packaging.PackageDigitalSignatureManager::.cctor`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0xf780`
- `0x4a5c0`

## string_xrefs

- `0x4ce9e`: `http://www.w3.org/2001/04/xmlenc#sha256`
- `0x4ce70`: `/package/services/digital-signature/origin.psdsor`
- `0x4ce85`: `application/vnd.openxmlformats-package.digital-signature-origin`
- `0x4cea8`: `http://schemas.openxmlformats.org/package/2006/relationships/digital-signature/origin`
- `0x4ceb2`: `http://schemas.openxmlformats.org/package/2006/relationships/digital-signature/signature`
- `0x4cebc`: `/package/services/digital-signature/xml-signature/`

## pseudocode

```c

```

## disassembly

```asm
0x4ce70  ldstr    aPackageService_1// "/package/services/digital-signature/ori"...
0x4ce75  ldc.i4.2
0x4ce76  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x4ce7b  call     class [System]System.Uri System.IO.Packaging.PackUriHelper::CreatePartUri(class [System]System.Uri partUri)
0x4ce80  stsfld   class [System]System.Uri System.IO.Packaging.PackageDigitalSignatureManager::_defaultOriginPartName
0x4ce85  ldstr    aApplicationVnd_3// "application/vnd.openxmlformats-package."...
0x4ce8a  newobj   instance void MS.Internal.ContentType::.ctor(string contentType)
0x4ce8f  stsfld   class MS.Internal.ContentType System.IO.Packaging.PackageDigitalSignatureManager::_originPartContentType
0x4ce94  ldstr    aN// "N"
0x4ce99  stsfld   string System.IO.Packaging.PackageDigitalSignatureManager::_guidStorageFormatString
0x4ce9e  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/04/xmlenc#sha256"
0x4cea3  stsfld   string System.IO.Packaging.PackageDigitalSignatureManager::_defaultHashAlgorithm
0x4cea8  ldstr    aHttpSchemasOpe_6// "http://schemas.openxmlformats.org/packa"...
0x4cead  stsfld   string System.IO.Packaging.PackageDigitalSignatureManager::_originRelationshipType
0x4ceb2  ldstr    aHttpSchemasOpe_7// "http://schemas.openxmlformats.org/packa"...
0x4ceb7  stsfld   string System.IO.Packaging.PackageDigitalSignatureManager::_originToSignatureRelationshipType
0x4cebc  ldstr    aPackageService_2// "/package/services/digital-signature/xml"...
0x4cec1  stsfld   string System.IO.Packaging.PackageDigitalSignatureManager::_defaultSignaturePartNamePrefix
0x4cec6  ldstr    aPsdsxs// ".psdsxs"
0x4cecb  stsfld   string System.IO.Packaging.PackageDigitalSignatureManager::_defaultSignaturePartNameExtension
0x4ced0  ret
```
