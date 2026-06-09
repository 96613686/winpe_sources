# Microsoft.SharePoint.BusinessData.SystemSpecific.WebService.DynamicProxyGenerator::GenerateProxyAssembly

- ea: `0xb66280`
- end: `0xb66770`
- name: `Microsoft.SharePoint.BusinessData.SystemSpecific.WebService.DynamicProxyGenerator::GenerateProxyAssembly`
- size: `1264`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0xb65fd0`
- `0xb660b0`

## callees

- `0x589050`
- `0x58aea0`
- `0x9582b0`
- `0xb66280`
- `0xb69580`
- `0xb695a0`
- `0xb69610`
- `0xbf5250`

## string_xrefs

- `0xb663be`: `System.dll`
- `0xb663e2`: `System.Xml.dll`
- `0xb663d0`: `System.Data.dll`
- `0xb663f4`: `System.Web.Services.dll`
- `0xb66406`: `System.EnterpriseServices.dll`
- `0xb6673e`: `ApplicationRegistry_Exception_DynamicProxyGenerator_cs2`
- `0xb6628a`: `serviceDescriptionDocuments`
- `0xb662b1`: `protocolName`
- `0xb6644c`: `ApplicationRegistry_DynamicProxyGenerator_ReferenceGenerationFailure`
- `0xb664ba`: `' generated during Code dom creation and Service Description import`
- `0xb66519`: `' generated on WebReference during Code dom creation`
- `0xb66565`: `Trying to compile and link generated proxy assembly to filesystem`
- `0xb665f3`: `System.Web.Services.Protocols.SoapHttpClientProtocol`
- `0xb666fd`: `Error during web service Proxy compile: `

## pseudocode

```c

```

## disassembly

