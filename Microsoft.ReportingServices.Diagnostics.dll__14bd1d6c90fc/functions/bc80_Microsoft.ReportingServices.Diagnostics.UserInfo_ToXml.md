# Microsoft.ReportingServices.Diagnostics.UserInfo::ToXml

- ea: `0xbc80`
- end: `0xbd07`
- name: `Microsoft.ReportingServices.Diagnostics.UserInfo::ToXml`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb6d0`

## callees

- `0xbc80`

## string_xrefs

- `0xbc94`: `Paths`

## pseudocode

```c

```

## disassembly

```asm
0xbc80  ldarg.0
0xbc81  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.UserInfo::m_requests
0xbc86  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0xbc8b  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0xbc90  brtrue.s loc_BC93
0xbc92  ret
0xbc93  ldarg.1
0xbc94  ldstr    aPaths// "Paths"
0xbc99  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xbc9e  ldarg.0
0xbc9f  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.UserInfo::m_requests
0xbca4  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0xbca9  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xbcae  stloc.0
0xbcaf  br.s     loc_BCE5
0xbcb1  ldloc.0
0xbcb2  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xbcb7  castclass [mscorlib]System.String
0xbcbc  stloc.1
0xbcbd  ldarg.1
0xbcbe  ldstr    aPath_0// "Path"
0xbcc3  ldloc.1
0xbcc4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xbcc9  ldarg.1
0xbcca  ldstr    aNrreq// "NrReq"
0xbccf  ldarg.0
0xbcd0  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.UserInfo::m_requests
0xbcd5  ldloc.1
0xbcd6  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xbcdb  callvirt instance string [mscorlib]System.Object::ToString()
0xbce0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xbce5  ldloc.0
0xbce6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbceb  brtrue.s loc_BCB1
0xbced  leave.s  loc_BD00
0xbcef  ldloc.0
0xbcf0  isinst   [mscorlib]System.IDisposable
0xbcf5  stloc.2
0xbcf6  ldloc.2
0xbcf7  brfalse.s loc_BCFF
0xbcf9  ldloc.2
0xbcfa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbcff  endfinally
0xbd00  ldarg.1
0xbd01  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xbd06  ret
```
