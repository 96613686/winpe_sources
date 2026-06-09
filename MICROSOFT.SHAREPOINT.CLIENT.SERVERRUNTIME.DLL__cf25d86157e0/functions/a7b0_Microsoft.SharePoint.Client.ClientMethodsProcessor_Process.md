# Microsoft.SharePoint.Client.ClientMethodsProcessor::Process

- ea: `0xa7b0`
- end: `0xa9bc`
- name: `Microsoft.SharePoint.Client.ClientMethodsProcessor::Process`
- size: `524`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x63c0`

## callees

- `0x54f0`
- `0x5c30`
- `0x5c80`
- `0x9840`
- `0x98e0`
- `0x9ea0`
- `0xa750`
- `0xa7b0`
- `0xa9c0`
- `0xaa30`
- `0xaac0`
- `0xb070`
- `0xb820`
- `0xdf50`
- `0xe000`
- `0xe010`
- `0xe140`
- `0xe3a0`
- `0xe420`
- `0xe680`
- `0x12440`
- `0x13000`
- `0x13030`
- `0x13210`
- `0x16f00`
- `0x17f80`
- `0x18770`
- `0x18af0`

## string_xrefs

- `0xa9a0`: `application/json; charset=utf-8`
- `0xa7cc`: `cq:ObjectPaths`

## pseudocode

```c

