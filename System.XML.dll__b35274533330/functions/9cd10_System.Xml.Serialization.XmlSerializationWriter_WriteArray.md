# System.Xml.Serialization.XmlSerializationWriter::WriteArray

- ea: `0x9cd10`
- end: `0x9d05b`
- name: `System.Xml.Serialization.XmlSerializationWriter::WriteArray`
- size: `843`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x9d1d0`

## callees

- `0x13310`
- `0x13320`
- `0x13410`
- `0x13450`
- `0x407b0`
- `0x407d0`
- `0x74600`
- `0x9b6a0`
- `0x9b6b0`
- `0x9bc30`
- `0x9bd20`
- `0x9c720`
- `0x9cd10`
- `0x9d090`
- `0x9d280`

## string_xrefs

- `0x9cd7f`: `http://www.w3.org/2001/XMLSchema`
- `0x9ce21`: `http://www.w3.org/2001/XMLSchema`
- `0x9ce7e`: `http://schemas.xmlsoap.org/soap/encoding/`
- `0x9cf02`: `http://schemas.xmlsoap.org/soap/encoding/`
- `0x9d000`: `http://schemas.xmlsoap.org/soap/encoding/`

## pseudocode

```c

```

## disassembly

```asm
0x9cd10  ldarg.s  4
0x9cd12  ldnull
0x9cd13  call     class [mscorlib]System.Type System.Xml.Serialization.TypeScope::GetArrayElementType(class [mscorlib]System.Type type, string memberInfo)
0x9cd18  stloc.0
0x9cd19  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x9cd1e  stloc.3
0x9cd1f  ldarg.0
0x9cd20  ldfld    bool System.Xml.Serialization.XmlSerializationWriter::soap12
0x9cd25  brtrue.s loc_9CD67
0x9cd27  br.s     loc_9CD3D
0x9cd29  ldloc.0
0x9cd2a  ldnull
0x9cd2b  call     class [mscorlib]System.Type System.Xml.Serialization.TypeScope::GetArrayElementType(class [mscorlib]System.Type type, string memberInfo)
0x9cd30  stloc.0
0x9cd31  ldloc.3
0x9cd32  ldstr    asc_12E3FA// "[]"
0x9cd37  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9cd3c  pop
0x9cd3d  ldloc.0
0x9cd3e  callvirt instance bool [mscorlib]System.Type::get_IsArray()
0x9cd43  brtrue.s loc_9CD57
0x9cd45  ldtoken  [mscorlib]System.Collections.IEnumerable
0x9cd4a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9cd4f  ldloc.0
0x9cd50  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x9cd55  brfalse.s loc_9CD67
0x9cd57  ldarg.0
0x9cd58  ldloc.0
0x9cd59  ldc.i4.0
0x9cd5a  call     instance class System.Xml.XmlQualifiedName System.Xml.Serialization.XmlSerializationWriter::GetPrimitiveTypeName(class [mscorlib]System.Type type, bool throwIfUnknown)
0x9cd5f  ldnull
0x9cd60  call     bool System.Xml.XmlQualifiedName::op_Equality(class System.Xml.XmlQualifiedName a, class System.Xml.XmlQualifiedName b)
0x9cd65  brtrue.s loc_9CD29
0x9cd67  ldloc.0
0x9cd68  ldtoken  [mscorlib]System.Object
0x9cd6d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9cd72  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9cd77  brfalse.s loc_9CD8A
0x9cd79  ldstr    aAnytype// "anyType"
0x9cd7e  stloc.1
0x9cd7f  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x9cd84  stloc.2
0x9cd85  br       loc_9CE42
0x9cd8a  ldarg.0
0x9cd8b  ldloc.0
0x9cd8c  call     instance class TypeEntry System.Xml.Serialization.XmlSerializationWriter::GetTypeEntry(class [mscorlib]System.Type t)
0x9cd91  stloc.s  4
0x9cd93  ldloc.s  4
0x9cd95  brfalse.s loc_9CDAC
0x9cd97  ldloc.s  4
0x9cd99  ldfld    string TypeEntry::typeName
0x9cd9e  stloc.1
0x9cd9f  ldloc.s  4
0x9cda1  ldfld    string TypeEntry::typeNs
0x9cda6  stloc.2
0x9cda7  br       loc_9CE42
0x9cdac  ldarg.0
0x9cdad  ldfld    bool System.Xml.Serialization.XmlSerializationWriter::soap12
0x9cdb2  brfalse.s loc_9CE29
0x9cdb4  ldarg.0
0x9cdb5  ldloc.0
0x9cdb6  ldc.i4.0
0x9cdb7  call     instance class System.Xml.XmlQualifiedName System.Xml.Serialization.XmlSerializationWriter::GetPrimitiveTypeName(class [mscorlib]System.Type type, bool throwIfUnknown)
0x9cdbc  stloc.s  5
0x9cdbe  ldloc.s  5
0x9cdc0  ldnull
0x9cdc1  call     bool System.Xml.XmlQualifiedName::op_Inequality(class System.Xml.XmlQualifiedName a, class System.Xml.XmlQualifiedName b)
0x9cdc6  brfalse.s loc_9CDDA
0x9cdc8  ldloc.s  5
0x9cdca  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x9cdcf  stloc.1
0x9cdd0  ldloc.s  5
0x9cdd2  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x9cdd7  stloc.2
0x9cdd8  br.s     loc_9CE42
0x9cdda  ldloc.0
0x9cddb  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::get_BaseType()
0x9cde0  stloc.s  6
0x9cde2  br.s     loc_9CDFB
0x9cde4  ldarg.0
0x9cde5  ldloc.s  6
0x9cde7  call     instance class TypeEntry System.Xml.Serialization.XmlSerializationWriter::GetTypeEntry(class [mscorlib]System.Type t)
0x9cdec  stloc.s  4
0x9cdee  ldloc.s  4
0x9cdf0  brtrue.s loc_9CE05
0x9cdf2  ldloc.s  6
0x9cdf4  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::get_BaseType()
0x9cdf9  stloc.s  6
0x9cdfb  ldloc.s  6
0x9cdfd  ldnull
0x9cdfe  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9ce03  brtrue.s loc_9CDE4
0x9ce05  ldloc.s  4
0x9ce07  brfalse.s loc_9CE1B
0x9ce09  ldloc.s  4
0x9ce0b  ldfld    string TypeEntry::typeName
0x9ce10  stloc.1
0x9ce11  ldloc.s  4
0x9ce13  ldfld    string TypeEntry::typeNs
0x9ce18  stloc.2
0x9ce19  br.s     loc_9CE42
0x9ce1b  ldstr    aAnytype// "anyType"
0x9ce20  stloc.1
0x9ce21  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x9ce26  stloc.2
0x9ce27  br.s     loc_9CE42
0x9ce29  ldarg.0
0x9ce2a  ldloc.0
0x9ce2b  call     instance class System.Xml.XmlQualifiedName System.Xml.Serialization.XmlSerializationWriter::GetPrimitiveTypeName(class [mscorlib]System.Type type)
0x9ce30  stloc.s  7
0x9ce32  ldloc.s  7
0x9ce34  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x9ce39  stloc.1
0x9ce3a  ldloc.s  7
0x9ce3c  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x9ce41  stloc.2
0x9ce42  ldloc.3
0x9ce43  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x9ce48  ldc.i4.0
0x9ce49  ble.s    loc_9CE58
0x9ce4b  ldloc.1
0x9ce4c  ldloc.3
0x9ce4d  callvirt instance string [mscorlib]System.Object::ToString()
0x9ce52  call     string [mscorlib]System.String::Concat(string, string)
0x9ce57  stloc.1
0x9ce58  ldarg.0
0x9ce59  ldfld    bool System.Xml.Serialization.XmlSerializationWriter::soap12
0x9ce5e  brfalse.s loc_9CE78
0x9ce60  ldarg.1
0x9ce61  brfalse.s loc_9CE78
0x9ce63  ldarg.1
0x9ce64  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9ce69  ldc.i4.0
0x9ce6a  ble.s    loc_9CE78
0x9ce6c  ldarg.0
0x9ce6d  ldarg.1
0x9ce6e  ldarg.2
0x9ce6f  ldnull
0x9ce70  ldc.i4.0
0x9ce71  call     instance void System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string name, string ns, object o, bool writePrefixed)
0x9ce76  br.s     loc_9CE8A
0x9ce78  ldarg.0
0x9ce79  ldstr    aArray_0// "Array"
0x9ce7e  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/encodin"...
0x9ce83  ldnull
0x9ce84  ldc.i4.1
0x9ce85  call     instance void System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string name, string ns, object o, bool writePrefixed)
0x9ce8a  ldarg.0
0x9ce8b  ldarg.3
0x9ce8c  ldc.i4.0
0x9ce8d  call     instance void System.Xml.Serialization.XmlSerializationWriter::WriteId(object o, bool addToReferencesList)
0x9ce92  ldarg.s  4
0x9ce94  callvirt instance bool [mscorlib]System.Type::get_IsArray()
0x9ce99  brfalse  loc_9CF61
0x9ce9e  ldarg.3
0x9ce9f  castclass [mscorlib]System.Array
0x9cea4  stloc.s  8
0x9cea6  ldloc.s  8
0x9cea8  callvirt instance int32 [mscorlib]System.Array::get_Length()
0x9cead  stloc.s  9
0x9ceaf  ldarg.0
0x9ceb0  ldfld    bool System.Xml.Serialization.XmlSerializationWriter::soap12
0x9ceb5  brfalse.s loc_9CEF7
0x9ceb7  ldarg.0
0x9ceb8  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9cebd  ldstr    aItemtype// "itemType"
0x9cec2  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2003/05/soap-encoding"
0x9cec7  ldarg.0
0x9cec8  ldloc.1
0x9cec9  ldloc.2
0x9ceca  call     instance string System.Xml.Serialization.XmlSerializationWriter::GetQualifiedName(string name, string ns)
0x9cecf  callvirt instance void System.Xml.XmlWriter::WriteAttributeString(string localName, string ns, string value)
0x9ced4  ldarg.0
0x9ced5  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9ceda  ldstr    aArraysize// "arraySize"
0x9cedf  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2003/05/soap-encoding"
0x9cee4  ldloca.s 9
0x9cee6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9ceeb  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9cef0  callvirt instance void System.Xml.XmlWriter::WriteAttributeString(string localName, string ns, string value)
0x9cef5  br.s     loc_9CF2F
0x9cef7  ldarg.0
0x9cef8  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9cefd  ldstr    aArraytype// "arrayType"
0x9cf02  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/encodin"...
0x9cf07  ldarg.0
0x9cf08  ldloc.1
0x9cf09  ldloc.2
0x9cf0a  call     instance string System.Xml.Serialization.XmlSerializationWriter::GetQualifiedName(string name, string ns)
0x9cf0f  ldstr    asc_12BE9A// "["
0x9cf14  ldloca.s 9
0x9cf16  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9cf1b  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9cf20  ldstr    asc_12BE9E// "]"
0x9cf25  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x9cf2a  callvirt instance void System.Xml.XmlWriter::WriteAttributeString(string localName, string ns, string value)
0x9cf2f  ldc.i4.0
0x9cf30  stloc.s  0xA
0x9cf32  br.s     loc_9CF56
0x9cf34  ldarg.0
0x9cf35  ldstr    aItem// "Item"
0x9cf3a  ldstr    asc_1284AE// ""
0x9cf3f  ldloc.s  8
0x9cf41  ldloc.s  0xA
0x9cf43  callvirt instance object [mscorlib]System.Array::GetValue(int32)
0x9cf48  ldloc.0
0x9cf49  ldc.i4.0
0x9cf4a  ldc.i4.1
0x9cf4b  call     instance void System.Xml.Serialization.XmlSerializationWriter::WritePotentiallyReferencingElement(string n, string ns, object o, class [mscorlib]System.Type ambientType, bool suppressReference, bool isNullable)
0x9cf50  ldloc.s  0xA
0x9cf52  ldc.i4.1
0x9cf53  add
0x9cf54  stloc.s  0xA
0x9cf56  ldloc.s  0xA
0x9cf58  ldloc.s  9
0x9cf5a  blt.s    loc_9CF34
0x9cf5c  br       loc_9D04F
0x9cf61  ldtoken  [mscorlib]System.Collections.ICollection
0x9cf66  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9cf6b  ldarg.s  4
0x9cf6d  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x9cf72  brtrue.s loc_9CF77
0x9cf74  ldc.i4.m1
0x9cf75  br.s     loc_9CF82
0x9cf77  ldarg.3
0x9cf78  castclass [mscorlib]System.Collections.ICollection
0x9cf7d  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x9cf82  stloc.s  0xB
0x9cf84  ldarg.0
0x9cf85  ldfld    bool System.Xml.Serialization.XmlSerializationWriter::soap12
0x9cf8a  brfalse.s loc_9CFD1
0x9cf8c  ldarg.0
0x9cf8d  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9cf92  ldstr    aItemtype// "itemType"
0x9cf97  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2003/05/soap-encoding"
0x9cf9c  ldarg.0
0x9cf9d  ldloc.1
0x9cf9e  ldloc.2
0x9cf9f  call     instance string System.Xml.Serialization.XmlSerializationWriter::GetQualifiedName(string name, string ns)
0x9cfa4  callvirt instance void System.Xml.XmlWriter::WriteAttributeString(string localName, string ns, string value)
0x9cfa9  ldloc.s  0xB
0x9cfab  ldc.i4.0
0x9cfac  blt.s    loc_9D019
0x9cfae  ldarg.0
0x9cfaf  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9cfb4  ldstr    aArraysize// "arraySize"
0x9cfb9  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2003/05/soap-encoding"
0x9cfbe  ldloca.s 0xB
0x9cfc0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9cfc5  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9cfca  callvirt instance void System.Xml.XmlWriter::WriteAttributeString(string localName, string ns, string value)
0x9cfcf  br.s     loc_9D019
0x9cfd1  ldloc.s  0xB
0x9cfd3  ldc.i4.0
0x9cfd4  bge.s    loc_9CFDD
0x9cfd6  ldstr    asc_12E3FA// "[]"
0x9cfdb  br.s     loc_9CFF3
0x9cfdd  ldstr    asc_12BE9A// "["
0x9cfe2  ldloca.s 0xB
0x9cfe4  call     instance string [mscorlib]System.Int32::ToString()
0x9cfe9  ldstr    asc_12BE9E// "]"
0x9cfee  call     string [mscorlib]System.String::Concat(string, string, string)
0x9cff3  stloc.s  0xD
0x9cff5  ldarg.0
0x9cff6  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9cffb  ldstr    aArraytype// "arrayType"
0x9d000  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/encodin"...
0x9d005  ldarg.0
0x9d006  ldloc.1
0x9d007  ldloc.2
0x9d008  call     instance string System.Xml.Serialization.XmlSerializationWriter::GetQualifiedName(string name, string ns)
0x9d00d  ldloc.s  0xD
0x9d00f  call     string [mscorlib]System.String::Concat(string, string)
0x9d014  callvirt instance void System.Xml.XmlWriter::WriteAttributeString(string localName, string ns, string value)
0x9d019  ldarg.3
0x9d01a  castclass [mscorlib]System.Collections.IEnumerable
0x9d01f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x9d024  stloc.s  0xC
0x9d026  ldloc.s  0xC
0x9d028  brfalse.s loc_9D04F
0x9d02a  br.s     loc_9D046
0x9d02c  ldarg.0
0x9d02d  ldstr    aItem// "Item"
0x9d032  ldstr    asc_1284AE// ""
0x9d037  ldloc.s  0xC
0x9d039  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9d03e  ldloc.0
0x9d03f  ldc.i4.0
0x9d040  ldc.i4.1
0x9d041  call     instance void System.Xml.Serialization.XmlSerializationWriter::WritePotentiallyReferencingElement(string n, string ns, object o, class [mscorlib]System.Type ambientType, bool suppressReference, bool isNullable)
0x9d046  ldloc.s  0xC
0x9d048  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9d04d  brtrue.s loc_9D02C
0x9d04f  ldarg.0
0x9d050  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9d055  callvirt instance void System.Xml.XmlWriter::WriteEndElement()
0x9d05a  ret
```
