# Microsoft.ReportingServices.Modeling.ModelGeneration.CreateRoleRule::CreateRole

- ea: `0x26ca0`
- end: `0x26df2`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.CreateRoleRule::CreateRole`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x26bb0`

## callees

- `0xc840`
- `0xc890`
- `0xd990`
- `0xeb30`
- `0xeb40`
- `0xeb50`
- `0x10800`
- `0x109f0`
- `0x13070`
- `0x13a60`
- `0x13a70`
- `0x151d0`
- `0x153d0`
- `0x15400`
- `0x15430`
- `0x15510`
- `0x15520`
- `0x26ca0`
- `0x26e00`
- `0x26ea0`
- `0x29820`
- `0x29ab0`

## pseudocode

```c

```

## disassembly

```asm
0x26ca0  newobj   instance void Microsoft.ReportingServices.Modeling.ModelRole::.ctor()
0x26ca5  stloc.0
0x26ca6  ldarg.2
0x26ca7  callvirt instance class Microsoft.ReportingServices.Modeling.ModelFieldFolderItemCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_Fields()
0x26cac  ldloc.0
0x26cad  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.ModelFieldFolderItem>::Add(var<u1>)
0x26cb2  ldarg.2
0x26cb3  ldarg.3
0x26cb4  ceq
0x26cb6  stloc.1
0x26cb7  ldarg.0
0x26cb8  ldfld    bool Microsoft.ReportingServices.Modeling.ModelGeneration.CreateRoleRule::m_useColumnNames
0x26cbd  ldloc.1
0x26cbe  or
0x26cbf  brfalse  loc_26D81
0x26cc4  ldarg.0
0x26cc5  ldarg.1
0x26cc6  ldloc.1
0x26cc7  call     instance string Microsoft.ReportingServices.Modeling.ModelGeneration.CreateRoleRule::GetTargetName(class Microsoft.ReportingServices.Modeling.DsvRelation relation, bool selfRelation)
0x26ccc  stloc.2
0x26ccd  ldloc.2
0x26cce  brfalse  loc_26D81
0x26cd3  ldarg.s  6
0x26cd5  brfalse.s loc_26CF1
0x26cd7  ldloc.2
0x26cd8  ldarg.3
0x26cd9  callvirt instance string Microsoft.ReportingServices.Modeling.ModelItem::get_Name()
0x26cde  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x26ce3  brfalse.s loc_26CF1
0x26ce5  ldloc.0
0x26ce6  ldloc.2
0x26ce7  callvirt instance void Microsoft.ReportingServices.Modeling.ModelItem::set_Name(string value)
0x26cec  br       loc_26D81
0x26cf1  ldarg.s  6
0x26cf3  brtrue   loc_26D81
0x26cf8  ldnull
0x26cf9  stloc.3
0x26cfa  ldarg.2
0x26cfb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.ModelField> Microsoft.ReportingServices.Modeling.ModelEntity::GetAllFields()
0x26d00  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.ModelField>::GetEnumerator()
0x26d05  stloc.s  4
0x26d07  br.s     loc_26D28
0x26d09  ldloc.s  4
0x26d0b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.ReportingServices.Modeling.ModelField>::get_Current()
0x26d10  isinst   Microsoft.ReportingServices.Modeling.ModelRole
0x26d15  stloc.s  5
0x26d17  ldloc.s  5
0x26d19  brfalse.s loc_26D28
0x26d1b  ldloc.s  5
0x26d1d  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedEntity()
0x26d22  ldarg.3
0x26d23  bne.un.s loc_26D28
0x26d25  ldloc.s  5
0x26d27  stloc.3
0x26d28  ldloc.s  4
0x26d2a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26d2f  brtrue.s loc_26D09
0x26d31  leave.s  loc_26D3F
0x26d33  ldloc.s  4
0x26d35  brfalse.s loc_26D3E
0x26d37  ldloc.s  4
0x26d39  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26d3e  endfinally
0x26d3f  ldloc.3
0x26d40  brfalse.s loc_26D81
0x26d42  ldarg.1
0x26d43  ldloc.0
0x26d44  ldarg.3
0x26d45  ldloc.2
0x26d46  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.CreateRoleRule::SetSourceRoleNameWithEntity(class Microsoft.ReportingServices.Modeling.DsvRelation relation, class Microsoft.ReportingServices.Modeling.ModelRole role, class Microsoft.ReportingServices.Modeling.ModelEntity toEntity, string targetName)
0x26d4b  ldloc.3
0x26d4c  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelField::get_UseAutoName()
0x26d51  brfalse.s loc_26D81
0x26d53  ldloc.3
0x26d54  callvirt instance class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::get_Binding()
0x26d59  brtrue.s loc_26D5E
0x26d5b  ldnull
0x26d5c  br.s     loc_26D69
0x26d5e  ldloc.3
0x26d5f  callvirt instance class Microsoft.ReportingServices.Modeling.RelationBinding Microsoft.ReportingServices.Modeling.ModelRole::get_Binding()
0x26d64  callvirt instance class Microsoft.ReportingServices.Modeling.DsvRelation Microsoft.ReportingServices.Modeling.RelationBinding::GetRelation()
0x26d69  stloc.s  6
0x26d6b  ldarg.0
0x26d6c  ldloc.s  6
0x26d6e  ldc.i4.0
0x26d6f  call     instance string Microsoft.ReportingServices.Modeling.ModelGeneration.CreateRoleRule::GetTargetName(class Microsoft.ReportingServices.Modeling.DsvRelation relation, bool selfRelation)
0x26d74  stloc.s  7
0x26d76  ldloc.s  6
0x26d78  ldloc.3
0x26d79  ldarg.3
0x26d7a  ldloc.s  7
0x26d7c  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.CreateRoleRule::SetSourceRoleNameWithEntity(class Microsoft.ReportingServices.Modeling.DsvRelation relation, class Microsoft.ReportingServices.Modeling.ModelRole role, class Microsoft.ReportingServices.Modeling.ModelEntity toEntity, string targetName)
0x26d81  ldloc.0
0x26d82  ldarg.s  6
0x26d84  brtrue.s loc_26D91
0x26d86  ldarg.1
0x26d87  callvirt instance bool Microsoft.ReportingServices.Modeling.DsvRelation::get_OneToOne()
0x26d8c  brtrue.s loc_26D91
0x26d8e  ldc.i4.1
0x26d8f  br.s     loc_26D92
0x26d91  ldc.i4.0
0x26d92  callvirt instance void Microsoft.ReportingServices.Modeling.ModelRole::set_Cardinality(valuetype Microsoft.ReportingServices.Modeling.Cardinality value)
0x26d97  ldarg.s  6
0x26d99  brfalse.s loc_26DAF
0x26d9b  ldloc.0
0x26d9c  ldarg.1
0x26d9d  callvirt instance bool Microsoft.ReportingServices.Modeling.DsvRelation::get_OptionalTarget()
0x26da2  brtrue.s loc_26DA7
0x26da4  ldc.i4.1
0x26da5  br.s     loc_26DA8
0x26da7  ldc.i4.0
0x26da8  callvirt instance void Microsoft.ReportingServices.Modeling.ModelRole::set_Optionality(valuetype Microsoft.ReportingServices.Modeling.Optionality value)
0x26dad  br.s     loc_26DC1
0x26daf  ldloc.0
0x26db0  ldarg.1
0x26db1  callvirt instance bool Microsoft.ReportingServices.Modeling.DsvRelation::get_OptionalSource()
0x26db6  brtrue.s loc_26DBB
0x26db8  ldc.i4.1
0x26db9  br.s     loc_26DBC
0x26dbb  ldc.i4.0
0x26dbc  callvirt instance void Microsoft.ReportingServices.Modeling.ModelRole::set_Optionality(valuetype Microsoft.ReportingServices.Modeling.Optionality value)
0x26dc1  ldloc.0
0x26dc2  ldarg.1
0x26dc3  callvirt instance string Microsoft.ReportingServices.Modeling.DsvItem::get_Name()
0x26dc8  ldarg.s  6
0x26dca  brtrue.s loc_26DCF
0x26dcc  ldc.i4.0
0x26dcd  br.s     loc_26DD0
0x26dcf  ldc.i4.1
0x26dd0  newobj   instance void Microsoft.ReportingServices.Modeling.RelationBinding::.ctor(string name, valuetype Microsoft.ReportingServices.Modeling.RelationEnd relationEnd)
0x26dd5  callvirt instance void Microsoft.ReportingServices.Modeling.ModelRole::set_Binding(class Microsoft.ReportingServices.Modeling.RelationBinding value)
0x26dda  ldarg.s  6
0x26ddc  brfalse.s loc_26DE5
0x26dde  ldarg.0
0x26ddf  ldloc.0
0x26de0  call     instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::MoveFieldSortedByOrdinal(class Microsoft.ReportingServices.Modeling.ModelField field)
0x26de5  ldarg.0
0x26de6  ldloc.0
0x26de7  ldarg.s  4
0x26de9  ldarg.s  5
0x26deb  call     instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::FinalizeModelItem(class Microsoft.ReportingServices.Modeling.ModelItem item, class [System.Xml]System.Xml.XPath.IXPathNavigable fragment, class [System.Xml]System.Xml.XPath.IXPathNavigable folderFragment)
0x26df0  ldloc.0
0x26df1  ret
```
