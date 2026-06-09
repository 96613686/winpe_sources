# Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::ParseMembers

- ea: `0x2a70`
- end: `0x2b00`
- name: `Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::ParseMembers`
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
- `0x2a70`
- `0x2b90`

## pseudocode

```c

```

## disassembly

```asm
0x2a70  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x2a75  stloc.0
0x2a76  ldarg.0
0x2a77  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x2a7c  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x2a81  stloc.2
0x2a82  br.s     loc_2AC8
0x2a84  ldloc.2
0x2a85  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2a8a  castclass [System.Xml]System.Xml.XmlNode
0x2a8f  stloc.3
0x2a90  ldloc.3
0x2a91  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x2a96  stloc.s  4
0x2a98  ldloc.s  4
0x2a9a  ldstr    aDeny// "Deny"
0x2a9f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2aa4  brfalse.s loc_2AB4
0x2aa6  ldloc.0
0x2aa7  ldloc.3
0x2aa8  call     string Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::ReadNodeText(class [System.Xml]System.Xml.XmlNode node)
0x2aad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2ab2  br.s     loc_2AC8
0x2ab4  ldloc.3
0x2ab5  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x2aba  ldc.i4.8
0x2abb  beq.s    loc_2AC8
0x2abd  ldloc.3
0x2abe  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x2ac3  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowInvalidFormat(string)
0x2ac8  ldloc.2
0x2ac9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2ace  brtrue.s loc_2A84
0x2ad0  leave.s  loc_2AE6
0x2ad2  ldloc.2
0x2ad3  isinst   [mscorlib]System.IDisposable
0x2ad8  stloc.s  5
0x2ada  ldloc.s  5
0x2adc  brfalse.s loc_2AE5
0x2ade  ldloc.s  5
0x2ae0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ae5  endfinally
0x2ae6  newobj   instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::.ctor()
0x2aeb  stloc.1
0x2aec  ldloc.1
0x2aed  ldloc.0
0x2aee  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x2af3  ldarg.1
0x2af4  ldstr    aMembers// "Members"
0x2af9  ldloc.1
0x2afa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::Add(var<u1>, !!T0)
0x2aff  ret
```
