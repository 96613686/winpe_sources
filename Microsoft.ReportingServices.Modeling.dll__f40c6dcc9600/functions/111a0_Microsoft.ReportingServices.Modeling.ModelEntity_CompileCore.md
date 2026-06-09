# Microsoft.ReportingServices.Modeling.ModelEntity::CompileCore

- ea: `0x111a0`
- end: `0x112bf`
- name: `Microsoft.ReportingServices.Modeling.ModelEntity::CompileCore`
- size: `287`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callees

- `0x8510`
- `0xc120`
- `0xc510`
- `0xc650`
- `0x106b0`
- `0x10770`
- `0x107a0`
- `0x107d0`
- `0x10830`
- `0x10860`
- `0x111a0`
- `0x118c0`
- `0x11d70`
- `0x12340`
- `0x126f0`
- `0x14390`
- `0x24830`
- `0x24a60`
- `0x24bc0`
- `0x25a90`
- `0x25b70`

## string_xrefs

- `0x1122c`: `DefaultSecurityFilter`
- `0x11212`: `SecurityFilters`

## pseudocode

```c

```

## disassembly

```asm
0x111a0  ldarg.0
0x111a1  ldarg.1
0x111a2  call     instance void Microsoft.ReportingServices.Modeling.ModelItem::CompileCore(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x111a7  ldarg.0
0x111a8  ldfld    class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::m_identAttrs
0x111ad  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Count()
0x111b2  brtrue.s loc_111C7
0x111b4  ldarg.1
0x111b5  ldc.i4.s 0x21
0x111b7  ldarg.1
0x111b8  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x111bd  call     string Microsoft.ReportingServices.Modeling.SRErrors::MissingIdentifyingAttributes(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x111c2  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x111c7  ldarg.0
0x111c8  ldfld    class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::m_identAttrs
0x111cd  ldarg.1
0x111ce  ldstr    aIdentifyingatt// "IdentifyingAttributes"
0x111d3  ldc.i4.s 9
0x111d5  callvirt instance void Microsoft.ReportingServices.Modeling.AttributeReferenceCollection::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, string collectionName, valuetype Microsoft.ReportingServices.Modeling.AttributeReferenceCompilation flag)
0x111da  ldarg.0
0x111db  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultDetailAttributes()
0x111e0  ldarg.1
0x111e1  ldstr    aDefaultdetaila// "DefaultDetailAttributes"
0x111e6  ldc.i4.8
0x111e7  callvirt instance void Microsoft.ReportingServices.Modeling.AttributeReferenceCollection::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, string collectionName, valuetype Microsoft.ReportingServices.Modeling.AttributeReferenceCompilation flag)
0x111ec  ldarg.0
0x111ed  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultAggregateAttributes()
0x111f2  ldarg.1
0x111f3  ldstr    aDefaultaggrega_0// "DefaultAggregateAttributes"
0x111f8  ldc.i4.s 0xA
0x111fa  callvirt instance void Microsoft.ReportingServices.Modeling.AttributeReferenceCollection::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, string collectionName, valuetype Microsoft.ReportingServices.Modeling.AttributeReferenceCompilation flag)
0x111ff  ldarg.0
0x11200  call     instance class Microsoft.ReportingServices.Modeling.SortAttributeCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_SortAttributes()
0x11205  ldarg.1
0x11206  callvirt instance void Microsoft.ReportingServices.Modeling.SortAttributeCollection::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x1120b  ldarg.0
0x1120c  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_SecurityFilters()
0x11211  ldarg.1
0x11212  ldstr    aSecurityfilter// "SecurityFilters"
0x11217  ldc.i4.5
0x11218  callvirt instance void Microsoft.ReportingServices.Modeling.AttributeReferenceCollection::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, string collectionName, valuetype Microsoft.ReportingServices.Modeling.AttributeReferenceCompilation flag)
0x1121d  ldarg.0
0x1121e  call     instance class Microsoft.ReportingServices.Modeling.AttributeReference Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultSecurityFilter()
0x11223  brfalse.s loc_11237
0x11225  ldarg.0
0x11226  call     instance class Microsoft.ReportingServices.Modeling.AttributeReference Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultSecurityFilter()
0x1122b  ldarg.1
0x1122c  ldstr    aDefaultsecurit// "DefaultSecurityFilter"
0x11231  ldc.i4.5
0x11232  callvirt instance void Microsoft.ReportingServices.Modeling.AttributeReference::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, string parentPropertyName, valuetype Microsoft.ReportingServices.Modeling.AttributeReferenceCompilation flag)
0x11237  ldarg.1
0x11238  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldCheckBindings()
0x1123d  brfalse.s loc_112AA
0x1123f  ldarg.0
0x11240  ldfld    class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::m_binding
0x11245  isinst   Microsoft.ReportingServices.Modeling.TableBinding
0x1124a  stloc.0
0x1124b  ldarg.0
0x1124c  ldfld    class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::m_binding
0x11251  isinst   Microsoft.ReportingServices.Modeling.ColumnBinding
0x11256  stloc.1
0x11257  ldloc.0
0x11258  brfalse.s loc_11266
0x1125a  ldloc.0
0x1125b  ldarg.1
0x1125c  ldloca.s 2
0x1125e  callvirt instance bool Microsoft.ReportingServices.Modeling.TableBinding::CheckBinding(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, [out] class Microsoft.ReportingServices.Modeling.DsvTable& table)
0x11263  pop
0x11264  br.s     loc_112AA
0x11266  ldloc.1
0x11267  brfalse.s loc_11297
0x11269  ldloc.1
0x1126a  ldarg.1
0x1126b  ldc.i4.1
0x1126c  ldloca.s 3
0x1126e  ldloca.s 4
0x11270  callvirt instance bool Microsoft.ReportingServices.Modeling.ColumnBinding::CheckBinding(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, bool topLevel, [out] class Microsoft.ReportingServices.Modeling.DsvColumn& column, [out] valuetype Microsoft.ReportingServices.Modeling.DataType& columnDataType)
0x11275  brfalse.s loc_112AA
0x11277  ldloc.s  4
0x11279  ldc.i4.6
0x1127a  bne.un.s loc_112AA
0x1127c  ldarg.1
0x1127d  ldc.i4.s 0x3A
0x1127f  ldarg.1
0x11280  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x11285  ldloc.1
0x11286  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ColumnBinding::GetColumnDescriptor()
0x1128b  call     string Microsoft.ReportingServices.Modeling.SRErrors::BinaryEntityColumn(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor columnTypeAndName)
0x11290  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x11295  br.s     loc_112AA
0x11297  ldarg.1
0x11298  ldc.i4.s 0x32
0x1129a  ldarg.1
0x1129b  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x112a0  call     string Microsoft.ReportingServices.Modeling.SRErrors::MissingBinding_Entity(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x112a5  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x112aa  ldarg.0
0x112ab  call     instance class Microsoft.ReportingServices.Modeling.EntityInheritance Microsoft.ReportingServices.Modeling.ModelEntity::get_Inheritance()
0x112b0  brfalse.s loc_112BE
0x112b2  ldarg.0
0x112b3  call     instance class Microsoft.ReportingServices.Modeling.EntityInheritance Microsoft.ReportingServices.Modeling.ModelEntity::get_Inheritance()
0x112b8  ldarg.1
0x112b9  callvirt instance void Microsoft.ReportingServices.Modeling.EntityInheritance::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x112be  ret
```
