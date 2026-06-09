# System.Web.UI.WebControls.ObjectDataSourceView::ExecuteUpdate

- ea: `0xce0f0`
- end: `0xce3f4`
- name: `System.Web.UI.WebControls.ObjectDataSourceView::ExecuteUpdate`
- size: `772`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `installer_update`

## callees

- `0x34f20`
- `0x34fa0`
- `0x5f1b0`
- `0x68550`
- `0x691e0`
- `0x69350`
- `0xcbe60`
- `0xcc5e0`
- `0xcc950`
- `0xccca0`
- `0xccf20`
- `0xcd0f0`
- `0xcd140`
- `0xcd170`
- `0xcd4b0`
- `0xce0f0`
- `0xce470`
- `0xce670`
- `0xce8d0`
- `0xce950`
- `0xceba0`
- `0xcebb0`
- `0xceea0`
- `0xcf0d0`
- `0xd1140`

## string_xrefs

- `0xce0f8`: `ObjectDataSourceView_UpdateNotSupported`
- `0xce158`: `DataSourceView_update`
- `0xce1cd`: `DataSourceView_update`

## pseudocode

```c

```

## disassembly

```asm
0xce0f0  ldarg.0
0xce0f1  callvirt instance bool System.Web.UI.DataSourceView::get_CanUpdate()
0xce0f6  brtrue.s loc_CE11C
0xce0f8  ldstr    aObjectdatasour_12// "ObjectDataSourceView_UpdateNotSupported"
0xce0fd  ldc.i4.1
0xce0fe  newarr   [mscorlib]System.Object
0xce103  dup
0xce104  ldc.i4.0
0xce105  ldarg.0
0xce106  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xce10b  callvirt instance string System.Web.UI.Control::get_ID()
0xce110  stelem.ref
0xce111  call     string System.Web.SR::GetString(string name, object[] args)
0xce116  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xce11b  throw
0xce11c  ldarg.0
0xce11d  ldarg.0
0xce11e  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_TypeName()
0xce123  call     instance class [mscorlib]System.Type System.Web.UI.WebControls.ObjectDataSourceView::GetType(string typeName)
0xce128  stloc.0
0xce129  ldarg.0
0xce12a  call     instance class [mscorlib]System.Type System.Web.UI.WebControls.ObjectDataSourceView::TryGetDataObjectType()
0xce12f  stloc.1
0xce130  ldloc.1
0xce131  ldnull
0xce132  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xce137  brfalse  loc_CE2C4
0xce13c  ldarg.0
0xce13d  call     instance valuetype System.Web.UI.ConflictOptions System.Web.UI.WebControls.ObjectDataSourceView::get_ConflictDetection()
0xce142  ldc.i4.1
0xce143  bne.un   loc_CE24D
0xce148  ldarg.3
0xce149  brtrue.s loc_CE184
0xce14b  ldstr    aObjectdatasour_5// "ObjectDataSourceView_Pessimistic"
0xce150  ldc.i4.3
0xce151  newarr   [mscorlib]System.Object
0xce156  dup
0xce157  ldc.i4.0
0xce158  ldstr    aDatasourceview_3// "DataSourceView_update"
0xce15d  call     string System.Web.SR::GetString(string name)
0xce162  stelem.ref
0xce163  dup
0xce164  ldc.i4.1
0xce165  ldarg.0
0xce166  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xce16b  callvirt instance string System.Web.UI.Control::get_ID()
0xce170  stelem.ref
0xce171  dup
0xce172  ldc.i4.2
0xce173  ldstr    aOldvalues// "oldValues"
0xce178  stelem.ref
0xce179  call     string System.Web.SR::GetString(string name, object[] args)
0xce17e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xce183  throw
0xce184  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xce189  newobj   instance void [System]System.Collections.Specialized.OrderedDictionary::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0xce18e  stloc.s  5
0xce190  ldnull
0xce191  stloc.s  6
0xce193  ldarg.0
0xce194  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_UpdateParameters()
0xce199  ldarg.3
0xce19a  ldloc.s  5
0xce19c  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination)
0xce1a1  ldarg.0
0xce1a2  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_UpdateParameters()
0xce1a7  ldarg.1
0xce1a8  ldloc.s  5
0xce1aa  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination)
0xce1af  ldarg.0
0xce1b0  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_UpdateParameters()
0xce1b5  ldarg.2
0xce1b6  ldloc.s  5
0xce1b8  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination)
0xce1bd  ldarg.3
0xce1be  brtrue.s loc_CE1F9
0xce1c0  ldstr    aObjectdatasour_5// "ObjectDataSourceView_Pessimistic"
0xce1c5  ldc.i4.3
0xce1c6  newarr   [mscorlib]System.Object
0xce1cb  dup
0xce1cc  ldc.i4.0
0xce1cd  ldstr    aDatasourceview_3// "DataSourceView_update"
0xce1d2  call     string System.Web.SR::GetString(string name)
0xce1d7  stelem.ref
0xce1d8  dup
0xce1d9  ldc.i4.1
0xce1da  ldarg.0
0xce1db  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xce1e0  callvirt instance string System.Web.UI.Control::get_ID()
0xce1e5  stelem.ref
0xce1e6  dup
0xce1e7  ldc.i4.2
0xce1e8  ldstr    aOldvalues// "oldValues"
0xce1ed  stelem.ref
0xce1ee  call     string System.Web.SR::GetString(string name, object[] args)
0xce1f3  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xce1f8  throw
0xce1f9  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xce1fe  newobj   instance void [System]System.Collections.Specialized.OrderedDictionary::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0xce203  stloc.s  6
0xce205  ldarg.0
0xce206  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_UpdateParameters()
0xce20b  ldarg.3
0xce20c  ldloc.s  6
0xce20e  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination)
0xce213  ldarg.0
0xce214  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_UpdateParameters()
0xce219  ldarg.1
0xce21a  ldloc.s  6
0xce21c  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination)
0xce221  ldarg.0
0xce222  ldloc.1
0xce223  ldloc.s  5
0xce225  call     instance object System.Web.UI.WebControls.ObjectDataSourceView::BuildDataObject(class [mscorlib]System.Type dataObjectType, class [mscorlib]System.Collections.IDictionary inputParameters)
0xce22a  stloc.s  7
0xce22c  ldarg.0
0xce22d  ldloc.1
0xce22e  ldloc.s  6
0xce230  call     instance object System.Web.UI.WebControls.ObjectDataSourceView::BuildDataObject(class [mscorlib]System.Type dataObjectType, class [mscorlib]System.Collections.IDictionary inputParameters)
0xce235  stloc.s  8
0xce237  ldarg.0
0xce238  ldloc.0
0xce239  ldarg.0
0xce23a  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_UpdateMethod()
0xce23f  ldloc.1
0xce240  ldloc.s  8
0xce242  ldloc.s  7
0xce244  ldc.i4.3
0xce245  call     instance valuetype ObjectDataSourceMethod System.Web.UI.WebControls.ObjectDataSourceView::GetResolvedMethodData(class [mscorlib]System.Type type, string methodName, class [mscorlib]System.Type dataObjectType, object oldDataObject, object newDataObject, valuetype System.Web.UI.DataSourceOperation operation)
0xce24a  stloc.2
0xce24b  br.s     loc_CE2A1
0xce24d  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xce252  newobj   instance void [System]System.Collections.Specialized.OrderedDictionary::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0xce257  stloc.s  9
0xce259  ldarg.0
0xce25a  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_UpdateParameters()
0xce25f  ldarg.3
0xce260  ldloc.s  9
0xce262  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination)
0xce267  ldarg.0
0xce268  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_UpdateParameters()
0xce26d  ldarg.1
0xce26e  ldloc.s  9
0xce270  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination)
0xce275  ldarg.0
0xce276  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_UpdateParameters()
0xce27b  ldarg.2
0xce27c  ldloc.s  9
0xce27e  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination)
0xce283  ldarg.0
0xce284  ldloc.1
0xce285  ldloc.s  9
0xce287  call     instance object System.Web.UI.WebControls.ObjectDataSourceView::BuildDataObject(class [mscorlib]System.Type dataObjectType, class [mscorlib]System.Collections.IDictionary inputParameters)
0xce28c  stloc.s  0xA
0xce28e  ldarg.0
0xce28f  ldloc.0
0xce290  ldarg.0
0xce291  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_UpdateMethod()
0xce296  ldloc.1
0xce297  ldnull
0xce298  ldloc.s  0xA
0xce29a  ldc.i4.3
0xce29b  call     instance valuetype ObjectDataSourceMethod System.Web.UI.WebControls.ObjectDataSourceView::GetResolvedMethodData(class [mscorlib]System.Type type, string methodName, class [mscorlib]System.Type dataObjectType, object oldDataObject, object newDataObject, valuetype System.Web.UI.DataSourceOperation operation)
0xce2a0  stloc.2
0xce2a1  ldloc.2
0xce2a2  ldfld    class [System]System.Collections.Specialized.OrderedDictionary ObjectDataSourceMethod::Parameters
0xce2a7  newobj   instance void System.Web.UI.WebControls.ObjectDataSourceMethodEventArgs::.ctor(class [System]System.Collections.Specialized.IOrderedDictionary inputParameters)
0xce2ac  stloc.s  4
0xce2ae  ldarg.0
0xce2af  ldloc.s  4
0xce2b1  callvirt instance void System.Web.UI.WebControls.ObjectDataSourceView::OnUpdating(class System.Web.UI.WebControls.ObjectDataSourceMethodEventArgs e)
0xce2b6  ldloc.s  4
0xce2b8  callvirt instance bool [System]System.ComponentModel.CancelEventArgs::get_Cancel()
0xce2bd  brfalse  loc_CE3BD
0xce2c2  ldc.i4.0
0xce2c3  ret
0xce2c4  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xce2c9  newobj   instance void [System]System.Collections.Specialized.OrderedDictionary::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0xce2ce  stloc.s  0xB
0xce2d0  ldarg.0
0xce2d1  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_OldValuesParameterFormatString()
0xce2d6  stloc.s  0xC
0xce2d8  ldarg.0
0xce2d9  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_UpdateParameters()
0xce2de  ldarg.0
0xce2df  ldfld    class System.Web.HttpContext System.Web.UI.WebControls.ObjectDataSourceView::_context
0xce2e4  ldarg.0
0xce2e5  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xce2ea  callvirt instance class [System]System.Collections.Specialized.IOrderedDictionary System.Web.UI.WebControls.ParameterCollection::GetValues(class System.Web.HttpContext context, class System.Web.UI.Control control)
0xce2ef  stloc.s  0xD
0xce2f1  ldarg.1
0xce2f2  brfalse.s loc_CE34A
0xce2f4  ldarg.1
0xce2f5  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.IDictionary::GetEnumerator()
0xce2fa  stloc.s  0xF
0xce2fc  br.s     loc_CE32A
0xce2fe  ldloc.s  0xF
0xce300  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xce305  unbox.any [mscorlib]System.Collections.DictionaryEntry
0xce30a  stloc.s  0x10
0xce30c  ldloc.s  0xD
0xce30e  ldloca.s 0x10
0xce310  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0xce315  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0xce31a  brfalse.s loc_CE32A
0xce31c  ldloc.s  0xD
0xce31e  ldloca.s 0x10
0xce320  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0xce325  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0xce32a  ldloc.s  0xF
0xce32c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xce331  brtrue.s loc_CE2FE
0xce333  leave.s  loc_CE34A
0xce335  ldloc.s  0xF
0xce337  isinst   [mscorlib]System.IDisposable
0xce33c  stloc.s  0x11
0xce33e  ldloc.s  0x11
0xce340  brfalse.s loc_CE349
0xce342  ldloc.s  0x11
0xce344  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xce349  endfinally
0xce34a  ldarg.0
0xce34b  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_UpdateParameters()
0xce350  ldloc.s  0xD
0xce352  ldloc.s  0xB
0xce354  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination)
0xce359  ldarg.0
0xce35a  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_UpdateParameters()
0xce35f  ldarg.2
0xce360  ldloc.s  0xB
0xce362  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination)
0xce367  ldarg.0
0xce368  call     instance valuetype System.Web.UI.ConflictOptions System.Web.UI.WebControls.ObjectDataSourceView::get_ConflictDetection()
0xce36d  ldc.i4.1
0xce36e  bne.un.s loc_CE380
0xce370  ldarg.0
0xce371  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_UpdateParameters()
0xce376  ldarg.3
0xce377  ldloc.s  0xB
0xce379  ldloc.s  0xC
0xce37b  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination, string parameterNameFormatString)
0xce380  ldarg.0
0xce381  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_UpdateParameters()
0xce386  ldarg.1
0xce387  ldloc.s  0xB
0xce389  ldloc.s  0xC
0xce38b  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination, string parameterNameFormatString)
0xce390  ldloc.s  0xB
0xce392  newobj   instance void System.Web.UI.WebControls.ObjectDataSourceMethodEventArgs::.ctor(class [System]System.Collections.Specialized.IOrderedDictionary inputParameters)
0xce397  stloc.s  0xE
0xce399  ldarg.0
0xce39a  ldloc.s  0xE
0xce39c  callvirt instance void System.Web.UI.WebControls.ObjectDataSourceView::OnUpdating(class System.Web.UI.WebControls.ObjectDataSourceMethodEventArgs e)
0xce3a1  ldloc.s  0xE
0xce3a3  callvirt instance bool [System]System.ComponentModel.CancelEventArgs::get_Cancel()
0xce3a8  brfalse.s loc_CE3AC
0xce3aa  ldc.i4.0
0xce3ab  ret
0xce3ac  ldarg.0
0xce3ad  ldloc.0
0xce3ae  ldarg.0
0xce3af  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_UpdateMethod()
0xce3b4  ldloc.s  0xB
0xce3b6  ldc.i4.3
0xce3b7  call     instance valuetype ObjectDataSourceMethod System.Web.UI.WebControls.ObjectDataSourceView::GetResolvedMethodData(class [mscorlib]System.Type type, string methodName, class [mscorlib]System.Collections.IDictionary allParameters, valuetype System.Web.UI.DataSourceOperation operation)
0xce3bc  stloc.2
0xce3bd  ldarg.0
0xce3be  ldloc.2
0xce3bf  call     instance class ObjectDataSourceResult System.Web.UI.WebControls.ObjectDataSourceView::InvokeMethod(valuetype ObjectDataSourceMethod method)
0xce3c4  stloc.3
0xce3c5  ldarg.0
0xce3c6  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xce3cb  callvirt instance class System.Web.UI.SqlDataSourceCache System.Web.UI.WebControls.ObjectDataSource::get_Cache()
0xce3d0  callvirt instance bool System.Web.UI.DataSourceCache::get_Enabled()
0xce3d5  brfalse.s loc_CE3E2
0xce3d7  ldarg.0
0xce3d8  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xce3dd  callvirt instance void System.Web.UI.WebControls.ObjectDataSource::InvalidateCacheEntry()
0xce3e2  ldarg.0
0xce3e3  ldsfld   class [mscorlib]System.EventArgs [mscorlib]System.EventArgs::Empty
0xce3e8  callvirt instance void System.Web.UI.DataSourceView::OnDataSourceViewChanged(class [mscorlib]System.EventArgs e)
0xce3ed  ldloc.3
0xce3ee  ldfld    int32 ObjectDataSourceResult::AffectedRows
0xce3f3  ret
```
