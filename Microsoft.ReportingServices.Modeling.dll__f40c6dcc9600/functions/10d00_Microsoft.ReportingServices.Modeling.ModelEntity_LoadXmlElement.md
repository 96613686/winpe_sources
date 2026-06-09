# Microsoft.ReportingServices.Modeling.ModelEntity::LoadXmlElement

- ea: `0x10d00`
- end: `0x11048`
- name: `Microsoft.ReportingServices.Modeling.ModelEntity::LoadXmlElement`
- size: `840`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x97d0`
- `0xa750`
- `0xa760`
- `0xa7b0`
- `0xa850`
- `0xa870`
- `0xa8e0`
- `0xa9e0`
- `0xaa40`
- `0xc0b0`
- `0xc470`
- `0x10710`
- `0x10770`
- `0x107a0`
- `0x107d0`
- `0x10800`
- `0x10830`
- `0x108b0`
- `0x108c0`
- `0x108d0`
- `0x10d00`
- `0x117d0`
- `0x11d10`
- `0x122e0`
- `0x12600`
- `0x13f10`
- `0x243d0`
- `0x25a90`
- `0x25b70`

## string_xrefs

- `0x10e38`: `DefaultSecurityFilter`
- `0x10fb3`: `DefaultSecurityFilter`
- `0x10ecb`: `SecurityFilters`
- `0x10f9b`: `Failed to read AttributeReference inside of DefaultSecurityFilter element.`
- `0x10fbf`: `Failed to move to </DefaultSecurityFilter>.`

## pseudocode

```c

