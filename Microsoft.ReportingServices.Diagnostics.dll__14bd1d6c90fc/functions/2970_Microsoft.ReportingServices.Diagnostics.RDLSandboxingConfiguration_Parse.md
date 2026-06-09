# Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::Parse

- ea: `0x2970`
- end: `0x2a63`
- name: `Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::Parse`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7390`

## callees

- `0x17d0`
- `0x1820`
- `0x2970`
- `0x2a70`
- `0x2b00`
- `0x2b90`
- `0x2ff0`
- `0x3020`

## pseudocode

```c

```

## disassembly

```asm
0x2970  newobj   instance void Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag::.ctor()
0x2975  stloc.0
0x2976  newobj   instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::.ctor()
0x297b  stloc.1
0x297c  ldloc.1
0x297d  ldloc.0
0x297e  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x2983  ldarg.1
0x2984  ldc.i4.s 0x68
0x2986  ldloc.1
0x2987  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::Add(var<u1>, !!T0)
0x298c  ldarg.0
0x298d  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x2992  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x2997  stloc.2
0x2998  br       loc_2A41
0x299d  ldloc.2
0x299e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x29a3  castclass [System.Xml]System.Xml.XmlNode
0x29a8  stloc.3
0x29a9  ldloc.3
0x29aa  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x29af  stloc.s  4
0x29b1  ldloc.s  4
0x29b3  ldstr    aMaxexpressionl// "MaxExpressionLength"
0x29b8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x29bd  brtrue.s loc_2A07
0x29bf  ldloc.s  4
0x29c1  ldstr    aMaxresourcesiz// "MaxResourceSize"
0x29c6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x29cb  brtrue.s loc_2A07
0x29cd  ldloc.s  4
0x29cf  ldstr    aMaxstringresul// "MaxStringResultLength"
0x29d4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x29d9  brtrue.s loc_2A07
0x29db  ldloc.s  4
0x29dd  ldstr    aMaxarrayresult// "MaxArrayResultLength"
0x29e2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x29e7  brtrue.s loc_2A07
0x29e9  ldloc.s  4
0x29eb  ldstr    aTypes// "Types"
0x29f0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x29f5  brtrue.s loc_2A1B
0x29f7  ldloc.s  4
0x29f9  ldstr    aMembers// "Members"
0x29fe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2a03  brtrue.s loc_2A24
0x2a05  br.s     loc_2A2D
0x2a07  ldloc.0
0x2a08  ldloc.3
0x2a09  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x2a0e  ldloc.3
0x2a0f  call     string Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::ReadNodeText(class [System.Xml]System.Xml.XmlNode node)
0x2a14  callvirt instance void Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag::Add(string propertyId, string value)
0x2a19  br.s     loc_2A41
0x2a1b  ldloc.3
0x2a1c  ldloc.0
0x2a1d  call     void Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::ParseTypes(class [System.Xml]System.Xml.XmlNode node, class Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag properties)
0x2a22  br.s     loc_2A41
0x2a24  ldloc.3
0x2a25  ldloc.0
0x2a26  call     void Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::ParseMembers(class [System.Xml]System.Xml.XmlNode node, class Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag properties)
0x2a2b  br.s     loc_2A41
0x2a2d  ldloc.3
0x2a2e  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x2a33  ldc.i4.8
0x2a34  beq.s    loc_2A41
0x2a36  ldloc.3
0x2a37  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x2a3c  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowInvalidFormat(string)
0x2a41  ldloc.2
0x2a42  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2a47  brtrue   loc_299D
0x2a4c  leave.s  loc_2A62
0x2a4e  ldloc.2
0x2a4f  isinst   [mscorlib]System.IDisposable
0x2a54  stloc.s  5
0x2a56  ldloc.s  5
0x2a58  brfalse.s loc_2A61
0x2a5a  ldloc.s  5
0x2a5c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a61  endfinally
0x2a62  ret
```
