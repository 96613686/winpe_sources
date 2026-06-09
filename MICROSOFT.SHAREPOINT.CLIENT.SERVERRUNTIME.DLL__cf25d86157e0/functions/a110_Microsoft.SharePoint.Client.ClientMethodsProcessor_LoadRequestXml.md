# Microsoft.SharePoint.Client.ClientMethodsProcessor::LoadRequestXml

- ea: `0xa110`
- end: `0xa3a8`
- name: `Microsoft.SharePoint.Client.ClientMethodsProcessor::LoadRequestXml`
- size: `664`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x9f90`

## callees

- `0x8880`
- `0x88a0`
- `0xa110`
- `0xa3b0`
- `0xa3c0`
- `0xa510`
- `0xa570`
- `0xa9c0`
- `0xe000`
- `0xe010`
- `0xe030`
- `0xe580`
- `0xf180`
- `0x17870`

## string_xrefs

- `0xa241`: `CSOM Request XML: `

## pseudocode

```c

```

## disassembly

```asm
0xa110  ldarg.0
0xa111  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0xa116  stfld    class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Client.ClientMethodsProcessor::m_xmlRequest
0xa11b  newobj   instance void [System.Xml]System.Xml.XmlUrlResolver::.ctor()
0xa120  ldc.i4.0
0xa121  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0xa126  newobj   instance void [System.Xml]System.Xml.XmlSecureResolver::.ctor(class [System.Xml]System.Xml.XmlResolver, class [mscorlib]System.Security.PermissionSet)
0xa12b  stloc.0
0xa12c  ldarg.0
0xa12d  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Client.ClientMethodsProcessor::m_xmlRequest
0xa132  ldloc.0
0xa133  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0xa138  ldarg.1
0xa139  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0xa13e  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding)
0xa143  stloc.1
0xa144  ldarg.0
0xa145  ldloc.1
0xa146  ldc.i4   0x400
0xa14b  newobj   instance void Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::.ctor(class [mscorlib]System.IO.TextReader reader, int32 bufferSize)
0xa150  stfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ClientMethodsProcessor::m_peekReader
0xa155  ldarg.0
0xa156  ldarg.0
0xa157  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ClientMethodsProcessor::m_peekReader
0xa15c  ldarg.2
0xa15d  call     instance string Microsoft.SharePoint.Client.ClientMethodsProcessor::SimpleCheckRequestVersion(class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader reader, class Microsoft.SharePoint.Client.ClientServiceHost host)
0xa162  stloc.2
0xa163  newobj   instance void [System.Xml]System.Xml.XmlReaderSettings::.ctor()
0xa168  stloc.3
0xa169  ldarg.2
0xa16a  callvirt instance class Microsoft.SharePoint.Client.ClientCallableSettings Microsoft.SharePoint.Client.ClientServiceHost::get_ClientCallableSettings()
0xa16f  callvirt instance bool Microsoft.SharePoint.Client.ClientCallableSettings::get_EnableXsdValidation()
0xa174  brfalse.s loc_A1C9
0xa176  ldarg.0
0xa177  ldfld    class [mscorlib]System.Version Microsoft.SharePoint.Client.ClientMethodsProcessor::m_requestSchemaVersion
0xa17c  ldsfld   class [mscorlib]System.Version Microsoft.SharePoint.Client.SchemaVersions::Version14
0xa181  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xa186  brfalse.s loc_A1A6
0xa188  ldarg.2
0xa189  ldc.i4   0x24E602
0xa18e  ldc.i4.4
0xa18f  ldstr    aRequestSchemaV// "Request schema version is 14"
0xa194  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0xa199  ldloc.3
0xa19a  call     class [System.Xml]System.Xml.Schema.XmlSchemaSet Microsoft.SharePoint.Client.ClientMethodsProcessor::get_SchemaSet()
0xa19f  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_Schemas(class [System.Xml]System.Xml.Schema.XmlSchemaSet)
0xa1a4  br.s     loc_A1C2
0xa1a6  ldarg.2
0xa1a7  ldc.i4   0x24E603
0xa1ac  ldc.i4.4
0xa1ad  ldstr    aRequestSchemaV_0// "Request schema version is 15"
0xa1b2  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0xa1b7  ldloc.3
0xa1b8  call     class [System.Xml]System.Xml.Schema.XmlSchemaSet Microsoft.SharePoint.Client.ClientMethodsProcessor::get_SchemaSet15()
0xa1bd  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_Schemas(class [System.Xml]System.Xml.Schema.XmlSchemaSet)
0xa1c2  ldloc.3
0xa1c3  ldc.i4.4
0xa1c4  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_ValidationType(valuetype [System.Xml]System.Xml.ValidationType)
0xa1c9  ldarg.0
0xa1ca  ldarg.0
0xa1cb  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ClientMethodsProcessor::m_peekReader
0xa1d0  ldloc.3
0xa1d1  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader, class [System.Xml]System.Xml.XmlReaderSettings)
0xa1d6  stfld    class [System.Xml]System.Xml.XmlReader Microsoft.SharePoint.Client.ClientMethodsProcessor::m_xmlReader
0xa1db  ldarg.0
0xa1dc  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.SharePoint.Client.ClientMethodsProcessor::m_xmlReader
0xa1e1  ldarg.2
0xa1e2  callvirt instance class Microsoft.SharePoint.Client.ClientCallableSettings Microsoft.SharePoint.Client.ClientServiceHost::get_ClientCallableSettings()
0xa1e7  callvirt instance int32 Microsoft.SharePoint.Client.ClientCallableSettings::get_RequestXmlMaxDepth()
0xa1ec  newobj   instance void Microsoft.SharePoint.Client.ClientXmlReader::.ctor(class [System.Xml]System.Xml.XmlReader reader, int32 maxDepth)
0xa1f1  stloc.s  4
0xa1f3  ldarg.0
0xa1f4  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Client.ClientMethodsProcessor::m_xmlRequest
0xa1f9  ldloc.s  4
0xa1fb  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0xa200  leave.s  loc_A231
0xa202  stloc.s  5
0xa204  ldarg.2
0xa205  ldc.i4   0x24E604
0xa20a  ldc.i4.1
0xa20b  ldstr    aCannotLoadRequ// "Cannot load request message. Exception="...
0xa210  ldc.i4.2
0xa211  newarr   [mscorlib]System.Object
0xa216  stloc.s  6
0xa218  ldloc.s  6
0xa21a  ldc.i4.0
0xa21b  ldloc.s  5
0xa21d  callvirt instance string [mscorlib]System.Object::ToString()
0xa222  stelem.ref
0xa223  ldloc.s  6
0xa225  ldc.i4.1
0xa226  ldloc.2
0xa227  stelem.ref
0xa228  ldloc.s  6
0xa22a  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0xa22f  rethrow
0xa231  ldarg.2
0xa232  ldc.i4.4
0xa233  callvirt instance bool Microsoft.SharePoint.Client.ClientServiceHost::ShouldTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel)
0xa238  brfalse.s loc_A256
0xa23a  ldarg.2
0xa23b  ldc.i4   0x157560
0xa240  ldc.i4.4
0xa241  ldstr    aCsomRequestXml// "CSOM Request XML: "
0xa246  ldarg.0
0xa247  call     instance string Microsoft.SharePoint.Client.ClientMethodsProcessor::GetRequestMessageToLog()
0xa24c  call     string [mscorlib]System.String::Concat(string, string)
0xa251  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0xa256  ldarg.0
0xa257  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Client.ClientMethodsProcessor::m_xmlRequest
0xa25c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xa261  brfalse.s loc_A27F
0xa263  ldarg.0
0xa264  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Client.ClientMethodsProcessor::m_xmlRequest
0xa269  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xa26e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_LocalName()
0xa273  ldstr    aRequest// "Request"
0xa278  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xa27d  brfalse.s loc_A2A5
0xa27f  ldarg.2
0xa280  ldc.i4   0x24E605
0xa285  ldc.i4.1
0xa286  ldstr    aInvalidRequest// "Invalid request message, cannot find Re"...
0xa28b  ldc.i4.1
0xa28c  newarr   [mscorlib]System.Object
0xa291  stloc.s  7
0xa293  ldloc.s  7
0xa295  ldc.i4.0
0xa296  ldloc.2
0xa297  stelem.ref
0xa298  ldloc.s  7
0xa29a  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0xa29f  call     class Microsoft.SharePoint.Client.ClientServiceException Microsoft.SharePoint.Client.ClientMethodsProcessor::GenericInvalidRequestException()
0xa2a4  throw
0xa2a5  ldarg.0
0xa2a6  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Client.ClientMethodsProcessor::m_xmlRequest
0xa2ab  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xa2b0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa2b5  ldstr    aSchemaversion// "SchemaVersion"
0xa2ba  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa2bf  brfalse.s loc_A300
0xa2c1  ldarg.0
0xa2c2  ldfld    class [mscorlib]System.Version Microsoft.SharePoint.Client.ClientMethodsProcessor::m_requestSchemaVersion
0xa2c7  ldnull
0xa2c8  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xa2cd  brtrue.s loc_A300
0xa2cf  ldarg.0
0xa2d0  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Client.ClientMethodsProcessor::m_xmlRequest
0xa2d5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xa2da  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa2df  ldstr    aSchemaversion// "SchemaVersion"
0xa2e4  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa2e9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa2ee  ldarg.0
0xa2ef  ldfld    class [mscorlib]System.Version Microsoft.SharePoint.Client.ClientMethodsProcessor::m_requestSchemaVersion
0xa2f4  callvirt instance string [mscorlib]System.Object::ToString()
0xa2f9  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xa2fe  brfalse.s loc_A326
0xa300  ldarg.2
0xa301  ldc.i4   0x24E606
0xa306  ldc.i4.1
0xa307  ldstr    aInvalidRequest_0// "Invalid request message, the schema ver"...
0xa30c  ldc.i4.1
0xa30d  newarr   [mscorlib]System.Object
0xa312  stloc.s  8
0xa314  ldloc.s  8
0xa316  ldc.i4.0
0xa317  ldloc.2
0xa318  stelem.ref
0xa319  ldloc.s  8
0xa31b  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0xa320  call     class Microsoft.SharePoint.Client.ClientServiceException Microsoft.SharePoint.Client.ClientMethodsProcessor::GenericInvalidRequestException()
0xa325  throw
0xa326  ldarg.0
0xa327  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Client.ClientMethodsProcessor::m_xmlRequest
0xa32c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xa331  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa336  ldstr    aLibraryversion// "LibraryVersion"
0xa33b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa340  brfalse.s loc_A381
0xa342  ldarg.0
0xa343  ldfld    class [mscorlib]System.Version Microsoft.SharePoint.Client.ClientMethodsProcessor::m_requestLibraryVersion
0xa348  ldnull
0xa349  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xa34e  brtrue.s loc_A381
0xa350  ldarg.0
0xa351  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Client.ClientMethodsProcessor::m_xmlRequest
0xa356  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xa35b  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa360  ldstr    aLibraryversion// "LibraryVersion"
0xa365  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa36a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa36f  ldarg.0
0xa370  ldfld    class [mscorlib]System.Version Microsoft.SharePoint.Client.ClientMethodsProcessor::m_requestLibraryVersion
0xa375  callvirt instance string [mscorlib]System.Object::ToString()
0xa37a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xa37f  brfalse.s loc_A3A7
0xa381  ldarg.2
0xa382  ldc.i4   0x24E607
0xa387  ldc.i4.1
0xa388  ldstr    aInvalidRequest_1// "Invalid request message, the library ve"...
0xa38d  ldc.i4.1
0xa38e  newarr   [mscorlib]System.Object
0xa393  stloc.s  9
0xa395  ldloc.s  9
0xa397  ldc.i4.0
0xa398  ldloc.2
0xa399  stelem.ref
0xa39a  ldloc.s  9
0xa39c  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0xa3a1  call     class Microsoft.SharePoint.Client.ClientServiceException Microsoft.SharePoint.Client.ClientMethodsProcessor::GenericInvalidRequestException()
0xa3a6  throw
0xa3a7  ret
```