```

## disassembly

```asm
0x10d00  ldarg.1
0x10d01  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_IsDefaultNamespace()
0x10d06  brfalse  loc_11040
0x10d0b  ldarg.1
0x10d0c  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName()
0x10d11  stloc.0
0x10d12  ldloc.0
0x10d13  brfalse  loc_11040
0x10d18  ldloc.0
0x10d19  call     instance int32 [mscorlib]System.String::get_Length()
0x10d1e  stloc.1
0x10d1f  ldloc.1
0x10d20  ldc.i4.5
0x10d21  sub
0x10d22  switch   loc_10EDF, loc_10DB1, loc_11040, loc_10E0D, loc_11040, loc_11040, loc_10E76, loc_11040, loc_11040, loc_10D80, loc_10ECA, loc_11040, loc_10DF8, loc_11040, loc_10E8B, loc_11040, loc_10D97, loc_11040, loc_10E4C
0x10d73  ldloc.1
0x10d74  ldc.i4.s 0x1A
0x10d76  beq      loc_10E61
0x10d7b  br       loc_11040
0x10d80  ldloc.0
0x10d81  ldc.i4.0
0x10d82  call     instance char [mscorlib]System.String::get_Chars(int32)
0x10d87  stloc.2
0x10d88  ldloc.2
0x10d89  ldc.i4.s 0x43
0x10d8b  beq.s    loc_10DCE
0x10d8d  ldloc.2
0x10d8e  ldc.i4.s 0x53
0x10d90  beq.s    loc_10DE3
0x10d92  br       loc_11040
0x10d97  ldloc.0
0x10d98  ldc.i4.0
0x10d99  call     instance char [mscorlib]System.String::get_Chars(int32)
0x10d9e  stloc.2
0x10d9f  ldloc.2
0x10da0  ldc.i4.s 0x44
0x10da2  beq      loc_10E37
0x10da7  ldloc.2
0x10da8  ldc.i4.s 0x49
0x10daa  beq.s    loc_10E22
0x10dac  br       loc_11040
0x10db1  ldloc.0
0x10db2  ldc.i4.0
0x10db3  call     instance char [mscorlib]System.String::get_Chars(int32)
0x10db8  stloc.2
0x10db9  ldloc.2
0x10dba  ldc.i4.s 0x43
0x10dbc  beq      loc_10EB5
0x10dc1  ldloc.2
0x10dc2  ldc.i4.s 0x46
0x10dc4  beq      loc_10EA0
0x10dc9  br       loc_11040
0x10dce  ldloc.0
0x10dcf  ldstr    aCollectionname// "CollectionName"
0x10dd4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10dd9  brtrue   loc_10EF4
0x10dde  br       loc_11040
0x10de3  ldloc.0
0x10de4  ldstr    aSortattributes// "SortAttributes"
0x10de9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10dee  brtrue   loc_10F48
0x10df3  br       loc_11040
0x10df8  ldloc.0
0x10df9  ldstr    aInstanceselect// "InstanceSelection"
0x10dfe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10e03  brtrue   loc_10F02
0x10e08  br       loc_11040
0x10e0d  ldloc.0
0x10e0e  ldstr    aIslookup// "IsLookup"
0x10e13  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10e18  brtrue   loc_10F10
0x10e1d  br       loc_11040
0x10e22  ldloc.0
0x10e23  ldstr    aIdentifyingatt// "IdentifyingAttributes"
0x10e28  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10e2d  brtrue   loc_10F1E
0x10e32  br       loc_11040
0x10e37  ldloc.0
0x10e38  ldstr    aDefaultsecurit// "DefaultSecurityFilter"
0x10e3d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10e42  brtrue   loc_10F8E
0x10e47  br       loc_11040
0x10e4c  ldloc.0
0x10e4d  ldstr    aDefaultdetaila// "DefaultDetailAttributes"
0x10e52  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10e57  brtrue   loc_10F2C
0x10e5c  br       loc_11040
0x10e61  ldloc.0
0x10e62  ldstr    aDefaultaggrega_0// "DefaultAggregateAttributes"
0x10e67  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10e6c  brtrue   loc_10F3A
0x10e71  br       loc_11040
0x10e76  ldloc.0
0x10e77  ldstr    aInheritance// "Inheritance"
0x10e7c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10e81  brtrue   loc_10F56
0x10e86  br       loc_11040
0x10e8b  ldloc.0
0x10e8c  ldstr    aDisjointinheri// "DisjointInheritance"
0x10e91  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10e96  brtrue   loc_10F64
0x10e9b  br       loc_11040
0x10ea0  ldloc.0
0x10ea1  ldstr    aFields// "Fields"
0x10ea6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10eab  brtrue   loc_10F72
0x10eb0  br       loc_11040
0x10eb5  ldloc.0
0x10eb6  ldstr    aColumn// "Column"
0x10ebb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10ec0  brtrue   loc_11006
0x10ec5  br       loc_11040
0x10eca  ldloc.0
0x10ecb  ldstr    aSecurityfilter// "SecurityFilters"
0x10ed0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10ed5  brtrue   loc_10F80
0x10eda  br       loc_11040
0x10edf  ldloc.0
0x10ee0  ldstr    aTable// "Table"
0x10ee5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10eea  brtrue   loc_10FCC
0x10eef  br       loc_11040
0x10ef4  ldarg.0
0x10ef5  ldarg.1
0x10ef6  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsString()
0x10efb  stfld    string Microsoft.ReportingServices.Modeling.ModelEntity::m_collectionName
0x10f00  ldc.i4.1
0x10f01  ret
0x10f02  ldarg.0
0x10f03  ldarg.1
0x10f04  callvirt T0x2B000054
0x10f09  stfld    valuetype Microsoft.ReportingServices.Modeling.EntityInstanceSelection Microsoft.ReportingServices.Modeling.ModelEntity::m_instanceSelection
0x10f0e  ldc.i4.1
0x10f0f  ret
0x10f10  ldarg.0
0x10f11  ldarg.1
0x10f12  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsBoolean()
0x10f17  stfld    bool Microsoft.ReportingServices.Modeling.ModelEntity::m_lookup
0x10f1c  ldc.i4.1
0x10f1d  ret
0x10f1e  ldarg.0
0x10f1f  ldfld    class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::m_identAttrs
0x10f24  ldarg.1
0x10f25  callvirt instance void Microsoft.ReportingServices.Modeling.AttributeReferenceCollection::Load(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x10f2a  ldc.i4.1
0x10f2b  ret
0x10f2c  ldarg.0
0x10f2d  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultDetailAttributes()
0x10f32  ldarg.1
0x10f33  callvirt instance void Microsoft.ReportingServices.Modeling.AttributeReferenceCollection::Load(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x10f38  ldc.i4.1
0x10f39  ret
0x10f3a  ldarg.0
0x10f3b  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultAggregateAttributes()
0x10f40  ldarg.1
0x10f41  callvirt instance void Microsoft.ReportingServices.Modeling.AttributeReferenceCollection::Load(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x10f46  ldc.i4.1
0x10f47  ret
0x10f48  ldarg.0
0x10f49  call     instance class Microsoft.ReportingServices.Modeling.SortAttributeCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_SortAttributes()
0x10f4e  ldarg.1
0x10f4f  callvirt instance void Microsoft.ReportingServices.Modeling.SortAttributeCollection::Load(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x10f54  ldc.i4.1
0x10f55  ret
0x10f56  ldarg.0
0x10f57  ldarg.1
0x10f58  call     class Microsoft.ReportingServices.Modeling.EntityInheritance Microsoft.ReportingServices.Modeling.EntityInheritance::FromReader(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x10f5d  call     instance void Microsoft.ReportingServices.Modeling.ModelEntity::set_Inheritance(class Microsoft.ReportingServices.Modeling.EntityInheritance value)
0x10f62  ldc.i4.1
0x10f63  ret
0x10f64  ldarg.0
0x10f65  ldarg.1
0x10f66  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsBoolean()
0x10f6b  stfld    bool Microsoft.ReportingServices.Modeling.ModelEntity::m_disjointInheritance
0x10f70  ldc.i4.1
0x10f71  ret
0x10f72  ldarg.0
0x10f73  call     instance class Microsoft.ReportingServices.Modeling.ModelFieldFolderItemCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_Fields()
0x10f78  ldarg.1
0x10f79  callvirt instance void class Microsoft.ReportingServices.Modeling.OwnedModelItemCollection`1<class Microsoft.ReportingServices.Modeling.ModelFieldFolderItem>::Load(class Microsoft.ReportingServices.Modeling.ModelingXmlReader)
0x10f7e  ldc.i4.1
0x10f7f  ret
0x10f80  ldarg.0
0x10f81  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_SecurityFilters()
0x10f86  ldarg.1
0x10f87  callvirt instance void Microsoft.ReportingServices.Modeling.AttributeReferenceCollection::Load(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x10f8c  ldc.i4.1
0x10f8d  ret
0x10f8e  ldarg.1
0x10f8f  ldstr    aAttributerefer// "AttributeReference"
0x10f94  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::MoveToDescendant(string name)
0x10f99  brtrue.s loc_10FA6
0x10f9b  ldstr    aFailedToReadAt// "Failed to read AttributeReference insid"...
0x10fa0  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x10fa5  throw
0x10fa6  ldarg.0
0x10fa7  ldarg.1
0x10fa8  call     class Microsoft.ReportingServices.Modeling.AttributeReference Microsoft.ReportingServices.Modeling.AttributeReference::FromReader(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x10fad  call     instance void Microsoft.ReportingServices.Modeling.ModelEntity::set_DefaultSecurityFilter(class Microsoft.ReportingServices.Modeling.AttributeReference value)
0x10fb2  ldarg.1
0x10fb3  ldstr    aDefaultsecurit// "DefaultSecurityFilter"
0x10fb8  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::MoveToEndElement(string name)
0x10fbd  brtrue.s loc_10FCA
0x10fbf  ldstr    aFailedToMoveTo// "Failed to move to </DefaultSecurityFilt"...
0x10fc4  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x10fc9  throw
0x10fca  ldc.i4.1
0x10fcb  ret
0x10fcc  ldarg.0
0x10fcd  call     instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x10fd2  brfalse.s loc_10FF8
0x10fd4  ldarg.1
0x10fd5  callvirt instance class Microsoft.ReportingServices.Modeling.ValidationContext Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Validation()
0x10fda  ldc.i4.8
0x10fdb  ldarg.1
0x10fdc  callvirt instance class Microsoft.ReportingServices.Modeling.ValidationContext Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Validation()
0x10fe1  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x10fe6  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidEntityBinding(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x10feb  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x10ff0  ldarg.1
0x10ff1  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlReader::Skip()
0x10ff6  ldc.i4.1
0x10ff7  ret
0x10ff8  ldarg.0
0x10ff9  ldarg.1
0x10ffa  call     class Microsoft.ReportingServices.Modeling.TableBinding Microsoft.ReportingServices.Modeling.TableBinding::FromReader(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x10fff  call     instance void Microsoft.ReportingServices.Modeling.ModelEntity::set_Binding(class Microsoft.ReportingServices.Modeling.Binding value)
0x11004  ldc.i4.1
0x11005  ret
0x11006  ldarg.0
0x11007  call     instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x1100c  brfalse.s loc_11032
0x1100e  ldarg.1
0x1100f  callvirt instance class Microsoft.ReportingServices.Modeling.ValidationContext Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Validation()
0x11014  ldc.i4.8
0x11015  ldarg.1
0x11016  callvirt instance class Microsoft.ReportingServices.Modeling.ValidationContext Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Validation()
0x1101b  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x11020  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidEntityBinding(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x11025  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x1102a  ldarg.1
0x1102b  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlReader::Skip()
0x11030  ldc.i4.1
0x11031  ret
0x11032  ldarg.0
0x11033  ldarg.1
0x11034  call     class Microsoft.ReportingServices.Modeling.ColumnBinding Microsoft.ReportingServices.Modeling.ColumnBinding::FromReader(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x11039  call     instance void Microsoft.ReportingServices.Modeling.ModelEntity::set_Binding(class Microsoft.ReportingServices.Modeling.Binding value)
0x1103e  ldc.i4.1
0x1103f  ret
0x11040  ldarg.0
0x11041  ldarg.1
0x11042  call     instance bool Microsoft.ReportingServices.Modeling.ModelItem::LoadXmlElement(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x11047  ret
```
