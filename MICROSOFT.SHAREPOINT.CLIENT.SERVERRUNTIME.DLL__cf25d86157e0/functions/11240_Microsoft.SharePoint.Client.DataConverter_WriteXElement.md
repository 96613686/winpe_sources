# Microsoft.SharePoint.Client.DataConverter::WriteXElement

- ea: `0x11240`
- end: `0x11384`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteXElement`
- size: `324`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x11090`
- `0x110c0`
- `0x11240`

## callees

- `0x11240`
- `0x13030`
- `0x13210`
- `0x13220`
- `0x132d0`
- `0x13410`
- `0x13720`

## string_xrefs

- `0x11243`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x11240  ldarg.0
0x11241  brtrue.s loc_1124E
0x11243  ldstr    aWriter// "writer"
0x11248  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1124d  throw
0x1124e  ldarg.1
0x1124f  brtrue.s loc_11258
0x11251  ldarg.0
0x11252  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x11257  ret
0x11258  ldarg.0
0x11259  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartObjectScope()
0x1125e  ldarg.3
0x1125f  brfalse.s loc_11273
0x11261  ldarg.0
0x11262  ldstr    aObjecttype// "_ObjectType_"
0x11267  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x1126c  ldarg.0
0x1126d  ldarg.3
0x1126e  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0x11273  ldarg.0
0x11274  ldstr    aName// "Name"
0x11279  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x1127e  ldarg.0
0x1127f  ldarg.1
0x11280  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x11285  callvirt instance string [mscorlib]System.Object::ToString()
0x1128a  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0x1128f  ldc.i4.0
0x11290  stloc.0
0x11291  ldarg.1
0x11292  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XAttribute> [System.Xml.Linq]System.Xml.Linq.XElement::Attributes()
0x11297  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XAttribute>::GetEnumerator()
0x1129c  stloc.s  4
0x1129e  br.s     loc_112DB
0x112a0  ldloc.s  4
0x112a2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XAttribute>::get_Current()
0x112a7  stloc.1
0x112a8  ldloc.0
0x112a9  brtrue.s loc_112BE
0x112ab  ldarg.0
0x112ac  ldstr    aAttributes// "Attributes"
0x112b1  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x112b6  ldarg.0
0x112b7  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartObjectScope()
0x112bc  ldc.i4.1
0x112bd  stloc.0
0x112be  ldarg.0
0x112bf  ldloc.1
0x112c0  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Name()
0x112c5  callvirt instance string [mscorlib]System.Object::ToString()
0x112ca  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x112cf  ldarg.0
0x112d0  ldloc.1
0x112d1  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x112d6  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0x112db  ldloc.s  4
0x112dd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x112e2  brtrue.s loc_112A0
0x112e4  leave.s  loc_112F2
0x112e6  ldloc.s  4
0x112e8  brfalse.s loc_112F1
0x112ea  ldloc.s  4
0x112ec  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x112f1  endfinally
0x112f2  ldloc.0
0x112f3  brfalse.s loc_112FB
0x112f5  ldarg.0
0x112f6  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x112fb  ldc.i4.0
0x112fc  stloc.2
0x112fd  ldarg.1
0x112fe  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XNode> [System.Xml.Linq]System.Xml.Linq.XContainer::DescendantNodes()
0x11303  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XNode>::GetEnumerator()
0x11308  stloc.s  5
0x1130a  br.s     loc_1135D
0x1130c  ldloc.s  5
0x1130e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XNode>::get_Current()
0x11313  stloc.3
0x11314  ldloc.2
0x11315  brtrue.s loc_1132A
0x11317  ldarg.0
0x11318  ldstr    aChildren// "Children"
0x1131d  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x11322  ldarg.0
0x11323  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x11328  ldc.i4.1
0x11329  stloc.2
0x1132a  ldloc.3
0x1132b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml.Linq]System.Xml.Linq.XObject::get_NodeType()
0x11330  ldc.i4.1
0x11331  bne.un.s loc_11343
0x11333  ldarg.0
0x11334  ldloc.3
0x11335  castclass [System.Xml.Linq]System.Xml.Linq.XElement
0x1133a  ldarg.2
0x1133b  ldnull
0x1133c  call     void Microsoft.SharePoint.Client.DataConverter::WriteXElement(class Microsoft.SharePoint.Client.JsonWriter writer, class [System.Xml.Linq]System.Xml.Linq.XElement elem, class Microsoft.SharePoint.Client.ProxyContext proxyContext, string type)
0x11341  br.s     loc_1135D
0x11343  ldloc.3
0x11344  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml.Linq]System.Xml.Linq.XObject::get_NodeType()
0x11349  ldc.i4.3
0x1134a  bne.un.s loc_1135D
0x1134c  ldarg.0
0x1134d  ldloc.3
0x1134e  castclass [System.Xml.Linq]System.Xml.Linq.XText
0x11353  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XText::get_Value()
0x11358  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0x1135d  ldloc.s  5
0x1135f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11364  brtrue.s loc_1130C
0x11366  leave.s  loc_11374
0x11368  ldloc.s  5
0x1136a  brfalse.s loc_11373
0x1136c  ldloc.s  5
0x1136e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11373  endfinally
0x11374  ldloc.2
0x11375  brfalse.s loc_1137D
0x11377  ldarg.0
0x11378  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x1137d  ldarg.0
0x1137e  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x11383  ret
```
