# Microsoft.ReportingServices.Diagnostics.MapTileServerConfiguration::Parse

- ea: `0x1b70`
- end: `0x1c35`
- name: `Microsoft.ReportingServices.Diagnostics.MapTileServerConfiguration::Parse`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7390`

## callees

- `0x17d0`
- `0x1820`
- `0x1b70`
- `0x1ed0`
- `0x1f00`

## string_xrefs

- `0x1bda`: `CacheLevel`

## pseudocode

```c

```

## disassembly

```asm
0x1b70  newobj   instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::.ctor()
0x1b75  stloc.0
0x1b76  newobj   instance void Microsoft.ReportingServices.Diagnostics.MapTileServerConfigurationPropertyBag::.ctor()
0x1b7b  stloc.1
0x1b7c  ldloc.0
0x1b7d  ldloc.1
0x1b7e  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x1b83  ldarg.1
0x1b84  ldc.i4.s 0x69
0x1b86  ldloc.0
0x1b87  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::Add(var<u1>, !!T0)
0x1b8c  ldarg.0
0x1b8d  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x1b92  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x1b97  stloc.2
0x1b98  br.s     loc_1C13
0x1b9a  ldloc.2
0x1b9b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1ba0  castclass [System.Xml]System.Xml.XmlNode
0x1ba5  stloc.3
0x1ba6  ldloc.3
0x1ba7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x1bac  stloc.s  4
0x1bae  ldloc.s  4
0x1bb0  ldstr    aMaxconnections// "MaxConnections"
0x1bb5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bba  brtrue.s loc_1BE6
0x1bbc  ldloc.s  4
0x1bbe  ldstr    aTimeout// "Timeout"
0x1bc3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bc8  brtrue.s loc_1BE6
0x1bca  ldloc.s  4
0x1bcc  ldstr    aAppid// "AppID"
0x1bd1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bd6  brtrue.s loc_1BE6
0x1bd8  ldloc.s  4
0x1bda  ldstr    aCachelevel// "CacheLevel"
0x1bdf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1be4  brfalse.s loc_1BFF
0x1be6  ldloc.1
0x1be7  ldloc.3
0x1be8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x1bed  ldloc.3
0x1bee  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x1bf3  callvirt instance string [mscorlib]System.String::Trim()
0x1bf8  callvirt instance void Microsoft.ReportingServices.Diagnostics.MapTileServerConfigurationPropertyBag::Add(string propertyId, string value)
0x1bfd  br.s     loc_1C13
0x1bff  ldloc.3
0x1c00  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x1c05  ldc.i4.8
0x1c06  beq.s    loc_1C13
0x1c08  ldloc.3
0x1c09  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x1c0e  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowInvalidFormat(string)
0x1c13  ldloc.2
0x1c14  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1c19  brtrue   loc_1B9A
0x1c1e  leave.s  loc_1C34
0x1c20  ldloc.2
0x1c21  isinst   [mscorlib]System.IDisposable
0x1c26  stloc.s  5
0x1c28  ldloc.s  5
0x1c2a  brfalse.s loc_1C33
0x1c2c  ldloc.s  5
0x1c2e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c33  endfinally
0x1c34  ret
```
