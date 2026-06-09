# Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseXML

- ea: `0x52e0`
- end: `0x55a3`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseXML`
- size: `707`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x5290`
- `0x52b0`
- `0x52e0`
- `0x5a70`
- `0x5bd0`
- `0x5e80`
- `0x6440`

## string_xrefs

- `0x53c1`: `Security`

## pseudocode

```c

```

## disassembly

```asm
0x52e0  ldarg.1
0x52e1  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x52e6  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x52eb  stloc.0
0x52ec  br       loc_5581
0x52f1  ldloc.0
0x52f2  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x52f7  castclass [System.Xml]System.Xml.XmlNode
0x52fc  stloc.1
0x52fd  ldnull
0x52fe  stloc.2
0x52ff  ldloc.1
0x5300  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5305  stloc.3
0x5306  ldloc.3
0x5307  brfalse  loc_5562
0x530c  ldloc.3
0x530d  call     instance int32 [mscorlib]System.String::get_Length()
0x5312  stloc.s  4
0x5314  ldloc.s  4
0x5316  ldc.i4.4
0x5317  sub
0x5318  switch   loc_53FF, loc_5562, loc_5453, loc_5562, loc_536B, loc_5562, loc_53EA, loc_547D, loc_5562, loc_5414, loc_5468, loc_538B, loc_5562, loc_5562, loc_5492, loc_54A7
0x535d  ldloc.s  4
0x535f  ldc.i4.s 0x1D
0x5361  beq      loc_54BC
0x5366  br       loc_5562
0x536b  ldloc.3
0x536c  ldc.i4.2
0x536d  call     instance char [mscorlib]System.String::get_Chars(int32)
0x5372  stloc.s  5
0x5374  ldloc.s  5
0x5376  ldc.i4.s 0x63
0x5378  beq.s    loc_53C0
0x537a  ldloc.s  5
0x537c  ldc.i4.s 0x6C
0x537e  beq.s    loc_53AB
0x5380  ldloc.s  5
0x5382  ldc.i4.s 0x73
0x5384  beq.s    loc_53D5
0x5386  br       loc_5562
0x538b  ldloc.3
0x538c  ldc.i4.0
0x538d  call     instance char [mscorlib]System.String::get_Chars(int32)
0x5392  stloc.s  5
0x5394  ldloc.s  5
0x5396  ldc.i4.s 0x45
0x5398  beq      loc_543E
0x539d  ldloc.s  5
0x539f  ldc.i4.s 0x4D
0x53a1  beq      loc_5429
0x53a6  br       loc_5562
0x53ab  ldloc.3
0x53ac  ldstr    aDelivery// "Delivery"
0x53b1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53b6  brtrue   loc_54D1
0x53bb  br       loc_5562
0x53c0  ldloc.3
0x53c1  ldstr    aSecurity// "Security"
0x53c6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53cb  brtrue   loc_5510
0x53d0  br       loc_5562
0x53d5  ldloc.3
0x53d6  ldstr    aDesigner// "Designer"
0x53db  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53e0  brtrue   loc_552B
0x53e5  br       loc_5562
0x53ea  ldloc.3
0x53eb  ldstr    aDeliveryui// "DeliveryUI"
0x53f0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53f5  brtrue   loc_54DD
0x53fa  br       loc_5562
0x53ff  ldloc.3
0x5400  ldstr    aData// "Data"
0x5405  call     bool [mscorlib]System.String::op_Equality(string, string)
0x540a  brtrue   loc_54E9
0x540f  br       loc_5562
0x5414  ldloc.3
0x5415  ldstr    aSemanticquery// "SemanticQuery"
0x541a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x541f  brtrue   loc_54F5
0x5424  br       loc_5562
0x5429  ldloc.3
0x542a  ldstr    aModelgeneratio// "ModelGeneration"
0x542f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5434  brtrue   loc_54FE
0x5439  br       loc_5562
0x543e  ldloc.3
0x543f  ldstr    aEventprocessin// "EventProcessing"
0x5444  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5449  brtrue   loc_5522
0x544e  br       loc_5562
0x5453  ldloc.3
0x5454  ldstr    aRender// "Render"
0x5459  call     bool [mscorlib]System.String::op_Equality(string, string)
0x545e  brtrue   loc_5507
0x5463  br       loc_5562
0x5468  ldloc.3
0x5469  ldstr    aAuthentication// "Authentication"
0x546e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5473  brtrue   loc_5519
0x5478  br       loc_5562
0x547d  ldloc.3
0x547e  ldstr    aReportitems// "ReportItems"
0x5483  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5488  brtrue   loc_5534
0x548d  br       loc_5562
0x5492  ldloc.3
0x5493  ldstr    aReportitemdesi// "ReportItemDesigner"
0x5498  call     bool [mscorlib]System.String::op_Equality(string, string)
0x549d  brtrue   loc_553D
0x54a2  br       loc_5562
0x54a7  ldloc.3
0x54a8  ldstr    aReportitemconv// "ReportItemConverter"
0x54ad  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54b2  brtrue   loc_5546
0x54b7  br       loc_5562
0x54bc  ldloc.3
0x54bd  ldstr    aReportdefiniti// "ReportDefinitionCustomization"
0x54c2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54c7  brtrue   loc_5557
0x54cc  br       loc_5562
0x54d1  ldarg.0
0x54d2  ldfld    class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::m_delivery
0x54d7  stloc.2
0x54d8  br       loc_5576
0x54dd  ldarg.0
0x54de  ldfld    class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::m_deliveryUI
0x54e3  stloc.2
0x54e4  br       loc_5576
0x54e9  ldarg.0
0x54ea  ldfld    class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::m_data
0x54ef  stloc.2
0x54f0  br       loc_5576
0x54f5  ldarg.0
0x54f6  ldfld    class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::m_semanticQuery
0x54fb  stloc.2
0x54fc  br.s     loc_5576
0x54fe  ldarg.0
0x54ff  ldfld    class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::m_modelGeneration
0x5504  stloc.2
0x5505  br.s     loc_5576
0x5507  ldarg.0
0x5508  ldfld    class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::m_renderer
0x550d  stloc.2
0x550e  br.s     loc_5576
0x5510  ldarg.0
0x5511  ldfld    class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::m_security
0x5516  stloc.2
0x5517  br.s     loc_5576
0x5519  ldarg.0
0x551a  ldfld    class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::m_authentication
0x551f  stloc.2
0x5520  br.s     loc_5576
0x5522  ldarg.0
0x5523  ldfld    class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::m_event
0x5528  stloc.2
0x5529  br.s     loc_5576
0x552b  ldarg.0
0x552c  ldfld    class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::m_designer
0x5531  stloc.2
0x5532  br.s     loc_5576
0x5534  ldarg.0
0x5535  ldfld    class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::m_reportItems
0x553a  stloc.2
0x553b  br.s     loc_5576
0x553d  ldarg.0
0x553e  call     instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_ReportItemDesigner()
0x5543  stloc.2
0x5544  br.s     loc_5576
0x5546  ldarg.0
0x5547  ldloc.1
0x5548  ldarg.0
0x5549  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_ReportItemConverter()
0x554e  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseReportItemConverters(class [System.Xml]System.Xml.XmlNode child, class [mscorlib]System.Collections.ArrayList array)
0x5553  ldnull
0x5554  stloc.2
0x5555  br.s     loc_5576
0x5557  ldarg.0
0x5558  ldloc.1
0x5559  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseReportDefinitionCustomization(class [System.Xml]System.Xml.XmlNode child)
0x555e  ldnull
0x555f  stloc.2
0x5560  br.s     loc_5576
0x5562  ldloc.1
0x5563  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x5568  ldc.i4.8
0x5569  beq.s    loc_5576
0x556b  ldloc.1
0x556c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5571  call     void Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowInvalidFormat(string element)
0x5576  ldloc.2
0x5577  brfalse.s loc_5581
0x5579  ldarg.0
0x557a  ldloc.1
0x557b  ldloc.2
0x557c  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensions(class [System.Xml]System.Xml.XmlNode child, class ExtensionArray array)
0x5581  ldloc.0
0x5582  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5587  brtrue   loc_52F1
0x558c  leave.s  loc_55A2
0x558e  ldloc.0
0x558f  isinst   [mscorlib]System.IDisposable
0x5594  stloc.s  6
0x5596  ldloc.s  6
0x5598  brfalse.s loc_55A1
0x559a  ldloc.s  6
0x559c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x55a1  endfinally
0x55a2  ret
```
