# Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifest1_1::.ctor

- ea: `0x6d6dc0`
- end: `0x6d70c2`
- name: `Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifest1_1::.ctor`
- size: `770`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

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
- `0x6d6d10`
- `0x6d6dc0`
- `0x93dab0`
- `0x957990`

## string_xrefs

- `0x6d6e11`: `{http://www.w3.org/2001/XMLSchema-instance}type`
- `0x6d6dd2`: `Promoting version 1.1 Agave manifest properties`
- `0x6d6dec`: `http://schemas.microsoft.com/office/appforoffice/1.1`
- `0x6d6e65`: `{http://schemas.microsoft.com/office/appforoffice/1.1}Dictionary`
- `0x6d6e92`: `{http://schemas.microsoft.com/office/appforoffice/1.1}TargetDialects`
- `0x6d6eb7`: `{http://schemas.microsoft.com/office/appforoffice/1.1}Id`
- `0x6d6ec9`: `{http://schemas.microsoft.com/office/appforoffice/1.1}AlternateId`
- `0x6d6edb`: `{http://schemas.microsoft.com/office/appforoffice/1.1}Version`
- `0x6d6eed`: `{http://schemas.microsoft.com/office/appforoffice/1.1}ProviderName`
- `0x6d6eff`: `{http://schemas.microsoft.com/office/appforoffice/1.1}DefaultLocale`
- `0x6d6f10`: `{http://schemas.microsoft.com/office/appforoffice/1.1}DisplayName`
- `0x6d6f28`: `{http://schemas.microsoft.com/office/appforoffice/1.1}Description`
- `0x6d6f40`: `{http://schemas.microsoft.com/office/appforoffice/1.1}DefaultSettings`
- `0x6d6f58`: `{http://schemas.microsoft.com/office/appforoffice/1.1}RequestedHeight`
- `0x6d6f6c`: `{http://schemas.microsoft.com/office/appforoffice/1.1}RequestedWidth`
- `0x6d6f91`: `{http://schemas.microsoft.com/office/appforoffice/1.1}IconUrl`
- `0x6d6fa9`: `{http://schemas.microsoft.com/office/appforoffice/1.1}HighResolutionIconUrl`
- `0x6d6fbc`: `{http://schemas.microsoft.com/office/appforoffice/1.1}Hosts`
- `0x6d6fcf`: `{http://schemas.microsoft.com/office/appforoffice/1.1}Requirements`
- `0x6d6fe2`: `{http://schemas.microsoft.com/office/appforoffice/1.1}TaskPaneAppVersionOverrides`
- `0x6d6ff5`: `{http://schemas.microsoft.com/office/appforoffice/1.1}ContentAppVersionOverrides`
- `0x6d700c`: `<OEC><Capabilities></Capabilities><Version1_1>\n            {0}\n            {1}\n            {2}\n            </Version1_1>\n            <TaskPaneAppVersionOverrides>\n            {3}\n            </TaskPaneAppVersionOverrides>\n            <ContentAppVersionOverrides>\n            {4}\n            </ContentAppVersionOverrides>\n            </OEC>`
- `0x6d709f`: `Version 1.1 Agave manifest properties promoted`

## pseudocode

```c

```

## disassembly

