# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseUrlReservations

- ea: `0x8690`
- end: `0x8ab5`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseUrlReservations`
- size: `1061`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7390`

## callees

- `0x8690`
- `0x8ef0`
- `0x8f90`
- `0x8fd0`

## string_xrefs

- `0x86dc`: `Configuration file element URLReservations has an invalid child element '{0}'. It will be ignored.`
- `0x873d`: `VirtualDirectory`
- `0x8784`: `ReportServerWebService`
- `0x87ca`: `Configuration file element UrlReservation has a invalid ApplicationName '{0}'. It will be ignored.`
- `0x880b`: `Configuration file element UrlReservation has a invalid VirtualRoot. It will be ignored.`
- `0x886a`: `Configuration file element URLs has an invalid child element '{0}'. It will be ignored.`
- `0x88b0`: `Configuration file element URL is missing a UrlString element. It will be ignored.`
- `0x8912`: `Configuration file element URLs has an invalid URL '{0}'. It will be ignored.`
- `0x89a4`: `Configuration file element UrlReservation is missing an Application element. It will be ignored.`
- `0x89cc`: `Configuration file element UrlReservation is missing a VirtualRoot element. It will be ignored.`

## pseudocode

```c

```

## disassembly

```asm
0x8690  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype Microsoft.ReportingServices.Diagnostics.UrlConfiguration>::.ctor()
0x8695  stloc.0
0x8696  ldarg.1
0x8697  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x869c  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x86a1  stloc.1
0x86a2  br       loc_8A88
0x86a7  ldloc.1
0x86a8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x86ad  castclass [System.Xml]System.Xml.XmlNode
0x86b2  stloc.2
0x86b3  ldnull
0x86b4  stloc.3
0x86b5  ldloc.2
0x86b6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x86bb  ldstr    aApplication// "Application"
0x86c0  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x86c5  brfalse.s loc_86FA
0x86c7  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x86cc  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x86d1  brfalse  loc_8A88
0x86d6  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x86db  ldc.i4.1
0x86dc  ldstr    aConfigurationF_0// "Configuration file element URLReservati"...
0x86e1  ldc.i4.1
0x86e2  newarr   [mscorlib]System.Object
0x86e7  dup
0x86e8  ldc.i4.0
0x86e9  ldloc.2
0x86ea  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x86ef  stelem.ref
0x86f0  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x86f5  br       loc_8A88
0x86fa  ldc.i4.s 0xB
0x86fc  stloc.s  4
0x86fe  ldnull
0x86ff  stloc.s  5
0x8701  ldnull
0x8702  stloc.s  6
0x8704  ldloc.2
0x8705  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x870a  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x870f  stloc.s  9
0x8711  br       loc_8966
0x8716  ldloc.s  9
0x8718  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x871d  castclass [System.Xml]System.Xml.XmlNode
0x8722  stloc.s  0xA
0x8724  ldloc.s  0xA
0x8726  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x872b  stloc.s  0xB
0x872d  ldloc.s  0xB
0x872f  ldstr    aName_0// "Name"
0x8734  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8739  brtrue.s loc_877B
0x873b  ldloc.s  0xB
0x873d  ldstr    aVirtualdirecto// "VirtualDirectory"
0x8742  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8747  brtrue   loc_87E3
0x874c  ldloc.s  0xB
0x874e  ldstr    aUrls// "URLs"
0x8753  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8758  brtrue   loc_881A
0x875d  ldloc.s  0xA
0x875f  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x8764  ldc.i4.8
0x8765  beq      loc_8966
0x876a  ldloc.s  0xA
0x876c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8771  call     void Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ThrowInvalidFormat(string element)
0x8776  br       loc_8966
0x877b  ldloc.s  0xA
0x877d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8782  stloc.3
0x8783  ldloc.3
0x8784  ldstr    aReportserverwe// "ReportServerWebService"
0x8789  call     bool [mscorlib]System.String::op_Equality(string, string)
0x878e  brtrue.s loc_87AC
0x8790  ldloc.3
0x8791  ldstr    aReportmanager// "ReportManager"
0x8796  call     bool [mscorlib]System.String::op_Equality(string, string)
0x879b  brtrue.s loc_87B4
0x879d  ldloc.3
0x879e  ldstr    aReportserverwe_0// "ReportServerWebApp"
0x87a3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x87a8  brtrue.s loc_87BC
0x87aa  br.s     loc_87C4
0x87ac  ldc.i4.1
0x87ad  stloc.s  4
0x87af  br       loc_8966
0x87b4  ldc.i4.2
0x87b5  stloc.s  4
0x87b7  br       loc_8966
0x87bc  ldc.i4.3
0x87bd  stloc.s  4
0x87bf  br       loc_8966
0x87c4  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x87c9  ldc.i4.1
0x87ca  ldstr    aConfigurationF_1// "Configuration file element UrlReservati"...
0x87cf  ldc.i4.1
0x87d0  newarr   [mscorlib]System.Object
0x87d5  dup
0x87d6  ldc.i4.0
0x87d7  ldloc.3
0x87d8  stelem.ref
0x87d9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x87de  leave    loc_8A88
0x87e3  ldloc.s  0xA
0x87e5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x87ea  ldloca.s 5
0x87ec  call     bool Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseVirtualRoot(string url, [out] string& path)
0x87f1  brtrue   loc_8966
0x87f6  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x87fb  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x8800  brfalse  loc_8966
0x8805  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x880a  ldc.i4.1
0x880b  ldstr    aConfigurationF_2// "Configuration file element UrlReservati"...
0x8810  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x8815  leave    loc_8A88
0x881a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.Diagnostics.UrlReservation>::.ctor()
0x881f  stloc.s  6
0x8821  ldloc.s  0xA
0x8823  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x8828  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x882d  stloc.s  0xC
0x882f  br       loc_8943
0x8834  ldloc.s  0xC
0x8836  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x883b  castclass [System.Xml]System.Xml.XmlNode
0x8840  stloc.s  0xD
0x8842  ldloc.s  0xD
0x8844  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8849  ldstr    aUrl// "URL"
0x884e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x8853  brfalse.s loc_8889
0x8855  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x885a  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x885f  brfalse  loc_8943
0x8864  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x8869  ldc.i4.1
0x886a  ldstr    aConfigurationF_3// "Configuration file element URLs has an "...
0x886f  ldc.i4.1
0x8870  newarr   [mscorlib]System.Object
0x8875  dup
0x8876  ldc.i4.0
0x8877  ldloc.s  0xD
0x8879  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x887e  stelem.ref
0x887f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x8884  br       loc_8943
0x8889  ldloc.s  0xD
0x888b  ldstr    aUrlstring// "UrlString"
0x8890  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8895  stloc.s  0xE
0x8897  ldloc.s  0xE
0x8899  brtrue.s loc_88BF
0x889b  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x88a0  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x88a5  brfalse  loc_8943
0x88aa  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x88af  ldc.i4.1
0x88b0  ldstr    aConfigurationF_4// "Configuration file element URL is missi"...
0x88b5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x88ba  br       loc_8943
0x88bf  ldloc.s  0xE
0x88c1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x88c6  stloc.s  0xF
0x88c8  ldloc.s  0xF
0x88ca  ldloca.s 0x10
0x88cc  ldloca.s 0x13
0x88ce  ldloca.s 0x14
0x88d0  ldloca.s 0x11
0x88d2  ldloca.s 0x12
0x88d4  call     bool Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseUrlPrefix(string url, [out] string& scheme, [out] string& host, [out] string& port, [out] string& prefix, [out] string& path)
0x88d9  brfalse.s loc_8900
0x88db  ldloc.s  0x10
0x88dd  ldsfld   string [System]System.Uri::UriSchemeHttp
0x88e2  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x88e7  brfalse.s loc_88F7
0x88e9  ldloc.s  0x10
0x88eb  ldsfld   string [System]System.Uri::UriSchemeHttps
0x88f0  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x88f5  brtrue.s loc_8900
0x88f7  ldloc.s  0x12
0x88f9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x88fe  brtrue.s loc_8929
0x8900  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x8905  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x890a  brfalse.s loc_8943
0x890c  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x8911  ldc.i4.1
0x8912  ldstr    aConfigurationF_5// "Configuration file element URLs has an "...
0x8917  ldc.i4.1
0x8918  newarr   [mscorlib]System.Object
0x891d  dup
0x891e  ldc.i4.0
0x891f  ldloc.s  0xF
0x8921  stelem.ref
0x8922  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x8927  br.s     loc_8943
0x8929  ldloca.s 0x15
0x892b  initobj  Microsoft.ReportingServices.Diagnostics.UrlReservation
0x8931  ldloca.s 0x15
0x8933  ldloc.s  0x11
0x8935  stfld    string Microsoft.ReportingServices.Diagnostics.UrlReservation::UrlPrefix
0x893a  ldloc.s  6
0x893c  ldloc.s  0x15
0x893e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.Diagnostics.UrlReservation>::Add(var<u1>)
0x8943  ldloc.s  0xC
0x8945  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x894a  brtrue   loc_8834
0x894f  leave.s  loc_8966
0x8951  ldloc.s  0xC
0x8953  isinst   [mscorlib]System.IDisposable
0x8958  stloc.s  0x16
0x895a  ldloc.s  0x16
0x895c  brfalse.s loc_8965
0x895e  ldloc.s  0x16
0x8960  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8965  endfinally
0x8966  ldloc.s  9
0x8968  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x896d  brtrue   loc_8716
0x8972  leave.s  loc_8989
0x8974  ldloc.s  9
0x8976  isinst   [mscorlib]System.IDisposable
0x897b  stloc.s  0x16
0x897d  ldloc.s  0x16
0x897f  brfalse.s loc_8988
0x8981  ldloc.s  0x16
0x8983  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8988  endfinally
0x8989  ldloc.s  4
0x898b  ldc.i4.s 0xB
0x898d  bne.un.s loc_89B3
0x898f  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x8994  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x8999  brfalse  loc_8A88
0x899e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x89a3  ldc.i4.1
0x89a4  ldstr    aConfigurationF_6// "Configuration file element UrlReservati"...
0x89a9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x89ae  br       loc_8A88
0x89b3  ldloc.s  5
0x89b5  brtrue.s loc_89DB
0x89b7  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x89bc  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x89c1  brfalse  loc_8A88
0x89c6  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x89cb  ldc.i4.1
0x89cc  ldstr    aConfigurationF_7// "Configuration file element UrlReservati"...
0x89d1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x89d6  br       loc_8A88
0x89db  ldloc.s  6
0x89dd  brfalse.s loc_89E8
0x89df  ldloc.s  6
0x89e1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.Diagnostics.UrlReservation>::get_Count()
0x89e6  brtrue.s loc_8A13
0x89e8  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x89ed  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x89f2  brfalse  loc_8A88
0x89f7  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x89fc  ldc.i4.1
0x89fd  ldstr    aNoUrlsSpecifed// "No URLs specifed for Application {0}. I"...
0x8a02  ldc.i4.1
0x8a03  newarr   [mscorlib]System.Object
0x8a08  dup
0x8a09  ldc.i4.0
0x8a0a  ldloc.3
0x8a0b  stelem.ref
0x8a0c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x8a11  br.s     loc_8A88
0x8a13  ldloca.s 7
0x8a15  initobj  Microsoft.ReportingServices.Diagnostics.UrlConfiguration
0x8a1b  ldloca.s 7
0x8a1d  ldloc.s  5
0x8a1f  stfld    string Microsoft.ReportingServices.Diagnostics.UrlConfiguration::VirtualRoot
0x8a24  ldloc.s  6
0x8a26  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.Diagnostics.UrlReservation>::get_Count()
0x8a2b  newarr   Microsoft.ReportingServices.Diagnostics.UrlReservation
0x8a30  stloc.s  8
0x8a32  ldc.i4.0
0x8a33  stloc.s  0x17
0x8a35  br.s     loc_8A6D
0x8a37  ldloc.s  6
0x8a39  ldloc.s  0x17
0x8a3b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.Diagnostics.UrlReservation>::get_Item(!!T0)
0x8a40  stloc.s  0x18
0x8a42  ldloca.s 0x18
0x8a44  ldloc.s  0x18
0x8a46  ldfld    string Microsoft.ReportingServices.Diagnostics.UrlReservation::UrlPrefix
0x8a4b  ldloc.s  5
0x8a4d  ldstr    asc_1254E// "/"
0x8a52  call     string [mscorlib]System.String::Concat(string, string, string)
0x8a57  stfld    string Microsoft.ReportingServices.Diagnostics.UrlReservation::UrlPrefix
0x8a5c  ldloc.s  8
0x8a5e  ldloc.s  0x17
0x8a60  ldloc.s  0x18
0x8a62  stelem   Microsoft.ReportingServices.Diagnostics.UrlReservation
  ... truncated ...
```
