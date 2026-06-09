# Microsoft.ReportingServices.Modeling.AttributeReference::Compile

- ea: `0x118c0`
- end: `0x11a5b`
- name: `Microsoft.ReportingServices.Modeling.AttributeReference::Compile`
- size: `411`
- prototype: ``
- caller_count: `3`
- callee_count: `25`
- tags: `service_task, broker_com_uri`

## callers

- `0x111a0`
- `0x11d70`
- `0x120a0`

## callees

- `0x84f0`
- `0x8500`
- `0x8720`
- `0x8740`
- `0x88c0`
- `0x9d20`
- `0xeed0`
- `0xeef0`
- `0x118c0`
- `0x13710`
- `0x139d0`
- `0x13ac0`
- `0x13ae0`
- `0x1df90`
- `0x1e260`
- `0x24530`
- `0x24850`
- `0x24870`
- `0x24890`
- `0x248b0`
- `0x248d0`
- `0x25590`
- `0x25a90`
- `0x25b70`
- `0x25b80`

## pseudocode

```c

```

## disassembly

```asm
0x118c0  ldarg.0
0x118c1  ldarg.1
0x118c2  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x118c7  call     instance void Microsoft.ReportingServices.Modeling.ModelingObject::Compile(bool shouldPersist)
0x118cc  ldarg.2
0x118cd  ldstr    aAttributerefer_0// ".AttributeReference.AttributeID"
0x118d2  call     string [mscorlib]System.String::Concat(string, string)
0x118d7  stloc.0
0x118d8  ldarg.1
0x118d9  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldCheckInvalidRefsDuringCompilation()
0x118de  brfalse.s loc_1191E
0x118e0  ldarg.0
0x118e1  ldfld    class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::m_attribute
0x118e6  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelItem::get_IsInvalidRefTarget()
0x118eb  brfalse.s loc_1191E
0x118ed  ldarg.1
0x118ee  ldc.i4.s 0x11
0x118f0  ldstr    aAttributeid// "AttributeID"
0x118f5  ldarg.1
0x118f6  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x118fb  ldarg.0
0x118fc  ldfld    class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::m_attribute
0x11901  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0x11906  stloc.3
0x11907  ldloca.s 3
0x11909  constrained. Microsoft.ReportingServices.Modeling.QName
0x1190f  callvirt instance string [mscorlib]System.Object::ToString()
0x11914  call     string Microsoft.ReportingServices.Modeling.SRErrors::ItemNotFound_MultipleProperties(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0x11919  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x1191e  ldarg.0
0x1191f  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.AttributeReference::m_path
0x11924  ldarg.1
0x11925  ldarg.0
0x11926  ldfld    class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::m_attribute
0x1192b  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelFieldFolderItem::get_Entity()
0x11930  ldloca.s 1
0x11932  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.ExpressionPath::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, class Microsoft.ReportingServices.Modeling.IQueryEntity desiredTargetEntity, [out] class Microsoft.ReportingServices.Modeling.IQueryEntity& actualTargetEntity)
0x11937  stloc.2
0x11938  ldloc.2
0x11939  brtrue.s loc_1193C
0x1193b  ret
0x1193c  ldloc.2
0x1193d  callvirt instance valuetype Microsoft.ReportingServices.Modeling.Cardinality Microsoft.ReportingServices.Modeling.ExpressionPath::GetCardinality()
0x11942  ldc.i4.1
0x11943  bne.un.s loc_11971
0x11945  ldarg.0
0x11946  ldfld    class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::m_attribute
0x1194b  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelAttribute::get_IsAggregate()
0x11950  brtrue.s loc_11971
0x11952  ldarg.1
0x11953  ldc.i4.s 0x22
0x11955  ldloc.0
0x11956  ldarg.1
0x11957  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x1195c  ldarg.0
0x1195d  ldfld    class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::m_attribute
0x11962  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x11967  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidSetAttributeReference(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor attributeTypeAndName)
0x1196c  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x11971  ldarg.1
0x11972  ldloc.1
0x11973  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::PushContextEntity(class Microsoft.ReportingServices.Modeling.IQueryEntity entity)
0x11978  ldarg.1
0x11979  ldarg.0
0x1197a  ldfld    class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::m_attribute
0x1197f  ldloc.0
0x11980  ldc.i4.1
0x11981  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::CheckContextEntityMatch(class Microsoft.ReportingServices.Modeling.ModelFieldFolderItem field, string propertyName, bool multipleInScope)
0x11986  brtrue.s loc_1198D
0x11988  leave    loc_11A5A
0x1198d  ldarg.3
0x1198e  ldc.i4.1
0x1198f  and
0x11990  brfalse.s loc_119BE
0x11992  ldarg.0
0x11993  ldfld    class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::m_attribute
0x11998  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelAttribute::get_IsAggregate()
0x1199d  brfalse.s loc_119BE
0x1199f  ldarg.1
0x119a0  ldc.i4.s 0x23
0x119a2  ldloc.0
0x119a3  ldarg.1
0x119a4  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x119a9  ldarg.0
0x119aa  ldfld    class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::m_attribute
0x119af  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x119b4  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidAggregateAttributeReference(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor attributeTypeAndName)
0x119b9  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x119be  ldarg.3
0x119bf  ldc.i4.2
0x119c0  and
0x119c1  brfalse.s loc_119EF
0x119c3  ldarg.0
0x119c4  ldfld    class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::m_attribute
0x119c9  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelAttribute::get_IsAggregate()
0x119ce  brtrue.s loc_119EF
0x119d0  ldarg.1
0x119d1  ldc.i4.s 0x24
0x119d3  ldloc.0
0x119d4  ldarg.1
0x119d5  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x119da  ldarg.0
0x119db  ldfld    class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::m_attribute
0x119e0  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x119e5  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidScalarAttributeReference(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor attributeTypeAndName)
0x119ea  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x119ef  ldarg.3
0x119f0  ldc.i4.4
0x119f1  and
0x119f2  brfalse.s loc_11A20
0x119f4  ldarg.0
0x119f5  ldfld    class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::m_attribute
0x119fa  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelAttribute::get_IsFilter()
0x119ff  brtrue.s loc_11A20
0x11a01  ldarg.1
0x11a02  ldc.i4.s 0x25
0x11a04  ldloc.0
0x11a05  ldarg.1
0x11a06  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x11a0b  ldarg.0
0x11a0c  ldfld    class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::m_attribute
0x11a11  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x11a16  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidNonFilterAttributeReference(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor attributeTypeAndName)
0x11a1b  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x11a20  ldarg.3
0x11a21  ldc.i4.8
0x11a22  and
0x11a23  brfalse.s loc_11A51
0x11a25  ldarg.0
0x11a26  ldfld    class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::m_attribute
0x11a2b  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelItem::get_Hidden()
0x11a30  brfalse.s loc_11A51
0x11a32  ldarg.1
0x11a33  ldc.i4.s 0x26
0x11a35  ldloc.0
0x11a36  ldarg.1
0x11a37  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x11a3c  ldarg.0
0x11a3d  ldfld    class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::m_attribute
0x11a42  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x11a47  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidHiddenAttributeReference(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor attributeTypeAndName)
0x11a4c  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedWarning(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x11a51  leave.s  loc_11A5A
0x11a53  ldarg.1
0x11a54  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::PopContextEntity()
0x11a59  endfinally
0x11a5a  ret
```