```

## disassembly

```asm
0xa7b0  ldarg.0
0xa7b1  ldarg.0
0xa7b2  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0xa7b7  call     valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Client.Utility::GetExecutionTimeout(class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0xa7bc  stfld    valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Client.ClientMethodsProcessor::m_dtTimeout
0xa7c1  ldarg.0
0xa7c2  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Client.ClientMethodsProcessor::m_xmlRequest
0xa7c7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xa7cc  ldstr    aCqObjectpaths// "cq:ObjectPaths"
0xa7d1  call     class [System.Xml]System.Xml.XmlNamespaceManager Microsoft.SharePoint.Client.ClientMethodsProcessor::get_NamespaceManager()
0xa7d6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa7db  stloc.0
0xa7dc  ldloc.0
0xa7dd  brfalse  loc_A863
0xa7e2  ldloc.0
0xa7e3  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0xa7e8  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0xa7ed  stloc.s  6
0xa7ef  br.s     loc_A843
0xa7f1  ldloc.s  6
0xa7f3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa7f8  castclass [System.Xml]System.Xml.XmlNode
0xa7fd  stloc.1
0xa7fe  ldloc.1
0xa7ff  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0xa804  ldc.i4.1
0xa805  bne.un.s loc_A843
0xa807  ldloc.1
0xa808  ldstr    aId// "Id"
0xa80d  call     string Microsoft.SharePoint.Client.Utility::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attrName)
0xa812  stloc.2
0xa813  ldarg.0
0xa814  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Xml]System.Xml.XmlElement> Microsoft.SharePoint.Client.ClientMethodsProcessor::m_pathIdToObjectPathMap
0xa819  ldloc.2
0xa81a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Xml]System.Xml.XmlElement>::ContainsKey(var<u1>)
0xa81f  brfalse.s loc_A831
0xa821  ldstr    aClientrequesti// "ClientRequestInvalidRequestGenericError"
0xa826  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId)
0xa82b  newobj   instance void Microsoft.SharePoint.Client.ClientServiceException::.ctor(string message)
0xa830  throw
0xa831  ldarg.0
0xa832  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Xml]System.Xml.XmlElement> Microsoft.SharePoint.Client.ClientMethodsProcessor::m_pathIdToObjectPathMap
0xa837  ldloc.2
0xa838  ldloc.1
0xa839  castclass [System.Xml]System.Xml.XmlElement
0xa83e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Xml]System.Xml.XmlElement>::set_Item(var<u1>, !!T0)
0xa843  ldloc.s  6
0xa845  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa84a  brtrue.s loc_A7F1
0xa84c  leave.s  loc_A863
0xa84e  ldloc.s  6
0xa850  isinst   [mscorlib]System.IDisposable
0xa855  stloc.s  7
0xa857  ldloc.s  7
0xa859  brfalse.s loc_A862
0xa85b  ldloc.s  7
0xa85d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa862  endfinally
0xa863  ldarg.0
0xa864  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ClientMethodsProcessor::m_serviceSurrogate
0xa869  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::EnsureRequestHandlers()
0xa86e  ldarg.0
0xa86f  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ClientMethodsProcessor::m_serviceSurrogate
0xa874  ldsfld   class Microsoft.SharePoint.Client.ClientServiceEventArgs Microsoft.SharePoint.Client.ClientServiceEventArgs::Empty
0xa879  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::OnRequestExecuting(class Microsoft.SharePoint.Client.ClientServiceEventArgs e)
0xa87e  ldarg.0
0xa87f  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xa884  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0xa889  ldarg.0
0xa88a  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xa88f  ldnull
0xa890  ldarg.0
0xa891  ldfld    class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.ClientMethodsProcessor::m_proxyContext
0xa896  call     void Microsoft.SharePoint.Client.ClientMethodsProcessor::WriteResponseHeader(class Microsoft.SharePoint.Client.JsonWriter writer, class [mscorlib]System.Exception ex, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa89b  ldarg.0
0xa89c  ldarg.0
0xa89d  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Client.ClientMethodsProcessor::m_xmlRequest
0xa8a2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0xa8a7  ldstr    aCqActions// "cq:Actions"
0xa8ac  call     class [System.Xml]System.Xml.XmlNamespaceManager Microsoft.SharePoint.Client.ClientMethodsProcessor::get_NamespaceManager()
0xa8b1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa8b6  call     instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessStatements(class [System.Xml]System.Xml.XmlNode xe)
0xa8bb  ldarg.0
0xa8bc  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xa8c1  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0xa8c6  ldarg.0
0xa8c7  call     instance class Microsoft.SharePoint.Client.ClientMethodsProcessorResult Microsoft.SharePoint.Client.ClientMethodsProcessor::CreateResult()
0xa8cc  stloc.s  5
0xa8ce  leave    loc_A9B9
0xa8d3  ldarg.0
0xa8d4  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ClientMethodsProcessor::m_serviceSurrogate
0xa8d9  ldarg.0
0xa8da  call     instance class [mscorlib]System.Collections.Generic.List`1<object> Microsoft.SharePoint.Client.RequestProcessor::get_RequestedObjects()
0xa8df  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>> class [mscorlib]System.Collections.Generic.List`1<object>::AsReadOnly()
0xa8e4  newobj   instance void Microsoft.SharePoint.Client.ClientServiceEventArgs::.ctor(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<object> objects)
0xa8e9  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::OnRequestExecuted(class Microsoft.SharePoint.Client.ClientServiceEventArgs e)
0xa8ee  endfinally
0xa8ef  stloc.3
0xa8f0  ldarg.0
0xa8f1  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0xa8f6  ldloc.3
0xa8f7  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::LogRequestScopeException(class [mscorlib]System.Exception ex)
0xa8fc  ldloc.3
0xa8fd  call     bool Microsoft.SharePoint.Client.Utility::FIsFatalException(class [mscorlib]System.Exception e)
0xa902  brfalse.s loc_A906
0xa904  rethrow
0xa906  ldarg.0
0xa907  call     instance string Microsoft.SharePoint.Client.ClientMethodsProcessor::GetRequestMessageToLog()
0xa90c  stloc.s  4
0xa90e  ldloc.3
0xa90f  call     class [mscorlib]System.Exception Microsoft.SharePoint.Client.ClientMethodsProcessor::ReplaceExceptionWithRedirectExceptionIfNecessary(class [mscorlib]System.Exception ex)
0xa914  stloc.3
0xa915  ldarg.0
0xa916  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ClientMethodsProcessor::m_serviceSurrogate
0xa91b  ldc.i4   0x157561
0xa920  ldc.i4.1
0xa921  ldloc.3
0xa922  callvirt instance string [mscorlib]System.Object::ToString()
0xa927  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0xa92c  ldarg.0
0xa92d  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ClientMethodsProcessor::m_serviceSurrogate
0xa932  ldc.i4   0x215788
0xa937  ldc.i4.1
0xa938  ldstr    aRequestmessage_0// "RequestMessage: {0}"
0xa93d  ldc.i4.1
0xa93e  newarr   [mscorlib]System.Object
0xa943  stloc.s  8
0xa945  ldloc.s  8
0xa947  ldc.i4.0
0xa948  ldloc.s  4
0xa94a  stelem.ref
0xa94b  ldloc.s  8
0xa94d  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0xa952  ldarg.0
0xa953  newobj   instance void Microsoft.SharePoint.Utilities.ChunkStringBuilder::.ctor()
0xa958  stfld    class Microsoft.SharePoint.Utilities.ChunkStringBuilder Microsoft.SharePoint.Client.ClientMethodsProcessor::m_sb
0xa95d  ldarg.0
0xa95e  ldarg.0
0xa95f  ldfld    class Microsoft.SharePoint.Utilities.ChunkStringBuilder Microsoft.SharePoint.Client.ClientMethodsProcessor::m_sb
0xa964  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa969  callvirt instance class [mscorlib]System.IO.TextWriter Microsoft.SharePoint.Utilities.ChunkStringBuilder::CreateTextWriter(class [mscorlib]System.IFormatProvider formatProvider)
0xa96e  newobj   instance void Microsoft.SharePoint.Client.JsonWriter::.ctor(class [mscorlib]System.IO.TextWriter writer)
0xa973  stfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xa978  ldarg.0
0xa979  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xa97e  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0xa983  ldarg.0
0xa984  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xa989  ldloc.3
0xa98a  ldarg.0
0xa98b  ldfld    class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.ClientMethodsProcessor::m_proxyContext
0xa990  call     void Microsoft.SharePoint.Client.ClientMethodsProcessor::WriteResponseHeader(class Microsoft.SharePoint.Client.JsonWriter writer, class [mscorlib]System.Exception ex, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa995  ldarg.0
0xa996  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xa99b  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0xa9a0  ldstr    aApplicationJso// "application/json; charset=utf-8"
0xa9a5  ldarg.0
0xa9a6  ldfld    class Microsoft.SharePoint.Utilities.ChunkStringBuilder Microsoft.SharePoint.Client.ClientMethodsProcessor::m_sb
0xa9ab  callvirt instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.ChunkStringBuilder::CreateUTF8ReadonlyStream()
0xa9b0  newobj   instance void Microsoft.SharePoint.Client.ClientMethodsProcessorResult::.ctor(string contentType, class [mscorlib]System.IO.Stream outputStream)
0xa9b5  stloc.s  5
0xa9b7  leave.s  loc_A9B9
0xa9b9  ldloc.s  5
0xa9bb  ret
```