```asm
0xb66280  newobj   instance void <>c__DisplayClass5::.ctor()
0xb66285  stloc.s  0x15
0xb66287  ldarg.1
0xb66288  brtrue.s loc_B66295
0xb6628a  ldstr    aServicedescrip// "serviceDescriptionDocuments"
0xb6628f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb66294  throw
0xb66295  ldarg.2
0xb66296  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb6629b  brfalse.s loc_B662A8
0xb6629d  ldstr    aProxynamespace// "proxyNamespaceName"
0xb662a2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb662a7  throw
0xb662a8  ldarg.s  4
0xb662aa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb662af  brfalse.s loc_B662BC
0xb662b1  ldstr    aProtocolname// "protocolName"
0xb662b6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb662bb  throw
0xb662bc  ldstr    aCsharp// "CSharp"
0xb662c1  call     class [System]System.CodeDom.Compiler.CodeDomProvider [System]System.CodeDom.Compiler.CodeDomProvider::CreateProvider(string)
0xb662c6  stloc.0
0xb662c7  ldarg.2
0xb662c8  ldc.i4.1
0xb662c9  newarr   [mscorlib]System.Char
0xb662ce  stloc.s  0x16
0xb662d0  ldloc.s  0x16
0xb662d2  ldc.i4.0
0xb662d3  ldc.i4.s 0x2E
0xb662d5  stelem.i2
0xb662d6  ldloc.s  0x16
0xb662d8  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xb662dd  stloc.1
0xb662de  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xb662e3  stloc.2
0xb662e4  ldloc.1
0xb662e5  stloc.s  0x17
0xb662e7  ldc.i4.0
0xb662e8  stloc.s  0x18
0xb662ea  br.s     loc_B6631E
0xb662ec  ldloc.s  0x17
0xb662ee  ldloc.s  0x18
0xb662f0  ldelem.ref
0xb662f1  stloc.3
0xb662f2  ldloc.0
0xb662f3  ldloc.3
0xb662f4  callvirt instance string [System]System.CodeDom.Compiler.CodeDomProvider::CreateEscapedIdentifier(string)
0xb662f9  stloc.s  4
0xb662fb  ldloc.0
0xb662fc  ldloc.s  4
0xb662fe  callvirt instance bool [System]System.CodeDom.Compiler.CodeDomProvider::IsValidIdentifier(string)
0xb66303  brtrue.s loc_B66310
0xb66305  ldstr    aInvalidProxyna// "Invalid proxyNamespaceName"
0xb6630a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xb6630f  throw
0xb66310  ldloc.2
0xb66311  ldloc.s  4
0xb66313  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb66318  ldloc.s  0x18
0xb6631a  ldc.i4.1
0xb6631b  add
0xb6631c  stloc.s  0x18
0xb6631e  ldloc.s  0x18
0xb66320  ldloc.s  0x17
0xb66322  ldlen
0xb66323  conv.i4
0xb66324  blt.s    loc_B662EC
0xb66326  ldstr    asc_C68090// "."
0xb6632b  ldloc.2
0xb6632c  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0xb66331  stloc.s  5
0xb66333  ldloc.s  5
0xb66335  newobj   instance void [System]System.CodeDom.CodeNamespace::.ctor(string)
0xb6633a  stloc.s  6
0xb6633c  ldc.i4.1
0xb6633d  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_SPS_BusinessData()
0xb66342  call     bool Microsoft.SharePoint.Diagnostics.PortalLog::ShouldLog(valuetype Microsoft.SharePoint.Diagnostics.PortalLogLevel level, class Microsoft.SharePoint.Diagnostics.ULSCat categoryID)
0xb66347  brfalse.s loc_B66363
0xb66349  ldc.i4   0x202221D1
0xb6634e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_SPS_BusinessData()
0xb66353  ldstr    aTryingToGenera_0// "Trying to generate code dom for Proxy A"...
0xb66358  ldc.i4.0
0xb66359  newarr   [mscorlib]System.Object
0xb6635e  call     void Microsoft.SharePoint.Diagnostics.PortalLog::LogStringTag(int32 tag, class Microsoft.SharePoint.Diagnostics.ULSCat categoryID, string format, object[] args)
0xb66363  ldarg.1
0xb66364  ldloc.s  6
0xb66366  ldarg.s  4
0xb66368  ldnull
0xb66369  ldnull
0xb6636a  newobj   instance void [System.Web.Services]System.Web.Services.Description.WebReference::.ctor(class [System.Web.Services]System.Web.Services.Discovery.DiscoveryClientDocumentCollection, class [System]System.CodeDom.CodeNamespace, string, string, string)
0xb6636f  stloc.s  7
0xb66371  newobj   instance void [System.Web.Services]System.Web.Services.Description.WebReferenceCollection::.ctor()
0xb66376  stloc.s  8
0xb66378  ldloc.s  8
0xb6637a  ldloc.s  7
0xb6637c  callvirt instance int32 [System.Web.Services]System.Web.Services.Description.WebReferenceCollection::Add(class [System.Web.Services]System.Web.Services.Description.WebReference)
0xb66381  pop
0xb66382  newobj   instance void [System.Web.Services]System.Web.Services.Description.WebReferenceOptions::.ctor()
0xb66387  stloc.s  9
0xb66389  ldloc.s  9
0xb6638b  ldc.i4.0
0xb6638c  callvirt instance void [System.Web.Services]System.Web.Services.Description.WebReferenceOptions::set_Style(valuetype [System.Web.Services]System.Web.Services.Description.ServiceDescriptionImportStyle)
0xb66391  ldloc.s  9
0xb66393  ldc.i4.1
0xb66394  callvirt instance void [System.Web.Services]System.Web.Services.Description.WebReferenceOptions::set_Verbose(bool)
0xb66399  ldloc.s  9
0xb6639b  ldc.i4.0
0xb6639c  callvirt instance void [System.Web.Services]System.Web.Services.Description.WebReferenceOptions::set_CodeGenerationOptions(valuetype [System.Xml]System.Xml.Serialization.CodeGenerationOptions)
0xb663a1  newobj   instance void [System]System.CodeDom.CodeCompileUnit::.ctor()
0xb663a6  stloc.s  0xA
0xb663a8  ldloc.s  0xA
0xb663aa  callvirt instance class [System]System.CodeDom.CodeNamespaceCollection [System]System.CodeDom.CodeCompileUnit::get_Namespaces()
0xb663af  ldloc.s  6
0xb663b1  callvirt instance int32 [System]System.CodeDom.CodeNamespaceCollection::Add(class [System]System.CodeDom.CodeNamespace)
0xb663b6  pop
0xb663b7  ldloc.s  0xA
0xb663b9  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.CodeCompileUnit::get_ReferencedAssemblies()
0xb663be  ldstr    aSystemDll// "System.dll"
0xb663c3  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xb663c8  pop
0xb663c9  ldloc.s  0xA
0xb663cb  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.CodeCompileUnit::get_ReferencedAssemblies()
0xb663d0  ldstr    aSystemDataDll// "System.Data.dll"
0xb663d5  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xb663da  pop
0xb663db  ldloc.s  0xA
0xb663dd  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.CodeCompileUnit::get_ReferencedAssemblies()
0xb663e2  ldstr    aSystemXmlDll// "System.Xml.dll"
0xb663e7  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xb663ec  pop
0xb663ed  ldloc.s  0xA
0xb663ef  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.CodeCompileUnit::get_ReferencedAssemblies()
0xb663f4  ldstr    aSystemWebServi// "System.Web.Services.dll"
0xb663f9  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xb663fe  pop
0xb663ff  ldloc.s  0xA
0xb66401  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.CodeCompileUnit::get_ReferencedAssemblies()
0xb66406  ldstr    aSystemEnterpri// "System.EnterpriseServices.dll"
0xb6640b  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xb66410  pop
0xb66411  ldloc.s  0xA
0xb66413  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.CodeCompileUnit::get_ReferencedAssemblies()
0xb66418  ldsfld   class [mscorlib]System.Type Microsoft.SharePoint.BusinessData.SystemSpecific.WebService.DynamicProxyGenerator::BdcSoapHttpClientProtocolType
0xb6641d  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xb66422  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0xb66427  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xb6642c  pop
0xb6642d  ldnull
0xb6642e  stloc.s  0xB
0xb66430  ldloc.s  8
0xb66432  ldloc.0
0xb66433  ldloc.s  0xA
0xb66435  ldloc.s  9
0xb66437  call     class [System]System.Collections.Specialized.StringCollection [System.Web.Services]System.Web.Services.Description.ServiceDescriptionImporter::GenerateWebReferences(class [System.Web.Services]System.Web.Services.Description.WebReferenceCollection, class [System]System.CodeDom.Compiler.CodeDomProvider, class [System]System.CodeDom.CodeCompileUnit, class [System.Web.Services]System.Web.Services.Description.WebReferenceOptions)
0xb6643c  stloc.s  0xB
0xb6643e  leave.s  loc_B66478
0xb66440  stloc.s  0xC
0xb66442  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb66447  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb6644c  ldstr    aApplicationreg_623// "ApplicationRegistry_DynamicProxyGenerat"...
0xb66451  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb66456  ldc.i4.1
0xb66457  newarr   [mscorlib]System.Object
0xb6645c  stloc.s  0x19
0xb6645e  ldloc.s  0x19
0xb66460  ldc.i4.0
0xb66461  ldloc.s  0xC
0xb66463  callvirt instance string [mscorlib]System.Exception::get_Message()
0xb66468  stelem.ref
0xb66469  ldloc.s  0x19
0xb6646b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb66470  ldloc.s  0xC
0xb66472  newobj   instance void [Microsoft.BusinessData]Microsoft.BusinessData.Runtime.CannotConnectException::.ctor(string, class [mscorlib]System.Exception)
0xb66477  throw
0xb66478  ldc.i4.2
0xb66479  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_SPS_BusinessData()
0xb6647e  call     bool Microsoft.SharePoint.Diagnostics.PortalLog::ShouldLog(valuetype Microsoft.SharePoint.Diagnostics.PortalLogLevel level, class Microsoft.SharePoint.Diagnostics.ULSCat categoryID)
0xb66483  brfalse  loc_B6654E
0xb66488  ldloc.s  0xB
0xb6648a  brfalse.s loc_B664EF
0xb6648c  ldloc.s  0xB
0xb6648e  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::get_Count()
0xb66493  brfalse.s loc_B664EF
0xb66495  ldloc.s  0xB
0xb66497  callvirt instance class [System]System.Collections.Specialized.StringEnumerator [System]System.Collections.Specialized.StringCollection::GetEnumerator()
0xb6649c  stloc.s  0x1A
0xb6649e  br.s     loc_B664CF
0xb664a0  ldloc.s  0x1A
0xb664a2  callvirt instance string [System]System.Collections.Specialized.StringEnumerator::get_Current()
0xb664a7  stloc.s  0xD
0xb664a9  ldc.i4   0x202221D2
0xb664ae  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_SPS_BusinessData()
0xb664b3  ldstr    aWarning_2// "Warning '"
0xb664b8  ldloc.s  0xD
0xb664ba  ldstr    aGeneratedDurin// "' generated during Code dom creation an"...
0xb664bf  call     string [mscorlib]System.String::Concat(string, string, string)
0xb664c4  ldc.i4.0
0xb664c5  newarr   [mscorlib]System.Object
0xb664ca  call     void Microsoft.SharePoint.Diagnostics.PortalLog::LogStringTag(int32 tag, class Microsoft.SharePoint.Diagnostics.ULSCat categoryID, string format, object[] args)
0xb664cf  ldloc.s  0x1A
0xb664d1  callvirt instance bool [System]System.Collections.Specialized.StringEnumerator::MoveNext()
0xb664d6  brtrue.s loc_B664A0
0xb664d8  leave.s  loc_B664EF
0xb664da  ldloc.s  0x1A
0xb664dc  isinst   [mscorlib]System.IDisposable
0xb664e1  stloc.s  0x1B
0xb664e3  ldloc.s  0x1B
0xb664e5  brfalse.s loc_B664EE
0xb664e7  ldloc.s  0x1B
0xb664e9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb664ee  endfinally
0xb664ef  ldloc.s  7
0xb664f1  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.Web.Services]System.Web.Services.Description.WebReference::get_ValidationWarnings()
0xb664f6  callvirt instance class [System]System.Collections.Specialized.StringEnumerator [System]System.Collections.Specialized.StringCollection::GetEnumerator()
0xb664fb  stloc.s  0x1C
0xb664fd  br.s     loc_B6652E
0xb664ff  ldloc.s  0x1C
0xb66501  callvirt instance string [System]System.Collections.Specialized.StringEnumerator::get_Current()
0xb66506  stloc.s  0xE
0xb66508  ldc.i4   0x202221D3
0xb6650d  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_SPS_BusinessData()
0xb66512  ldstr    aWarning_2// "Warning '"
0xb66517  ldloc.s  0xE
0xb66519  ldstr    aGeneratedOnWeb// "' generated on WebReference during Code"...
0xb6651e  call     string [mscorlib]System.String::Concat(string, string, string)
0xb66523  ldc.i4.0
0xb66524  newarr   [mscorlib]System.Object
0xb66529  call     void Microsoft.SharePoint.Diagnostics.PortalLog::LogStringTag(int32 tag, class Microsoft.SharePoint.Diagnostics.ULSCat categoryID, string format, object[] args)
0xb6652e  ldloc.s  0x1C
0xb66530  callvirt instance bool [System]System.Collections.Specialized.StringEnumerator::MoveNext()
0xb66535  brtrue.s loc_B664FF
0xb66537  leave.s  loc_B6654E
0xb66539  ldloc.s  0x1C
0xb6653b  isinst   [mscorlib]System.IDisposable
0xb66540  stloc.s  0x1D
0xb66542  ldloc.s  0x1D
0xb66544  brfalse.s loc_B6654D
0xb66546  ldloc.s  0x1D
0xb66548  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb6654d  endfinally
0xb6654e  ldc.i4.1
0xb6654f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_SPS_BusinessData()
0xb66554  call     bool Microsoft.SharePoint.Diagnostics.PortalLog::ShouldLog(valuetype Microsoft.SharePoint.Diagnostics.PortalLogLevel level, class Microsoft.SharePoint.Diagnostics.ULSCat categoryID)
0xb66559  brfalse.s loc_B66575
0xb6655b  ldc.i4   0x202221D4
0xb66560  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_SPS_BusinessData()
0xb66565  ldstr    aTryingToCompil// "Trying to compile and link generated pr"...
0xb6656a  ldc.i4.0
0xb6656b  newarr   [mscorlib]System.Object
0xb66570  call     void Microsoft.SharePoint.Diagnostics.PortalLog::LogStringTag(int32 tag, class Microsoft.SharePoint.Diagnostics.ULSCat categoryID, string format, object[] args)
0xb66575  newobj   instance void [System]System.CodeDom.Compiler.CompilerParameters::.ctor()
0xb6657a  stloc.s  0xF
0xb6657c  ldloc.s  0xF
0xb6657e  ldc.i4.0
0xb6657f  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_GenerateInMemory(bool)
0xb66584  ldloc.s  0xF
0xb66586  ldstr    aOptimize_0// "/optimize"
0xb6658b  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_CompilerOptions(string)
0xb66590  ldloc.s  0xF
0xb66592  ldarg.3
0xb66593  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_OutputAssembly(string)
0xb66598  ldloc.s  6
0xb6659a  callvirt instance class [System]System.CodeDom.CodeTypeDeclarationCollection [System]System.CodeDom.CodeNamespace::get_Types()
0xb6659f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xb665a4  stloc.s  0x1E
0xb665a6  br       loc_B66637
0xb665ab  ldloc.s  0x1E
0xb665ad  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xb665b2  castclass [System]System.CodeDom.CodeTypeDeclaration
0xb665b7  stloc.s  0x10
0xb665b9  ldloc.s  0x10
0xb665bb  brfalse.s loc_B66637
0xb665bd  ldloc.s  0x10
0xb665bf  callvirt instance class [System]System.CodeDom.CodeTypeReferenceCollection [System]System.CodeDom.CodeTypeDeclaration::get_BaseTypes()
0xb665c4  brfalse.s loc_B66637
0xb665c6  ldc.i4.0
0xb665c7  stloc.s  0x11
0xb665c9  br.s     loc_B66627
0xb665cb  ldloc.s  0x10
0xb665cd  callvirt instance class [System]System.CodeDom.CodeTypeReferenceCollection [System]System.CodeDom.CodeTypeDeclaration::get_BaseTypes()
0xb665d2  ldloc.s  0x11
0xb665d4  callvirt instance class [System]System.CodeDom.CodeTypeReference [System]System.CodeDom.CodeTypeReferenceCollection::get_Item(int32)
0xb665d9  callvirt instance string [System]System.CodeDom.CodeTypeReference::get_BaseType()
0xb665de  brfalse.s loc_B66621
0xb665e0  ldloc.s  0x10
0xb665e2  callvirt instance class [System]System.CodeDom.CodeTypeReferenceCollection [System]System.CodeDom.CodeTypeDeclaration::get_BaseTypes()
0xb665e7  ldloc.s  0x11
0xb665e9  callvirt instance class [System]System.CodeDom.CodeTypeReference [System]System.CodeDom.CodeTypeReferenceCollection::get_Item(int32)
0xb665ee  callvirt instance string [System]System.CodeDom.CodeTypeReference::get_BaseType()
0xb665f3  ldstr    aSystemWebServi_0// "System.Web.Services.Protocols.SoapHttpC"...
0xb665f8  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0xb665fd  brtrue.s loc_B66621
0xb665ff  ldloc.s  0x10
0xb66601  callvirt instance class [System]System.CodeDom.CodeTypeReferenceCollection [System]System.CodeDom.CodeTypeDeclaration::get_BaseTypes()
0xb66606  ldloc.s  0x11
0xb66608  ldtoken  [Microsoft.BusinessData]Microsoft.BusinessData.SystemSpecific.BdcSoapHttpClientProtocol
0xb6660d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb66612  callvirt instance string [mscorlib]System.Type::get_FullName()
0xb66617  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(string)
0xb6661c  callvirt instance void [System]System.CodeDom.CodeTypeReferenceCollection::set_Item(int32, class [System]System.CodeDom.CodeTypeReference)
  ... truncated ...
```
