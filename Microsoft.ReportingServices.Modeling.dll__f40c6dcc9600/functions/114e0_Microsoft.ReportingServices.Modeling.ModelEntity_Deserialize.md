# Microsoft.ReportingServices.Modeling.ModelEntity::Deserialize

- ea: `0x114e0`
- end: `0x11675`
- name: `Microsoft.ReportingServices.Modeling.ModelEntity::Deserialize`
- size: `405`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1d40`
- `0x1e20`
- `0x1eb0`
- `0x25d0`
- `0x3890`
- `0x3970`
- `0x3990`
- `0x5c90`
- `0x6920`
- `0x97d0`
- `0x9d40`
- `0x10710`
- `0x10760`
- `0x10770`
- `0x107a0`
- `0x107d0`
- `0x10800`
- `0x10830`
- `0x108b0`
- `0x108d0`
- `0x114e0`
- `0x116a0`
- `0x12f00`

## pseudocode

```c

```

## disassembly

```asm
0x114e0  ldarg.0
0x114e1  ldarg.1
0x114e2  call     instance void Microsoft.ReportingServices.Modeling.ModelEntityFolderItem::Deserialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader reader)
0x114e7  ldarg.0
0x114e8  call     instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.Modeling.ModelingObject::AllowWriteOperations()
0x114ed  stloc.0
0x114ee  ldarga.s 1
0x114f0  call     class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.Modeling.ModelEntity::get_Declaration()
0x114f5  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::RegisterDeclaration(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration declaration)
0x114fa  br       loc_1165C
0x114ff  ldarga.s 1
0x11501  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::get_CurrentMember()
0x11506  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberName Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_MemberName()
0x1150b  stloc.1
0x1150c  ldloc.1
0x1150d  ldc.i4.s 0x37
0x1150f  beq      loc_115F3
0x11514  ldloc.1
0x11515  ldc.i4.s 0x43
0x11517  beq      loc_1161E
0x1151c  ldloc.1
0x1151d  ldc.i4.s 0x54
0x1151f  sub
0x11520  switch   loc_11556, loc_11568, loc_1157A, loc_1158C, loc_115A3, loc_115B5, loc_115C6, loc_115D7, loc_115E5, loc_11601, loc_1160F
0x11551  br       loc_11632
0x11556  ldarg.0
0x11557  ldarga.s 1
0x11559  call     instance string Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadString()
0x1155e  stfld    string Microsoft.ReportingServices.Modeling.ModelEntity::m_collectionName
0x11563  br       loc_1165C
0x11568  ldarg.0
0x11569  ldarga.s 1
0x1156b  call     instance unsigned int8 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadByte()
0x11570  stfld    valuetype Microsoft.ReportingServices.Modeling.EntityInstanceSelection Microsoft.ReportingServices.Modeling.ModelEntity::m_instanceSelection
0x11575  br       loc_1165C
0x1157a  ldarg.0
0x1157b  ldarga.s 1
0x1157d  call     instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadBoolean()
0x11582  stfld    bool Microsoft.ReportingServices.Modeling.ModelEntity::m_lookup
0x11587  br       loc_1165C
0x1158c  ldarg.0
0x1158d  ldarga.s 1
0x1158f  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadRIFObject()
0x11594  castclass Microsoft.ReportingServices.Modeling.EntityInheritance
0x11599  call     instance void Microsoft.ReportingServices.Modeling.ModelEntity::set_Inheritance(class Microsoft.ReportingServices.Modeling.EntityInheritance value)
0x1159e  br       loc_1165C
0x115a3  ldarg.0
0x115a4  ldarga.s 1
0x115a6  call     instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadBoolean()
0x115ab  stfld    bool Microsoft.ReportingServices.Modeling.ModelEntity::m_disjointInheritance
0x115b0  br       loc_1165C
0x115b5  ldarg.0
0x115b6  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_IdentifyingAttributes()
0x115bb  ldarg.1
0x115bc  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable::Deserialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader reader)
0x115c1  br       loc_1165C
0x115c6  ldarg.0
0x115c7  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultDetailAttributes()
0x115cc  ldarg.1
0x115cd  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable::Deserialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader reader)
0x115d2  br       loc_1165C
0x115d7  ldarg.0
0x115d8  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultAggregateAttributes()
0x115dd  ldarg.1
0x115de  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable::Deserialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader reader)
0x115e3  br.s     loc_1165C
0x115e5  ldarg.0
0x115e6  call     instance class Microsoft.ReportingServices.Modeling.SortAttributeCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_SortAttributes()
0x115eb  ldarg.1
0x115ec  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable::Deserialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader reader)
0x115f1  br.s     loc_1165C
0x115f3  ldarg.0
0x115f4  call     instance class Microsoft.ReportingServices.Modeling.ModelFieldFolderItemCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_Fields()
0x115f9  ldarg.1
0x115fa  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable::Deserialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader reader)
0x115ff  br.s     loc_1165C
0x11601  ldarg.0
0x11602  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_SecurityFilters()
0x11607  ldarg.1
0x11608  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable::Deserialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader reader)
0x1160d  br.s     loc_1165C
0x1160f  ldarg.0
0x11610  ldarga.s 1
0x11612  call     T0x2B000057
0x11617  call     instance void Microsoft.ReportingServices.Modeling.ModelEntity::set_DefaultSecurityFilter(class Microsoft.ReportingServices.Modeling.AttributeReference value)
0x1161c  br.s     loc_1165C
0x1161e  ldarg.0
0x1161f  ldarga.s 1
0x11621  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadRIFObject()
0x11626  castclass Microsoft.ReportingServices.Modeling.Binding
0x1162b  call     instance void Microsoft.ReportingServices.Modeling.ModelEntity::set_Binding(class Microsoft.ReportingServices.Modeling.Binding value)
0x11630  br.s     loc_1165C
0x11632  ldstr    aUnexpectedMemb// "Unexpected member: "
0x11637  ldarga.s 1
0x11639  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::get_CurrentMember()
0x1163e  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberName Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_MemberName()
0x11643  stloc.2
0x11644  ldloca.s 2
0x11646  constrained. Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberName
0x1164c  callvirt instance string [mscorlib]System.Object::ToString()
0x11651  call     string [mscorlib]System.String::Concat(string, string)
0x11656  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1165b  throw
0x1165c  ldarga.s 1
0x1165e  call     instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::NextMember()
0x11663  brtrue   loc_114FF
0x11668  leave.s  loc_11674
0x1166a  ldloc.0
0x1166b  brfalse.s loc_11673
0x1166d  ldloc.0
0x1166e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11673  endfinally
0x11674  ret
```
