# Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifest::.ctor

- ea: `0x6d6a70`
- end: `0x6d6cb1`
- name: `Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifest::.ctor`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x6d2330`

## callees

- `0x6d6600`
- `0x6d6610`
- `0x6d6630`
- `0x6d6650`
- `0x6d6670`
- `0x6d6690`
- `0x6d66f0`
- `0x6d6710`
- `0x6d6730`
- `0x6d6770`
- `0x6d6790`
- `0x6d67a0`
- `0x6d67f0`
- `0x6d6810`
- `0x6d6870`
- `0x6d6950`
- `0x6d69c0`
- `0x6d6a70`
- `0x93dab0`
- `0x957990`

## string_xrefs

- `0x6d6a82`: `Promoting base version Agave manifest properties`
- `0x6d6a9c`: `http://schemas.microsoft.com/office/appforoffice/1.0`
- `0x6d6ac1`: `{http://www.w3.org/2001/XMLSchema-instance}type`
- `0x6d6b15`: `{http://schemas.microsoft.com/office/appforoffice/1.0}Dictionary`
- `0x6d6b42`: `{http://schemas.microsoft.com/office/appforoffice/1.0}TargetDialects`
- `0x6d6b67`: `{http://schemas.microsoft.com/office/appforoffice/1.0}Id`
- `0x6d6b79`: `{http://schemas.microsoft.com/office/appforoffice/1.0}AlternateId`
- `0x6d6b8b`: `{http://schemas.microsoft.com/office/appforoffice/1.0}Version`
- `0x6d6b9d`: `{http://schemas.microsoft.com/office/appforoffice/1.0}ProviderName`
- `0x6d6baf`: `{http://schemas.microsoft.com/office/appforoffice/1.0}DefaultLocale`
- `0x6d6bc0`: `{http://schemas.microsoft.com/office/appforoffice/1.0}DisplayName`
- `0x6d6bd8`: `{http://schemas.microsoft.com/office/appforoffice/1.0}Description`
- `0x6d6bf0`: `{http://schemas.microsoft.com/office/appforoffice/1.0}DefaultSettings`
- `0x6d6c08`: `{http://schemas.microsoft.com/office/appforoffice/1.0}RequestedHeight`
- `0x6d6c1c`: `{http://schemas.microsoft.com/office/appforoffice/1.0}RequestedWidth`
- `0x6d6c41`: `{http://schemas.microsoft.com/office/appforoffice/1.0}IconUrl`
- `0x6d6c59`: `{http://schemas.microsoft.com/office/appforoffice/1.0}Capabilities`
- `0x6d6c8e`: `Base version Agave manifest properties promoted`

## pseudocode

```c

```

## disassembly

