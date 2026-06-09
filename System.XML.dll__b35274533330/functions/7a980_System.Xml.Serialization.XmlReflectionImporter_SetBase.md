# System.Xml.Serialization.XmlReflectionImporter::SetBase

- ea: `0x7a980`
- end: `0x7aa9a`
- name: `System.Xml.Serialization.XmlReflectionImporter::SetBase`
- size: `282`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x7a790`
- `0x7a980`

## callees

- `0x13310`
- `0x13380`
- `0x622f0`
- `0x69e40`
- `0x69e80`
- `0x6a050`
- `0x6b080`
- `0x6b0c0`
- `0x7a980`
- `0xcfe50`
- `0xd4230`
- `0xd5360`
- `0xd6cd0`
- `0xd6cf0`

## string_xrefs

- `0x7a98f`: `http://www.w3.org/2001/XMLSchema`
- `0x7a9bd`: `XmlMissingSchema`
- `0x7a9e5`: `XmlGetSchemaInclude`

## pseudocode

```c

```

## disassembly

```asm
0x7a980  ldarg.2
0x7a981  callvirt instance bool System.Xml.XmlQualifiedName::get_IsEmpty()
0x7a986  brfalse.s loc_7A989
0x7a988  ret
0x7a989  ldarg.2
0x7a98a  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x7a98f  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x7a994  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7a999  brfalse.s loc_7A99C
0x7a99b  ret
0x7a99c  ldarg.1
0x7a99d  callvirt instance class System.Xml.Schema.XmlSchemaSet System.Xml.Serialization.SerializableMapping::get_Schemas()
0x7a9a2  stloc.0
0x7a9a3  ldloc.0
0x7a9a4  ldarg.2
0x7a9a5  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x7a9aa  callvirt instance class [mscorlib]System.Collections.ICollection System.Xml.Schema.XmlSchemaSet::Schemas(string targetNamespace)
0x7a9af  castclass [mscorlib]System.Collections.ArrayList
0x7a9b4  stloc.1
0x7a9b5  ldloc.1
0x7a9b6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x7a9bb  brtrue.s loc_7A9DC
0x7a9bd  ldstr    aXmlmissingsche// "XmlMissingSchema"
0x7a9c2  ldc.i4.1
0x7a9c3  newarr   [mscorlib]System.Object
0x7a9c8  dup
0x7a9c9  ldc.i4.0
0x7a9ca  ldarg.2
0x7a9cb  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x7a9d0  stelem.ref
0x7a9d1  call     string System.Xml.Res::GetString(string name, object[] args)
0x7a9d6  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7a9db  throw
0x7a9dc  ldloc.1
0x7a9dd  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x7a9e2  ldc.i4.1
0x7a9e3  ble.s    loc_7AA1E
0x7a9e5  ldstr    aXmlgetschemain// "XmlGetSchemaInclude"
0x7a9ea  ldc.i4.3
0x7a9eb  newarr   [mscorlib]System.Object
0x7a9f0  dup
0x7a9f1  ldc.i4.0
0x7a9f2  ldarg.2
0x7a9f3  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x7a9f8  stelem.ref
0x7a9f9  dup
0x7a9fa  ldc.i4.1
0x7a9fb  ldtoken  System.Xml.Serialization.IXmlSerializable
0x7aa00  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7aa05  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7aa0a  stelem.ref
0x7aa0b  dup
0x7aa0c  ldc.i4.2
0x7aa0d  ldstr    aGetschema// "GetSchema"
0x7aa12  stelem.ref
0x7aa13  call     string System.Xml.Res::GetString(string name, object[] args)
0x7aa18  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7aa1d  throw
0x7aa1e  ldloc.1
0x7aa1f  ldc.i4.0
0x7aa20  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x7aa25  castclass System.Xml.Schema.XmlSchema
0x7aa2a  stloc.2
0x7aa2b  ldloc.2
0x7aa2c  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchema::get_SchemaTypes()
0x7aa31  ldarg.2
0x7aa32  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0x7aa37  castclass System.Xml.Schema.XmlSchemaType
0x7aa3c  stloc.3
0x7aa3d  ldloc.3
0x7aa3e  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Schema.XmlSchemaType::get_Redefined()
0x7aa43  brtrue.s loc_7AA48
0x7aa45  ldloc.3
0x7aa46  br.s     loc_7AA4E
0x7aa48  ldloc.3
0x7aa49  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Schema.XmlSchemaType::get_Redefined()
0x7aa4e  stloc.3
0x7aa4f  ldarg.0
0x7aa50  ldfld    class System.Xml.Serialization.NameTable System.Xml.Serialization.XmlReflectionImporter::serializables
0x7aa55  ldarg.2
0x7aa56  callvirt instance object System.Xml.Serialization.NameTable::get_Item(class System.Xml.XmlQualifiedName qname)
0x7aa5b  brtrue.s loc_7AA82
0x7aa5d  ldarg.2
0x7aa5e  ldloc.0
0x7aa5f  newobj   instance void System.Xml.Serialization.SerializableMapping::.ctor(class System.Xml.XmlQualifiedName xsiType, class System.Xml.Schema.XmlSchemaSet schemas)
0x7aa64  stloc.s  4
0x7aa66  ldarg.0
0x7aa67  ldloc.s  4
0x7aa69  ldloc.3
0x7aa6a  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_DerivedFrom()
0x7aa6f  call     instance void System.Xml.Serialization.XmlReflectionImporter::SetBase(class System.Xml.Serialization.SerializableMapping mapping, class System.Xml.XmlQualifiedName baseQname)
0x7aa74  ldarg.0
0x7aa75  ldfld    class System.Xml.Serialization.NameTable System.Xml.Serialization.XmlReflectionImporter::serializables
0x7aa7a  ldarg.2
0x7aa7b  ldloc.s  4
0x7aa7d  callvirt instance void System.Xml.Serialization.NameTable::Add(class System.Xml.XmlQualifiedName qname, object value)
0x7aa82  ldarg.1
0x7aa83  ldarg.0
0x7aa84  ldfld    class System.Xml.Serialization.NameTable System.Xml.Serialization.XmlReflectionImporter::serializables
0x7aa89  ldarg.2
0x7aa8a  callvirt instance object System.Xml.Serialization.NameTable::get_Item(class System.Xml.XmlQualifiedName qname)
0x7aa8f  castclass System.Xml.Serialization.SerializableMapping
0x7aa94  callvirt instance void System.Xml.Serialization.SerializableMapping::SetBaseMapping(class System.Xml.Serialization.SerializableMapping mapping)
0x7aa99  ret
```
