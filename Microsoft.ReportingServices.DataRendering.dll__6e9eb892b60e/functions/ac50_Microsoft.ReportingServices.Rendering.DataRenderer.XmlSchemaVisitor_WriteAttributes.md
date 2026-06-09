# Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::WriteAttributes

- ea: `0xac50`
- end: `0xacf3`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::WriteAttributes`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xad40`

## callees

- `0xa4f0`
- `0xac50`
- `0xadf0`

## string_xrefs

- `0xac9a`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c

```

## disassembly

```asm
0xac50  ldarg.0
0xac51  ldfld    class Scope Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_currentScope
0xac56  ldfld    class [mscorlib]System.Collections.Hashtable Scope::Attributes
0xac5b  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0xac60  ldc.i4.0
0xac61  ble      loc_ACF2
0xac66  ldarg.0
0xac67  ldfld    class Scope Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_currentScope
0xac6c  ldfld    class [mscorlib]System.Collections.Hashtable Scope::Attributes
0xac71  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0xac76  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xac7b  stloc.0
0xac7c  br.s     loc_ACD7
0xac7e  ldloc.0
0xac7f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xac84  castclass [mscorlib]System.String
0xac89  stloc.1
0xac8a  ldarg.0
0xac8b  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xac90  ldstr    aXsd// "xsd"
0xac95  ldstr    aAttribute// "attribute"
0xac9a  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2001/XMLSchema"
0xac9f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0xaca4  ldarg.0
0xaca5  ldstr    aName_0// "name"
0xacaa  ldloc.1
0xacab  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xacb0  ldarg.0
0xacb1  ldarg.0
0xacb2  ldfld    class Scope Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_currentScope
0xacb7  ldfld    class [mscorlib]System.Collections.Hashtable Scope::Attributes
0xacbc  ldloc.1
0xacbd  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xacc2  unbox.any [mscorlib]System.TypeCode
0xacc7  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::WriteXmlType(valuetype [mscorlib]System.TypeCode tc)
0xaccc  ldarg.0
0xaccd  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xacd2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xacd7  ldloc.0
0xacd8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xacdd  brtrue.s loc_AC7E
0xacdf  leave.s  loc_ACF2
0xace1  ldloc.0
0xace2  isinst   [mscorlib]System.IDisposable
0xace7  stloc.2
0xace8  ldloc.2
0xace9  brfalse.s loc_ACF1
0xaceb  ldloc.2
0xacec  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xacf1  endfinally
0xacf2  ret
```
