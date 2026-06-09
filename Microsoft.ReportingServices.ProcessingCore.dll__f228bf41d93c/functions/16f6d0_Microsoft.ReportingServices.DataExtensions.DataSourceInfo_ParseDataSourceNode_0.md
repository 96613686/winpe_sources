# Microsoft.ReportingServices.DataExtensions.DataSourceInfo::ParseDataSourceNode_0

- ea: `0x16f6d0`
- end: `0x16f7a0`
- name: `Microsoft.ReportingServices.DataExtensions.DataSourceInfo::ParseDataSourceNode_0`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x16f6c0`

## callees

- `0x16f6d0`
- `0x16f7a0`
- `0x16fb10`
- `0x16fb80`

## string_xrefs

- `0x16f6f5`: `Extension`

## pseudocode

```c

```

## disassembly

```asm
0x16f6d0  ldarg.0
0x16f6d1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x16f6d6  ldstr    aDatasource// "DataSource"
0x16f6db  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x16f6e0  brfalse.s loc_16F6E8
0x16f6e2  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0x16f6e7  throw
0x16f6e8  ldarg.0
0x16f6e9  ldstr    aName_1// "Name"
0x16f6ee  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x16f6f3  stloc.0
0x16f6f4  ldarg.0
0x16f6f5  ldstr    aExtension_0// "Extension"
0x16f6fa  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x16f6ff  pop
0x16f700  ldarg.0
0x16f701  ldstr    aDatasourcedefi// "DataSourceDefinition"
0x16f706  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x16f70b  stloc.1
0x16f70c  ldarg.0
0x16f70d  ldstr    aDatasourcerefe// "DataSourceReference"
0x16f712  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x16f717  stloc.2
0x16f718  ldnull
0x16f719  stloc.3
0x16f71a  ldarg.2
0x16f71b  brtrue.s loc_16F720
0x16f71d  ldloc.0
0x16f71e  brfalse.s loc_16F72A
0x16f720  ldloc.1
0x16f721  ldnull
0x16f722  ceq
0x16f724  ldloc.2
0x16f725  ldnull
0x16f726  ceq
0x16f728  bne.un.s loc_16F760
0x16f72a  ldc.i4.1
0x16f72b  stloc.s  5
0x16f72d  ldarg.1
0x16f72e  brfalse.s loc_16F756
0x16f730  ldarg.0
0x16f731  ldstr    aInvaliddatasou// "InvalidDataSourceReference"
0x16f736  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x16f73b  brfalse.s loc_16F756
0x16f73d  ldc.i4.0
0x16f73e  stloc.s  5
0x16f740  ldloc.0
0x16f741  brfalse.s loc_16F74B
0x16f743  ldloc.0
0x16f744  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x16f749  br.s     loc_16F750
0x16f74b  ldstr    asc_27B730// ""
0x16f750  newobj   instance void Microsoft.ReportingServices.DataExtensions.DataSourceInfo::.ctor(string originalName)
0x16f755  stloc.3
0x16f756  ldloc.s  5
0x16f758  brfalse.s loc_16F760
0x16f75a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0x16f75f  throw
0x16f760  ldloc.0
0x16f761  brfalse.s loc_16F76B
0x16f763  ldloc.0
0x16f764  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x16f769  br.s     loc_16F770
0x16f76b  ldstr    asc_27B730// ""
0x16f770  stloc.s  4
0x16f772  ldloc.1
0x16f773  brfalse.s loc_16F788
0x16f775  ldloc.s  4
0x16f777  ldloc.s  4
0x16f779  ldloc.1
0x16f77a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x16f77f  ldarg.3
0x16f780  newobj   instance void Microsoft.ReportingServices.DataExtensions.DataSourceInfo::.ctor(string name, string originalName, string dataSourceDefinition, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IDataProtection dataProtection)
0x16f785  stloc.3
0x16f786  br.s     loc_16F79E
0x16f788  ldloc.2
0x16f789  brfalse.s loc_16F79E
0x16f78b  ldloc.s  4
0x16f78d  ldloc.2
0x16f78e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x16f793  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x16f798  newobj   instance void Microsoft.ReportingServices.DataExtensions.DataSourceInfo::.ctor(string originalName, string referenceName, valuetype [mscorlib]System.Guid linkID)
0x16f79d  stloc.3
0x16f79e  ldloc.3
0x16f79f  ret
```
