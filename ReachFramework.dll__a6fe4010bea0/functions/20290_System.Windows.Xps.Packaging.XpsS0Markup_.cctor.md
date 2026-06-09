# System.Windows.Xps.Packaging.XpsS0Markup::.cctor

- ea: `0x20290`
- end: `0x20421`
- name: `System.Windows.Xps.Packaging.XpsS0Markup::.cctor`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3f440`

## string_xrefs

- `0x20298`: `http://schemas.microsoft.com/xps/2005/06`
- `0x202a0`: `http://schemas.microsoft.com/xps/2005/06`
- `0x202a8`: `http://schemas.microsoft.com/xps/2005/06`
- `0x202b3`: `application/xaml+xml`
- `0x202c2`: `application/vnd.ms-package.xps-fixeddocumentsequence+xml`
- `0x202d1`: `application/vnd.ms-package.xps-fixeddocument+xml`
- `0x202e0`: `application/vnd.ms-package.xps-fixedpage+xml`
- `0x202ef`: `application/vnd.ms-package.xps-documentstructure+xml`
- `0x202fe`: `application/vnd.ms-package.xps-storyfragments+xml`
- `0x2030d`: `application/vnd.ms-printing.printticket+xml`
- `0x2031c`: `application/xml`
- `0x2032b`: `application/vnd.openxmlformats-package.core-properties+xml`
- `0x20349`: `application/vnd.ms-opentype`
- `0x20367`: `application/vnd.ms-package.obfuscated-opentype`
- `0x20385`: `application/vnd.openxmlformats-package.digital-signature-origin`
- `0x20394`: `application/vnd.openxmlformats-package.digital-signature-certificate`
- `0x203a3`: `application/vnd.ms-package.xps-discard-control+xml`
- `0x203b2`: `application/vnd.openxmlformats-package.relationships+xml`
- `0x20407`: `application/vnd.ms-package.xps-resourcedictionary+xml`

## pseudocode

```c

```

## disassembly

```asm
0x20290  ldc.i4.3
0x20291  newarr   [mscorlib]System.String
0x20296  dup
0x20297  ldc.i4.0
0x20298  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/xps/2005/0"...
0x2029d  stelem.ref
0x2029e  dup
0x2029f  ldc.i4.1
0x202a0  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/xps/2005/0"...
0x202a5  stelem.ref
0x202a6  dup
0x202a7  ldc.i4.2
0x202a8  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/xps/2005/0"...
0x202ad  stelem.ref
0x202ae  stsfld   string[] System.Windows.Xps.Packaging.XpsS0Markup::_xmlnsUri
0x202b3  ldstr    aApplicationXam// "application/xaml+xml"
0x202b8  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x202bd  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_applicationXaml
0x202c2  ldstr    aApplicationVnd// "application/vnd.ms-package.xps-fixeddoc"...
0x202c7  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x202cc  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_documentSequenceContentType
0x202d1  ldstr    aApplicationVnd_0// "application/vnd.ms-package.xps-fixeddoc"...
0x202d6  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x202db  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_fixedDocumentContentType
0x202e0  ldstr    aApplicationVnd_1// "application/vnd.ms-package.xps-fixedpag"...
0x202e5  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x202ea  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_fixedPageContentType
0x202ef  ldstr    aApplicationVnd_2// "application/vnd.ms-package.xps-document"...
0x202f4  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x202f9  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_documentStructureContentType
0x202fe  ldstr    aApplicationVnd_3// "application/vnd.ms-package.xps-storyfra"...
0x20303  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x20308  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_storyFragmentsContentType
0x2030d  ldstr    aApplicationVnd_4// "application/vnd.ms-printing.printticket"...
0x20312  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x20317  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_printTicketContentType
0x2031c  ldstr    aApplicationXml// "application/xml"
0x20321  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x20326  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_signatureDefinitionType
0x2032b  ldstr    aApplicationVnd_5// "application/vnd.openxmlformats-package."...
0x20330  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x20335  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_coreDocumentPropertiesContentType
0x2033a  ldstr    aApplicationRes// "application/resource-PLACEHOLDER"
0x2033f  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x20344  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_resourceContentType
0x20349  ldstr    aApplicationVnd_6// "application/vnd.ms-opentype"
0x2034e  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x20353  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_fontContentType
0x20358  ldstr    aApplicationVnd_7// "application/vnd.ms-color.iccprofile"
0x2035d  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x20362  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_colorContextContentType
0x20367  ldstr    aApplicationVnd_8// "application/vnd.ms-package.obfuscated-o"...
0x2036c  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x20371  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_obfuscatedContentType
0x20376  ldstr    aImageJpeg// "image/jpeg"
0x2037b  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x20380  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_jpgContentType
0x20385  ldstr    aApplicationVnd_9// "application/vnd.openxmlformats-package."...
0x2038a  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x2038f  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_sigOriginContentType
0x20394  ldstr    aApplicationVnd_10// "application/vnd.openxmlformats-package."...
0x20399  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x2039e  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_sigCertContentType
0x203a3  ldstr    aApplicationVnd_11// "application/vnd.ms-package.xps-discard-"...
0x203a8  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x203ad  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_discardContentType
0x203b2  ldstr    aApplicationVnd_12// "application/vnd.openxmlformats-package."...
0x203b7  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x203bc  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_relationshipContentType
0x203c1  ldstr    aImagePng// "image/png"
0x203c6  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x203cb  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_pngContentType
0x203d0  ldstr    aImageTiff// "image/tiff"
0x203d5  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x203da  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_tifContentType
0x203df  ldstr    aTif// "tif"
0x203e4  stsfld   string System.Windows.Xps.Packaging.XpsS0Markup::_tifExtension
0x203e9  ldstr    aImageVndMsPhot// "image/vnd.ms-photo"
0x203ee  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x203f3  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_wdpContentType
0x203f8  ldstr    aImageVndMsPhot// "image/vnd.ms-photo"
0x203fd  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x20402  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_wmpContentType
0x20407  ldstr    aApplicationVnd_13// "application/vnd.ms-package.xps-resource"...
0x2040c  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x20411  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::_resourceDictionaryContentType
0x20416  newobj   instance void XmlnsUriContainer::.ctor()
0x2041b  stsfld   class XmlnsUriContainer System.Windows.Xps.Packaging.XpsS0Markup::_xmlnsUriContainer
0x20420  ret
```
