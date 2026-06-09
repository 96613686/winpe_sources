# Microsoft.ReportingServices.Modeling.ModelRole::CompileCore

- ea: `0x15960`
- end: `0x15b3c`
- name: `Microsoft.ReportingServices.Modeling.ModelRole::CompileCore`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `service_task, broker_com_uri`

## callees

- `0x8510`
- `0x8720`
- `0x8740`
- `0x88c0`
- `0x10690`
- `0x108c0`
- `0x13710`
- `0x13af0`
- `0x14390`
- `0x15390`
- `0x153d0`
- `0x15420`
- `0x154e0`
- `0x15960`
- `0x15b40`
- `0x15bb0`
- `0x249d0`
- `0x249f0`
- `0x24ca0`
- `0x25410`
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
0x15960  ldarg.0
0x15961  ldarg.1
0x15962  call     instance void Microsoft.ReportingServices.Modeling.ModelItem::CompileCore(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x15967  ldarg.0
0x15968  ldarg.1
0x15969  ldc.i4.0
0x1596a  call     instance bool Microsoft.ReportingServices.Modeling.ModelRole::ValidateRelatedRoleReference(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, bool forceInvalidRefTargetCheck)
0x1596f  brtrue.s loc_15972
0x15971  ret
0x15972  ldarg.0
0x15973  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::m_relatedRole
0x15978  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelItem::get_Model()
0x1597d  ldarg.0
0x1597e  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelItem::get_Model()
0x15983  beq.s    loc_159A9
0x15985  ldarg.1
0x15986  ldc.i4.s 0x75
0x15988  ldstr    aRelatedroleid// "RelatedRoleID"
0x1598d  ldarg.1
0x1598e  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x15993  ldarg.0
0x15994  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::m_relatedRole
0x15999  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x1599e  call     string Microsoft.ReportingServices.Modeling.SRErrors::WrongSemanticModel_ModelItem(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor referencedTypeAndName)
0x159a3  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x159a8  ret
0x159a9  ldarg.0
0x159aa  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::m_relatedRole
0x159af  callvirt instance class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedRole()
0x159b4  ldarg.0
0x159b5  beq.s    loc_159E8
0x159b7  ldarg.1
0x159b8  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x159bd  stloc.0
0x159be  ldarg.0
0x159bf  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::m_relatedRole
0x159c4  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x159c9  stloc.1
0x159ca  ldarg.1
0x159cb  ldc.i4.s 0x2E
0x159cd  ldloc.0
0x159ce  ldloca.s 0
0x159d0  call     instance string Microsoft.ReportingServices.Modeling.SRObjectDescriptor::get_ObjectName()
0x159d5  ldloc.1
0x159d6  ldloca.s 1
0x159d8  call     instance string Microsoft.ReportingServices.Modeling.SRObjectDescriptor::get_ObjectName()
0x159dd  call     string Microsoft.ReportingServices.Modeling.SRErrors::RelatedRolesMismatch(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string objectName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor relatedRoleTypeAndName, string relatedRoleName)
0x159e2  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x159e7  ret
0x159e8  ldarg.0
0x159e9  call     instance class HiddenFieldCollection Microsoft.ReportingServices.Modeling.ModelRole::get_HiddenFields()
0x159ee  ldarg.1
0x159ef  ldstr    aHiddenfields// "HiddenFields"
0x159f4  ldstr    aFieldfolderite// "FieldFolderItemID"
0x159f9  callvirt instance bool class Microsoft.ReportingServices.Modeling.ModelItemCollection`2<class Microsoft.ReportingServices.Modeling.ModelFieldFolderItem, class Microsoft.ReportingServices.Modeling.ModelRole>::CheckInvalidRefs(class Microsoft.ReportingServices.Modeling.CompilationContext, string, string)
0x159fe  brfalse.s loc_15A66
0x15a00  ldarg.0
0x15a01  call     instance class HiddenFieldCollection Microsoft.ReportingServices.Modeling.ModelRole::get_HiddenFields()
0x15a06  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.ModelFieldFolderItem>::get_Count()
0x15a0b  ldc.i4.0
0x15a0c  ble.s    loc_15A66
0x15a0e  ldarg.0
0x15a0f  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedEntity()
0x15a14  brfalse.s loc_15A66
0x15a16  ldarg.1
0x15a17  ldarg.0
0x15a18  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedEntity()
0x15a1d  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::PushContextEntity(class Microsoft.ReportingServices.Modeling.IQueryEntity entity)
0x15a22  ldarg.0
0x15a23  call     instance class HiddenFieldCollection Microsoft.ReportingServices.Modeling.ModelRole::get_HiddenFields()
0x15a28  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.ModelFieldFolderItem>::GetEnumerator()
0x15a2d  stloc.2
0x15a2e  br.s     loc_15A46
0x15a30  ldloca.s 2
0x15a32  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.ModelFieldFolderItem>::get_Current()
0x15a37  stloc.3
0x15a38  ldarg.1
0x15a39  ldloc.3
0x15a3a  ldstr    aHiddenfieldsFi// "HiddenFields.FieldFolderItemID"
0x15a3f  ldc.i4.1
0x15a40  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::CheckContextEntityMatch(class Microsoft.ReportingServices.Modeling.ModelFieldFolderItem field, string propertyName, bool multipleInScope)
0x15a45  pop
0x15a46  ldloca.s 2
0x15a48  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.ModelFieldFolderItem>::MoveNext()
0x15a4d  brtrue.s loc_15A30
0x15a4f  leave.s  loc_15A66
0x15a51  ldloca.s 2
0x15a53  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.ModelFieldFolderItem>
0x15a59  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15a5e  endfinally
0x15a5f  ldarg.1
0x15a60  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::PopContextEntity()
0x15a65  endfinally
0x15a66  ldarg.0
0x15a67  ldfld    bool Microsoft.ReportingServices.Modeling.ModelRole::m_promoteLookup
0x15a6c  brfalse.s loc_15AD4
0x15a6e  ldarg.0
0x15a6f  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelFieldFolderItem::get_Entity()
0x15a74  brfalse.s loc_15AA1
0x15a76  ldarg.0
0x15a77  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelFieldFolderItem::get_Entity()
0x15a7c  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelEntity::get_IsLookup()
0x15a81  brtrue.s loc_15AA1
0x15a83  ldarg.1
0x15a84  ldc.i4.s 0x40
0x15a86  ldarg.1
0x15a87  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x15a8c  ldarg.0
0x15a8d  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelFieldFolderItem::get_Entity()
0x15a92  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x15a97  call     string Microsoft.ReportingServices.Modeling.SRErrors::PromoteLookupForNonLookupEntity(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor entityTypeAndName)
0x15a9c  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x15aa1  ldarg.0
0x15aa2  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedEntity()
0x15aa7  brfalse.s loc_15AD4
0x15aa9  ldarg.0
0x15aaa  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedEntity()
0x15aaf  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelEntity::get_IsLookup()
0x15ab4  brtrue.s loc_15AD4
0x15ab6  ldarg.1
0x15ab7  ldc.i4.s 0x40
0x15ab9  ldarg.1
0x15aba  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x15abf  ldarg.0
0x15ac0  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedEntity()
0x15ac5  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x15aca  call     string Microsoft.ReportingServices.Modeling.SRErrors::PromoteLookupForNonLookupEntity(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor entityTypeAndName)
0x15acf  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x15ad4  ldarg.1
0x15ad5  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldCheckBindings()
0x15ada  brfalse.s loc_15B3B
0x15adc  ldarg.0
0x15add  ldarg.1
0x15ade  ldloca.s 4
0x15ae0  call     instance void Microsoft.ReportingServices.Modeling.ModelRole::CompileCheckBinding(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, [out] bool& forColumnBoundEntity)
0x15ae5  ldloc.s  4
0x15ae7  brfalse.s loc_15B3B
0x15ae9  ldarg.0
0x15aea  call     instance valuetype Microsoft.ReportingServices.Modeling.Optionality Microsoft.ReportingServices.Modeling.ModelRole::get_Optionality()
0x15aef  ldc.i4.1
0x15af0  beq.s    loc_15B3B
0x15af2  ldarg.0
0x15af3  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelFieldFolderItem::get_Entity()
0x15af8  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x15afd  stloc.s  5
0x15aff  ldarg.0
0x15b00  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedEntity()
0x15b05  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x15b0a  stloc.s  6
0x15b0c  ldarg.1
0x15b0d  ldc.i4.s 0x2F
0x15b0f  ldarg.1
0x15b10  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x15b15  ldloc.s  5
0x15b17  ldloc.s  6
0x15b19  ldarg.0
0x15b1a  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelFieldFolderItem::get_Entity()
0x15b1f  callvirt instance class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::get_Binding()
0x15b24  isinst   Microsoft.ReportingServices.Modeling.ColumnBinding
0x15b29  brtrue.s loc_15B2F
0x15b2b  ldloc.s  6
0x15b2d  br.s     loc_15B31
0x15b2f  ldloc.s  5
0x15b31  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidOptionalityOfRoleForColumnBoundEntity(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor roleEntityTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor relatedEntityTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor columnBoundEntityTypeAndName)
0x15b36  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedWarning(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x15b3b  ret
```
