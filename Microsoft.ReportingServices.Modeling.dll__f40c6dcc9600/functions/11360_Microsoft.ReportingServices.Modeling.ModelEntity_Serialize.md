# Microsoft.ReportingServices.Modeling.ModelEntity::Serialize

- ea: `0x11360`
- end: `0x114d8`
- name: `Microsoft.ReportingServices.Modeling.ModelEntity::Serialize`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callees

- `0x3f80`
- `0x4070`
- `0x40c0`
- `0x4100`
- `0x53c0`
- `0x53d0`
- `0x5450`
- `0x5c80`
- `0x6920`
- `0x97d0`
- `0x106b0`
- `0x10760`
- `0x10770`
- `0x107a0`
- `0x107d0`
- `0x10800`
- `0x10830`
- `0x10860`
- `0x108c0`
- `0x11360`
- `0x116a0`
- `0x12ea0`

## pseudocode

```c

```

## disassembly

```asm
0x11360  ldarg.0
0x11361  ldarg.1
0x11362  call     instance void Microsoft.ReportingServices.Modeling.ModelEntityFolderItem::Serialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter writer)
0x11367  ldarga.s 1
0x11369  call     class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.Modeling.ModelEntity::get_Declaration()
0x1136e  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::RegisterDeclaration(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration declaration)
0x11373  br       loc_114CB
0x11378  ldarga.s 1
0x1137a  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::get_CurrentMember()
0x1137f  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberName Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_MemberName()
0x11384  stloc.0
0x11385  ldloc.0
0x11386  ldc.i4.s 0x37
0x11388  beq      loc_11467
0x1138d  ldloc.0
0x1138e  ldc.i4.s 0x43
0x11390  beq      loc_11492
0x11395  ldloc.0
0x11396  ldc.i4.s 0x54
0x11398  sub
0x11399  switch   loc_113CF, loc_113E1, loc_113F3, loc_11405, loc_11417, loc_11429, loc_1143A, loc_1144B, loc_11459, loc_11475, loc_11483
0x113ca  br       loc_114A1
0x113cf  ldarga.s 1
0x113d1  ldarg.0
0x113d2  ldfld    string Microsoft.ReportingServices.Modeling.ModelEntity::m_collectionName
0x113d7  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::Write(string value)
0x113dc  br       loc_114CB
0x113e1  ldarga.s 1
0x113e3  ldarg.0
0x113e4  ldfld    valuetype Microsoft.ReportingServices.Modeling.EntityInstanceSelection Microsoft.ReportingServices.Modeling.ModelEntity::m_instanceSelection
0x113e9  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::Write(unsigned int8 value)
0x113ee  br       loc_114CB
0x113f3  ldarga.s 1
0x113f5  ldarg.0
0x113f6  ldfld    bool Microsoft.ReportingServices.Modeling.ModelEntity::m_lookup
0x113fb  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::Write(bool value)
0x11400  br       loc_114CB
0x11405  ldarga.s 1
0x11407  ldarg.0
0x11408  call     instance class Microsoft.ReportingServices.Modeling.EntityInheritance Microsoft.ReportingServices.Modeling.ModelEntity::get_Inheritance()
0x1140d  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::Write(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable persistableObj)
0x11412  br       loc_114CB
0x11417  ldarga.s 1
0x11419  ldarg.0
0x1141a  ldfld    bool Microsoft.ReportingServices.Modeling.ModelEntity::m_disjointInheritance
0x1141f  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::Write(bool value)
0x11424  br       loc_114CB
0x11429  ldarg.0
0x1142a  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_IdentifyingAttributes()
0x1142f  ldarg.1
0x11430  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable::Serialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter writer)
0x11435  br       loc_114CB
0x1143a  ldarg.0
0x1143b  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultDetailAttributes()
0x11440  ldarg.1
0x11441  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable::Serialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter writer)
0x11446  br       loc_114CB
0x1144b  ldarg.0
0x1144c  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultAggregateAttributes()
0x11451  ldarg.1
0x11452  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable::Serialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter writer)
0x11457  br.s     loc_114CB
0x11459  ldarg.0
0x1145a  call     instance class Microsoft.ReportingServices.Modeling.SortAttributeCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_SortAttributes()
0x1145f  ldarg.1
0x11460  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable::Serialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter writer)
0x11465  br.s     loc_114CB
0x11467  ldarg.0
0x11468  call     instance class Microsoft.ReportingServices.Modeling.ModelFieldFolderItemCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_Fields()
0x1146d  ldarg.1
0x1146e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable::Serialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter writer)
0x11473  br.s     loc_114CB
0x11475  ldarg.0
0x11476  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_SecurityFilters()
0x1147b  ldarg.1
0x1147c  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable::Serialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter writer)
0x11481  br.s     loc_114CB
0x11483  ldarga.s 1
0x11485  ldarg.0
0x11486  call     instance class Microsoft.ReportingServices.Modeling.AttributeReference Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultSecurityFilter()
0x1148b  call     T0x2B000056
0x11490  br.s     loc_114CB
0x11492  ldarga.s 1
0x11494  ldarg.0
0x11495  call     instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x1149a  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::Write(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable persistableObj)
0x1149f  br.s     loc_114CB
0x114a1  ldstr    aUnexpectedMemb// "Unexpected member: "
0x114a6  ldarga.s 1
0x114a8  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::get_CurrentMember()
0x114ad  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberName Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_MemberName()
0x114b2  stloc.1
0x114b3  ldloca.s 1
0x114b5  constrained. Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberName
0x114bb  callvirt instance string [mscorlib]System.Object::ToString()
0x114c0  call     string [mscorlib]System.String::Concat(string, string)
0x114c5  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x114ca  throw
0x114cb  ldarga.s 1
0x114cd  call     instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::NextMember()
0x114d2  brtrue   loc_11378
0x114d7  ret
```
