# Microsoft.SharePoint.Client.DataConverter::WriteXmlElement

- ea: `0x110e0`
- end: `0x11235`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteXmlElement`
- size: `341`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x11030`
- `0x11060`
- `0x110e0`

## callees

- `0x110e0`
- `0x13030`
- `0x13210`
- `0x13220`
- `0x132d0`
- `0x13410`
- `0x13720`

## string_xrefs

- `0x110e3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x110e0  ldarg.0
0x110e1  brtrue.s loc_110EE
0x110e3  ldstr    aWriter// "writer"
0x110e8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x110ed  throw
0x110ee  ldarg.1
0x110ef  brtrue.s loc_110F8
0x110f1  ldarg.0
0x110f2  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x110f7  ret
0x110f8  ldarg.0
0x110f9  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartObjectScope()
0x110fe  ldarg.3
0x110ff  brfalse.s loc_11113
0x11101  ldarg.0
0x11102  ldstr    aObjecttype// "_ObjectType_"
0x11107  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x1110c  ldarg.0
0x1110d  ldarg.3
0x1110e  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0x11113  ldarg.0
0x11114  ldstr    aName// "Name"
0x11119  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x1111e  ldarg.0
0x1111f  ldarg.1
0x11120  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x11125  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0x1112a  ldarg.1
0x1112b  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x11130  callvirt instance int32 [System.Xml]System.Xml.XmlNamedNodeMap::get_Count()
0x11135  ldc.i4.0
0x11136  ble.s    loc_1119C
0x11138  ldarg.0
0x11139  ldstr    aAttributes// "Attributes"
0x1113e  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x11143  ldarg.0
0x11144  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartObjectScope()
0x11149  ldarg.1
0x1114a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1114f  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNamedNodeMap::GetEnumerator()
0x11154  stloc.2
0x11155  br.s     loc_1117B
0x11157  ldloc.2
0x11158  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1115d  castclass [System.Xml]System.Xml.XmlAttribute
0x11162  stloc.0
0x11163  ldarg.0
0x11164  ldloc.0
0x11165  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x1116a  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x1116f  ldarg.0
0x11170  ldloc.0
0x11171  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x11176  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0x1117b  ldloc.2
0x1117c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11181  brtrue.s loc_11157
0x11183  leave.s  loc_11196
0x11185  ldloc.2
0x11186  isinst   [mscorlib]System.IDisposable
0x1118b  stloc.3
0x1118c  ldloc.3
0x1118d  brfalse.s loc_11195
0x1118f  ldloc.3
0x11190  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11195  endfinally
0x11196  ldarg.0
0x11197  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x1119c  ldarg.1
0x1119d  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x111a2  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x111a7  ldc.i4.0
0x111a8  ble      loc_1122E
0x111ad  ldarg.0
0x111ae  ldstr    aChildren// "Children"
0x111b3  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x111b8  ldarg.0
0x111b9  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x111be  ldarg.1
0x111bf  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x111c4  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x111c9  stloc.s  4
0x111cb  br.s     loc_11208
0x111cd  ldloc.s  4
0x111cf  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x111d4  castclass [System.Xml]System.Xml.XmlNode
0x111d9  stloc.1
0x111da  ldloc.1
0x111db  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x111e0  ldc.i4.1
0x111e1  bne.un.s loc_111F3
0x111e3  ldarg.0
0x111e4  ldloc.1
0x111e5  castclass [System.Xml]System.Xml.XmlElement
0x111ea  ldarg.2
0x111eb  ldnull
0x111ec  call     void Microsoft.SharePoint.Client.DataConverter::WriteXmlElement(class Microsoft.SharePoint.Client.JsonWriter writer, class [System.Xml]System.Xml.XmlElement elem, class Microsoft.SharePoint.Client.ProxyContext proxyContext, string type)
0x111f1  br.s     loc_11208
0x111f3  ldloc.1
0x111f4  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x111f9  ldc.i4.3
0x111fa  bne.un.s loc_11208
0x111fc  ldarg.0
0x111fd  ldloc.1
0x111fe  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x11203  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0x11208  ldloc.s  4
0x1120a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1120f  brtrue.s loc_111CD
0x11211  leave.s  loc_11228
0x11213  ldloc.s  4
0x11215  isinst   [mscorlib]System.IDisposable
0x1121a  stloc.s  5
0x1121c  ldloc.s  5
0x1121e  brfalse.s loc_11227
0x11220  ldloc.s  5
0x11222  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11227  endfinally
0x11228  ldarg.0
0x11229  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x1122e  ldarg.0
0x1122f  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x11234  ret
```
