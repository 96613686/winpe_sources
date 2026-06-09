# System.Xml.Serialization.XmlSerializationWriter::WriteStartElement_4

- ea: `0x9bd30`
- end: `0x9bfa2`
- name: `System.Xml.Serialization.XmlSerializationWriter::WriteStartElement_4`
- size: `626`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x9bce0`
- `0x9bcf0`
- `0x9bd00`
- `0x9bd10`
- `0x9bd20`

## callees

- `0x40790`
- `0x40970`
- `0x622f0`
- `0x9bd30`
- `0x9bfb0`
- `0x9c9d0`
- `0x9d310`
- `0x9d400`
- `0xab210`
- `0xab240`

## string_xrefs

- `0x9bf38`: `xmlns`
- `0x9bf67`: `xmlns`
- `0x9bd49`: `XmlCircularReference`
- `0x9bf1c`: `XmlInvalidXmlns`

## pseudocode

```c

```

## disassembly

```asm
0x9bd30  ldarg.3
0x9bd31  brfalse.s loc_9BD7A
0x9bd33  ldarg.0
0x9bd34  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializationWriter::objectsInUse
0x9bd39  brfalse.s loc_9BD7A
0x9bd3b  ldarg.0
0x9bd3c  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializationWriter::objectsInUse
0x9bd41  ldarg.3
0x9bd42  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0x9bd47  brfalse.s loc_9BD6D
0x9bd49  ldstr    aXmlcircularref_0// "XmlCircularReference"
0x9bd4e  ldc.i4.1
0x9bd4f  newarr   [mscorlib]System.Object
0x9bd54  dup
0x9bd55  ldc.i4.0
0x9bd56  ldarg.3
0x9bd57  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x9bd5c  callvirt instance string [mscorlib]System.Type::get_FullName()
0x9bd61  stelem.ref
0x9bd62  call     string System.Xml.Res::GetString(string name, object[] args)
0x9bd67  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9bd6c  throw
0x9bd6d  ldarg.0
0x9bd6e  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializationWriter::objectsInUse
0x9bd73  ldarg.3
0x9bd74  ldarg.3
0x9bd75  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9bd7a  ldnull
0x9bd7b  stloc.0
0x9bd7c  ldc.i4.0
0x9bd7d  stloc.1
0x9bd7e  ldarg.0
0x9bd7f  ldfld    class System.Xml.Serialization.XmlSerializerNamespaces System.Xml.Serialization.XmlSerializationWriter::namespaces
0x9bd84  brfalse  loc_9BE39
0x9bd89  ldarg.0
0x9bd8a  ldfld    class System.Xml.Serialization.XmlSerializerNamespaces System.Xml.Serialization.XmlSerializationWriter::namespaces
0x9bd8f  callvirt instance class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializerNamespaces::get_Namespaces()
0x9bd94  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0x9bd99  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x9bd9e  stloc.2
0x9bd9f  br.s     loc_9BDFE
0x9bda1  ldloc.2
0x9bda2  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9bda7  castclass [mscorlib]System.String
0x9bdac  stloc.3
0x9bdad  ldarg.0
0x9bdae  ldfld    class System.Xml.Serialization.XmlSerializerNamespaces System.Xml.Serialization.XmlSerializationWriter::namespaces
0x9bdb3  callvirt instance class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializerNamespaces::get_Namespaces()
0x9bdb8  ldloc.3
0x9bdb9  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x9bdbe  castclass [mscorlib]System.String
0x9bdc3  stloc.s  4
0x9bdc5  ldloc.3
0x9bdc6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9bdcb  ldc.i4.0
0x9bdcc  ble.s    loc_9BDDA
0x9bdce  ldloc.s  4
0x9bdd0  ldarg.2
0x9bdd1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9bdd6  brfalse.s loc_9BDDA
0x9bdd8  ldloc.3
0x9bdd9  stloc.0
0x9bdda  ldloc.3
0x9bddb  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9bde0  brtrue.s loc_9BDFE
0x9bde2  ldloc.s  4
0x9bde4  brfalse.s loc_9BDEF
0x9bde6  ldloc.s  4
0x9bde8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9bded  brtrue.s loc_9BDF1
0x9bdef  ldc.i4.1
0x9bdf0  stloc.1
0x9bdf1  ldarg.2
0x9bdf2  ldloc.s  4
0x9bdf4  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x9bdf9  brfalse.s loc_9BDFE
0x9bdfb  ldc.i4.1
0x9bdfc  starg.s  4
0x9bdfe  ldloc.2
0x9bdff  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9be04  brtrue.s loc_9BDA1
0x9be06  leave.s  loc_9BE1C
0x9be08  ldloc.2
0x9be09  isinst   [mscorlib]System.IDisposable
0x9be0e  stloc.s  5
0x9be10  ldloc.s  5
0x9be12  brfalse.s loc_9BE1B
0x9be14  ldloc.s  5
0x9be16  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9be1b  endfinally
0x9be1c  ldarg.0
0x9be1d  ldarg.0
0x9be1e  ldarg.0
0x9be1f  ldfld    class System.Xml.Serialization.XmlSerializerNamespaces System.Xml.Serialization.XmlSerializationWriter::namespaces
0x9be24  callvirt instance class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializerNamespaces::get_Namespaces()
0x9be29  ldarg.0
0x9be2a  ldfld    string System.Xml.Serialization.XmlSerializationWriter::aliasBase
0x9be2f  call     instance class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializationWriter::ListUsedPrefixes(class [mscorlib]System.Collections.Hashtable nsList, string prefix)
0x9be34  stfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializationWriter::usedPrefixes
0x9be39  ldarg.s  4
0x9be3b  brfalse.s loc_9BE6B
0x9be3d  ldloc.0
0x9be3e  brtrue.s loc_9BE6B
0x9be40  ldarg.2
0x9be41  brfalse.s loc_9BE6B
0x9be43  ldarg.2
0x9be44  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9be49  ldc.i4.0
0x9be4a  ble.s    loc_9BE6B
0x9be4c  ldarg.0
0x9be4d  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9be52  ldarg.2
0x9be53  callvirt instance string System.Xml.XmlWriter::LookupPrefix(string ns)
0x9be58  stloc.0
0x9be59  ldloc.0
0x9be5a  brfalse.s loc_9BE64
0x9be5c  ldloc.0
0x9be5d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9be62  brtrue.s loc_9BE6B
0x9be64  ldarg.0
0x9be65  call     instance string System.Xml.Serialization.XmlSerializationWriter::NextPrefix()
0x9be6a  stloc.0
0x9be6b  ldloc.0
0x9be6c  brtrue.s loc_9BE7B
0x9be6e  ldarg.s  5
0x9be70  brfalse.s loc_9BE7B
0x9be72  ldarg.s  5
0x9be74  ldarg.2
0x9be75  callvirt instance string System.Xml.Serialization.XmlSerializerNamespaces::LookupPrefix(string ns)
0x9be7a  stloc.0
0x9be7b  ldloc.1
0x9be7c  brfalse.s loc_9BE93
0x9be7e  ldloc.0
0x9be7f  brtrue.s loc_9BE93
0x9be81  ldarg.2
0x9be82  brfalse.s loc_9BE93
0x9be84  ldarg.2
0x9be85  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9be8a  brfalse.s loc_9BE93
0x9be8c  ldarg.0
0x9be8d  call     instance string System.Xml.Serialization.XmlSerializationWriter::NextPrefix()
0x9be92  stloc.0
0x9be93  ldarg.0
0x9be94  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9be99  ldloc.0
0x9be9a  ldarg.1
0x9be9b  ldarg.2
0x9be9c  callvirt instance void System.Xml.XmlWriter::WriteStartElement(string prefix, string localName, string ns)
0x9bea1  ldarg.0
0x9bea2  ldfld    class System.Xml.Serialization.XmlSerializerNamespaces System.Xml.Serialization.XmlSerializationWriter::namespaces
0x9bea7  brfalse  loc_9BF99
0x9beac  ldarg.0
0x9bead  ldfld    class System.Xml.Serialization.XmlSerializerNamespaces System.Xml.Serialization.XmlSerializationWriter::namespaces
0x9beb2  callvirt instance class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializerNamespaces::get_Namespaces()
0x9beb7  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0x9bebc  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x9bec1  stloc.s  6
0x9bec3  br       loc_9BF76
0x9bec8  ldloc.s  6
0x9beca  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9becf  castclass [mscorlib]System.String
0x9bed4  stloc.s  7
0x9bed6  ldarg.0
0x9bed7  ldfld    class System.Xml.Serialization.XmlSerializerNamespaces System.Xml.Serialization.XmlSerializationWriter::namespaces
0x9bedc  callvirt instance class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializerNamespaces::get_Namespaces()
0x9bee1  ldloc.s  7
0x9bee3  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x9bee8  castclass [mscorlib]System.String
0x9beed  stloc.s  8
0x9beef  ldloc.s  7
0x9bef1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9bef6  brtrue.s loc_9BF05
0x9bef8  ldloc.s  8
0x9befa  brfalse.s loc_9BF76
0x9befc  ldloc.s  8
0x9befe  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9bf03  brfalse.s loc_9BF76
0x9bf05  ldloc.s  8
0x9bf07  brfalse.s loc_9BF12
0x9bf09  ldloc.s  8
0x9bf0b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9bf10  brtrue.s loc_9BF49
0x9bf12  ldloc.s  7
0x9bf14  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9bf19  ldc.i4.0
0x9bf1a  ble.s    loc_9BF37
0x9bf1c  ldstr    aXmlinvalidxmln// "XmlInvalidXmlns"
0x9bf21  ldc.i4.1
0x9bf22  newarr   [mscorlib]System.Object
0x9bf27  dup
0x9bf28  ldc.i4.0
0x9bf29  ldloc.s  7
0x9bf2b  stelem.ref
0x9bf2c  call     string System.Xml.Res::GetString(string name, object[] args)
0x9bf31  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9bf36  throw
0x9bf37  ldarg.0
0x9bf38  ldstr    aXmlns// "xmlns"
0x9bf3d  ldloc.s  7
0x9bf3f  ldnull
0x9bf40  ldloc.s  8
0x9bf42  call     instance void System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string prefix, string localName, string ns, string value)
0x9bf47  br.s     loc_9BF76
0x9bf49  ldarg.0
0x9bf4a  ldfld    class System.Xml.XmlWriter System.Xml.Serialization.XmlSerializationWriter::w
0x9bf4f  ldloc.s  8
0x9bf51  callvirt instance string System.Xml.XmlWriter::LookupPrefix(string ns)
0x9bf56  brtrue.s loc_9BF76
0x9bf58  ldloc.0
0x9bf59  brtrue.s loc_9BF66
0x9bf5b  ldloc.s  7
0x9bf5d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9bf62  brtrue.s loc_9BF66
0x9bf64  leave.s  loc_9BF99
0x9bf66  ldarg.0
0x9bf67  ldstr    aXmlns// "xmlns"
0x9bf6c  ldloc.s  7
0x9bf6e  ldnull
0x9bf6f  ldloc.s  8
0x9bf71  call     instance void System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string prefix, string localName, string ns, string value)
0x9bf76  ldloc.s  6
0x9bf78  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9bf7d  brtrue   loc_9BEC8
0x9bf82  leave.s  loc_9BF99
0x9bf84  ldloc.s  6
0x9bf86  isinst   [mscorlib]System.IDisposable
0x9bf8b  stloc.s  5
0x9bf8d  ldloc.s  5
0x9bf8f  brfalse.s loc_9BF98
0x9bf91  ldloc.s  5
0x9bf93  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9bf98  endfinally
0x9bf99  ldarg.0
0x9bf9a  ldarg.s  5
0x9bf9c  call     instance void System.Xml.Serialization.XmlSerializationWriter::WriteNamespaceDeclarations(class System.Xml.Serialization.XmlSerializerNamespaces xmlns)
0x9bfa1  ret
```
