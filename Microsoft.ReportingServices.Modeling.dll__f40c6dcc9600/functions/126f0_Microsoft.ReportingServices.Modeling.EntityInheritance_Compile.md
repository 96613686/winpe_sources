# Microsoft.ReportingServices.Modeling.EntityInheritance::Compile

- ea: `0x126f0`
- end: `0x1292e`
- name: `Microsoft.ReportingServices.Modeling.EntityInheritance::Compile`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `service_task, broker_com_uri`

## callers

- `0x111a0`

## callees

- `0x8500`
- `0x8510`
- `0x97d0`
- `0xbce0`
- `0xbda0`
- `0xbe40`
- `0xbe90`
- `0xca00`
- `0xca40`
- `0xd990`
- `0xeab0`
- `0xeac0`
- `0xead0`
- `0xeae0`
- `0x108c0`
- `0x126f0`
- `0x139d0`
- `0x13ae0`
- `0x13af0`
- `0x24510`
- `0x24a80`
- `0x24be0`
- `0x24c10`
- `0x25410`
- `0x25590`
- `0x25a90`
- `0x25b70`
- `0x25b80`

## pseudocode

```c

```

## disassembly

```asm
0x126f0  ldarg.0
0x126f1  ldfld    class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.EntityInheritance::m_owner
0x126f6  brtrue.s loc_12703
0x126f8  ldstr    aMOwnerIsNull// "m_owner is null"
0x126fd  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x12702  throw
0x12703  ldarg.1
0x12704  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldCheckInvalidRefsDuringCompilation()
0x12709  brfalse.s loc_1274A
0x1270b  ldarg.0
0x1270c  ldfld    class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.EntityInheritance::m_inheritsFrom
0x12711  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelItem::get_IsInvalidRefTarget()
0x12716  brfalse.s loc_1274A
0x12718  ldarg.1
0x12719  ldc.i4.s 0x11
0x1271b  ldstr    aInheritanceInh// "Inheritance.InheritsFromEntityID"
0x12720  ldarg.1
0x12721  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x12726  ldarg.0
0x12727  ldfld    class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.EntityInheritance::m_inheritsFrom
0x1272c  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0x12731  stloc.0
0x12732  ldloca.s 0
0x12734  constrained. Microsoft.ReportingServices.Modeling.QName
0x1273a  callvirt instance string [mscorlib]System.Object::ToString()
0x1273f  call     string Microsoft.ReportingServices.Modeling.SRErrors::ItemNotFound(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0x12744  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x12749  ret
0x1274a  ldarg.0
0x1274b  ldfld    class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.EntityInheritance::m_owner
0x12750  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelItem::get_Model()
0x12755  ldarg.0
0x12756  ldfld    class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.EntityInheritance::m_inheritsFrom
0x1275b  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelItem::get_Model()
0x12760  beq.s    loc_12786
0x12762  ldarg.1
0x12763  ldc.i4.s 0x75
0x12765  ldstr    aInheritanceInh// "Inheritance.InheritsFromEntityID"
0x1276a  ldarg.1
0x1276b  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x12770  ldarg.0
0x12771  ldfld    class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.EntityInheritance::m_inheritsFrom
0x12776  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x1277b  call     string Microsoft.ReportingServices.Modeling.SRErrors::WrongSemanticModel_ModelItem(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor referencedTypeAndName)
0x12780  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x12785  ret
0x12786  ldarg.1
0x12787  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldCheckBindings()
0x1278c  brfalse  loc_1292D
0x12791  ldarg.0
0x12792  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.EntityInheritance::m_binding
0x12797  brtrue.s loc_127AD
0x12799  ldarg.1
0x1279a  ldc.i4.s 0x32
0x1279c  ldarg.1
0x1279d  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x127a2  call     string Microsoft.ReportingServices.Modeling.SRErrors::MissingBinding_Inheritance(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x127a7  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x127ac  ret
0x127ad  ldarg.0
0x127ae  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.EntityInheritance::m_binding
0x127b3  ldarg.1
0x127b4  ldstr    aInheritanceRel// "Inheritance.Relation"
0x127b9  ldloca.s 1
0x127bb  callvirt instance bool Microsoft.ReportingServices.Modeling.RelationBinding::CheckBinding(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, string propertyName, [out] class Microsoft.ReportingServices.Modeling.DsvRelation& relation)
0x127c0  brfalse  loc_1292D
0x127c5  ldarg.0
0x127c6  ldfld    class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.EntityInheritance::m_owner
0x127cb  callvirt instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x127d0  brtrue.s loc_127D5
0x127d2  ldnull
0x127d3  br.s     loc_127E5
0x127d5  ldarg.0
0x127d6  ldfld    class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.EntityInheritance::m_owner
0x127db  callvirt instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x127e0  callvirt instance class Microsoft.ReportingServices.Modeling.DsvTable Microsoft.ReportingServices.Modeling.Binding::GetTable()
0x127e5  stloc.2
0x127e6  ldarg.0
0x127e7  ldfld    class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.EntityInheritance::m_inheritsFrom
0x127ec  callvirt instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x127f1  brtrue.s loc_127F6
0x127f3  ldnull
0x127f4  br.s     loc_12806
0x127f6  ldarg.0
0x127f7  ldfld    class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.EntityInheritance::m_inheritsFrom
0x127fc  callvirt instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x12801  callvirt instance class Microsoft.ReportingServices.Modeling.DsvTable Microsoft.ReportingServices.Modeling.Binding::GetTable()
0x12806  stloc.3
0x12807  ldloc.2
0x12808  brfalse  loc_1292D
0x1280d  ldloc.3
0x1280e  brfalse  loc_1292D
0x12813  ldloc.2
0x12814  ldloc.1
0x12815  callvirt instance class Microsoft.ReportingServices.Modeling.DsvTable Microsoft.ReportingServices.Modeling.DsvRelation::get_SourceTable()
0x1281a  bne.un.s loc_12825
0x1281c  ldloc.3
0x1281d  ldloc.1
0x1281e  callvirt instance class Microsoft.ReportingServices.Modeling.DsvTable Microsoft.ReportingServices.Modeling.DsvRelation::get_TargetTable()
0x12823  beq.s    loc_1285F
0x12825  ldarg.1
0x12826  ldc.i4.s 0x3B
0x12828  ldstr    aInheritanceRel// "Inheritance.Relation"
0x1282d  ldarg.1
0x1282e  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x12833  ldarg.0
0x12834  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.EntityInheritance::m_binding
0x12839  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.RelationBinding::GetRelationDescriptor()
0x1283e  ldloc.2
0x1283f  callvirt instance string Microsoft.ReportingServices.Modeling.DsvItem::get_Name()
0x12844  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.Binding::GetTableDescriptor(string tableName)
0x12849  ldloc.3
0x1284a  callvirt instance string Microsoft.ReportingServices.Modeling.DsvItem::get_Name()
0x1284f  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.Binding::GetTableDescriptor(string tableName)
0x12854  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidInheritanceRelationTable(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor relationTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor sourceTableTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor targetTableTypeAndName)
0x12859  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x1285e  ret
0x1285f  ldloc.1
0x12860  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.ReportingServices.Modeling.DsvColumn> Microsoft.ReportingServices.Modeling.DsvRelation::get_SourceColumns()
0x12865  ldarg.0
0x12866  ldfld    class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.EntityInheritance::m_owner
0x1286b  callvirt instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x12870  ldarg.1
0x12871  ldstr    aInheritanceRel// "Inheritance.Relation"
0x12876  call     bool Microsoft.ReportingServices.Modeling.Binding::CheckColumns(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.DsvColumn> columns, class Microsoft.ReportingServices.Modeling.Binding parentBinding, class Microsoft.ReportingServices.Modeling.CompilationContext ctx, string propertyName)
0x1287b  brfalse  loc_1292D
0x12880  ldloc.1
0x12881  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.ReportingServices.Modeling.DsvColumn> Microsoft.ReportingServices.Modeling.DsvRelation::get_TargetColumns()
0x12886  ldarg.0
0x12887  ldfld    class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.EntityInheritance::m_inheritsFrom
0x1288c  callvirt instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x12891  ldarg.1
0x12892  ldstr    aInheritanceRel// "Inheritance.Relation"
0x12897  call     bool Microsoft.ReportingServices.Modeling.Binding::CheckColumns(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.DsvColumn> columns, class Microsoft.ReportingServices.Modeling.Binding parentBinding, class Microsoft.ReportingServices.Modeling.CompilationContext ctx, string propertyName)
0x1289c  brfalse  loc_1292D
0x128a1  ldloc.1
0x128a2  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.ReportingServices.Modeling.DsvColumn> Microsoft.ReportingServices.Modeling.DsvRelation::get_SourceColumns()
0x128a7  ldarg.0
0x128a8  ldfld    class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.EntityInheritance::m_owner
0x128ad  callvirt instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x128b2  call     bool Microsoft.ReportingServices.Modeling.Binding::AreColumnsUnique(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.DsvColumn> columns, class Microsoft.ReportingServices.Modeling.Binding parentBinding)
0x128b7  brtrue.s loc_128E7
0x128b9  ldarg.1
0x128ba  ldc.i4.s 0x3C
0x128bc  ldstr    aInheritanceRel// "Inheritance.Relation"
0x128c1  ldarg.1
0x128c2  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x128c7  ldarg.0
0x128c8  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.EntityInheritance::m_binding
0x128cd  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.RelationBinding::GetRelationDescriptor()
0x128d2  ldloc.2
0x128d3  callvirt instance string Microsoft.ReportingServices.Modeling.DsvItem::get_Name()
0x128d8  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.Binding::GetTableDescriptor(string tableName)
0x128dd  call     string Microsoft.ReportingServices.Modeling.SRErrors::NonUniqueInheritanceRelationColumns(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor relationTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor tableTypeAndName)
0x128e2  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedWarning(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x128e7  ldloc.1
0x128e8  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.ReportingServices.Modeling.DsvColumn> Microsoft.ReportingServices.Modeling.DsvRelation::get_TargetColumns()
0x128ed  ldarg.0
0x128ee  ldfld    class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.EntityInheritance::m_inheritsFrom
0x128f3  callvirt instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x128f8  call     bool Microsoft.ReportingServices.Modeling.Binding::AreColumnsUnique(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.DsvColumn> columns, class Microsoft.ReportingServices.Modeling.Binding parentBinding)
0x128fd  brtrue.s loc_1292D
0x128ff  ldarg.1
0x12900  ldc.i4.s 0x3C
0x12902  ldstr    aInheritanceRel// "Inheritance.Relation"
0x12907  ldarg.1
0x12908  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x1290d  ldarg.0
0x1290e  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.EntityInheritance::m_binding
0x12913  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.RelationBinding::GetRelationDescriptor()
0x12918  ldloc.3
0x12919  callvirt instance string Microsoft.ReportingServices.Modeling.DsvItem::get_Name()
0x1291e  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.Binding::GetTableDescriptor(string tableName)
0x12923  call     string Microsoft.ReportingServices.Modeling.SRErrors::NonUniqueInheritanceRelationColumns(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor relationTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor tableTypeAndName)
0x12928  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedWarning(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x1292d  ret
```
