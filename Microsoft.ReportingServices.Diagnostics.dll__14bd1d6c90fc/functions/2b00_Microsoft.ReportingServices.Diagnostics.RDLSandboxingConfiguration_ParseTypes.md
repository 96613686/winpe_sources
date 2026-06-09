# Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::ParseTypes

- ea: `0x2b00`
- end: `0x2b90`
- name: `Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::ParseTypes`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2970`

## callees

- `0x17d0`
- `0x1820`
- `0x2b00`
- `0x3060`

## pseudocode

```c

```

## disassembly

```asm
0x2b00  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag>::.ctor()
0x2b05  stloc.0
0x2b06  ldarg.0
0x2b07  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x2b0c  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x2b11  stloc.2
0x2b12  br.s     loc_2B58
0x2b14  ldloc.2
0x2b15  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2b1a  castclass [System.Xml]System.Xml.XmlNode
0x2b1f  stloc.3
0x2b20  ldloc.3
0x2b21  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x2b26  stloc.s  4
0x2b28  ldloc.s  4
0x2b2a  ldstr    aAllow// "Allow"
0x2b2f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2b34  brfalse.s loc_2B44
0x2b36  ldloc.0
0x2b37  ldloc.3
0x2b38  call     class Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag Microsoft.ReportingServices.Diagnostics.RDLSandboxingTypeInfo::Parse(class [System.Xml]System.Xml.XmlNode node)
0x2b3d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag>::Add(var<u1>)
0x2b42  br.s     loc_2B58
0x2b44  ldloc.3
0x2b45  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x2b4a  ldc.i4.8
0x2b4b  beq.s    loc_2B58
0x2b4d  ldloc.3
0x2b4e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x2b53  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowInvalidFormat(string)
0x2b58  ldloc.2
0x2b59  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2b5e  brtrue.s loc_2B14
0x2b60  leave.s  loc_2B76
0x2b62  ldloc.2
0x2b63  isinst   [mscorlib]System.IDisposable
0x2b68  stloc.s  5
0x2b6a  ldloc.s  5
0x2b6c  brfalse.s loc_2B75
0x2b6e  ldloc.s  5
0x2b70  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b75  endfinally
0x2b76  newobj   instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::.ctor()
0x2b7b  stloc.1
0x2b7c  ldloc.1
0x2b7d  ldloc.0
0x2b7e  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x2b83  ldarg.1
0x2b84  ldstr    aTypes// "Types"
0x2b89  ldloc.1
0x2b8a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::Add(var<u1>, !!T0)
0x2b8f  ret
```
