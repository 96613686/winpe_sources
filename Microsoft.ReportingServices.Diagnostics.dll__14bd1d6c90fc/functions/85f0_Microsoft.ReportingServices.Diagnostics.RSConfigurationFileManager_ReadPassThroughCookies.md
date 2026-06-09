# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ReadPassThroughCookies

- ea: `0x85f0`
- end: `0x8682`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ReadPassThroughCookies`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x8530`

## callees

- `0x17d0`
- `0x1820`
- `0x85f0`
- `0x8fd0`

## pseudocode

```c

```

## disassembly

```asm
0x85f0  ldnull
0x85f1  stloc.0
0x85f2  ldarg.0
0x85f3  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x85f8  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x85fd  stloc.1
0x85fe  br.s     loc_864A
0x8600  ldloc.1
0x8601  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8606  castclass [System.Xml]System.Xml.XmlNode
0x860b  stloc.2
0x860c  ldloc.2
0x860d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8612  ldstr    aPassthroughcoo_0// "PassThroughCookie"
0x8617  call     bool [mscorlib]System.String::op_Equality(string, string)
0x861c  brfalse.s loc_8636
0x861e  ldloc.0
0x861f  brtrue.s loc_8627
0x8621  newobj   instance void [System]System.Collections.Specialized.StringCollection::.ctor()
0x8626  stloc.0
0x8627  ldloc.0
0x8628  ldloc.2
0x8629  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x862e  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x8633  pop
0x8634  br.s     loc_864A
0x8636  ldloc.2
0x8637  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x863c  ldc.i4.8
0x863d  beq.s    loc_864A
0x863f  ldloc.2
0x8640  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8645  call     void Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ThrowInvalidFormat(string element)
0x864a  ldloc.1
0x864b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8650  brtrue.s loc_8600
0x8652  leave.s  loc_8665
0x8654  ldloc.1
0x8655  isinst   [mscorlib]System.IDisposable
0x865a  stloc.3
0x865b  ldloc.3
0x865c  brfalse.s loc_8664
0x865e  ldloc.3
0x865f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8664  endfinally
0x8665  ldloc.0
0x8666  brfalse.s loc_8681
0x8668  newobj   instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::.ctor()
0x866d  stloc.s  4
0x866f  ldloc.s  4
0x8671  ldloc.0
0x8672  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x8677  ldarg.1
0x8678  ldc.i4.s 0xD
0x867a  ldloc.s  4
0x867c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::Add(var<u1>, !!T0)
0x8681  ret
```
