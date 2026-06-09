# Microsoft.ReportingServices.Library.DataSourceAdaptor::ConstructFromODCFile

- ea: `0x23e10`
- end: `0x23ffc`
- name: `Microsoft.ReportingServices.Library.DataSourceAdaptor::ConstructFromODCFile`
- size: `492`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x22e10`
- `0x22f80`
- `0x23e10`

## string_xrefs

- `0x23e2a`: `<xml id=msodc>(?<odc>.*?)</xml>`
- `0x23eb1`: `urn:schemas-microsoft-com:office:odc`

## pseudocode

```c

```

## disassembly

```asm
0x23e10  ldarg.0
0x23e11  callvirt instance unsigned int8[] Microsoft.ReportingServices.Library.CatalogItem::get_Content()
0x23e16  stloc.0
0x23e17  ldloc.0
0x23e18  brtrue.s loc_23E1C
0x23e1a  ldnull
0x23e1b  ret
0x23e1c  ldnull
0x23e1d  stloc.1
0x23e1e  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x23e23  ldloc.0
0x23e24  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x23e29  stloc.2
0x23e2a  ldstr    aXmlIdMsodcOdcX// "<xml id=msodc>(?<odc>.*?)</xml>"
0x23e2f  ldc.i4.s 0x11
0x23e31  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x23e36  ldloc.2
0x23e37  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string)
0x23e3c  stloc.3
0x23e3d  ldloc.3
0x23e3e  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x23e43  brfalse.s loc_23E6B
0x23e45  ldloc.3
0x23e46  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x23e4b  callvirt instance int32 [System]System.Text.RegularExpressions.GroupCollection::get_Count()
0x23e50  ldc.i4.0
0x23e51  ble.s    loc_23E6B
0x23e53  ldloc.3
0x23e54  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x23e59  ldstr    aOdc_0// "odc"
0x23e5e  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x23e63  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x23e68  stloc.1
0x23e69  br.s     loc_23E71
0x23e6b  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0x23e70  throw
0x23e71  nop
0x23e72  ldloc.1
0x23e73  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x23e78  newobj   instance void [System.Xml]System.Xml.XmlReaderSettings::.ctor()
0x23e7d  stloc.s  4
0x23e7f  ldloc.s  4
0x23e81  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader, class [System.Xml]System.Xml.XmlReaderSettings)
0x23e86  stloc.s  5
0x23e88  ldloc.s  5
0x23e8a  stloc.s  6
0x23e8c  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x23e91  stloc.s  7
0x23e93  ldloc.s  7
0x23e95  ldloc.s  5
0x23e97  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0x23e9c  ldloc.s  7
0x23e9e  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x23ea3  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x23ea8  stloc.s  8
0x23eaa  ldloc.s  8
0x23eac  ldstr    aOdc_0// "odc"
0x23eb1  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:office:odc"
0x23eb6  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x23ebb  ldloc.s  7
0x23ebd  ldstr    aOdcOfficedatac// "/odc:OfficeDataConnection/odc:Connectio"...
0x23ec2  ldloc.s  8
0x23ec4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x23ec9  stloc.s  9
0x23ecb  ldloc.s  9
0x23ecd  brtrue.s loc_23EEE
0x23ecf  ldloc.s  7
0x23ed1  ldstr    aOdcOfficedatac_0// "/odc:OfficeDataConnection/odc:Connectio"...
0x23ed6  ldloc.s  8
0x23ed8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x23edd  stloc.s  9
0x23edf  ldloc.s  9
0x23ee1  brtrue.s loc_23EEE
0x23ee3  ldstr    aOdcOfficedatac_1// "/odc:OfficeDataConnection/odc:Connectio"...
0x23ee8  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x23eed  throw
0x23eee  ldloc.s  9
0x23ef0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x23ef5  ldstr    aOdcType// "odc:Type"
0x23efa  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x23eff  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x23f04  stloc.s  0xA
0x23f06  ldc.i4.0
0x23f07  stloc.s  0xB
0x23f09  ldloc.s  7
0x23f0b  ldstr    aOdcOfficedatac_2// "/odc:OfficeDataConnection/odc:Connectio"...
0x23f10  ldloc.s  8
0x23f12  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x23f17  stloc.s  0xC
0x23f19  ldloc.s  0xC
0x23f1b  brfalse.s loc_23F67
0x23f1d  ldloc.s  0xC
0x23f1f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x23f24  stloc.s  0xF
0x23f26  ldloc.s  0xF
0x23f28  ldstr    aNone// "None"
0x23f2d  ldc.i4.5
0x23f2e  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x23f33  brfalse.s loc_23F3A
0x23f35  ldc.i4.4
0x23f36  stloc.s  0xB
0x23f38  br.s     loc_23F6A
0x23f3a  ldloc.s  0xF
0x23f3c  ldstr    aIntegrated// "Integrated"
0x23f41  ldc.i4.5
0x23f42  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x23f47  brfalse.s loc_23F4E
0x23f49  ldc.i4.3
0x23f4a  stloc.s  0xB
0x23f4c  br.s     loc_23F6A
0x23f4e  ldloc.s  0xF
0x23f50  ldstr    aStored// "Stored"
0x23f55  ldc.i4.5
0x23f56  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x23f5b  brfalse.s loc_23F62
0x23f5d  ldc.i4.1
0x23f5e  stloc.s  0xB
0x23f60  br.s     loc_23F6A
0x23f62  ldc.i4.1
0x23f63  stloc.s  0xB
0x23f65  br.s     loc_23F6A
0x23f67  ldc.i4.3
0x23f68  stloc.s  0xB
0x23f6a  ldloc.s  9
0x23f6c  ldstr    aOdcConnections// "odc:ConnectionString"
0x23f71  ldloc.s  8
0x23f73  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x23f78  dup
0x23f79  brtrue.s loc_23F86
0x23f7b  ldstr    aOdcConnections// "odc:ConnectionString"
0x23f80  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x23f85  throw
0x23f86  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x23f8b  stloc.s  0xD
0x23f8d  ldarg.0
0x23f8e  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.CatalogItem::get_ItemContext()
0x23f93  callvirt instance string class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemName()
0x23f98  ldstr    asc_90EAC// ""
0x23f9d  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::.ctor(string, string)
0x23fa2  stloc.s  0xE
0x23fa4  ldloc.s  0xE
0x23fa6  ldloc.s  0xA
0x23fa8  callvirt instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::set_Extension(string)
0x23fad  ldloc.s  0xE
0x23faf  ldloc.s  0xD
0x23fb1  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IDataProtection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.DataProtection::get_Instance()
0x23fb6  callvirt instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::SetConnectionString(string, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IDataProtection)
0x23fbb  ldloc.s  0xE
0x23fbd  ldloc.s  0xB
0x23fbf  callvirt instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::set_CredentialsRetrieval(valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo/CredentialsRetrievalOption)
0x23fc4  ldloc.s  0xB
0x23fc6  ldc.i4.1
0x23fc7  bne.un.s loc_23FD9
0x23fc9  ldloc.s  0xE
0x23fcb  ldc.i4.0
0x23fcc  callvirt instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::set_ImpersonateUser(bool)
0x23fd1  ldloc.s  0xE
0x23fd3  ldc.i4.0
0x23fd4  callvirt instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::set_WindowsCredentials(bool)
0x23fd9  ldloc.s  0xE
0x23fdb  ldc.i4.0
0x23fdc  callvirt instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo::ValidateDefinition(bool)
0x23fe1  ldloc.s  0xE
0x23fe3  stloc.s  0x10
0x23fe5  leave.s  loc_23FF9
0x23fe7  ldloc.s  6
0x23fe9  brfalse.s loc_23FF2
0x23feb  ldloc.s  6
0x23fed  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23ff2  endfinally
0x23ff3  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MalformedXmlException::.ctor(class [System.Xml]System.Xml.XmlException)
0x23ff8  throw
0x23ff9  ldloc.s  0x10
0x23ffb  ret
```
