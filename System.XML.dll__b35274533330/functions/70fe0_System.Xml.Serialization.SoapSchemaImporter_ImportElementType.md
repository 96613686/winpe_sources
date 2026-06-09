# System.Xml.Serialization.SoapSchemaImporter::ImportElementType

- ea: `0x70fe0`
- end: `0x7111d`
- name: `System.Xml.Serialization.SoapSchemaImporter::ImportElementType`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x70f20`

## callees

- `0x13310`
- `0x13320`
- `0x13380`
- `0x622f0`
- `0x68c00`
- `0x70fe0`
- `0x711f0`
- `0x712a0`
- `0x85600`
- `0xd29f0`
- `0xd2a80`
- `0xd2ab0`
- `0xd2ae0`

## string_xrefs

- `0x7103e`: `XmlInvalidSchemaElementType`
- `0x7106f`: `XmlInvalidSchemaElementType`
- `0x710b4`: `XmlInvalidSubstitutionGroupUse`
- `0x710e3`: `XmlElementMissingType`

## pseudocode

```c

```

## disassembly

```asm
0x70fe0  ldarg.1
0x70fe1  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaElement::get_SchemaTypeName()
0x70fe6  callvirt instance bool System.Xml.XmlQualifiedName::get_IsEmpty()
0x70feb  brtrue.s loc_71000
0x70fed  ldarg.0
0x70fee  ldarg.1
0x70fef  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaElement::get_SchemaTypeName()
0x70ff4  ldc.i4.0
0x70ff5  call     instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.SoapSchemaImporter::ImportType(class System.Xml.XmlQualifiedName name, bool excludeFromImport)
0x70ffa  stloc.0
0x70ffb  br       loc_71114
0x71000  ldarg.1
0x71001  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Schema.XmlSchemaElement::get_SchemaType()
0x71006  brfalse  loc_710A0
0x7100b  ldarg.1
0x7100c  call     class System.Xml.XmlQualifiedName System.Xml.Serialization.XmlSchemas::GetParentName(class System.Xml.Schema.XmlSchemaObject item)
0x71011  stloc.1
0x71012  ldarg.1
0x71013  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Schema.XmlSchemaElement::get_SchemaType()
0x71018  isinst   System.Xml.Schema.XmlSchemaComplexType
0x7101d  brfalse.s loc_7106F
0x7101f  ldarg.0
0x71020  ldarg.1
0x71021  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Schema.XmlSchemaElement::get_SchemaType()
0x71026  castclass System.Xml.Schema.XmlSchemaComplexType
0x7102b  ldarg.2
0x7102c  ldc.i4.0
0x7102d  call     instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.SoapSchemaImporter::ImportType(class System.Xml.Schema.XmlSchemaComplexType type, string typeNs, bool excludeFromImport)
0x71032  stloc.0
0x71033  ldloc.0
0x71034  isinst   System.Xml.Serialization.ArrayMapping
0x71039  brtrue   loc_71114
0x7103e  ldstr    aXmlinvalidsche// "XmlInvalidSchemaElementType"
0x71043  ldc.i4.3
0x71044  newarr   [mscorlib]System.Object
0x71049  dup
0x7104a  ldc.i4.0
0x7104b  ldloc.1
0x7104c  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x71051  stelem.ref
0x71052  dup
0x71053  ldc.i4.1
0x71054  ldloc.1
0x71055  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x7105a  stelem.ref
0x7105b  dup
0x7105c  ldc.i4.2
0x7105d  ldarg.1
0x7105e  callvirt instance string System.Xml.Schema.XmlSchemaElement::get_Name()
0x71063  stelem.ref
0x71064  call     string System.Xml.Res::GetString(string name, object[] args)
0x71069  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7106e  throw
0x7106f  ldstr    aXmlinvalidsche// "XmlInvalidSchemaElementType"
0x71074  ldc.i4.3
0x71075  newarr   [mscorlib]System.Object
0x7107a  dup
0x7107b  ldc.i4.0
0x7107c  ldloc.1
0x7107d  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x71082  stelem.ref
0x71083  dup
0x71084  ldc.i4.1
0x71085  ldloc.1
0x71086  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x7108b  stelem.ref
0x7108c  dup
0x7108d  ldc.i4.2
0x7108e  ldarg.1
0x7108f  callvirt instance string System.Xml.Schema.XmlSchemaElement::get_Name()
0x71094  stelem.ref
0x71095  call     string System.Xml.Res::GetString(string name, object[] args)
0x7109a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7109f  throw
0x710a0  ldarg.1
0x710a1  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaElement::get_SubstitutionGroup()
0x710a6  callvirt instance bool System.Xml.XmlQualifiedName::get_IsEmpty()
0x710ab  brtrue.s loc_710DC
0x710ad  ldarg.1
0x710ae  call     class System.Xml.XmlQualifiedName System.Xml.Serialization.XmlSchemas::GetParentName(class System.Xml.Schema.XmlSchemaObject item)
0x710b3  stloc.2
0x710b4  ldstr    aXmlinvalidsubs// "XmlInvalidSubstitutionGroupUse"
0x710b9  ldc.i4.2
0x710ba  newarr   [mscorlib]System.Object
0x710bf  dup
0x710c0  ldc.i4.0
0x710c1  ldloc.2
0x710c2  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x710c7  stelem.ref
0x710c8  dup
0x710c9  ldc.i4.1
0x710ca  ldloc.2
0x710cb  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x710d0  stelem.ref
0x710d1  call     string System.Xml.Res::GetString(string name, object[] args)
0x710d6  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x710db  throw
0x710dc  ldarg.1
0x710dd  call     class System.Xml.XmlQualifiedName System.Xml.Serialization.XmlSchemas::GetParentName(class System.Xml.Schema.XmlSchemaObject item)
0x710e2  stloc.3
0x710e3  ldstr    aXmlelementmiss// "XmlElementMissingType"
0x710e8  ldc.i4.3
0x710e9  newarr   [mscorlib]System.Object
0x710ee  dup
0x710ef  ldc.i4.0
0x710f0  ldloc.3
0x710f1  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x710f6  stelem.ref
0x710f7  dup
0x710f8  ldc.i4.1
0x710f9  ldloc.3
0x710fa  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x710ff  stelem.ref
0x71100  dup
0x71101  ldc.i4.2
0x71102  ldarg.1
0x71103  callvirt instance string System.Xml.Schema.XmlSchemaElement::get_Name()
0x71108  stelem.ref
0x71109  call     string System.Xml.Res::GetString(string name, object[] args)
0x7110e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x71113  throw
0x71114  ldloc.0
0x71115  ldc.i4.1
0x71116  callvirt instance void System.Xml.Serialization.TypeMapping::set_ReferencedByElement(bool value)
0x7111b  ldloc.0
0x7111c  ret
```
