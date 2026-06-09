# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseDocument

- ea: `0x7390`
- end: `0x77a9`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseDocument`
- size: `1049`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x7280`
- `0x7340`

## callees

- `0x1700`
- `0x1710`
- `0x1750`
- `0x17c0`
- `0x17d0`
- `0x1820`
- `0x1b70`
- `0x2970`
- `0x7390`
- `0x77b0`
- `0x77e0`
- `0x7d20`
- `0x8440`
- `0x8690`
- `0x8ac0`
- `0x8fd0`
- `0x100d0`

## string_xrefs

- `0x739b`: `Configuration`
- `0x7523`: `Extensions`
- `0x75bd`: `Service`
- `0x75e9`: `InstallationID`
- `0x75ff`: `InstallationIDWebApp`
- `0x7683`: `MapTileServerConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x7390  ldarg.1
0x7391  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x7396  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x739b  ldstr    aConfiguration// "Configuration"
0x73a0  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x73a5  brfalse.s loc_73B7
0x73a7  ldarg.1
0x73a8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x73ad  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x73b2  call     void Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ThrowInvalidFormat(string element)
0x73b7  newobj   instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::.ctor()
0x73bc  stloc.0
0x73bd  ldarg.1
0x73be  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x73c3  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x73c8  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x73cd  stloc.1
0x73ce  br       loc_7786
0x73d3  ldloc.1
0x73d4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x73d9  castclass [System.Xml]System.Xml.XmlNode
0x73de  stloc.2
0x73df  ldloc.2
0x73e0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x73e5  stloc.3
0x73e6  ldloc.2
0x73e7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x73ec  stloc.s  4
0x73ee  ldloc.s  4
0x73f0  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x73f5  stloc.s  5
0x73f7  ldloc.s  5
0x73f9  ldc.i4   0x7BF3B2FB
0x73fe  bgt.un   loc_7492
0x7403  ldloc.s  5
0x7405  ldc.i4   0x534DB3E1
0x740a  bgt.un.s loc_744F
0x740c  ldloc.s  5
0x740e  ldc.i4   0x322871CA
0x7413  bgt.un.s loc_7432
0x7415  ldloc.s  5
0x7417  ldc.i4   0x2F4569F
0x741c  beq      loc_7629
0x7421  ldloc.s  5
0x7423  ldc.i4   0x322871CA
0x7428  beq      loc_754D
0x742d  br       loc_7786
0x7432  ldloc.s  5
0x7434  ldc.i4   0x3ADAF658
0x7439  beq      loc_7681
0x743e  ldloc.s  5
0x7440  ldc.i4   0x534DB3E1
0x7445  beq      loc_763F
0x744a  br       loc_7786
0x744f  ldloc.s  5
0x7451  ldc.i4   0x74B5E35C
0x7456  bgt.un.s loc_7475
0x7458  ldloc.s  5
0x745a  ldc.i4   0x69FBA5B5
0x745f  beq      loc_75FD
0x7464  ldloc.s  5
0x7466  ldc.i4   0x74B5E35C
0x746b  beq      loc_766B
0x7470  br       loc_7786
0x7475  ldloc.s  5
0x7477  ldc.i4   0x7B93DF52
0x747c  beq      loc_7613
0x7481  ldloc.s  5
0x7483  ldc.i4   0x7BF3B2FB
0x7488  beq      loc_75D1
0x748d  br       loc_7786
0x7492  ldloc.s  5
0x7494  ldc.i4   0xA46A7648
0x7499  bgt.un.s loc_74D8
0x749b  ldloc.s  5
0x749d  ldc.i4   0x9DC3AA14
0x74a2  bgt.un.s loc_74BE
0x74a4  ldloc.s  5
0x74a6  ldc.i4   0x91A62C98
0x74ab  beq      loc_75E7
0x74b0  ldloc.s  5
0x74b2  ldc.i4   0x9DC3AA14
0x74b7  beq.s    loc_7537
0x74b9  br       loc_7786
0x74be  ldloc.s  5
0x74c0  ldc.i4   0x9EACE8EB
0x74c5  beq.s    loc_7521
0x74c7  ldloc.s  5
0x74c9  ldc.i4   0xA46A7648
0x74ce  beq      loc_758F
0x74d3  br       loc_7786
0x74d8  ldloc.s  5
0x74da  ldc.i4   0xBD2D49D1
0x74df  bgt.un.s loc_74FB
0x74e1  ldloc.s  5
0x74e3  ldc.i4   0xB643C704
0x74e8  beq      loc_75BB
0x74ed  ldloc.s  5
0x74ef  ldc.i4   0xBD2D49D1
0x74f4  beq.s    loc_7563
0x74f6  br       loc_7786
0x74fb  ldloc.s  5
0x74fd  ldc.i4   0xDA139714
0x7502  beq      loc_75A5
0x7507  ldloc.s  5
0x7509  ldc.i4   0xDC29871F
0x750e  beq.s    loc_7579
0x7510  ldloc.s  5
0x7512  ldc.i4   0xF8486781
0x7517  beq      loc_7655
0x751c  br       loc_7786
0x7521  ldloc.s  4
0x7523  ldstr    aExtensions// "Extensions"
0x7528  call     bool [mscorlib]System.String::op_Equality(string, string)
0x752d  brtrue   loc_7697
0x7532  br       loc_7786
0x7537  ldloc.s  4
0x7539  ldstr    aAdd// "Add"
0x753e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7543  brtrue   loc_76A3
0x7548  br       loc_7786
0x754d  ldloc.s  4
0x754f  ldstr    aDsn// "Dsn"
0x7554  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7559  brtrue   loc_76AF
0x755e  br       loc_7786
0x7563  ldloc.s  4
0x7565  ldstr    aConnectiontype// "ConnectionType"
0x756a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x756f  brtrue   loc_76BD
0x7574  br       loc_7786
0x7579  ldloc.s  4
0x757b  ldstr    aLogonuser// "LogonUser"
0x7580  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7585  brtrue   loc_76CB
0x758a  br       loc_7786
0x758f  ldloc.s  4
0x7591  ldstr    aLogondomain// "LogonDomain"
0x7596  call     bool [mscorlib]System.String::op_Equality(string, string)
0x759b  brtrue   loc_76DE
0x75a0  br       loc_7786
0x75a5  ldloc.s  4
0x75a7  ldstr    aLogoncred// "LogonCred"
0x75ac  call     bool [mscorlib]System.String::op_Equality(string, string)
0x75b1  brtrue   loc_76F1
0x75b6  br       loc_7786
0x75bb  ldloc.s  4
0x75bd  ldstr    aService// "Service"
0x75c2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x75c7  brtrue   loc_7704
0x75cc  br       loc_7786
0x75d1  ldloc.s  4
0x75d3  ldstr    aUi// "UI"
0x75d8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x75dd  brtrue   loc_770D
0x75e2  br       loc_7786
0x75e7  ldloc.s  4
0x75e9  ldstr    aInstallationid_1// "InstallationID"
0x75ee  call     bool [mscorlib]System.String::op_Equality(string, string)
0x75f3  brtrue   loc_7716
0x75f8  br       loc_7786
0x75fd  ldloc.s  4
0x75ff  ldstr    aInstallationid_2// "InstallationIDWebApp"
0x7604  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7609  brtrue   loc_7721
0x760e  br       loc_7786
0x7613  ldloc.s  4
0x7615  ldstr    aHtmlviewerstyl// "HTMLViewerStyleSheet"
0x761a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x761f  brtrue   loc_772C
0x7624  br       loc_7786
0x7629  ldloc.s  4
0x762b  ldstr    aInstanceid// "InstanceId"
0x7630  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7635  brtrue   loc_7737
0x763a  br       loc_7786
0x763f  ldloc.s  4
0x7641  ldstr    aUrlreservation// "URLReservations"
0x7646  call     bool [mscorlib]System.String::op_Equality(string, string)
0x764b  brtrue   loc_7742
0x7650  br       loc_7786
0x7655  ldloc.s  4
0x7657  ldstr    aAuthentication_0// "Authentication"
0x765c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7661  brtrue   loc_776C
0x7666  br       loc_7786
0x766b  ldloc.s  4
0x766d  ldstr    aRdlsandboxing// "RDLSandboxing"
0x7672  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7677  brtrue   loc_7776
0x767c  br       loc_7786
0x7681  ldloc.s  4
0x7683  ldstr    aMaptileserverc// "MapTileServerConfiguration"
0x7688  call     bool [mscorlib]System.String::op_Equality(string, string)
0x768d  brtrue   loc_777F
0x7692  br       loc_7786
0x7697  ldloc.2
0x7698  ldloc.0
0x7699  call     void Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseExtensions(class [System.Xml]System.Xml.XmlNode child, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties)
0x769e  br       loc_7786
0x76a3  ldloc.2
0x76a4  ldloc.0
0x76a5  call     void Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseSetting(class [System.Xml]System.Xml.XmlNode node, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties)
0x76aa  br       loc_7786
0x76af  ldloc.0
0x76b0  ldc.i4.s 0x3B
0x76b2  ldloc.3
0x76b3  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value)
0x76b8  br       loc_7786
0x76bd  ldloc.0
0x76be  ldc.i4.s 0x3C
0x76c0  ldloc.3
0x76c1  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value)
0x76c6  br       loc_7786
0x76cb  ldloc.0
0x76cc  ldc.i4.s 0x3D
0x76ce  ldloc.3
0x76cf  ldstr    aLogonuser// "LogonUser"
0x76d4  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value, string name)
0x76d9  br       loc_7786
0x76de  ldloc.0
0x76df  ldc.i4.s 0x3E
0x76e1  ldloc.3
0x76e2  ldstr    aLogondomain// "LogonDomain"
0x76e7  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value, string name)
0x76ec  br       loc_7786
0x76f1  ldloc.0
0x76f2  ldc.i4.s 0x3F
0x76f4  ldloc.3
0x76f5  ldstr    aLogoncred// "LogonCred"
0x76fa  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value, string name)
0x76ff  br       loc_7786
0x7704  ldloc.2
0x7705  ldloc.0
0x7706  call     void Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseServiceConfiguration(class [System.Xml]System.Xml.XmlNode node, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties)
0x770b  br.s     loc_7786
0x770d  ldloc.2
0x770e  ldloc.0
0x770f  call     void Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseUIConfiguration(class [System.Xml]System.Xml.XmlNode node, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties)
0x7714  br.s     loc_7786
0x7716  ldloc.0
0x7717  ldc.i4.s 0x1D
0x7719  ldloc.3
0x771a  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value)
0x771f  br.s     loc_7786
0x7721  ldloc.0
0x7722  ldc.i4.s 0x1E
0x7724  ldloc.3
0x7725  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value)
0x772a  br.s     loc_7786
0x772c  ldloc.0
0x772d  ldc.i4.s 0x4C
0x772f  ldloc.3
0x7730  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value)
0x7735  br.s     loc_7786
0x7737  ldloc.0
0x7738  ldc.i4.s 0x1C
0x773a  ldloc.3
0x773b  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value)
0x7740  br.s     loc_7786
0x7742  newobj   instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::.ctor()
0x7747  stloc.s  6
0x7749  ldloc.s  6
0x774b  ldarg.0
0x774c  ldloc.2
0x774d  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype Microsoft.ReportingServices.Diagnostics.UrlConfiguration> Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseUrlReservations(class [System.Xml]System.Xml.XmlNode node)
0x7752  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x7757  ldloc.s  6
0x7759  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x775e  brfalse.s loc_7786
0x7760  ldloc.0
0x7761  ldc.i4.s 0x64
0x7763  ldloc.s  6
0x7765  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::Add(var<u1>, !!T0)
0x776a  br.s     loc_7786
0x776c  ldarg.0
0x776d  ldloc.2
0x776e  ldloc.0
0x776f  call     instance void Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseAuthentication(class [System.Xml]System.Xml.XmlNode node, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties)
0x7774  br.s     loc_7786
0x7776  ldloc.2
0x7777  ldloc.0
0x7778  call     void Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::Parse(class [System.Xml]System.Xml.XmlNode node, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties)
0x777d  br.s     loc_7786
0x777f  ldloc.2
0x7780  ldloc.0
0x7781  call     void Microsoft.ReportingServices.Diagnostics.MapTileServerConfiguration::Parse(class [System.Xml]System.Xml.XmlNode node, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties)
0x7786  ldloc.1
0x7787  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x778c  brtrue   loc_73D3
0x7791  leave.s  loc_77A7
0x7793  ldloc.1
0x7794  isinst   [mscorlib]System.IDisposable
0x7799  stloc.s  7
0x779b  ldloc.s  7
0x779d  brfalse.s loc_77A6
0x779f  ldloc.s  7
0x77a1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x77a6  endfinally
0x77a7  ldloc.0
  ... truncated ...
```
