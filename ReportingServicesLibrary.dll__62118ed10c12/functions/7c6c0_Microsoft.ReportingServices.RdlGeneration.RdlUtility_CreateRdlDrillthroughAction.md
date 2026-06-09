# Microsoft.ReportingServices.RdlGeneration.RdlUtility::CreateRdlDrillthroughAction

- ea: `0x7c6c0`
- end: `0x7c82f`
- name: `Microsoft.ReportingServices.RdlGeneration.RdlUtility::CreateRdlDrillthroughAction`
- size: `367`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x79da0`
- `0x7a5a0`

## callees

- `0x7aa70`
- `0x7bf20`
- `0x7c6c0`
- `0x7c830`
- `0x80090`
- `0x800a0`
- `0x800c0`
- `0x80110`
- `0x81770`
- `0x82c50`
- `0x82c70`
- `0x82c80`

## string_xrefs

- `0x7c7a9`: `rs:Command`
- `0x7c7e1`: `.RewrittenCommandText`
- `0x7c810`: `=CreateDrillthroughContext()`

## pseudocode

```c

```

## disassembly

```asm
0x7c6c0  newobj   instance void Microsoft.ReportingServices.Design.RdlModel.Action::.ctor()
0x7c6c5  stloc.0
0x7c6c6  newobj   instance void Microsoft.ReportingServices.Design.RdlModel.Parameter::.ctor()
0x7c6cb  stloc.1
0x7c6cc  newobj   instance void Microsoft.ReportingServices.Design.RdlModel.Parameter::.ctor()
0x7c6d1  stloc.2
0x7c6d2  newobj   instance void Microsoft.ReportingServices.Design.RdlModel.Parameter::.ctor()
0x7c6d7  stloc.3
0x7c6d8  newobj   instance void Microsoft.ReportingServices.Design.RdlModel.Parameter::.ctor()
0x7c6dd  stloc.s  4
0x7c6df  ldarg.2
0x7c6e0  callvirt instance class [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.RdlGeneration.RdlTotalExpression::get_OriginalExpression()
0x7c6e5  call     class [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.RdlGeneration.RdlUtility::GetDrillPath(class [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.Expression expr)
0x7c6ea  stloc.s  5
0x7c6ec  ldloc.s  5
0x7c6ee  callvirt instance bool class [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.CheckedCollection`1<class [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.PathItem>::get_IsEmpty()
0x7c6f3  brtrue.s loc_7C708
0x7c6f5  ldloc.s  5
0x7c6f7  callvirt instance class [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.PathItem [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.ExpressionPath::get_LastItem()
0x7c6fc  callvirt instance class [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.IQueryEntity [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.PathItem::get_TargetEntity()
0x7c701  callvirt instance class [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.ModelEntity [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.IQueryEntity::get_ModelEntity()
0x7c706  br.s     loc_7C709
0x7c708  ldarg.1
0x7c709  stloc.s  6
0x7c70b  ldloc.0
0x7c70c  ldstr    aDatasourcesDat// "=DataSources!dataSource1.DataSourceRefe"...
0x7c711  callvirt instance void Microsoft.ReportingServices.Design.RdlModel.Action::set_ReportName(string value)
0x7c716  ldloc.0
0x7c717  callvirt instance class Microsoft.ReportingServices.Design.RdlModel.Parameters Microsoft.ReportingServices.Design.RdlModel.Action::get_Parameters()
0x7c71c  brtrue.s loc_7C729
0x7c71e  ldloc.0
0x7c71f  newobj   instance void Microsoft.ReportingServices.Design.RdlModel.Parameters::.ctor()
0x7c724  callvirt instance void Microsoft.ReportingServices.Design.RdlModel.Action::set_Parameters(class Microsoft.ReportingServices.Design.RdlModel.Parameters value)
0x7c729  ldloc.1
0x7c72a  ldstr    aRsEntityid// "rs:EntityID"
0x7c72f  stfld    string Microsoft.ReportingServices.Design.RdlModel.Parameter::Name
0x7c734  ldloc.1
0x7c735  ldloc.s  6
0x7c737  callvirt instance valuetype [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.QName [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0x7c73c  stloc.s  9
0x7c73e  ldloca.s 9
0x7c740  constrained. [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.QName
0x7c746  callvirt instance string [mscorlib]System.Object::ToString()
0x7c74b  newobj   instance void Microsoft.ReportingServices.Design.RdlModel.Expression::.ctor(string expression)
0x7c750  stfld    class Microsoft.ReportingServices.Design.RdlModel.Expression Microsoft.ReportingServices.Design.RdlModel.Parameter::Value
0x7c755  ldloc.0
0x7c756  callvirt instance class Microsoft.ReportingServices.Design.RdlModel.Parameters Microsoft.ReportingServices.Design.RdlModel.Action::get_Parameters()
0x7c75b  ldloc.1
0x7c75c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x7c761  pop
0x7c762  ldloc.2
0x7c763  ldstr    aRsDrilltype// "rs:DrillType"
0x7c768  stfld    string Microsoft.ReportingServices.Design.RdlModel.Parameter::Name
0x7c76d  ldloc.s  5
0x7c76f  callvirt instance valuetype [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.Cardinality [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.ExpressionPath::GetCardinality()
0x7c774  ldc.i4.1
0x7c775  beq.s    loc_7C77E
0x7c777  ldstr    aDetail// "Detail"
0x7c77c  br.s     loc_7C783
0x7c77e  ldstr    aList_0// "List"
0x7c783  stloc.s  7
0x7c785  ldarg.3
0x7c786  brfalse.s loc_7C78F
0x7c788  ldstr    aList_0// "List"
0x7c78d  stloc.s  7
0x7c78f  ldloc.2
0x7c790  ldloc.s  7
0x7c792  newobj   instance void Microsoft.ReportingServices.Design.RdlModel.Expression::.ctor(string expression)
0x7c797  stfld    class Microsoft.ReportingServices.Design.RdlModel.Expression Microsoft.ReportingServices.Design.RdlModel.Parameter::Value
0x7c79c  ldloc.0
0x7c79d  callvirt instance class Microsoft.ReportingServices.Design.RdlModel.Parameters Microsoft.ReportingServices.Design.RdlModel.Action::get_Parameters()
0x7c7a2  ldloc.2
0x7c7a3  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x7c7a8  pop
0x7c7a9  ldstr    aRsCommand// "rs:Command"
0x7c7ae  ldstr    aDrillthrough// "Drillthrough"
0x7c7b3  newobj   instance void Microsoft.ReportingServices.Design.RdlModel.Parameter::.ctor(string name, string value)
0x7c7b8  stloc.s  8
0x7c7ba  ldloc.0
0x7c7bb  callvirt instance class Microsoft.ReportingServices.Design.RdlModel.Parameters Microsoft.ReportingServices.Design.RdlModel.Action::get_Parameters()
0x7c7c0  ldloc.s  8
0x7c7c2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x7c7c7  pop
0x7c7c8  ldloc.3
0x7c7c9  ldstr    aDrillthroughso// "DrillthroughSourceQuery"
0x7c7ce  stfld    string Microsoft.ReportingServices.Design.RdlModel.Parameter::Name
0x7c7d3  ldloc.3
0x7c7d4  ldstr    aDatasets// "=DataSets!"
0x7c7d9  ldarg.0
0x7c7da  ldarg.s  6
0x7c7dc  call     instance string Microsoft.ReportingServices.RdlGeneration.RdlUtility::GetRdlScopeName(object key)
0x7c7e1  ldstr    aRewrittencomma// ".RewrittenCommandText"
0x7c7e6  call     string [mscorlib]System.String::Concat(string, string, string)
0x7c7eb  newobj   instance void Microsoft.ReportingServices.Design.RdlModel.Expression::.ctor(string expression)
0x7c7f0  stfld    class Microsoft.ReportingServices.Design.RdlModel.Expression Microsoft.ReportingServices.Design.RdlModel.Parameter::Value
0x7c7f5  ldloc.0
0x7c7f6  callvirt instance class Microsoft.ReportingServices.Design.RdlModel.Parameters Microsoft.ReportingServices.Design.RdlModel.Action::get_Parameters()
0x7c7fb  ldloc.3
0x7c7fc  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x7c801  pop
0x7c802  ldloc.s  4
0x7c804  ldstr    aDrillthroughco// "DrillthroughContext"
0x7c809  stfld    string Microsoft.ReportingServices.Design.RdlModel.Parameter::Name
0x7c80e  ldloc.s  4
0x7c810  ldstr    aCreatedrillthr// "=CreateDrillthroughContext()"
0x7c815  newobj   instance void Microsoft.ReportingServices.Design.RdlModel.Expression::.ctor(string expression)
0x7c81a  stfld    class Microsoft.ReportingServices.Design.RdlModel.Expression Microsoft.ReportingServices.Design.RdlModel.Parameter::Value
0x7c81f  ldloc.0
0x7c820  callvirt instance class Microsoft.ReportingServices.Design.RdlModel.Parameters Microsoft.ReportingServices.Design.RdlModel.Action::get_Parameters()
0x7c825  ldloc.s  4
0x7c827  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x7c82c  pop
0x7c82d  ldloc.0
0x7c82e  ret
```