```asm
0x6d6dc0  ldarg.0
0x6d6dc1  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::.ctor()
0x6d6dc6  ldc.i4   0x4C90C9
0x6d6dcb  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppMarketplace()
0x6d6dd0  ldc.i4.s 0x32
0x6d6dd2  ldstr    aPromotingVersi// "Promoting version 1.1 Agave manifest pr"...
0x6d6dd7  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x6d6ddc  call     string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifest1_1::get_ManifestSchema()
0x6d6de1  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x6d6de6  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0x6d6deb  stloc.0
0x6d6dec  ldstr    aHttpSchemasMic_86// "http://schemas.microsoft.com/office/app"...
0x6d6df1  ldloc.0
0x6d6df2  call     class [System.Xml]System.Xml.XmlReaderSettings Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetXmlReaderSettings(string nameSpace, class [System.Xml]System.Xml.XmlReader xsdReader)
0x6d6df7  stloc.1
0x6d6df8  ldarg.1
0x6d6df9  ldloc.1
0x6d6dfa  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.Stream, class [System.Xml]System.Xml.XmlReaderSettings)
0x6d6dff  stloc.2
0x6d6e00  ldloc.2
0x6d6e01  call     class [System.Xml.Linq]System.Xml.Linq.XDocument [System.Xml.Linq]System.Xml.Linq.XDocument::Load(class [System.Xml]System.Xml.XmlReader)
0x6d6e06  stloc.3
0x6d6e07  ldloc.3
0x6d6e08  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XDocument::get_Root()
0x6d6e0d  stloc.s  4
0x6d6e0f  ldloc.s  4
0x6d6e11  ldstr    aHttpWwwW3Org20_16// "{http://www.w3.org/2001/XMLSchema-insta"...
0x6d6e16  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6d6e1b  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6d6e20  stloc.s  5
0x6d6e22  ldarg.0
0x6d6e23  ldloc.s  5
0x6d6e25  brfalse.s loc_6D6E30
0x6d6e27  ldloc.s  5
0x6d6e29  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x6d6e2e  br.s     loc_6D6E35
0x6d6e30  ldsfld   string [mscorlib]System.String::Empty
0x6d6e35  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_Type(string value)
0x6d6e3a  ldarg.0
0x6d6e3b  call     instance string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::get_Type()
0x6d6e40  ldc.i4.s 0x3A
0x6d6e42  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0x6d6e47  stloc.s  6
0x6d6e49  ldloc.s  6
0x6d6e4b  ldc.i4.0
0x6d6e4c  ble.s    loc_6D6E63
0x6d6e4e  ldarg.0
0x6d6e4f  ldarg.0
0x6d6e50  call     instance string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::get_Type()
0x6d6e55  ldloc.s  6
0x6d6e57  ldc.i4.1
0x6d6e58  add
0x6d6e59  callvirt instance string [mscorlib]System.String::Substring(int32)
0x6d6e5e  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_Type(string value)
0x6d6e63  ldloc.s  4
0x6d6e65  ldstr    aHttpSchemasMic_87// "{http://schemas.microsoft.com/office/ap"...
0x6d6e6a  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6d6e6f  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6d6e74  stloc.s  7
0x6d6e76  ldarg.0
0x6d6e77  ldsfld   string [mscorlib]System.String::Empty
0x6d6e7c  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_TargetLanguagesXML(string value)
0x6d6e81  ldloc.s  7
0x6d6e83  brfalse.s loc_6D6EB4
0x6d6e85  ldarg.0
0x6d6e86  ldstr    aDictionaryapp// "DictionaryApp"
0x6d6e8b  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_Type(string value)
0x6d6e90  ldloc.s  7
0x6d6e92  ldstr    aHttpSchemasMic_88// "{http://schemas.microsoft.com/office/ap"...
0x6d6e97  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6d6e9c  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6d6ea1  stloc.s  8
0x6d6ea3  ldloc.s  8
0x6d6ea5  brfalse.s loc_6D6EB4
0x6d6ea7  ldarg.0
0x6d6ea8  ldloc.s  8
0x6d6eaa  callvirt instance string [mscorlib]System.Object::ToString()
0x6d6eaf  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_TargetLanguagesXML(string value)
0x6d6eb4  ldarg.0
0x6d6eb5  ldloc.s  4
0x6d6eb7  ldstr    aHttpSchemasMic_89// "{http://schemas.microsoft.com/office/ap"...
0x6d6ebc  call     string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetString(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string elementName)
0x6d6ec1  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_ID(string value)
0x6d6ec6  ldarg.0
0x6d6ec7  ldloc.s  4
0x6d6ec9  ldstr    aHttpSchemasMic_90// "{http://schemas.microsoft.com/office/ap"...
0x6d6ece  call     string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetString(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string elementName)
0x6d6ed3  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_AlternateId(string value)
0x6d6ed8  ldarg.0
0x6d6ed9  ldloc.s  4
0x6d6edb  ldstr    aHttpSchemasMic_91// "{http://schemas.microsoft.com/office/ap"...
0x6d6ee0  call     string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetString(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string elementName)
0x6d6ee5  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_VersionString(string value)
0x6d6eea  ldarg.0
0x6d6eeb  ldloc.s  4
0x6d6eed  ldstr    aHttpSchemasMic_92// "{http://schemas.microsoft.com/office/ap"...
0x6d6ef2  call     string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetString(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string elementName)
0x6d6ef7  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_ProviderName(string value)
0x6d6efc  ldarg.0
0x6d6efd  ldloc.s  4
0x6d6eff  ldstr    aHttpSchemasMic_93// "{http://schemas.microsoft.com/office/ap"...
0x6d6f04  call     string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetString(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string elementName)
0x6d6f09  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_DefaultLocale(string value)
0x6d6f0e  ldloc.s  4
0x6d6f10  ldstr    aHttpSchemasMic_94// "{http://schemas.microsoft.com/office/ap"...
0x6d6f15  ldarg.0
0x6d6f16  ldflda   string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::title
0x6d6f1b  ldarg.0
0x6d6f1c  ldflda   string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::titleXml
0x6d6f21  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetLocaleAwareSettings(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string elementName, [out] string& defaultValue, [out] string& outXml)
0x6d6f26  ldloc.s  4
0x6d6f28  ldstr    aHttpSchemasMic_95// "{http://schemas.microsoft.com/office/ap"...
0x6d6f2d  ldarg.0
0x6d6f2e  ldflda   string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::description
0x6d6f33  ldarg.0
0x6d6f34  ldflda   string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::descriptionXml
0x6d6f39  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetLocaleAwareSettings(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string elementName, [out] string& defaultValue, [out] string& outXml)
0x6d6f3e  ldloc.s  4
0x6d6f40  ldstr    aHttpSchemasMic_96// "{http://schemas.microsoft.com/office/ap"...
0x6d6f45  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6d6f4a  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6d6f4f  stloc.s  9
0x6d6f51  ldloc.s  9
0x6d6f53  brfalse.s loc_6D6F7F
0x6d6f55  ldarg.0
0x6d6f56  ldloc.s  9
0x6d6f58  ldstr    aHttpSchemasMic_97// "{http://schemas.microsoft.com/office/ap"...
0x6d6f5d  ldc.i4.s 0x20
0x6d6f5f  call     int32 Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetInteger(class [System.Xml.Linq]System.Xml.Linq.XElement rootElement, string elementName, int32 defaultValue)
0x6d6f64  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_RequestedHeight(int32 value)
0x6d6f69  ldarg.0
0x6d6f6a  ldloc.s  9
0x6d6f6c  ldstr    aHttpSchemasMic_98// "{http://schemas.microsoft.com/office/ap"...
0x6d6f71  ldc.i4.s 0x20
0x6d6f73  call     int32 Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetInteger(class [System.Xml.Linq]System.Xml.Linq.XElement rootElement, string elementName, int32 defaultValue)
0x6d6f78  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_RequestedWidth(int32 value)
0x6d6f7d  br.s     loc_6D6F8F
0x6d6f7f  ldarg.0
0x6d6f80  ldc.i4.s 0x20
0x6d6f82  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_RequestedHeight(int32 value)
0x6d6f87  ldarg.0
0x6d6f88  ldc.i4.s 0x20
0x6d6f8a  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_RequestedWidth(int32 value)
0x6d6f8f  ldloc.s  4
0x6d6f91  ldstr    aHttpSchemasMic_99// "{http://schemas.microsoft.com/office/ap"...
0x6d6f96  ldarg.0
0x6d6f97  ldflda   string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::iconUrl
0x6d6f9c  ldarg.0
0x6d6f9d  ldflda   string Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::iconUrlXml
0x6d6fa2  call     void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::GetLocaleAwareSettings(class [System.Xml.Linq]System.Xml.Linq.XElement parentElement, string elementName, [out] string& defaultValue, [out] string& outXml)
0x6d6fa7  ldloc.s  4
0x6d6fa9  ldstr    aHttpSchemasMic_100// "{http://schemas.microsoft.com/office/ap"...
0x6d6fae  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6d6fb3  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6d6fb8  stloc.s  0xA
0x6d6fba  ldloc.s  4
0x6d6fbc  ldstr    aHttpSchemasMic_101// "{http://schemas.microsoft.com/office/ap"...
0x6d6fc1  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6d6fc6  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6d6fcb  stloc.s  0xB
0x6d6fcd  ldloc.s  4
0x6d6fcf  ldstr    aHttpSchemasMic_102// "{http://schemas.microsoft.com/office/ap"...
0x6d6fd4  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6d6fd9  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6d6fde  stloc.s  0xC
0x6d6fe0  ldloc.s  4
0x6d6fe2  ldstr    aHttpSchemasMic_103// "{http://schemas.microsoft.com/office/ap"...
0x6d6fe7  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6d6fec  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6d6ff1  stloc.s  0xD
0x6d6ff3  ldloc.s  4
0x6d6ff5  ldstr    aHttpSchemasMic_104// "{http://schemas.microsoft.com/office/ap"...
0x6d6ffa  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6d6fff  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6d7004  stloc.s  0xE
0x6d7006  ldarg.0
0x6d7007  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6d700c  ldstr    aOecCapabilitie// "<OEC><Capabilities></Capabilities><Vers"...
0x6d7011  ldc.i4.5
0x6d7012  newarr   [mscorlib]System.Object
0x6d7017  stloc.s  0xF
0x6d7019  ldloc.s  0xF
0x6d701b  ldc.i4.0
0x6d701c  ldloc.s  0xA
0x6d701e  brfalse.s loc_6D7029
0x6d7020  ldloc.s  0xA
0x6d7022  callvirt instance string [mscorlib]System.Object::ToString()
0x6d7027  br.s     loc_6D702E
0x6d7029  ldsfld   string [mscorlib]System.String::Empty
0x6d702e  stelem.ref
0x6d702f  ldloc.s  0xF
0x6d7031  ldc.i4.1
0x6d7032  ldloc.s  0xB
0x6d7034  brfalse.s loc_6D703F
0x6d7036  ldloc.s  0xB
0x6d7038  callvirt instance string [mscorlib]System.Object::ToString()
0x6d703d  br.s     loc_6D7044
0x6d703f  ldsfld   string [mscorlib]System.String::Empty
0x6d7044  stelem.ref
0x6d7045  ldloc.s  0xF
0x6d7047  ldc.i4.2
0x6d7048  ldloc.s  0xC
0x6d704a  brfalse.s loc_6D7055
0x6d704c  ldloc.s  0xC
0x6d704e  callvirt instance string [mscorlib]System.Object::ToString()
0x6d7053  br.s     loc_6D705A
0x6d7055  ldsfld   string [mscorlib]System.String::Empty
0x6d705a  stelem.ref
0x6d705b  ldloc.s  0xF
0x6d705d  ldc.i4.3
0x6d705e  ldloc.s  0xD
0x6d7060  brfalse.s loc_6D706B
0x6d7062  ldloc.s  0xD
0x6d7064  callvirt instance string [mscorlib]System.Object::ToString()
0x6d7069  br.s     loc_6D7070
0x6d706b  ldsfld   string [mscorlib]System.String::Empty
0x6d7070  stelem.ref
0x6d7071  ldloc.s  0xF
0x6d7073  ldc.i4.4
0x6d7074  ldloc.s  0xE
0x6d7076  brfalse.s loc_6D7081
0x6d7078  ldloc.s  0xE
0x6d707a  callvirt instance string [mscorlib]System.Object::ToString()
0x6d707f  br.s     loc_6D7086
0x6d7081  ldsfld   string [mscorlib]System.String::Empty
0x6d7086  stelem.ref
0x6d7087  ldloc.s  0xF
0x6d7089  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6d708e  call     instance void Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPOfficeExtensionManifestBase::set_CapabilitiesXML(string value)
0x6d7093  ldc.i4   0x4C90CA
0x6d7098  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppMarketplace()
0x6d709d  ldc.i4.s 0x32
0x6d709f  ldstr    aVersion11Agave// "Version 1.1 Agave manifest properties p"...
0x6d70a4  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x6d70a9  leave.s  loc_6D70B5
0x6d70ab  ldloc.2
0x6d70ac  brfalse.s loc_6D70B4
0x6d70ae  ldloc.2
0x6d70af  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d70b4  endfinally
0x6d70b5  leave.s  loc_6D70C1
0x6d70b7  ldloc.0
0x6d70b8  brfalse.s loc_6D70C0
0x6d70ba  ldloc.0
0x6d70bb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d70c0  endfinally
0x6d70c1  ret
```
