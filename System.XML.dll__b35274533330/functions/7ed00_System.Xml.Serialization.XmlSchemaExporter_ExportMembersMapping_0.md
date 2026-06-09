# System.Xml.Serialization.XmlSchemaExporter::ExportMembersMapping_0

- ea: `0x7ed00`
- end: `0x7ee62`
- name: `System.Xml.Serialization.XmlSchemaExporter::ExportMembersMapping_0`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config`

## callers

- `0x7ecf0`

## callees

- `0x622f0`
- `0x68600`
- `0x68660`
- `0x68690`
- `0x686d0`
- `0x69620`
- `0x69640`
- `0x69660`
- `0x696f0`
- `0x69ce0`
- `0x69d20`
- `0x72dd0`
- `0x79510`
- `0x79520`
- `0x79660`
- `0x7ed00`
- `0x7f180`
- `0x7f1b0`
- `0x7f500`
- `0x80580`

## string_xrefs

- `0x7ed59`: `XmlBareAttributeMember`
- `0x7ed85`: `XmlBareTextMember`
- `0x7ede1`: `XmlIllegalArrayElement`

## pseudocode

```c

```

## disassembly

```asm
0x7ed00  ldarg.1
0x7ed01  callvirt instance void System.Xml.Serialization.XmlMapping::CheckShallow()
0x7ed06  ldarg.1
0x7ed07  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.XmlMapping::get_Accessor()
0x7ed0c  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7ed11  castclass System.Xml.Serialization.MembersMapping
0x7ed16  stloc.0
0x7ed17  ldarg.0
0x7ed18  ldarg.1
0x7ed19  callvirt instance class System.Xml.Serialization.TypeScope System.Xml.Serialization.XmlMapping::get_Scope()
0x7ed1e  call     instance void System.Xml.Serialization.XmlSchemaExporter::CheckScope(class System.Xml.Serialization.TypeScope scope)
0x7ed23  ldloc.0
0x7ed24  callvirt instance bool System.Xml.Serialization.MembersMapping::get_HasWrapperElement()
0x7ed29  ldarg.2
0x7ed2a  and
0x7ed2b  brfalse.s loc_7ED3F
0x7ed2d  ldarg.0
0x7ed2e  ldarg.1
0x7ed2f  callvirt instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.XmlMapping::get_Accessor()
0x7ed34  call     instance class System.Xml.Schema.XmlSchemaElement System.Xml.Serialization.XmlSchemaExporter::ExportElement(class System.Xml.Serialization.ElementAccessor accessor)
0x7ed39  pop
0x7ed3a  br       loc_7EE55
0x7ed3f  ldloc.0
0x7ed40  callvirt instance class System.Xml.Serialization.MemberMapping[] System.Xml.Serialization.MembersMapping::get_Members()
0x7ed45  stloc.1
0x7ed46  ldc.i4.0
0x7ed47  stloc.2
0x7ed48  br       loc_7EE4C
0x7ed4d  ldloc.1
0x7ed4e  ldloc.2
0x7ed4f  ldelem.ref
0x7ed50  stloc.3
0x7ed51  ldloc.3
0x7ed52  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x7ed57  brfalse.s loc_7ED7D
0x7ed59  ldstr    aXmlbareattribu// "XmlBareAttributeMember"
0x7ed5e  ldc.i4.1
0x7ed5f  newarr   [mscorlib]System.Object
0x7ed64  dup
0x7ed65  ldc.i4.0
0x7ed66  ldloc.3
0x7ed67  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x7ed6c  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x7ed71  stelem.ref
0x7ed72  call     string System.Xml.Res::GetString(string name, object[] args)
0x7ed77  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7ed7c  throw
0x7ed7d  ldloc.3
0x7ed7e  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x7ed83  brfalse.s loc_7EDA9
0x7ed85  ldstr    aXmlbaretextmem// "XmlBareTextMember"
0x7ed8a  ldc.i4.1
0x7ed8b  newarr   [mscorlib]System.Object
0x7ed90  dup
0x7ed91  ldc.i4.0
0x7ed92  ldloc.3
0x7ed93  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x7ed98  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x7ed9d  stelem.ref
0x7ed9e  call     string System.Xml.Res::GetString(string name, object[] args)
0x7eda3  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7eda8  throw
0x7eda9  ldloc.3
0x7edaa  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.AccessorMapping::get_Elements()
0x7edaf  brfalse  loc_7EE48
0x7edb4  ldloc.3
0x7edb5  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.AccessorMapping::get_Elements()
0x7edba  ldlen
0x7edbb  brfalse  loc_7EE48
0x7edc0  ldloc.3
0x7edc1  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x7edc6  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsArrayLike()
0x7edcb  brfalse.s loc_7EE07
0x7edcd  ldloc.3
0x7edce  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.AccessorMapping::get_Elements()
0x7edd3  ldc.i4.0
0x7edd4  ldelem.ref
0x7edd5  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7edda  isinst   System.Xml.Serialization.ArrayMapping
0x7eddf  brtrue.s loc_7EE07
0x7ede1  ldstr    aXmlillegalarra_1// "XmlIllegalArrayElement"
0x7ede6  ldc.i4.1
0x7ede7  newarr   [mscorlib]System.Object
0x7edec  dup
0x7eded  ldc.i4.0
0x7edee  ldloc.3
0x7edef  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.AccessorMapping::get_Elements()
0x7edf4  ldc.i4.0
0x7edf5  ldelem.ref
0x7edf6  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x7edfb  stelem.ref
0x7edfc  call     string System.Xml.Res::GetString(string name, object[] args)
0x7ee01  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7ee06  throw
0x7ee07  ldarg.2
0x7ee08  brfalse.s loc_7EE1B
0x7ee0a  ldarg.0
0x7ee0b  ldloc.3
0x7ee0c  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.AccessorMapping::get_Elements()
0x7ee11  ldc.i4.0
0x7ee12  ldelem.ref
0x7ee13  call     instance class System.Xml.Schema.XmlSchemaElement System.Xml.Serialization.XmlSchemaExporter::ExportElement(class System.Xml.Serialization.ElementAccessor accessor)
0x7ee18  pop
0x7ee19  br.s     loc_7EE48
0x7ee1b  ldarg.0
0x7ee1c  ldloc.3
0x7ee1d  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.AccessorMapping::get_Elements()
0x7ee22  ldc.i4.0
0x7ee23  ldelem.ref
0x7ee24  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7ee29  ldloc.3
0x7ee2a  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.AccessorMapping::get_Elements()
0x7ee2f  ldc.i4.0
0x7ee30  ldelem.ref
0x7ee31  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x7ee36  ldloc.3
0x7ee37  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.AccessorMapping::get_Elements()
0x7ee3c  ldc.i4.0
0x7ee3d  ldelem.ref
0x7ee3e  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0x7ee43  call     instance void System.Xml.Serialization.XmlSchemaExporter::ExportMapping(class System.Xml.Serialization.Mapping mapping, string ns, bool isAny)
0x7ee48  ldloc.2
0x7ee49  ldc.i4.1
0x7ee4a  add
0x7ee4b  stloc.2
0x7ee4c  ldloc.2
0x7ee4d  ldloc.1
0x7ee4e  ldlen
0x7ee4f  conv.i4
0x7ee50  blt      loc_7ED4D
0x7ee55  ldarg.0
0x7ee56  ldarg.1
0x7ee57  callvirt instance class System.Xml.Serialization.TypeScope System.Xml.Serialization.XmlMapping::get_Scope()
0x7ee5c  call     instance void System.Xml.Serialization.XmlSchemaExporter::ExportRootIfNecessary(class System.Xml.Serialization.TypeScope typeScope)
0x7ee61  ret
```
