# System.Xml.ValidateNames::ValidateNameInternal

- ea: `0xeb80`
- end: `0xedc1`
- name: `System.Xml.ValidateNames::ValidateNameInternal`
- size: `577`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0xeb60`
- `0xeb70`

## callees

- `0xe890`
- `0xeae0`
- `0xeb40`
- `0xeb80`
- `0xedd0`
- `0x12660`
- `0x12680`

## string_xrefs

- `0xed03`: `http://www.w3.org/XML/1998/namespace`
- `0xebf2`: `xmlns`
- `0xed29`: `xmlns`
- `0xec02`: `XmlBadName`
- `0xecce`: `XmlBadName`
- `0xec46`: `Xml_InvalidPIName`
- `0xed7d`: `Xml_InvalidPIName`
- `0xec60`: `XmlNoNameAllowed`
- `0xeda5`: `XmlNoNameAllowed`
- `0xecac`: `Xml_PrefixForEmptyNs`
- `0xed16`: `Xml_XmlPrefix`
- `0xed39`: `Xml_XmlnsPrefix`
- `0xed57`: `Xml_NamespaceDeclXmlXmlns`

## pseudocode

```c

```

## disassembly

```asm
0xeb80  ldarg.s  4
0xeb82  ldc.i4.1
0xeb83  and
0xeb84  brfalse.s loc_EBAE
0xeb86  ldarg.0
0xeb87  callvirt instance int32 [mscorlib]System.String::get_Length()
0xeb8c  brfalse.s loc_EB9A
0xeb8e  ldarg.0
0xeb8f  ldarg.s  5
0xeb91  call     bool System.Xml.ValidateNames::ParseNCNameInternal(string s, bool throwOnError)
0xeb96  brtrue.s loc_EB9A
0xeb98  ldc.i4.0
0xeb99  ret
0xeb9a  ldarg.1
0xeb9b  callvirt instance int32 [mscorlib]System.String::get_Length()
0xeba0  brfalse.s loc_EBAE
0xeba2  ldarg.1
0xeba3  ldarg.s  5
0xeba5  call     bool System.Xml.ValidateNames::ParseNCNameInternal(string s, bool throwOnError)
0xebaa  brtrue.s loc_EBAE
0xebac  ldc.i4.0
0xebad  ret
0xebae  ldarg.s  4
0xebb0  ldc.i4.2
0xebb1  and
0xebb2  brfalse  loc_EC7A
0xebb7  ldarg.3
0xebb8  ldc.i4.1
0xebb9  beq.s    loc_EBC8
0xebbb  ldarg.3
0xebbc  ldc.i4.2
0xebbd  beq.s    loc_EBE9
0xebbf  ldarg.3
0xebc0  ldc.i4.7
0xebc1  beq.s    loc_EC29
0xebc3  br       loc_EC54
0xebc8  ldarg.1
0xebc9  callvirt instance int32 [mscorlib]System.String::get_Length()
0xebce  brtrue   loc_EC7A
0xebd3  ldarg.s  5
0xebd5  brfalse.s loc_EBE7
0xebd7  ldstr    aXdomEmptyLocal// "Xdom_Empty_LocalName"
0xebdc  ldsfld   string [mscorlib]System.String::Empty
0xebe1  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg)
0xebe6  throw
0xebe7  ldc.i4.0
0xebe8  ret
0xebe9  ldarg.2
0xebea  callvirt instance int32 [mscorlib]System.String::get_Length()
0xebef  brtrue.s loc_EBC8
0xebf1  ldarg.1
0xebf2  ldstr    aXmlns// "xmlns"
0xebf7  callvirt instance bool [mscorlib]System.String::Equals(string)
0xebfc  brfalse.s loc_EBC8
0xebfe  ldarg.s  5
0xec00  brfalse.s loc_EC27
0xec02  ldstr    aXmlbadname// "XmlBadName"
0xec07  ldc.i4.2
0xec08  newarr   [mscorlib]System.String
0xec0d  dup
0xec0e  ldc.i4.0
0xec0f  ldarga.s 3
0xec11  constrained. System.Xml.XPath.XPathNodeType
0xec17  callvirt instance string [mscorlib]System.Object::ToString()
0xec1c  stelem.ref
0xec1d  dup
0xec1e  ldc.i4.1
0xec1f  ldarg.1
0xec20  stelem.ref
0xec21  newobj   instance void System.Xml.XmlException::.ctor(string res, string[] args)
0xec26  throw
0xec27  ldc.i4.0
0xec28  ret
0xec29  ldarg.1
0xec2a  callvirt instance int32 [mscorlib]System.String::get_Length()
0xec2f  brfalse.s loc_EC42
0xec31  ldarg.1
0xec32  callvirt instance int32 [mscorlib]System.String::get_Length()
0xec37  ldc.i4.3
0xec38  bne.un.s loc_EC7A
0xec3a  ldarg.1
0xec3b  call     bool System.Xml.ValidateNames::StartsWithXml(string s)
0xec40  brfalse.s loc_EC7A
0xec42  ldarg.s  5
0xec44  brfalse.s loc_EC52
0xec46  ldstr    aXmlInvalidpina// "Xml_InvalidPIName"
0xec4b  ldarg.1
0xec4c  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg)
0xec51  throw
0xec52  ldc.i4.0
0xec53  ret
0xec54  ldarg.1
0xec55  callvirt instance int32 [mscorlib]System.String::get_Length()
0xec5a  brfalse.s loc_EC7A
0xec5c  ldarg.s  5
0xec5e  brfalse.s loc_EC78
0xec60  ldstr    aXmlnonameallow// "XmlNoNameAllowed"
0xec65  ldarga.s 3
0xec67  constrained. System.Xml.XPath.XPathNodeType
0xec6d  callvirt instance string [mscorlib]System.Object::ToString()
0xec72  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg)
0xec77  throw
0xec78  ldc.i4.0
0xec79  ret
0xec7a  ldarg.s  4
0xec7c  ldc.i4.4
0xec7d  and
0xec7e  brfalse  loc_EDBF
0xec83  ldarg.3
0xec84  ldc.i4.1
0xec85  sub
0xec86  ldc.i4.2
0xec87  ble.un.s loc_EC95
0xec89  ldarg.3
0xec8a  ldc.i4.7
0xec8b  beq      loc_ED69
0xec90  br       loc_ED91
0xec95  ldarg.2
0xec96  callvirt instance int32 [mscorlib]System.String::get_Length()
0xec9b  brtrue.s loc_ECBE
0xec9d  ldarg.0
0xec9e  callvirt instance int32 [mscorlib]System.String::get_Length()
0xeca3  brfalse  loc_EDBF
0xeca8  ldarg.s  5
0xecaa  brfalse.s loc_ECBC
0xecac  ldstr    aXmlPrefixforem// "Xml_PrefixForEmptyNs"
0xecb1  ldsfld   string [mscorlib]System.String::Empty
0xecb6  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg)
0xecbb  throw
0xecbc  ldc.i4.0
0xecbd  ret
0xecbe  ldarg.0
0xecbf  callvirt instance int32 [mscorlib]System.String::get_Length()
0xecc4  brtrue.s loc_ECF5
0xecc6  ldarg.3
0xecc7  ldc.i4.2
0xecc8  bne.un.s loc_ECF5
0xecca  ldarg.s  5
0xeccc  brfalse.s loc_ECF3
0xecce  ldstr    aXmlbadname// "XmlBadName"
0xecd3  ldc.i4.2
0xecd4  newarr   [mscorlib]System.String
0xecd9  dup
0xecda  ldc.i4.0
0xecdb  ldarga.s 3
0xecdd  constrained. System.Xml.XPath.XPathNodeType
0xece3  callvirt instance string [mscorlib]System.Object::ToString()
0xece8  stelem.ref
0xece9  dup
0xecea  ldc.i4.1
0xeceb  ldarg.1
0xecec  stelem.ref
0xeced  newobj   instance void System.Xml.XmlException::.ctor(string res, string[] args)
0xecf2  throw
0xecf3  ldc.i4.0
0xecf4  ret
0xecf5  ldarg.0
0xecf6  ldstr    aXml// "xml"
0xecfb  callvirt instance bool [mscorlib]System.String::Equals(string)
0xed00  brfalse.s loc_ED28
0xed02  ldarg.2
0xed03  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0xed08  callvirt instance bool [mscorlib]System.String::Equals(string)
0xed0d  brtrue   loc_EDBF
0xed12  ldarg.s  5
0xed14  brfalse.s loc_ED26
0xed16  ldstr    aXmlXmlprefix// "Xml_XmlPrefix"
0xed1b  ldsfld   string [mscorlib]System.String::Empty
0xed20  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg)
0xed25  throw
0xed26  ldc.i4.0
0xed27  ret
0xed28  ldarg.0
0xed29  ldstr    aXmlns// "xmlns"
0xed2e  callvirt instance bool [mscorlib]System.String::Equals(string)
0xed33  brfalse.s loc_ED4B
0xed35  ldarg.s  5
0xed37  brfalse.s loc_ED49
0xed39  ldstr    aXmlXmlnsprefix// "Xml_XmlnsPrefix"
0xed3e  ldsfld   string [mscorlib]System.String::Empty
0xed43  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg)
0xed48  throw
0xed49  ldc.i4.0
0xed4a  ret
0xed4b  ldarg.2
0xed4c  call     bool System.Xml.ValidateNames::IsReservedNamespace(string s)
0xed51  brfalse.s loc_EDBF
0xed53  ldarg.s  5
0xed55  brfalse.s loc_ED67
0xed57  ldstr    aXmlNamespacede// "Xml_NamespaceDeclXmlXmlns"
0xed5c  ldsfld   string [mscorlib]System.String::Empty
0xed61  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg)
0xed66  throw
0xed67  ldc.i4.0
0xed68  ret
0xed69  ldarg.0
0xed6a  callvirt instance int32 [mscorlib]System.String::get_Length()
0xed6f  brtrue.s loc_ED79
0xed71  ldarg.2
0xed72  callvirt instance int32 [mscorlib]System.String::get_Length()
0xed77  brfalse.s loc_EDBF
0xed79  ldarg.s  5
0xed7b  brfalse.s loc_ED8F
0xed7d  ldstr    aXmlInvalidpina// "Xml_InvalidPIName"
0xed82  ldarg.0
0xed83  ldarg.1
0xed84  call     string System.Xml.ValidateNames::CreateName(string prefix, string localName)
0xed89  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg)
0xed8e  throw
0xed8f  ldc.i4.0
0xed90  ret
0xed91  ldarg.0
0xed92  callvirt instance int32 [mscorlib]System.String::get_Length()
0xed97  brtrue.s loc_EDA1
0xed99  ldarg.2
0xed9a  callvirt instance int32 [mscorlib]System.String::get_Length()
0xed9f  brfalse.s loc_EDBF
0xeda1  ldarg.s  5
0xeda3  brfalse.s loc_EDBD
0xeda5  ldstr    aXmlnonameallow// "XmlNoNameAllowed"
0xedaa  ldarga.s 3
0xedac  constrained. System.Xml.XPath.XPathNodeType
0xedb2  callvirt instance string [mscorlib]System.Object::ToString()
0xedb7  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg)
0xedbc  throw
0xedbd  ldc.i4.0
0xedbe  ret
0xedbf  ldc.i4.1
0xedc0  ret
```
