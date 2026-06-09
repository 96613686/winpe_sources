# System.Web.UI.WebControls.ObjectDataSourceView::ExecuteDelete

- ea: `0xcd850`
- end: `0xcda4b`
- name: `System.Web.UI.WebControls.ObjectDataSourceView::ExecuteDelete`
- size: `507`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: ``

## callees

- `0x34f20`
- `0x34fa0`
- `0x5f1b0`
- `0x68550`
- `0x69190`
- `0x69350`
- `0xcbe60`
- `0xcc5e0`
- `0xcc950`
- `0xccca0`
- `0xccd50`
- `0xccd80`
- `0xccf20`
- `0xcd0f0`
- `0xcd4b0`
- `0xcd850`
- `0xce470`
- `0xce670`
- `0xce8d0`
- `0xce950`
- `0xceba0`
- `0xcebb0`
- `0xcecc0`
- `0xcf0d0`
- `0xd1140`

## string_xrefs

- `0xcd858`: `ObjectDataSourceView_DeleteNotSupported`
- `0xcd8cf`: `DataSourceView_delete`
- `0xcd9ab`: `DataSourceView_delete`

## pseudocode

```c

```

## disassembly

```asm
0xcd850  ldarg.0
0xcd851  callvirt instance bool System.Web.UI.DataSourceView::get_CanDelete()
0xcd856  brtrue.s loc_CD87C
0xcd858  ldstr    aObjectdatasour_4// "ObjectDataSourceView_DeleteNotSupported"
0xcd85d  ldc.i4.1
0xcd85e  newarr   [mscorlib]System.Object
0xcd863  dup
0xcd864  ldc.i4.0
0xcd865  ldarg.0
0xcd866  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xcd86b  callvirt instance string System.Web.UI.Control::get_ID()
0xcd870  stelem.ref
0xcd871  call     string System.Web.SR::GetString(string name, object[] args)
0xcd876  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xcd87b  throw
0xcd87c  ldarg.0
0xcd87d  ldarg.0
0xcd87e  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_TypeName()
0xcd883  call     instance class [mscorlib]System.Type System.Web.UI.WebControls.ObjectDataSourceView::GetType(string typeName)
0xcd888  stloc.0
0xcd889  ldarg.0
0xcd88a  call     instance class [mscorlib]System.Type System.Web.UI.WebControls.ObjectDataSourceView::TryGetDataObjectType()
0xcd88f  stloc.1
0xcd890  ldloc.1
0xcd891  ldnull
0xcd892  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xcd897  brfalse  loc_CD94A
0xcd89c  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xcd8a1  newobj   instance void [System]System.Collections.Specialized.OrderedDictionary::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0xcd8a6  stloc.s  4
0xcd8a8  ldarg.0
0xcd8a9  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_DeleteParameters()
0xcd8ae  ldarg.1
0xcd8af  ldloc.s  4
0xcd8b1  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination)
0xcd8b6  ldarg.0
0xcd8b7  call     instance valuetype System.Web.UI.ConflictOptions System.Web.UI.WebControls.ObjectDataSourceView::get_ConflictDetection()
0xcd8bc  ldc.i4.1
0xcd8bd  bne.un.s loc_CD909
0xcd8bf  ldarg.2
0xcd8c0  brtrue.s loc_CD8FB
0xcd8c2  ldstr    aObjectdatasour_5// "ObjectDataSourceView_Pessimistic"
0xcd8c7  ldc.i4.3
0xcd8c8  newarr   [mscorlib]System.Object
0xcd8cd  dup
0xcd8ce  ldc.i4.0
0xcd8cf  ldstr    aDatasourceview_2// "DataSourceView_delete"
0xcd8d4  call     string System.Web.SR::GetString(string name)
0xcd8d9  stelem.ref
0xcd8da  dup
0xcd8db  ldc.i4.1
0xcd8dc  ldarg.0
0xcd8dd  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xcd8e2  callvirt instance string System.Web.UI.Control::get_ID()
0xcd8e7  stelem.ref
0xcd8e8  dup
0xcd8e9  ldc.i4.2
0xcd8ea  ldstr    aOldvalues// "oldValues"
0xcd8ef  stelem.ref
0xcd8f0  call     string System.Web.SR::GetString(string name, object[] args)
0xcd8f5  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xcd8fa  throw
0xcd8fb  ldarg.0
0xcd8fc  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_DeleteParameters()
0xcd901  ldarg.2
0xcd902  ldloc.s  4
0xcd904  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination)
0xcd909  ldarg.0
0xcd90a  ldloc.1
0xcd90b  ldloc.s  4
0xcd90d  call     instance object System.Web.UI.WebControls.ObjectDataSourceView::BuildDataObject(class [mscorlib]System.Type dataObjectType, class [mscorlib]System.Collections.IDictionary inputParameters)
0xcd912  stloc.s  5
0xcd914  ldarg.0
0xcd915  ldloc.0
0xcd916  ldarg.0
0xcd917  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_DeleteMethod()
0xcd91c  ldloc.1
0xcd91d  ldloc.s  5
0xcd91f  ldnull
0xcd920  ldc.i4.0
0xcd921  call     instance valuetype ObjectDataSourceMethod System.Web.UI.WebControls.ObjectDataSourceView::GetResolvedMethodData(class [mscorlib]System.Type type, string methodName, class [mscorlib]System.Type dataObjectType, object oldDataObject, object newDataObject, valuetype System.Web.UI.DataSourceOperation operation)
0xcd926  stloc.2
0xcd927  ldloc.2
0xcd928  ldfld    class [System]System.Collections.Specialized.OrderedDictionary ObjectDataSourceMethod::Parameters
0xcd92d  newobj   instance void System.Web.UI.WebControls.ObjectDataSourceMethodEventArgs::.ctor(class [System]System.Collections.Specialized.IOrderedDictionary inputParameters)
0xcd932  stloc.s  6
0xcd934  ldarg.0
0xcd935  ldloc.s  6
0xcd937  callvirt instance void System.Web.UI.WebControls.ObjectDataSourceView::OnDeleting(class System.Web.UI.WebControls.ObjectDataSourceMethodEventArgs e)
0xcd93c  ldloc.s  6
0xcd93e  callvirt instance bool [System]System.ComponentModel.CancelEventArgs::get_Cancel()
0xcd943  brfalse  loc_CDA14
0xcd948  ldc.i4.0
0xcd949  ret
0xcd94a  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xcd94f  newobj   instance void [System]System.Collections.Specialized.OrderedDictionary::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0xcd954  stloc.s  7
0xcd956  ldarg.0
0xcd957  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_OldValuesParameterFormatString()
0xcd95c  stloc.s  8
0xcd95e  ldarg.0
0xcd95f  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_DeleteParameters()
0xcd964  ldarg.0
0xcd965  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_DeleteParameters()
0xcd96a  ldarg.0
0xcd96b  ldfld    class System.Web.HttpContext System.Web.UI.WebControls.ObjectDataSourceView::_context
0xcd970  ldarg.0
0xcd971  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xcd976  callvirt instance class [System]System.Collections.Specialized.IOrderedDictionary System.Web.UI.WebControls.ParameterCollection::GetValues(class System.Web.HttpContext context, class System.Web.UI.Control control)
0xcd97b  ldloc.s  7
0xcd97d  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination)
0xcd982  ldarg.0
0xcd983  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_DeleteParameters()
0xcd988  ldarg.1
0xcd989  ldloc.s  7
0xcd98b  ldloc.s  8
0xcd98d  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination, string parameterNameFormatString)
0xcd992  ldarg.0
0xcd993  call     instance valuetype System.Web.UI.ConflictOptions System.Web.UI.WebControls.ObjectDataSourceView::get_ConflictDetection()
0xcd998  ldc.i4.1
0xcd999  bne.un.s loc_CD9E7
0xcd99b  ldarg.2
0xcd99c  brtrue.s loc_CD9D7
0xcd99e  ldstr    aObjectdatasour_5// "ObjectDataSourceView_Pessimistic"
0xcd9a3  ldc.i4.3
0xcd9a4  newarr   [mscorlib]System.Object
0xcd9a9  dup
0xcd9aa  ldc.i4.0
0xcd9ab  ldstr    aDatasourceview_2// "DataSourceView_delete"
0xcd9b0  call     string System.Web.SR::GetString(string name)
0xcd9b5  stelem.ref
0xcd9b6  dup
0xcd9b7  ldc.i4.1
0xcd9b8  ldarg.0
0xcd9b9  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xcd9be  callvirt instance string System.Web.UI.Control::get_ID()
0xcd9c3  stelem.ref
0xcd9c4  dup
0xcd9c5  ldc.i4.2
0xcd9c6  ldstr    aOldvalues// "oldValues"
0xcd9cb  stelem.ref
0xcd9cc  call     string System.Web.SR::GetString(string name, object[] args)
0xcd9d1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xcd9d6  throw
0xcd9d7  ldarg.0
0xcd9d8  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_DeleteParameters()
0xcd9dd  ldarg.2
0xcd9de  ldloc.s  7
0xcd9e0  ldloc.s  8
0xcd9e2  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination, string parameterNameFormatString)
0xcd9e7  ldloc.s  7
0xcd9e9  newobj   instance void System.Web.UI.WebControls.ObjectDataSourceMethodEventArgs::.ctor(class [System]System.Collections.Specialized.IOrderedDictionary inputParameters)
0xcd9ee  stloc.s  9
0xcd9f0  ldarg.0
0xcd9f1  ldloc.s  9
0xcd9f3  callvirt instance void System.Web.UI.WebControls.ObjectDataSourceView::OnDeleting(class System.Web.UI.WebControls.ObjectDataSourceMethodEventArgs e)
0xcd9f8  ldloc.s  9
0xcd9fa  callvirt instance bool [System]System.ComponentModel.CancelEventArgs::get_Cancel()
0xcd9ff  brfalse.s loc_CDA03
0xcda01  ldc.i4.0
0xcda02  ret
0xcda03  ldarg.0
0xcda04  ldloc.0
0xcda05  ldarg.0
0xcda06  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_DeleteMethod()
0xcda0b  ldloc.s  7
0xcda0d  ldc.i4.0
0xcda0e  call     instance valuetype ObjectDataSourceMethod System.Web.UI.WebControls.ObjectDataSourceView::GetResolvedMethodData(class [mscorlib]System.Type type, string methodName, class [mscorlib]System.Collections.IDictionary allParameters, valuetype System.Web.UI.DataSourceOperation operation)
0xcda13  stloc.2
0xcda14  ldarg.0
0xcda15  ldloc.2
0xcda16  call     instance class ObjectDataSourceResult System.Web.UI.WebControls.ObjectDataSourceView::InvokeMethod(valuetype ObjectDataSourceMethod method)
0xcda1b  stloc.3
0xcda1c  ldarg.0
0xcda1d  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xcda22  callvirt instance class System.Web.UI.SqlDataSourceCache System.Web.UI.WebControls.ObjectDataSource::get_Cache()
0xcda27  callvirt instance bool System.Web.UI.DataSourceCache::get_Enabled()
0xcda2c  brfalse.s loc_CDA39
0xcda2e  ldarg.0
0xcda2f  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xcda34  callvirt instance void System.Web.UI.WebControls.ObjectDataSource::InvalidateCacheEntry()
0xcda39  ldarg.0
0xcda3a  ldsfld   class [mscorlib]System.EventArgs [mscorlib]System.EventArgs::Empty
0xcda3f  callvirt instance void System.Web.UI.DataSourceView::OnDataSourceViewChanged(class [mscorlib]System.EventArgs e)
0xcda44  ldloc.3
0xcda45  ldfld    int32 ObjectDataSourceResult::AffectedRows
0xcda4a  ret
```
