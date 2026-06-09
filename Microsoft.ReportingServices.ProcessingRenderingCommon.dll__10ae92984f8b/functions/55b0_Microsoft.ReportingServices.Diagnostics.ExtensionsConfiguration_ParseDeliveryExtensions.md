# Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseDeliveryExtensions

- ea: `0x55b0`
- end: `0x56bb`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseDeliveryExtensions`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x5bd0`

## callees

- `0x4dc0`
- `0x4df0`
- `0x4e10`
- `0x4e20`
- `0x4e30`
- `0x5030`
- `0x55b0`
- `0x5cf0`
- `0x5d40`

## string_xrefs

- `0x564a`: `DefaultDeliveryExtension`
- `0x567c`: `More than one default delivery extension found`

## pseudocode

```c

```

## disassembly

```asm
0x55b0  ldc.i4.0
0x55b1  stloc.0
0x55b2  ldarg.1
0x55b3  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x55b8  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x55bd  stloc.1
0x55be  br       loc_5699
0x55c3  ldloc.1
0x55c4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x55c9  castclass [System.Xml]System.Xml.XmlNode
0x55ce  stloc.2
0x55cf  ldloc.2
0x55d0  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x55d5  ldc.i4.8
0x55d6  beq      loc_5699
0x55db  newobj   instance void Microsoft.ReportingServices.Diagnostics.DeliveryExtension::.ctor()
0x55e0  stloc.3
0x55e1  ldloc.3
0x55e2  ldarg.1
0x55e3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x55e8  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Type(string value)
0x55ed  ldloc.3
0x55ee  stloc.s  4
0x55f0  ldarg.0
0x55f1  ldloc.2
0x55f2  ldloca.s 4
0x55f4  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensionElement(class [System.Xml]System.Xml.XmlNode child, class Microsoft.ReportingServices.Diagnostics.Extension& extension)
0x55f9  ldloc.2
0x55fa  ldstr    aMaxretries// "MaxRetries"
0x55ff  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5604  stloc.s  5
0x5606  ldloc.s  5
0x5608  brfalse.s loc_5621
0x560a  ldloc.3
0x560b  ldloc.s  5
0x560d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5612  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5617  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x561c  callvirt instance void Microsoft.ReportingServices.Diagnostics.DeliveryExtension::set_MaxRetries(int32 value)
0x5621  ldloc.2
0x5622  ldstr    aSecondsbeforer// "SecondsBeforeRetry"
0x5627  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x562c  stloc.s  5
0x562e  ldloc.s  5
0x5630  brfalse.s loc_5649
0x5632  ldloc.3
0x5633  ldloc.s  5
0x5635  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x563a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x563f  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x5644  callvirt instance void Microsoft.ReportingServices.Diagnostics.DeliveryExtension::set_SecondsBeforeRetry(int32 value)
0x5649  ldloc.2
0x564a  ldstr    aDefaultdeliver// "DefaultDeliveryExtension"
0x564f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5654  stloc.s  5
0x5656  ldloc.s  5
0x5658  brfalse.s loc_5691
0x565a  ldloc.3
0x565b  ldloc.s  5
0x565d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5662  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5667  call     bool [mscorlib]System.Convert::ToBoolean(string, class [mscorlib]System.IFormatProvider)
0x566c  callvirt instance void Microsoft.ReportingServices.Diagnostics.DeliveryExtension::set_DefaultDeliveryExtension(bool value)
0x5671  ldloc.3
0x5672  callvirt instance bool Microsoft.ReportingServices.Diagnostics.DeliveryExtension::get_DefaultDeliveryExtension()
0x5677  ldloc.0
0x5678  and
0x5679  brfalse.s loc_5687
0x567b  ldnull
0x567c  ldstr    aMoreThanOneDef// "More than one default delivery extensio"...
0x5681  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(class [mscorlib]System.Exception, string)
0x5686  throw
0x5687  ldloc.3
0x5688  callvirt instance bool Microsoft.ReportingServices.Diagnostics.DeliveryExtension::get_DefaultDeliveryExtension()
0x568d  brfalse.s loc_5691
0x568f  ldc.i4.1
0x5690  stloc.0
0x5691  ldarg.0
0x5692  ldloc.3
0x5693  ldarg.2
0x5694  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::AddExtensionToArray(class Microsoft.ReportingServices.Diagnostics.Extension extension, class ExtensionArray array)
0x5699  ldloc.1
0x569a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x569f  brtrue   loc_55C3
0x56a4  leave.s  loc_56BA
0x56a6  ldloc.1
0x56a7  isinst   [mscorlib]System.IDisposable
0x56ac  stloc.s  6
0x56ae  ldloc.s  6
0x56b0  brfalse.s loc_56B9
0x56b2  ldloc.s  6
0x56b4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x56b9  endfinally
0x56ba  ret
```