```asm
0x6d6a70  ldarg.0
0x6d6a71  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::.ctor()
0x6d6a76  ldc.i4   0x4C90C7
0x6d6a7b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppMarketplace()
0x6d6a80  ldc.i4.s 0x32
0x6d6a82  ldstr    aPromotingBaseV// "Promoting base version Agave manifest p"...
0x6d6a87  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x6d6a8c  call     string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifest::get_ManifestSchema()
0x6d6a91  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x6d6a96  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0x6d6a9b  stloc.0
0x6d6a9c  ldstr    aHttpSchemasMic_71// "http://schemas.microsoft.com/office/app"...
0x6d6aa1  ldloc.0
0x6d6aa2  call     class [System.Xml]System.Xml.XmlReaderSettings Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetXmlReaderSettings(string nameSpace, class [System.Xml]System.Xml.XmlReader xsdReader)
0x6d6aa7  stloc.1
0x6d6aa8  ldarg.1
0x6d6aa9  ldloc.1
0x6d6aaa  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.Stream, class [System.Xml]System.Xml.XmlReaderSettings)
0x6d6aaf  stloc.2
0x6d6ab0  ldloc.2
0x6d6ab1  call     class [System.Xml.Linq]System.Xml.Linq.XDocument [System.Xml.Linq]System.Xml.Linq.XDocument::Load(class [System.Xml]System.Xml.XmlReader)
0x6d6ab6  stloc.3
0x6d6ab7  ldloc.3
0x6d6ab8  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XDocument::get_Root()
0x6d6abd  stloc.s  4
0x6d6abf  ldloc.s  4
0x6d6ac1  ldstr    aHttpWwwW3Org20_16// "{http://www.w3.org/2001/XMLSchema-insta"...
0x6d6ac6  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6d6acb  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6d6ad0  stloc.s  5
0x6d6ad2  ldarg.0
0x6d6ad3  ldloc.s  5
0x6d6ad5  brfalse.s loc_6D6AE0
0x6d6ad7  ldloc.s  5
0x6d6ad9  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x6d6ade  br.s     loc_6D6AE5
0x6d6ae0  ldsfld   string [mscorlib]System.String::Empty
0x6d6ae5  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_Type(string value)
0x6d6aea  ldarg.0
0x6d6aeb  call     instance string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::get_Type()
0x6d6af0  ldc.i4.s 0x3A
0x6d6af2  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0x6d6af7  stloc.s  6
0x6d6af9  ldloc.s  6
0x6d6afb  ldc.i4.0
0x6d6afc  ble.s    loc_6D6B13
0x6d6afe  ldarg.0
0x6d6aff  ldarg.0
0x6d6b00  call     instance string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::get_Type()
0x6d6b05  ldloc.s  6
0x6d6b07  ldc.i4.1
0x6d6b08  add
0x6d6b09  callvirt instance string [mscorlib]System.String::Substring(int32)
0x6d6b0e  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_Type(string value)
0x6d6b13  ldloc.s  4
0x6d6b15  ldstr    aHttpSchemasMic_72// "{http://schemas.microsoft.com/office/ap"...
0x6d6b1a  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6d6b1f  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6d6b24  stloc.s  7
0x6d6b26  ldarg.0
0x6d6b27  ldsfld   string [mscorlib]System.String::Empty
0x6d6b2c  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_TargetLanguagesXML(string value)
0x6d6b31  ldloc.s  7
0x6d6b33  brfalse.s loc_6D6B64
0x6d6b35  ldarg.0
0x6d6b36  ldstr    aDictionaryapp// "DictionaryApp"
0x6d6b3b  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_Type(string value)
0x6d6b40  ldloc.s  7
0x6d6b42  ldstr    aHttpSchemasMic_73// "{http://schemas.microsoft.com/office/ap"...
0x6d6b47  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6d6b4c  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6d6b51  stloc.s  8
0x6d6b53  ldloc.s  8
0x6d6b55  brfalse.s loc_6D6B64
0x6d6b57  ldarg.0
0x6d6b58  ldloc.s  8
0x6d6b5a  callvirt instance string [mscorlib]System.Object::ToString()
0x6d6b5f  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_TargetLanguagesXML(string value)
0x6d6b64  ldarg.0
0x6d6b65  ldloc.s  4
0x6d6b67  ldstr    aHttpSchemasMic_74// "{http://schemas.microsoft.com/office/ap"...
0x6d6b6c  call     string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetString(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string elementName)
0x6d6b71  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_ID(string value)
0x6d6b76  ldarg.0
0x6d6b77  ldloc.s  4
0x6d6b79  ldstr    aHttpSchemasMic_75// "{http://schemas.microsoft.com/office/ap"...
0x6d6b7e  call     string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetString(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string elementName)
0x6d6b83  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_AlternateId(string value)
0x6d6b88  ldarg.0
0x6d6b89  ldloc.s  4
0x6d6b8b  ldstr    aHttpSchemasMic_76// "{http://schemas.microsoft.com/office/ap"...
0x6d6b90  call     string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetString(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string elementName)
0x6d6b95  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_VersionString(string value)
0x6d6b9a  ldarg.0
0x6d6b9b  ldloc.s  4
0x6d6b9d  ldstr    aHttpSchemasMic_77// "{http://schemas.microsoft.com/office/ap"...
0x6d6ba2  call     string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetString(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string elementName)
0x6d6ba7  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_ProviderName(string value)
0x6d6bac  ldarg.0
0x6d6bad  ldloc.s  4
0x6d6baf  ldstr    aHttpSchemasMic_78// "{http://schemas.microsoft.com/office/ap"...
0x6d6bb4  call     string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetString(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string elementName)
0x6d6bb9  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_DefaultLocale(string value)
0x6d6bbe  ldloc.s  4
0x6d6bc0  ldstr    aHttpSchemasMic_79// "{http://schemas.microsoft.com/office/ap"...
0x6d6bc5  ldarg.0
0x6d6bc6  ldflda   string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::title
0x6d6bcb  ldarg.0
0x6d6bcc  ldflda   string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::titleXml
0x6d6bd1  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetLocaleAwareSettings(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string elementName, [out] string& defaultValue, [out] string& outXml)
0x6d6bd6  ldloc.s  4
0x6d6bd8  ldstr    aHttpSchemasMic_80// "{http://schemas.microsoft.com/office/ap"...
0x6d6bdd  ldarg.0
0x6d6bde  ldflda   string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::description
0x6d6be3  ldarg.0
0x6d6be4  ldflda   string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::descriptionXml
0x6d6be9  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetLocaleAwareSettings(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string elementName, [out] string& defaultValue, [out] string& outXml)
0x6d6bee  ldloc.s  4
0x6d6bf0  ldstr    aHttpSchemasMic_81// "{http://schemas.microsoft.com/office/ap"...
0x6d6bf5  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6d6bfa  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6d6bff  stloc.s  9
0x6d6c01  ldloc.s  9
0x6d6c03  brfalse.s loc_6D6C2F
0x6d6c05  ldarg.0
0x6d6c06  ldloc.s  9
0x6d6c08  ldstr    aHttpSchemasMic_82// "{http://schemas.microsoft.com/office/ap"...
0x6d6c0d  ldc.i4.s 0x20
0x6d6c0f  call     int32 Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetInteger(class [System.Xml.Linq]System.Xml.Linq.XElement rootElement, string elementName, int32 defaultValue)
0x6d6c14  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_RequestedHeight(int32 value)
0x6d6c19  ldarg.0
0x6d6c1a  ldloc.s  9
0x6d6c1c  ldstr    aHttpSchemasMic_83// "{http://schemas.microsoft.com/office/ap"...
0x6d6c21  ldc.i4.s 0x20
0x6d6c23  call     int32 Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetInteger(class [System.Xml.Linq]System.Xml.Linq.XElement rootElement, string elementName, int32 defaultValue)
0x6d6c28  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_RequestedWidth(int32 value)
0x6d6c2d  br.s     loc_6D6C3F
0x6d6c2f  ldarg.0
0x6d6c30  ldc.i4.s 0x20
0x6d6c32  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_RequestedHeight(int32 value)
0x6d6c37  ldarg.0
0x6d6c38  ldc.i4.s 0x20
0x6d6c3a  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_RequestedWidth(int32 value)
0x6d6c3f  ldloc.s  4
0x6d6c41  ldstr    aHttpSchemasMic_84// "{http://schemas.microsoft.com/office/ap"...
0x6d6c46  ldarg.0
0x6d6c47  ldflda   string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::iconUrl
0x6d6c4c  ldarg.0
0x6d6c4d  ldflda   string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::iconUrlXml
0x6d6c52  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetLocaleAwareSettings(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string elementName, [out] string& defaultValue, [out] string& outXml)
0x6d6c57  ldloc.s  4
0x6d6c59  ldstr    aHttpSchemasMic_85// "{http://schemas.microsoft.com/office/ap"...
0x6d6c5e  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6d6c63  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6d6c68  stloc.s  0xA
0x6d6c6a  ldarg.0
0x6d6c6b  ldloc.s  0xA
0x6d6c6d  brfalse.s loc_6D6C78
0x6d6c6f  ldloc.s  0xA
0x6d6c71  callvirt instance string [mscorlib]System.Object::ToString()
0x6d6c76  br.s     loc_6D6C7D
0x6d6c78  ldsfld   string [mscorlib]System.String::Empty
0x6d6c7d  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_CapabilitiesXML(string value)
0x6d6c82  ldc.i4   0x4C90C8
0x6d6c87  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppMarketplace()
0x6d6c8c  ldc.i4.s 0x32
0x6d6c8e  ldstr    aBaseVersionAga// "Base version Agave manifest properties "...
0x6d6c93  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x6d6c98  leave.s  loc_6D6CA4
0x6d6c9a  ldloc.2
0x6d6c9b  brfalse.s loc_6D6CA3
0x6d6c9d  ldloc.2
0x6d6c9e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d6ca3  endfinally
0x6d6ca4  leave.s  loc_6D6CB0
0x6d6ca6  ldloc.0
0x6d6ca7  brfalse.s loc_6D6CAF
0x6d6ca9  ldloc.0
0x6d6caa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d6caf  endfinally
0x6d6cb0  ret
```
