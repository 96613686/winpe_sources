# Microsoft.ReportingServices.Modeling.ModelRole::CompileCheckBinding

- ea: `0x15bb0`
- end: `0x15e2f`
- name: `Microsoft.ReportingServices.Modeling.ModelRole::CompileCheckBinding`
- size: `639`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `service_task, broker_com_uri`

## callers

- `0x15960`

## callees

- `0xbce0`
- `0xbda0`
- `0xbe40`
- `0xbe90`
- `0xc880`
- `0xc890`
- `0xc8d0`
- `0xca00`
- `0xca40`
- `0xd990`
- `0x108c0`
- `0x13710`
- `0x153d0`
- `0x15510`
- `0x15bb0`
- `0x24ac0`
- `0x24cc0`
- `0x24ce0`
- `0x24d00`
- `0x24d30`
- `0x25540`
- `0x25590`
- `0x25a90`
- `0x25b70`
- `0x25b80`

## pseudocode

```c

```

## disassembly

```asm
0x15bb0  ldarg.2
0x15bb1  ldc.i4.0
0x15bb2  stind.i1
0x15bb3  ldarg.0
0x15bb4  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedEntity()
0x15bb9  brtrue.s loc_15BBE
0x15bbb  ldnull
0x15bbc  br.s     loc_15BC9
0x15bbe  ldarg.0
0x15bbf  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedEntity()
0x15bc4  callvirt instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x15bc9  stloc.1
0x15bca  ldloc.1
0x15bcb  brtrue.s loc_15BD0
0x15bcd  ldnull
0x15bce  br.s     loc_15BD6
0x15bd0  ldloc.1
0x15bd1  callvirt instance class Microsoft.ReportingServices.Modeling.DsvTable Microsoft.ReportingServices.Modeling.Binding::GetTable()
0x15bd6  stloc.2
0x15bd7  ldarg.0
0x15bd8  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::m_binding
0x15bdd  brtrue   loc_15C6F
0x15be2  ldarg.0
0x15be3  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::m_relatedRole
0x15be8  callvirt instance class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::get_Binding()
0x15bed  brtrue.s loc_15C5B
0x15bef  ldarg.0
0x15bf0  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelFieldFolderItem::get_Entity()
0x15bf5  callvirt instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x15bfa  brfalse.s loc_15C5B
0x15bfc  ldarg.0
0x15bfd  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelFieldFolderItem::get_Entity()
0x15c02  callvirt instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x15c07  callvirt instance class Microsoft.ReportingServices.Modeling.DsvTable Microsoft.ReportingServices.Modeling.Binding::GetTable()
0x15c0c  ldloc.2
0x15c0d  bne.un.s loc_15C5B
0x15c0f  ldarg.0
0x15c10  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelFieldFolderItem::get_Entity()
0x15c15  callvirt instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x15c1a  isinst   Microsoft.ReportingServices.Modeling.ColumnBinding
0x15c1f  brfalse.s loc_15C33
0x15c21  ldarg.0
0x15c22  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedEntity()
0x15c27  callvirt instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x15c2c  isinst   Microsoft.ReportingServices.Modeling.TableBinding
0x15c31  brtrue.s loc_15C57
0x15c33  ldarg.0
0x15c34  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelFieldFolderItem::get_Entity()
0x15c39  callvirt instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x15c3e  isinst   Microsoft.ReportingServices.Modeling.TableBinding
0x15c43  brfalse.s loc_15C5B
0x15c45  ldarg.0
0x15c46  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedEntity()
0x15c4b  callvirt instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x15c50  isinst   Microsoft.ReportingServices.Modeling.ColumnBinding
0x15c55  brfalse.s loc_15C5B
0x15c57  ldarg.2
0x15c58  ldc.i4.1
0x15c59  stind.i1
0x15c5a  ret
0x15c5b  ldarg.1
0x15c5c  ldc.i4.s 0x32
0x15c5e  ldarg.1
0x15c5f  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x15c64  call     string Microsoft.ReportingServices.Modeling.SRErrors::MissingBinding_Role(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x15c69  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x15c6e  ret
0x15c6f  ldarg.0
0x15c70  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::m_binding
0x15c75  ldarg.1
0x15c76  ldstr    aRelation// "Relation"
0x15c7b  ldloca.s 0
0x15c7d  callvirt instance bool Microsoft.ReportingServices.Modeling.RelationBinding::CheckBinding(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, string propertyName, [out] class Microsoft.ReportingServices.Modeling.DsvRelation& relation)
0x15c82  brfalse  loc_15E2E
0x15c87  ldarg.0
0x15c88  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::m_relatedRole
0x15c8d  callvirt instance class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::get_Binding()
0x15c92  brfalse  loc_15D19
0x15c97  ldloc.0
0x15c98  ldarg.0
0x15c99  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::m_relatedRole
0x15c9e  callvirt instance class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::get_Binding()
0x15ca3  callvirt instance class Microsoft.ReportingServices.Modeling.DsvRelation Microsoft.ReportingServices.Modeling.RelationBinding::GetRelation()
0x15ca8  beq.s    loc_15D19
0x15caa  ldarg.0
0x15cab  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::m_binding
0x15cb0  callvirt instance valuetype Microsoft.ReportingServices.Modeling.RelationEnd Microsoft.ReportingServices.Modeling.RelationBinding::get_RelationEnd()
0x15cb5  brfalse.s loc_15CD7
0x15cb7  ldarg.0
0x15cb8  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::m_binding
0x15cbd  callvirt instance valuetype Microsoft.ReportingServices.Modeling.RelationEnd Microsoft.ReportingServices.Modeling.RelationBinding::get_RelationEnd()
0x15cc2  ldarg.0
0x15cc3  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::m_relatedRole
0x15cc8  callvirt instance class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::get_Binding()
0x15ccd  callvirt instance valuetype Microsoft.ReportingServices.Modeling.RelationEnd Microsoft.ReportingServices.Modeling.RelationBinding::get_RelationEnd()
0x15cd2  bne.un   loc_15E2E
0x15cd7  ldarg.1
0x15cd8  ldc.i4.s 0x41
0x15cda  ldarg.1
0x15cdb  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x15ce0  ldarg.0
0x15ce1  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::m_relatedRole
0x15ce6  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x15ceb  stloc.3
0x15cec  ldloca.s 3
0x15cee  call     instance string Microsoft.ReportingServices.Modeling.SRObjectDescriptor::get_ObjectName()
0x15cf3  ldarg.0
0x15cf4  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::m_binding
0x15cf9  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.RelationBinding::GetRelationDescriptor()
0x15cfe  ldarg.0
0x15cff  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::m_relatedRole
0x15d04  callvirt instance class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::get_Binding()
0x15d09  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.RelationBinding::GetRelationDescriptor()
0x15d0e  call     string Microsoft.ReportingServices.Modeling.SRErrors::RoleRelationsMismatch(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string relatedRoleName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor relationTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor relatedRelationTypeAndName)
0x15d13  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x15d18  ret
0x15d19  ldarg.0
0x15d1a  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::m_relatedRole
0x15d1f  callvirt instance class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::get_Binding()
0x15d24  brfalse.s loc_15D80
0x15d26  ldarg.0
0x15d27  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::m_binding
0x15d2c  callvirt instance valuetype Microsoft.ReportingServices.Modeling.RelationEnd Microsoft.ReportingServices.Modeling.RelationBinding::get_RelationEnd()
0x15d31  ldarg.0
0x15d32  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::m_relatedRole
0x15d37  callvirt instance class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::get_Binding()
0x15d3c  callvirt instance valuetype Microsoft.ReportingServices.Modeling.RelationEnd Microsoft.ReportingServices.Modeling.RelationBinding::get_RelationEnd()
0x15d41  bne.un.s loc_15D80
0x15d43  ldarg.1
0x15d44  ldc.i4.s 0x42
0x15d46  ldarg.1
0x15d47  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x15d4c  ldarg.0
0x15d4d  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::m_relatedRole
0x15d52  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x15d57  stloc.3
0x15d58  ldloca.s 3
0x15d5a  call     instance string Microsoft.ReportingServices.Modeling.SRObjectDescriptor::get_ObjectName()
0x15d5f  ldarg.0
0x15d60  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::m_binding
0x15d65  callvirt instance valuetype Microsoft.ReportingServices.Modeling.RelationEnd Microsoft.ReportingServices.Modeling.RelationBinding::get_RelationEnd()
0x15d6a  ldarg.0
0x15d6b  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::m_binding
0x15d70  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.RelationBinding::GetRelationDescriptor()
0x15d75  call     string Microsoft.ReportingServices.Modeling.SRErrors::RoleRelationEndsMismatch(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string relatedRoleName, valuetype Microsoft.ReportingServices.Modeling.RelationEnd relationEnd, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor relationTypeAndName)
0x15d7a  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x15d7f  ret
0x15d80  ldloc.2
0x15d81  brfalse.s loc_15DC6
0x15d83  ldarg.0
0x15d84  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::m_binding
0x15d89  callvirt instance class Microsoft.ReportingServices.Modeling.DsvTable Microsoft.ReportingServices.Modeling.Binding::GetTable()
0x15d8e  ldloc.2
0x15d8f  beq.s    loc_15DC6
0x15d91  ldarg.1
0x15d92  ldc.i4.s 0x43
0x15d94  ldarg.1
0x15d95  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x15d9a  ldarg.0
0x15d9b  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::m_binding
0x15da0  callvirt instance valuetype Microsoft.ReportingServices.Modeling.RelationEnd Microsoft.ReportingServices.Modeling.RelationBinding::get_RelationEnd()
0x15da5  ldarg.0
0x15da6  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::m_binding
0x15dab  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.RelationBinding::GetRelationDescriptor()
0x15db0  ldloc.2
0x15db1  callvirt instance string Microsoft.ReportingServices.Modeling.DsvItem::get_Name()
0x15db6  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.Binding::GetTableDescriptor(string tableName)
0x15dbb  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidRoleRelationTable(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.RelationEnd relationEnd, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor relationTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor tableTypeAndName)
0x15dc0  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x15dc5  ret
0x15dc6  ldarg.0
0x15dc7  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::m_binding
0x15dcc  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.ReportingServices.Modeling.DsvColumn> Microsoft.ReportingServices.Modeling.RelationBinding::GetColumns()
0x15dd1  ldloc.1
0x15dd2  ldarg.1
0x15dd3  ldstr    aRelation// "Relation"
0x15dd8  call     bool Microsoft.ReportingServices.Modeling.Binding::CheckColumns(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.DsvColumn> columns, class Microsoft.ReportingServices.Modeling.Binding parentBinding, class Microsoft.ReportingServices.Modeling.CompilationContext ctx, string propertyName)
0x15ddd  brfalse.s loc_15E2E
0x15ddf  ldarg.0
0x15de0  ldfld    valuetype Microsoft.ReportingServices.Modeling.Cardinality Microsoft.ReportingServices.Modeling.ModelRole::m_cardinality
0x15de5  brtrue.s loc_15E2E
0x15de7  ldarg.0
0x15de8  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::m_binding
0x15ded  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.ReportingServices.Modeling.DsvColumn> Microsoft.ReportingServices.Modeling.RelationBinding::GetColumns()
0x15df2  ldloc.1
0x15df3  call     bool Microsoft.ReportingServices.Modeling.Binding::AreColumnsUnique(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.DsvColumn> columns, class Microsoft.ReportingServices.Modeling.Binding parentBinding)
0x15df8  brtrue.s loc_15E2E
0x15dfa  ldarg.1
0x15dfb  ldc.i4.s 0x44
0x15dfd  ldarg.1
0x15dfe  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x15e03  ldarg.0
0x15e04  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::m_binding
0x15e09  callvirt instance valuetype Microsoft.ReportingServices.Modeling.RelationEnd Microsoft.ReportingServices.Modeling.RelationBinding::get_RelationEnd()
0x15e0e  ldarg.0
0x15e0f  ldfld    class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::m_binding
0x15e14  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.RelationBinding::GetRelationDescriptor()
0x15e19  ldloc.2
0x15e1a  callvirt instance string Microsoft.ReportingServices.Modeling.DsvItem::get_Name()
0x15e1f  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.Binding::GetTableDescriptor(string tableName)
0x15e24  call     string Microsoft.ReportingServices.Modeling.SRErrors::NonUniqueRoleRelationColumns(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.RelationEnd relationEnd, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor relationTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor tableTypeAndName)
0x15e29  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedWarning(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x15e2e  ret
```
